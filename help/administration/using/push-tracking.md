---
title: 实施推送跟踪
description: 利用本文档，可确保已在iOS和Android上正确实施推送通知跟踪。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 950d24e2-358f-44f8-98ea-643be61d4573
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '949'
ht-degree: 1%

---

# 实施推送跟踪 {#push-tracking}

## 关于推送跟踪 {#about-push-tracking}

要确保推送通知已完全开发，您需要确保正确实施了跟踪部分，因为并非每个推送通知都启用了跟踪。 要启用此功能，开发人员需要确定哪些投放启用了跟踪，Adobe Campaign Standard将发送一个名为 `_acsDeliveryTracking` 两个值 **on** 或 **关闭**. 对于将变量设置为的投放，应用程序开发人员应仅发送跟踪请求 **on**.

>[!IMPORTANT]
>
>此变量不适用于21.1版本之前设置的投放或使用自定义模板的投放。

推送跟踪分为三种类型：

* **推送展示次数**  — 将推送通知发送到设备并位于通知中心但完全未接触时。  这被视为一种印象。  在大多数情况下，如果展示次数与已交付的数量不同，则展示次数应相似。 它确保设备收到消息并将该信息转发回服务器。

* **推送点击**  — 将推送通知交付到设备且用户单击了设备时。  用户想要查看通知（这反过来又将移至推送打开跟踪）或关闭通知。

* **推送打开**  — 将推送通知交付到设备且用户单击了导致应用程序打开的通知时。  这类似于推送点击，除非取消通知后不会触发推送打开。

要实施Campaign Standard跟踪，移动设备应用程序需要包含Mobile SDK。 这些SDK可在Mobile ServicesAdobe中使用。 有关详细信息，请参见此 [ 页面](../../administration/using/configuring-a-mobile-application.md)。

要发送跟踪信息，需要发送三个变量。 两个是从Campaign Standard接收数据的一部分，另一个是操作变量，指示它是否是 **展示**, **单击** 或 **打开**.

| 变量 | 值 |
|:-:|:-:|
| broadlogId | 来自数据的_mId |
| deliveryId | 来自数据的_dId |
| 操作 | 1表示打开，2表示点击，7表示展示 |

## Android实施 {#implementation-android}

### 如何实施推送展示跟踪 {#push-impression-tracking-android}

对于展示次数跟踪，您必须在调用 **[!UICONTROL trackAction()]** 函数。

