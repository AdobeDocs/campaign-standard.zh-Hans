---
solution: Campaign Standard
product: campaign
title: 实施推送跟踪
description: 此文档允许您确保在iOS和Android上正确实施推送通知跟踪。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: 实例设置
role: 管理员
level: 富有经验
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 0%

---


# 实现本地跟踪{#local-tracking}

## 关于本地跟踪{#about-local-tracking}

在本页中，了解如何确保正确实施本地通知跟踪。 请注意，这意味着已配置本地通知。

本地通知跟踪可分为三种类型：

* **本地展示**  — 当本地通知已发送到设备并且位于通知中心，但完全未触及时。在大多数情况下，展示次数应与已交付数量相同，但应相似。 它确保设备收到消息并将该信息转发回服务器。

* **本地单击**  — 当向设备发送本地通知且用户单击了设备时。用户要么希望视图通知（通知将进而移动到本地打开跟踪），要么希望取消通知。

* **本地打开**  — 当向设备发送本地通知且用户单击了导致应用程序打开的通知时。这与本地单击类似，只是当通知被关闭时，不会触发本地打开。

要实施Adobe Campaign Standard跟踪，移动应用程序需要在应用程序中包含Mobile SDK。 这些SDK在[!DNL Adobe Mobile Services]中可用。

要发送跟踪信息，需要发送三个变量：两个是从Adobe Campaign接收的数据的一部分，另一个是操作变量，它指示它是印象、单击还是打开。

| 变量 | 值 |
| :-: | :-: |
| deliveryId | 来自传入数据的“deliveryId”（与使用“_dld”的推送跟踪类似） |
| broadlogId | 来自传入数据的&quot;broadlogId&quot;（与使用&quot;_mld&quot;的推送跟踪类似） |
| 行动 | “1”表示打开，“2”表示单击，“7”表示印象 |

## 实现本地印象跟踪{#implement-local-impression-tracking}

要进行印象跟踪，您需要在调用collectMessageInfo()或trackAction()函数时发送值“7”以执行操作。

### 对于Android {#implement-local-impression-tracking-android}

Adobe Experience Platform Mobile SDK在触发本地通知时开始其印象跟踪。

### 对于iOS {#implement-local-impression-tracking-ios}

要解释如何实施印象跟踪，我们需要了解应用程序的三种状态：

* **前景**:当应用程序当前处于活动状态时，并显示在前景中。

* **背景**:应用程序未在屏幕上，但进程也未关闭。当多次单击主按钮时，它通常会在后台显示所有应用程序。

* **关闭/关闭**:应用程序进程被终止时。如果关闭了某个应用程序，Apple在重新启动该应用程序之前不会调用它。 这意味着您永远无法真正了解iOS上何时收到通知。

要让印象跟踪在应用程序处于后台时仍然有效，我们需要发送“可用内容”让应用程序知道需要进行跟踪。

Adobe Experience Platform Mobile SDK在触发本地通知时开始其印象跟踪。

>[!CAUTION]
>
>iOS印象跟踪不准确，不应可靠查看。

## 实现单击跟踪{#implementing-click-tracking}

对于单击跟踪，您需要在调用collectMessageInfo()或trackAction()函数时发送值“2”以执行操作。

### 对于Android {#implement-click-tracking-android}

要跟踪单击，需要处理两种情况：

* 用户可以看到通知，但会清除通知。

* 用户看到通知并单击它，这将转为打开跟踪。

Adobe Experience Platform Mobile SDK会跟踪第一个单击场景。

### 对于iOS {#implement-click-tracking-ios}

```
// AppDelegate.swift
...
import os.log
import UserNotifications
...
  
func registerForPushNotifications() {
        let center = UNUserNotificationCenter.current()
        center.delegate = notificationDelegate
        //Here we are creating a new Category that allows us to handle Dismiss Actions
        let defaultCategory = UNNotificationCategory(identifier: "DEFAULT", actions: [], intentIdentifiers: [], options: .customDismissAction)
        //Add it to our array of Category, in this case we only have one
        center.setNotificationCategories([defaultCategory])
        center.requestAuthorization(options: [.alert, .sound, .badge]) {
            (granted, error) in
            os_log("Permission granted: %{public}@", type:. debug, granted.description)
            if error != nil {
                return
            }
            if granted {
                os_log("Notifications allowed", type: .debug)
            }
            else {
                os_log("Notifications denied", type: .debug)
            }
  
            // 2. Attempt registration for remote notifications on the main thread
            DispatchQueue.main.async {
                UIApplication.shared.registerForRemoteNotifications()
            }
        }
    }
```

然后，要处理取消并发送跟踪信息，您需要添加以下内容：

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                // If you're using  ACPCore v2.3.0 or later, use the line below.
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                // Else comment out the above line and uncomment the line below
                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
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
        //Looks it was opened based on the notification, lets get the tracking we passed on.
        Map<String, String> notificationData = (Map<String, Object>)data.getSerializableExtra("NOTIFICATION_USER_INFO");
        String deliveryId = (String)notificationData.get("deliveryId");
        String messageId = (String)notificationData.get("broadlogId");
  
  
  
        if (deliveryId != null && messageId != null) {
            HashMap<String, String> contextData = new HashMap<>();
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
  
            //Send Click Tracking since the user did click on the notification
            contextData.put("action", "2");
            // If you're using  ACPCore v1.4.0 or later, use the next line.
            MobileCore.collectMessageInfo(contextData);
            // Else comment out the above line and uncomment the line below
            // MobileCore.trackAction("tracking", contextData);
  
            //Send Open Tracking since the user opened the app
            contextData.put("action", "1");
            // If you're using  ACPCore v1.4.0 or later, use the next line.
            MobileCore.collectMessageInfo(contextData);
            // Else comment out the above line and uncomment the line below
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
  
    // Called when user clicks the local notification or also called from willPresent()
    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
  
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            //This is to handle the Dismiss Action
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
            // If you're using  ACPCore v2.3.0 or later, use the line below.
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            // Else comment out the above line and uncomment the line below
            // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
               // If you're using  ACPCore v2.3.0 or later, use the line below.
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
               // Else comment out the above line and uncomment the line below
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
