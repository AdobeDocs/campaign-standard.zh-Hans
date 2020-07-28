---
title: 显示 Adobe Campaign Standard 推送通知中的图像
description: 在此了解如何在iOS设备上显示Adobe Campaign推送通知中的图像。
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cf43edcacbab9f1f33ce29e23c0957d8bfa64e7d
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 2%

---


# 添加图像和视频iOS {#image-push}

>[!NOTE]
>
>此文档仅适用于iOS设备。

在此文档中，了解如何从Adobe Campaign StandardiOS推送通知中显示图像。

## 第1步： 设置推送通知 {#set-up-push}

Experience PlatformSDK支持推送通知。

接收推送通知的移动应用程序必须由管理员在Adobe Campaign界面中配置。

通过配置Adobe Campaign和Adobe Mobile Services，您将能够为活动使用移动应用程序的数据。 For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

要使用Experience CloudSDK应用程序发送推送通知，必须在Adobe Experience Platform Launch中设置移动应用程序，并在Adobe Campaign中进行配置。 For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

## 第2步： 在Adobe Campaign中自定义推送通知 {#customize-push}

要微调推送通知，Adobe Campaign允许您在设计推送通知时访问一组高级选项。

1. 创建推送通知。 For more on this, refer to this [page](../../channels/using/preparing-and-sending-a-push-notification.md).

1. 从您的推送通知内容页面访问该 **[!UICONTROL Advanced options]** 部分。

1. 在字段中输入文件的 **[!UICONTROL Rich media content URL]** URL。
对于iOS 10或更高版本，可插入图像、gif、音频和视频文件。

   ![](assets/push_notif_advanced_6.png)

1. 预览并保存推送通知。

## 第3步： 调整移动应用程序代码 {#mobile-app-code}

在Adobe Campaign中自定义推送通知后，您必须配置移动应用程序以在设备上显示图像。

>[!NOTE]
>
>如果您的应用程序位于Objective-C中，请参阅以下 [文档](https://docs.adobe.com/content/help/en/mobile-services/ios/messaging-ios/push-messaging/c-set-up-rich-push-notif-ios.html)。

如果您的应用程序 [!DNL Swift]在，请按照以下步骤操作：

1. 打开您的 [!DNL Xcode] 项目。

1. 在您的 [!DNL Xcode] 项目中，选 **[!UICONTROL File]** 择 **[!UICONTROL New]** > > **[!UICONTROL Target]**。

1. Select **[!UICONTROL Notification Service Extension]**.

   ![](assets/push_notif_advanced_12.png)

1. 检查是否 **已创建NotificationService** .swift文件类。

1. 编辑此类，并将默认内容替换为以下内容。
这允许应用程序使用图像URL处理传入参数，分析它，在本地复制它，然后从推送通知中显示它。

   ```
   import UserNotifications
   
   class NotificationService: UNNotificationServiceExtension {
   
   var contentHandler: ((UNNotificationContent) -> Void)?
   var bestAttemptContent: UNMutableNotificationContent?
   
   override func didReceive(_ request: UNNotificationRequest, withContentHandler contentHandler: @escaping (UNNotificationContent) -> Void) {
       self.contentHandler = contentHandler
       bestAttemptContent = (request.content.mutableCopy() as? UNMutableNotificationContent)
   
       if let bestAttemptContent = bestAttemptContent {
           var urlString:String? = nil
           if let urlImageString = request.content.userInfo["media-attachment-url"] as? String {
               urlString = urlImageString
           }
   
           if urlString != nil, let fileUrl = URL(string: urlString!) {
               print("fileUrl: \(fileUrl)")
   
               // Download the attachment
               URLSession.shared.downloadTask(with: fileUrl) { (location, response, error) in
                   if let location = location {
                       // Move temporary file to remove .tmp extension
                       if (error == nil) {
                           let tmpDirectory = NSTemporaryDirectory()
                           let tmpFile = "file://".appending(tmpDirectory).appending(fileUrl.lastPathComponent)
                           let tmpUrl = URL(string: tmpFile)!
                           try! FileManager.default.moveItem(at: location, to: tmpUrl)
   
                           // Add the attachment to the notification content
                           if let attachment = try? UNNotificationAttachment(identifier: fileUrl.lastPathComponent, url: tmpUrl) {
                               bestAttemptContent.attachments = [attachment]
                               }
                       }
                       if(error != nil) {
                           print("Failed to download attachment: \(error.debugDescription)")
                       }
                   }
                   // Serve the notification content
                   contentHandler(bestAttemptContent)
               }.resume()
           }
       }
   }
   
   override func serviceExtensionTimeWillExpire() {
       // Called just before the extension will be terminated by the system.
       // Use this as an opportunity to deliver your "best attempt" at modified content, otherwise the original push payload will be used.
       if let contentHandler = contentHandler, let bestAttemptContent = bestAttemptContent {
           contentHandler(bestAttemptContent)
       }
   }
   
   }
   ```

移动设备在发送通知时应接收以下有效负荷。

图像URL将映射为关键媒体附件URL。 这是从应用程序代码角度下必须处理的键／值对，才能下载和显示图像。

```
userInfo: [AnyHashable("media-attachment-url"): https://pbs.twimg.com/profile_images/876737835314950144/zPTs9b7o.jpg, AnyHashable("_dId"): 1de3ef93, AnyHashable("_mId"): h280a5, AnyHashable("aps"): {
 
    alert =     {
 
        body = "Message Body here";
 
        title = "This a push from Campaign";
 
    };
 
    badge = 1;
 
    "mutable-content" = 1;
 
}]
```

## 第4步： 测试发送推送 {#test-send-push}

您现在可以测试构建应用程序以及您在以上步骤2中创建的投放。 有关准备和发送推送通知的详细信息，请参阅 [此页](../../channels/using/preparing-and-sending-a-push-notification.md)。

![](assets/push_notif_advanced_34.png)

