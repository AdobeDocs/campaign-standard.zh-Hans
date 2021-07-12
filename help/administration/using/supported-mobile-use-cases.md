---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standard中使用Adobe Experience Platform SDK支持的移动使用案例
description: 本文档提供了有关如何支持移动使用案例的信息。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: 实例设置
role: Admin
level: Experienced
exl-id: 3cd8d756-a271-4e53-8ed0-984ce20298bc
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 0%

---

# Adobe Campaign Standard 中支持的移动使用案例 {#mobile-use-cases}

在本页中，您将找到[!DNL Adobe Campaign Standard]中使用[!DNL Adobe Experience Platform SDKs]支持的每个移动用例的列表。 请注意，支持这些用例涉及安装和配置[!DNL Adobe Experience Platform SDKs]、[!DNL Adobe Experience Platform Launch]和[!DNL Adobe Campaign Standard]。 有关此内容的详细信息，请参见此[页面](../../administration/using/configuring-a-mobile-application.md)。

Adobe Campaign Standard支持以下用例：

* [在Campaign Standard中注册移动用户档案](../../administration/using/supported-mobile-use-cases.md#register-mobile-profile)
* [将推送令牌发送到Campaign Standard](../../administration/using/supported-mobile-use-cases.md#send-push-token)
* [使用应用程序中的自定义数据扩充移动用户档案](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-custom)
* [使用应用程序中的生命周期数据扩充移动用户档案](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-lifecycle)
* [跟踪用户与推送通知的交互](../../administration/using/supported-mobile-use-cases.md#track-user-push)
* [在移动设备应用程序中实施自定义事件以触发应用程序内消息](../../administration/using/supported-mobile-use-cases.md#custom-event-inapp)
* [为基于应用程序内消息的用户档案模板设置其他身份验证的链接字段](../../administration/using/supported-mobile-use-cases.md#linkage-fields-inapp)

要配置这些用例，您需要[!DNL Experience Platform Launch]的以下扩展：

* **[!DNL Adobe Campaign Standard]** <br>要安装和配置Campaign Standard扩展，请参阅 [在Experience Platform Launch中配置Campaign Standard扩展](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#configure-the-campaign-standard-extension-in-experience-platform-launch)。
* **[!DNL Mobile Core]**，将自动安装。<br>有关Mobile Core扩展的更多信息，请参阅 [Mobile Core](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core)。
* **[!DNL Profile]**，将自动安装。<br>有关Profile扩展的更多信息，请参阅 [Profile](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/profile)。

## 在Campaign Standard中注册移动用户档案 {#register-mobile-profile}

### 使用iOS {#register-mobile-profile-ios}

在iOS中，需要以下[!DNL Experience Platform APIs]:

* **[!UICONTROL Lifecycle Start]**、应用程序启动时和应用程序处于前台时。
* **[!UICONTROL Lifecycle Pause]**，当应用程序处于后台时。

有关更多信息，请参阅iOS](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-ios)中的[生命周期扩展。

以下是iOS中此用例的实施示例：

```
 func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
  
  
 ACPCore.setLogLevel(.debug)
 appId = SettingsBundle.getLaunchAppId()
   
 //===== START Set up Adobe SDK =====
 ACPCore.configure(withAppId: appId)
   
 ACPCampaign.registerExtension()
 ACPIdentity.registerExtension()
 ACPLifecycle.registerExtension()
 ACPUserProfile.registerExtension()
 ACPSignal.registerExtension()
 ACPCore.start()
 ACPCore.lifecycleStart(nil)
   
 return true
 }
  
func applicationDidEnterBackground(_ application: UIApplication) {
 ACPCore.lifecyclePause()
 }
   
 func applicationDidBecomeActive(_ application: UIApplication) {
 // Workaround until jira AMSDK-7411 is fixed.
 sleep(2)
 ACPCore.lifecycleStart(nil)
 }
```

### 使用Android {#register-mobile-profile-android}

在Android中，需要使用以下[!DNL Experience Platform APIs]:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

有关更多信息，请参阅Android中的[生命周期扩展](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android)。

以下是Android中此用例的实施示例：

```
@Override
  
public void onResume() {
 super.onResume();
 MobileCore.setApplication(getApplication());
 MobileCore.lifecycleStart(null);
 handleOpenTracking();
 }
  
 @Override
 public void onPause() {
 super.onPause();
 MobileCore.lifecyclePause();
 }
```

## 将推送令牌发送到Adobe Campaign Standard {#send-push-token}

### 使用iOS {#send-push-token-ios}

在iOS中，需要以下[!DNL Experience Platform SDK]:

* **[!UICONTROL setPushIdentifier]** <br>有关更多信息，请参 [阅setPushIdentifier](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#setpushidentifier)。

以下是iOS中此用例的实施示例：

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
  
 // Register Device Token
 ACPCore.setPushIdentifier(deviceToken)
```

### 使用Android {#send-push-token-android}

在Android中，需要满足以下条件：[!DNL Experience Platform SDK]

* **[!UICONTROL setPushIdentifier]** <br>有关更多信息，请参 [阅setPushIdentifier](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#setpushidentifier)。

以下是Android中此用例的实施示例：

```
@Override
public void onNewToken(String token) {
    Log.d(TAG, "Refreshed token: " + token);
    MobileCore.setPushIdentifier(token);
}
```

## 使用应用程序中的自定义数据扩充移动用户档案 {#enrich-mobile-profile-custom}

要使此用例正常工作，您需要为PII回发创建规则。 有关更多信息，请参阅[PII回发](../../administration/using/configuring-rules-launch.md#pii-postback)。

### 使用iOS {#enrich-mobile-profile-custom-ios}

在iOS中，需要以下[!DNL Experience Platform API]:

* collectPII <br>有关更多信息，请参阅collectPII 。

以下是iOS中此用例的实施示例：

```
ACPCore.collectPii(["email":email, "firstName":firstName, "lastName":lastName])
```

### 使用Android {#enrich-mobile-profile-custom-android}

在Android中，需要满足以下条件：[!DNL Experience Platform API]

* collectPII <br>有关更多信息，请参阅collectPII 。

以下是Android中此用例的实施示例：

```
HashMap<String, String> data = new HashMap<>();
data.put("firstName", firstNameText);
data.put("lastName", lastNameText);
data.put("email", emailText);
MobileCore.collectPii(data);
```

## 使用应用程序中的生命周期数据扩充移动用户档案 {#enrich-mobile-profile-lifecycle}

要使此用例正常工作，您需要为PII回发创建规则。 有关更多信息，请参阅[PII回发](../../administration/using/configuring-rules-launch.md#pii-postback)。

>[!NOTE]
>
>Adobe Campaign不会将自定义数据或生命周期数据与移动设备应用程序区分开。 这两种类型的数据都可以使用collectPii回发规则发送到服务器，以响应移动设备应用程序中的事件。

### 使用iOS {#enrich-mobile-profile-lifecycle-ios}

在iOS中，需要以下[!DNL Experience Platform APIs]:

* **[!UICONTROL Lifecycle Start]**、应用程序启动时和应用程序处于前台时。
* **[!UICONTROL Lifecycle Pause]**，当应用程序处于后台时。

有关更多信息，请参阅iOS](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-ios)中的[生命周期扩展。

以下是iOS中此用例的实施示例：

```
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
  
  
 ACPCore.setLogLevel(.debug)
 appId = SettingsBundle.getLaunchAppId()
   
 //===== START Set up Adobe SDK =====
 ACPCore.configure(withAppId: appId)
   
 ACPCampaign.registerExtension()
 ACPIdentity.registerExtension()
 ACPLifecycle.registerExtension()
 ACPUserProfile.registerExtension()
 ACPSignal.registerExtension()
 ACPCore.start()
 ACPCore.lifecycleStart(nil)
   
 return true
 }
  
func applicationDidEnterBackground(_ application: UIApplication) {
 ACPCore.lifecyclePause()
 }
   
 func applicationDidBecomeActive(_ application: UIApplication) {
 // Workaround until jira AMSDK-7411 is fixed.
 sleep(2)
 ACPCore.lifecycleStart(nil)
 }
```

### 使用Android {#enrich-mobile-profile-lifecycle-android}

在Android中，需要使用以下[!DNL Experience Platform APIs]:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

有关更多信息，请参阅Android中的[生命周期扩展](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android)。

以下是Android中此用例的实施示例：

```
@Override
  
public void onResume() {
 super.onResume();
 MobileCore.setApplication(getApplication());
 MobileCore.lifecycleStart(null);
 handleOpenTracking();
 }
  
 @Override
 public void onPause() {
 super.onPause();
 MobileCore.lifecyclePause();
 }
```

## 跟踪用户与推送通知的交互 {#track-user-push}

您需要为推送通知跟踪回发创建规则。 有关更多信息，请参阅[推送通知跟踪回发](../../administration/using/configuring-rules-launch.md#push-tracking-postback)。

### 使用iOS {#track-user-push-ios}

在iOS中，需要以下[!DNL Experience Platform SDK]:

* **[!UICONTROL trackAction]**.有关更多信息，请参阅[跟踪应用程序操作](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)。

以下是iOS中此用例的实施示例：

```
let deliveryId = userInfo["_dId"] as? String
let broadlogId = userInfo["_mId"] as? String
if (deliveryId != nil && broadlogId != nil) {
    ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
}
```

### 使用Android {#track-user-push-android}

在Android中，需要满足以下条件：[!DNL Experience Platform SDK]

* **[!UICONTROL trackAction]**
有关更多信息，请参阅 [跟踪应用程序操作](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)。

以下是Android中此用例的实施示例：

```
contextData.put("deliveryId", deliveryId);
contextData.put("broadlogId", messageId);
contextData.put("action", "2");
MobileCore.trackAction("tracking", contextData);
```

## 在应用程序中实施自定义事件以触发应用程序内消息 {#custom-event-inapp}

### 使用iOS {#custom-event-inapp-ios}

在iOS中，需要以下[!DNL Experience Platform SDK]:

* **[!UICONTROL trackAction]**.有关更多信息，请参阅[跟踪应用程序操作](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)。

以下是iOS中此用例的实施示例：

```
ACPCore.trackAction(mobileEventName, data: [:] )
```

### 使用Android {#custom-event-inapp-android}

在Android中，需要满足以下条件：[!DNL Experience Platform SDK]

* **[!UICONTROL trackAction]**
有关更多信息，请参阅 [跟踪应用程序操作](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)。

以下是Android中此用例的实施示例：

```
MobileCore.trackAction(mobileEventText, new HashMap<String,String>());
```

## 设置用于其他身份验证的链接字段 {#linkage-fields-inapp}

### 使用iOS {#linkage-fields-inapp-ios}

要为基于iOS中应用程序内消息的用户档案模板设置附加身份验证的链接字段，需要满足以下条件：[!DNL Experience Platform SDK]:

* 设置链接字段<br>有关详细信息，请参阅[设置链接字段](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#set-linkage-fields)。
* 重置链接字段<br>有关更多信息，请参阅[重置链接字段](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#reset-linkage-fields)。

以下是此用例在iOS中的实施示例。

要设置链接字段：

```
var linkageFields = [String: String]()
linkageFields["cusEmail"] = "john.doe@email.com"
ACPCampaign.setLinkageFields(linkageFields)
```

要重置链接字段，请执行以下操作：

```
ACPCampaign.resetLinkageFields(linkageFields)
```

### 使用Android {#linkage-fields-inapp-android}

要为基于Android中应用程序内消息的用户档案模板设置其他身份验证的链接字段，需要以下Experience PlatformSDK:

* 设置链接字段<br>有关详细信息，请参阅[设置链接字段](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#set-linkage-fields)。
* 重置链接字段<br>有关更多信息，请参阅[重置链接字段](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#reset-linkage-fields)。

以下是Android中此用例的实施示例。

要设置链接字段：

```
HashMap<String, String> linkageFields = new HashMap<String, String>();
linkageFields.put("cusEmail", "john.doe@email.com");
Campaign.setLinkageFields(linkageFields);
```

要重置链接字段，请执行以下操作：

```
Campaign.resetLinkageFields()
```
