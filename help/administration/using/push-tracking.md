---
solution: Campaign Standard
product: campaign
title: 实施推送跟踪
description: 此文档允许您确保在iOS和Android上正确实施推送通知跟踪。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 1%

---


# 实施推送跟踪 {#push-tracking}

## 关于推送跟踪 {#about-push-tracking}

要确保已完全开发推送通知，您需要确保正确实施跟踪部分。
这假定您已经实施了推送通知实施的第一部分：

* 注册应用程序用户
* 处理推送通知消息

推送跟踪分为三种类型：

* **推送印象** -推送通知已发送到设备且位于通知中心，但完全未触及时。  这被认为是一种印象。  在大多数情况下，展示次数如果与已交付数不相同，则应相似。 它确保设备收到消息并将该信息转发回服务器。

* **推送单击** -当推送通知已发送到设备且用户已单击设备时。  用户要么希望视图通知（这反过来又将转到“推送打开”跟踪），要么取消通知。

* **推送打开** -当推送通知已发送到设备且用户单击了导致应用程序打开的通知时。  这与推送单击类似，但如果通知消失，则不会触发推送打开。

要实施Campaign Standard跟踪，移动应用程序需要包含Mobile SDK。 这些SDK可在AdobeMobile Services上使用。 有关详细信息，请参见此 [ 页面](../../administration/using/configuring-a-mobile-application.md)。

要发送跟踪信息，需要发送三个变量。 两个是从Campaign Standard接收的数据的一部分，一个操作变量指示它是“印象”、“ **单击**” **还是** “ **打开”**。

| 变量 | 值 |
|:-:|:-:|
| broadlogId | 数据的mId(_M) |
| deliveryId | 数据的dId(_D) |
| 行动 | 1表示打开，2表示单击，7表示印象 |

## 针对Android的实施 {#implementation-android}

### 如何实现推印跟踪 {#push-impression-tracking-android}

要进行印象跟踪，调用函数时必须发送值“7”以执行 **[!UICONTROL trackAction()]** 操作。

```
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
....{Handle push messages}....
  if (data.size() > 0) {
    String deliveryId = data.get("_dId");
    String messageId = data.get("_mId");
    HashMap<String, String> contextData = new HashMap<>();
    if (deliveryId != null && messageId != null) {
                contextData.put("deliveryId", deliveryId);
                contextData.put("broadlogId", messageId);
                contextData.put("action", "7");
                MobileCore.trackAction("tracking", contextData);
    }
  }
}
```

### 如何实现点击跟踪 {#push-click-tracking-android}

对于单击跟踪，您必须在调用函数时发送值“2”以执行 **[!UICONTROL trackAction()]** 操作。

要跟踪单击，需要处理两种情况：

* 用户可以看到通知，但会清除通知。
* 用户看到通知并单击它，将其转换为开放跟踪。

要处理此问题，您需要使用两种方法：一个用于单击通知，另一个用于取消通知。

**[!UICONTROL MyFirebaseMessagingService.java]**

```
private void sendNotification(Map<String, String> data) {
    Intent openIntent = new Intent(this, CollectPIIActivity.class);
    Intent dismissIntent = new Intent(this, NotificationDismissedReceiver.class);
    openIntent.addFlags(Intent.FLAG_ACTIVITY_CLEAR_TOP);
  
    //put the data map into the intent to track clickthroughs
    Bundle pushData = new Bundle();
    Set<String> keySet = data.keySet();
    for (String key : keySet) {
        pushData.putString(key, data.get(key));
    }
    openIntent.putExtras(pushData);
    dissmissIntent.putExtras(pushData);
  
  
    PendingIntent pendingIntent = PendingIntent.getActivity(this, 0, openIntent,
        PendingIntent.FLAG_UPDATE_CURRENT);
    PendingIntent onDismissPendingIntent = PendingIntent.getBroadcast(this.getApplicationContext(), 0, dismissIntent, 0);
  
    //<BUILD NOTIFICATION using notification builder>
    //Add both Intents to the notification
    notificationBuilder.setContentIntent(pendingIntent);
    notificationBuilder.setDeleteIntent(onDismissPendingIntent);
}
```

为了工作 **[!UICONTROL BroadcastReceiver]** ，您需要将其注册到 **[!UICONTROL AndroidManifest.xml]**

```
<manifest>
    <application>
        <receiver android:name=".NotificationDismissedReceiver">
        </receiver>
    </application>
</manifest>
```

NotificationDismessedReceiver.java