有关21.1版本之前创建的投放或包含自定义模板的投放，请参阅 [部分](../../administration/using/push-tracking.md#about-push-tracking).

```
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
....{Handle push messages}....
  if (data.size() > 0) {
    String deliveryId = data.get("_dId");
    String messageId = data.get("_mId");
    String acsDeliveryTracking = data.get("_acsDeliveryTracking");
 
    /*
    This is to handle deliveries created before 21.1 release or deliveries with custom template
    where acsDeliveryTracking is not available.
    */
    if( acsDeliveryTracking == null ) {
        acsDeliveryTracking = "on";
    }
 
    HashMap<String, String> contextData = new HashMap<>();
    if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
                contextData.put("deliveryId", deliveryId);
                contextData.put("broadlogId", messageId);
                contextData.put("action", "7");
                MobileCore.trackAction("tracking", contextData);
    }
  }
}
```

### 如何实施点击跟踪 {#push-click-tracking-android}

对于点击跟踪，您必须在调用时发送值“2”以执行操作 **[!UICONTROL trackAction()]** 函数。

要跟踪点击，需要处理两种情况：

* 用户看到通知但将其清除。
* 用户看到通知并单击它，即可将其转换为打开的跟踪。

要处理此问题，您需要使用两个意图：一个用于单击通知，另一个用于关闭通知。

有关21.1版本之前创建的投放或包含自定义模板的投放，请参阅 [部分](../../administration/using/push-tracking.md#about-push-tracking).

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

为了 **[!UICONTROL BroadcastReceiver]** 要工作，您需要将其注册到 **[!UICONTROL AndroidManifest.xml]**

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
        String acsDeliveryTracking = data.get("_acsDeliveryTracking");
         
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template
        where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == null ) {
            acsDeliveryTracking = "on";
        }
 
        HashMap<String, Object> contextData = new HashMap<>();
 
        //We only send the click tracking since the user dismissed the notification
        if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
            contextData.put("action", "2");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### 如何实施打开跟踪 {#push-open-tracking-android}

由于用户必须单击通知才能打开应用程序，因此您需要发送“1”和“2”。 如果应用程序未通过推送通知启动/打开，则不会发生跟踪事件。

要跟踪打开情况，您需要创建意图。 目的对象允许Android操作系统在完成某些操作后调用您的方法。 在这种情况下，单击通知以打开应用程序。

此代码基于点击展示次数跟踪的实施。 使用 **[!UICONTROL Intent]** 设置后，您现在需要将跟踪信息发送回Adobe Campaign Standard。 在这种情况下，您需要将 **[!UICONTROL Open Intent]** 要在您的应用程序中打开到特定视图，这将使用 **[!UICONTROL Intent Object]**.

有关21.1版本之前创建的投放或包含自定义模板的投放，请参阅 [部分](../../administration/using/push-tracking.md#about-push-tracking).

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
        //This was opened based on the notification, you need to get the tracking that was passed on.
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
        String acsDeliveryTracking = data.get("_acsDeliveryTracking");
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template
        where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == null) {
            acsDeliveryTracking = "on";
        }
 
        HashMap<String, String> contextData = new HashMap<>();
 
        if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
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

## iOS实施 {#implementation-iOS}

### 如何实施推送展示跟踪 {#push-impression-tracking-iOS}

对于展示次数跟踪，您必须在调用 **[!UICONTROL trackAction()]** 函数。

要了解iOS通知的工作方式，需要详细描述应用程序的三种状态：

* **前景**:当应用程序当前处于活动状态且当前处于屏幕上（在前台）时。
* **背景**:当is应用程序未在屏幕上，但进程未关闭时。 双击“主页”按钮时，通常会显示位于后台的所有应用程序。
* **关闭/关闭**:一个进程已被终止的应用程序。

如果某个应用程序关闭，Apple在该应用程序重新启动之前不会调用该应用程序。 这意味着您将无法知道何时在iOS上收到通知。

为了仍然 **[!UICONTROL Impression]** 在应用程序处于后台时跟踪工作，我们需要发送 **[!UICONTROL Content-Available]** 以告知应用程序必须完成跟踪。

>[!CAUTION]
>
>iOS展示次数跟踪不准确，不应被视为可靠。

有关21.1版本之前创建的投放或包含自定义模板的投放，请参阅 [部分](../../administration/using/push-tracking.md#about-push-tracking).

以下代码针对后台应用程序：

```
// In didReceiveRemoteNotification event handler in AppDelegate.m
 
//In order to handle push notification when only in background with content-available: 1
func application(_ application: UIApplication, didReceiveRemoteNotification userInfo: [AnyHashable : Any], fetchCompletionHandler completionHandler: @escaping (UIBackgroundFetchResult) -> Void) {
 
        //Check if the app is not in the foreground right now
        if(UIApplication.shared.applicationState != .active) {
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
               ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
            }
        }
        completionHandler(UIBackgroundFetchResult.noData)
    }
```

以下代码针对前台应用程序：

```
// This will get called when the app is in the foreground
 
func userNotificationCenter(_ center: UNUserNotificationCenter, willPresent notification: UNNotification, withCompletionHandler completionHandler: @escaping (UNNotificationPresentationOptions) -> Void) {
 
 
        let userInfo = notification.request.content.userInfo
        let deliveryId = userInfo["_dId"] as? String
        let broadlogId = userInfo["_mId"] as? String
        let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == nil ) {
            acsDeliveryTracking = "on";
        }
        if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
             ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
        }
        completionHandler([.alert,.sound])
    }
```

### 如何实施点击跟踪 {#push-click-tracking-iOS}

对于点击跟踪，您必须在调用时发送值“2”以执行操作 **[!UICONTROL trackAction()]** 函数。
有关21.1版本之前创建的投放或包含自定义模板的投放，请参阅 [部分](../../administration/using/push-tracking.md#about-push-tracking).

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

现在，发送推送通知时，您需要添加类别。 在本例中，我们将其称为“DEFAULT”。

![](assets/tracking_push.png)

然后处理 **[!UICONTROL Dismiss]** 并发送您需要添加以下内容的跟踪信息：

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

### 如何实施打开跟踪 {#push-open-tracking-iOS}

由于用户必须单击通知才能打开应用程序，因此您需要发送“1”和“2”。 如果应用程序未通过推送通知启动/打开，则不会发生跟踪事件。

有关21.1版本之前创建的投放或包含自定义模板的投放，请参阅 [部分](../../administration/using/push-tracking.md#about-push-tracking).

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
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
