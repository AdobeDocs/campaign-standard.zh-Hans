---
solution: Campaign Standard
product: campaign
title: 显示 Adobe Campaign Standard 推送通知中的图像
description: 在此处了解如何在iOS设备上通过Adobe Campaign推送通知显示图像。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 20%

---


# 添加图像和视频 iOS {#image-push}

>[!NOTE]
>
>此文档仅适用于iOS设备。

在此文档中，了解如何从Adobe Campaign Standard iOS推送通知中显示图像。

## 第1步：设置推送通知{#set-up-push}

Experience Platform SDK支持推送通知。

接收推送通知的移动应用程序必须由管理员在Adobe Campaign界面中配置。

通过配置Adobe Campaign和Adobe Mobile Services，您将能够将移动应用程序的数据用于活动。 有关详细信息，请参见此 [ 页面](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdk.html)。

要使用Experience Cloud SDK应用程序发送推送通知，必须在Adobe Experience Platform Launch中设置移动应用程序并在Adobe Campaign中配置。 有关详细信息，请参见此 [ 页面](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign)。

## 第2步：在Adobe Campaign{#customize-push}中自定义您的推送通知

要优化推送通知消息，可在设计推送通知消息时通过 Adobe Campaign 访问一组高级选项。

1. 创建推送通知. 有关详细信息，请参见此 [ 页面](../../channels/using/preparing-and-sending-a-push-notification.md)。

1. 从您的推送通知内容页面访问&#x200B;**[!UICONTROL Advanced options]**&#x200B;部分。

1. 在&#x200B;**[!UICONTROL Rich media content URL]**字段中输入文件的URL。
对于 iOS 10 或更高版本，可插入图像、GIF 动图、音频和视频文件。

   ![](assets/push_notif_advanced_6.png)

1. 预览并保存您的推送通知。

## 第3步：调整Mobile应用程序代码{#mobile-app-code}

在Adobe Campaign中自定义推送通知后，您必须配置移动应用程序以在设备上显示图像。

>[!NOTE]
>
>如果您的应用程序位于Objective-C中，请参阅以下[文档](https://docs.adobe.com/content/help/en/mobile-services/ios/messaging-ios/push-messaging/c-set-up-rich-push-notif-ios.html)。

如果您的应用程序位于[!DNL Swift]中，请按照以下步骤操作：

1. 打开[!DNL Xcode]项目。

1. 在您的[!DNL Xcode]项目中，选择&#x200B;**[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL Target]**。

1. 选择 **[!UICONTROL Notification Service Extension]**。

   ![](assets/push_notif_advanced_12.png)

1. 检查是否已创建&#x200B;**NotificationService.swift**&#x200B;文件类。

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

在发送通知时，移动设备应接收以下负载。

图像URL将映射为键媒体 — attachment-url。 这是从应用程序代码透视图下载和显示图像时必须处理的键/值对。

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

## 第4步：测试发送推送{#test-send-push}

您现在可以测试构建应用程序以及您在以上步骤2中创建的投放。 有关准备和发送推送通知的详细信息，请参阅此[页面](../../channels/using/preparing-and-sending-a-push-notification.md)。

![](assets/push_notif_advanced_34.png)

