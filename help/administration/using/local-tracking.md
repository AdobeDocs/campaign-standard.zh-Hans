---
solution: Campaign Standard
product: campaign
title: 实施推送跟踪
description: 此文档允许您确保在iOS和Android上正确实施推送通知跟踪。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Administrator
level: Experienced
translation-type: tm+mt
source-git-commit: a7a1aa2841410674597264927325c073fef4ce26
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---


# 实现本地跟踪{#local-tracking}

## 关于本地跟踪{#about-local-tracking}

在本页中，了解如何确保正确实施本地通知跟踪。 请注意，这意味着已配置本地通知。

本地通知跟踪可分为三种类型：

* **本地展示**  — 当本地通知已发送到设备并且位于通知中心，但完全未触及时。在大多数情况下，展示次数应与已交付数量相同，但应相似。 它确保设备收到消息并将该信息转发回服务器。

* **本地单击**  — 当向设备发送本地通知且用户单击了通知时。用户要么希望视图通知（通知将进而移动到本地打开跟踪），要么希望取消通知。

* **本地打开**  — 当向设备发送本地通知且用户单击了导致应用程序打开的通知时。这与本地单击类似，只是当通知被关闭时，不会触发本地打开。

要实施Adobe Campaign Standard跟踪，移动应用程序需要在应用程序中包含Mobile SDK。 这些SDK在[!DNL Adobe Mobile Services]中可用。

要发送跟踪信息，需要发送三个变量：两个是从Adobe Campaign接收的数据的一部分，另一个是操作变量，它指示它是印象、单击还是打开。

| 变量 | 值 |
| :-: | :-: |
| deliveryId | `deliveryId` 从传入数据(与使用的推送跟 `_dld` 踪类似) |
| broadlogId | `broadlogId` 从传入数据(与使用的推送跟 `_mld` 踪类似) |
| 行动 | “1”表示打开，“2”表示单击，“7”表示印象 |

## 实现本地印象跟踪{#implement-local-impression-tracking}

Adobe Experience Platform Mobile SDK将自动发送Android和iOS的展示事件，而无需任何其他配置。

## 实现单击跟踪{#implementing-click-tracking}

对于单击跟踪，您需要在调用`collectMessageInfo()`或`trackAction()`函数时发送值“2”以执行操作。

### 对于Android {#implement-click-tracking-android}

要跟踪单击，需要处理两种情况：

* 用户可以看到通知，但会清除通知。

   要在解除方案时跟踪单击，请在应用程序模块的AndroidManifest文件中添加广播接收器`NotificationDismissalHandler`。

   ```
   <receiver
   android:name="com.adobe.marketing.mobile.NotificationDismissalHandler">
   </receiver>
   ```

* 用户看到通知并单击它，这将转为打开跟踪。

   此方案应生成单击并打开。 跟踪此单击将是跟踪打开情况所需的实现的一部分。 请参阅[实施开放跟踪](#implement-open-tracking)。

### 对于iOS {#implement-click-tracking-ios}

要发送单击跟踪信息，您需要添加以下内容：

```
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {

   func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                
                //If you are using ACPCore v2.3.0 or later, use the next line.
                
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
                //Else comment out the above line and uncomment the line below
                
                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            
            ////MORE CODE
        }
        completionHandler()
    }
}
```

## 实现开放跟踪{#implement-open-tracking}

您需要发送“1”和“2”，因为用户必须单击通知才能打开应用程序。 如果应用程序未通过本地通知启动/打开，则不会发生跟踪事件。

### 对于Android {#implement-open-tracking-android}

要跟踪打开情况，我们需要创建意图。 “用途”对象允许Android OS在完成某些操作时调用您的方法，在这种情况下，单击通知以打开应用程序。

此代码基于实现点击印象跟踪。 在设置意图后，您现在需要将跟踪信息发送回Adobe Campaign。 在这种情况下，用户单击后将打开或置于前台，触发通知的Android视图([!DNL Activity])。 [!DNL Activity]中的意图对象包含可用于跟踪打开情况的通知数据。

MainActivity.java（扩展[!DNL Activity]）

```
@Override
protected void onResume() {
    super.onResume();
    handleTracking();
}
 
 
private void handleTracking() {

    //Check to see if this view was opened based on a notification

    Intent intent = getIntent();
    Bundle data = intent.getExtras();
 
    if (data != null) {

        //Opened based on the notification, you need to get the tracking that was passed on.

        Map<String, String> notificationData = (Map<String, Object>)data.getSerializableExtra("NOTIFICATION_USER_INFO");
        String deliveryId = (String)notificationData.get("deliveryId");
        String messageId = (String)notificationData.get("broadlogId");

        if (deliveryId != null && messageId != null) {
            HashMap<String, String> contextData = new HashMap<>();
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
 
            //Send click tracking since the user did click on the notification

            contextData.put("action", "2");

            //If you are using ACPCore v1.4.0 or later, use the next line.
    
            MobileCore.collectMessageInfo(contextData);

            //Else comment out the above line and uncomment the line below

            // MobileCore.trackAction("tracking", contextData);
 
            //Send open tracking since the user opened the app

            contextData.put("action", "1");

            //If you are using  ACPCore v1.4.0 or later, use the next line.

            MobileCore.collectMessageInfo(contextData);

            //Else comment out the above line and uncomment the line below

            // MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### 对于iOS {#implement-open-tracking-ios}

```
import os.log
import Foundation
import UserNotifications
import UserNotificationsUI
import ACPCore
 
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {
 
    //Called when user clicks the local notification or also called from willPresent()

    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
 
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:

            //This is to handle the Dismiss action

            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {

                //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])

                //Else comment out the above line and uncomment the line below

                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {

               //If you are using ACPCore v2.3.0 or later, use the next line.

               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])

               //Else comment out the above line and uncomment the line below

               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
