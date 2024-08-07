---
title: 实施本地跟踪
description: 了解如何确保已在iOS和Android上正确实施推送通知跟踪
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b983d0a3-c345-44d4-bc82-202bf6ed26ab
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 0%

---

# 实施本地跟踪 {#local-tracking}

## 关于本地跟踪 {#about-local-tracking}

在此页面中，了解如何确保正确实施本地通知跟踪。 请注意，这意味着已配置本地通知。

本地通知跟踪可以拆分为三种类型：

* **本地展示次数** — 本地通知已传送到设备并位于通知中心上，但完全没有被触碰时。 在大多数情况下，展示次数应与交付的展示次数大致相同。 它可确保设备确实收到消息，并将该信息中继回服务器。

* **本地点击** — 本地通知已送达设备，且用户已点击通知。 用户希望查看通知（通知随后将移至本地打开跟踪）或关闭通知。

* **本地打开** — 本地通知已传送到设备，且用户已单击导致应用程序打开的通知。 这与本地点击类似，不同之处在于，如果取消通知，则不会触发本地打开。

要为Adobe Campaign Standard实施跟踪，移动应用程序需要在应用程序中包含Mobile SDK。 这些SDK在[!DNL Adobe Mobile Services]中可用。

要发送跟踪信息，必须发送三个变量：两个变量是从Adobe Campaign接收的数据的一部分，另一个变量是操作变量，用于指示该变量是展示变量、单击变量还是打开变量。

| 变量 | 值 |
| :-: | :-: |
| deliveryId | 来自传入数据的`deliveryId`（与使用`_dld`的推送跟踪类似） |
| broadlogId | 来自传入数据的`broadlogId`（与使用`_mld`的推送跟踪类似） |
| 操作 | “1”表示打开，“2”表示单击，“7”表示展示 |

## 实施本地展示跟踪 {#implement-local-impression-tracking}

Adobe Experience Platform Mobile SDK将自动为Android和iOS发送展示事件，而无需任何其他配置。

## 实施点击跟踪 {#implementing-click-tracking}

对于点击跟踪，调用`collectMessageInfo()`或`trackAction()`函数时必须发送值“2”才能执行操作。

### 适用于Android的 {#implement-click-tracking-android}

要跟踪点击量，必须实施两种方案：

* 用户看到通知但将其清除。

  要在删除场景时跟踪点击，请将广播接收器`NotificationDismissalHandler`添加到应用程序模块的AndroidManifest文件中。

  ```
  <receiver
  android:name="com.adobe.marketing.mobile.NotificationDismissalHandler">
  </receiver>
  ```

* 用户看到通知并单击它，将变为打开跟踪。

  此方案应生成一个单击和一个打开操作。 跟踪此点击将是跟踪打开情况所需的实施的一部分。 请参阅[实施打开跟踪](#implement-open-tracking)。

### 适用于iOS的 {#implement-click-tracking-ios}

要发送点击跟踪信息，必须添加以下内容：

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

## 实施开放跟踪 {#implement-open-tracking}

您必须发送“1”和“2”，因为用户必须单击通知才能打开应用程序。 如果未通过本地通知启动/打开应用程序，则不会发生跟踪事件。

### 适用于Android的 {#implement-open-tracking-android}

要跟踪打开情况，我们必须创建意图。 目的对象允许Android OS在完成某些操作后调用您的方法，在此例中，单击通知以打开应用程序。

此代码基于点击展示跟踪的实施。 现在，对于意图集，您必须将跟踪信息发送回Adobe Campaign。 在这种情况下，触发通知的Android视图([!DNL Activity])将打开或作为用户单击的结果置于前台。 [!DNL Activity]中的目的对象包含可用于跟踪打开的通知数据。

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

        //Opened based on the notification, you must get the tracking that was passed on.

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

### 适用于iOS的 {#implement-open-tracking-ios}

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