```
public class NotificationDismissedReceiver extends BroadcastReceiver {
    private static final String TAG = NotificationDismissedReceiver.class.getSimpleName();
    @Override
    public void onReceive(Context context, Intent intent) {
        Bundle data = intent.getExtras();
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
  
        HashMap<String, Object> contextData = new HashMap<>();
  
        //We only send the click tracking since the user dismissed the notification
        if (deliveryId != null && messageId != null) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
            contextData.put("action", "1");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### 如何实现开放跟踪 {#push-open-tracking-android}

您将需要发送“1”和“2”，因为用户必须单击通知才能打开应用程序。 如果应用程序未通过推送通知启动／打开，则不会发生跟踪事件。

要跟踪打开情况，您需要创建“用途”。 目的对象允许Android OS在完成某些操作时调用您的方法。 在这种情况下，请单击通知以打开应用程序。

此代码基于点击印象跟踪的实现。 设置 **[!UICONTROL Intent]** 后，您现在需要将跟踪信息发送回Adobe Campaign Standard。 在这种情况下，您需要将该设置 **[!UICONTROL Open Intent]** 为在应用程序中打开某个视图，这将使用中的通知数据调用onResume方法 **[!UICONTROL Intent Object]**。

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
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
  
        HashMap<String, Object> contextData = new HashMap<>();
  
        if (deliveryId != null && messageId != null) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
  
            //Send Click Tracking since the user did click on the notification
            contextData.put("action", "2");
            MobileCore.trackAction("tracking", contextData);
  
            //Send Open Tracking since the user opened the app
            contextData.put("action", "1");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

## iOS的实施 {#implementation-iOS}

### 如何实现推印跟踪 {#push-impression-tracking-iOS}

要进行印象跟踪，调用函数时必须发送值“7”以执行 **[!UICONTROL trackAction()]** 操作。

要了解iOS通知的工作方式，需要详细说明应用程序的三种状态：

* **前景**:当应用程序当前处于活动状态且当前处于屏幕上时（在前台）。
* **背景**:当is应用程序未在屏幕上但进程未关闭时。 当您多次单击主页按钮时，它通常会显示背景中的所有应用程序。
* **关闭／关闭**:一款流程已被扼杀的应用。

如果应用程序关闭，则Apple在应用程序重新启动之前不会调用该应用程序。 这意味着您将无法知道在iOS上何时收到通知。

为了在应用程 **[!UICONTROL Impression]** 序处于后台时仍能进行跟踪，我们需要发送该 **[!UICONTROL Content-Available]** 应用程序，以告知该应用程序必须进行跟踪。

>[!CAUTION]
>
>iOS印象跟踪不准确，不应被视为可靠。

以下代码目标后台应用程序：

```
// In didReceiveRemoteNotification event handler in AppDelegate.m
  
//In order to handle push notification when only in background with content-available: 1
func application(_ application: UIApplication, didReceiveRemoteNotification userInfo: [AnyHashable : Any], fetchCompletionHandler completionHandler: @escaping (UIBackgroundFetchResult) -> Void) {
  
        //Check if the app is not in the foreground right now
        if(UIApplication.shared.applicationState != .active) {
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
               ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
            }
        }
        completionHandler(UIBackgroundFetchResult.noData)
    }
```

以下代码目标前台应用程序：

```
// This will get called when the app is in the foreground
  
func userNotificationCenter(_ center: UNUserNotificationCenter, willPresent notification: UNNotification, withCompletionHandler completionHandler: @escaping (UNNotificationPresentationOptions) -> Void) {
  
  
        let userInfo = notification.request.content.userInfo
        let deliveryId = userInfo["_dId"] as? String
        let broadlogId = userInfo["_mId"] as? String
        if (deliveryId != nil && broadlogId != nil) {
             ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
        }
        completionHandler([.alert,.sound])
    }
```

### 如何实现点击跟踪 {#push-click-tracking-iOS}

对于单击跟踪，您必须在调用函数时发送值“2”以执行 **[!UICONTROL trackAction()]** 操作。

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

现在，在发送推送通知时，您需要添加类别。 在本例中，我们将其称为“DEFAULT”。

![](assets/tracking_push.png)

然后，要处理 **[!UICONTROL Dismiss]** 并发送跟踪信息，您需要添加以下内容：

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

### 如何实现开放跟踪 {#push-open-tracking-iOS}

您将需要发送“1”和“2”，因为用户必须单击通知才能打开应用程序。 如果应用程序未通过推送通知启动／打开，则不会发生跟踪事件。

```
import Foundation
import UserNotifications
import UserNotificationsUI
  
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {
  
    // Called when user clicks the push notification or also called from willPresent()
    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
  
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            //This is to handle the Dismiss Action
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
