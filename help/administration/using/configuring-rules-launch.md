---
title: 配置标记规则以支持 Adobe Campaign Standard 用例
description: 了解如何配置标记规则以支持Adobe Campaign Standard用例
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b5f4f612-ea23-4007-b427-069777ecdd58
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '999'
ht-degree: 2%

---

# 配置标记规则以支持 Adobe Campaign Standard 用例 {#configuring-rules-launch}

在数据收集UI中，创建数据元素和规则以将PII和其他数据从移动应用程序发送到 [!DNL Adobe Campaign Standard].

要确保数据收集UI中的所有配置更改生效，您必须发布这些更改。 有关更多信息，请参阅 [发布](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration).

要在数据收集UI中创建规则，请执行以下步骤：

1. [创建数据元素](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [创建规则](../../administration/using/configuring-rules-launch.md#create-data-elements) 对于要支持的用例：
   * [PII回发](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [应用程序内跟踪回发](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [推送通知跟踪回发](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [位置回发](../../administration/using/configuring-rules-launch.md#location-postback)

## 创建数据元素 {#create-data-elements}

以下是我们建议您在数据收集UI中创建的数据元素。
您可以根据需要创建其他数据元素。

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

要创建这些数据元素，请执行以下操作：

1. 在数据收集UI中，从移动设备应用程序仪表板中，单击 **[!UICONTROL Data Elements]** 选项卡。

1. 要创建 **[!UICONTROL Experience Cloud ID]** 数据元素，单击 **[!UICONTROL Create New Data Element]**.

1. 在 **[!UICONTROL Name]** 字段，例如，键入 **mcid**.

1. 从 **[!UICONTROL Extension]** 下拉列表，选择 **[!UICONTROL Mobile Core]**. 则 **[!UICONTROL Experience Cloud ID]** 在 **[!UICONTROL Data element]** 类型下拉列表。

   ![](assets/do-not-localize/rules_1.png)

1. 要创建Pkey数据元素，请单击 **[!UICONTROL Add data element]**.

1. 在 **[!UICONTROL Name]** 字段，例如，键入 **pkey**.

1. 从 **[!UICONTROL Extension]** 下拉列表，选择 **[!UICONTROL Adobe Campaign Standard]**. 则 **[!UICONTROL pkey]** 在 **[!UICONTROL Data element]** 类型下拉列表。

1. 要创建Campaign服务器数据元素，请单击 **[!UICONTROL Add data element]**.

1. 在 **[!UICONTROL Name]** 字段中，键入名称，例如， **camp-server**.

1. 从 **[!UICONTROL Extension]** 下拉列表，选择 **[!UICONTROL Adobe Campaign Standard]**. 然后， **[!UICONTROL Campaign Server]** 在 **[!UICONTROL Data element]** 类型下拉列表。

## 创建规则 {#creating-rules}

您必须为以下内容创建规则：

* [PII回发](../../administration/using/configuring-rules-launch.md#pii-postback)
* [应用程序内跟踪回发](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [推送通知跟踪回发](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [位置回发](../../administration/using/configuring-rules-launch.md#location-postback)

### PII回发 {#pii-postback}

>[!NOTE]
>
>要将PII信息从移动应用程序发送到Adobe Campaign，您必须实施SDK API。 有关详细信息，请访问 [CollectPII](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#collectpii).

要将PII数据发送到 [!DNL Adobe Campaign Standard]，在数据收集UI中创建规则：

1. 在数据收集UI中，从移动设备应用程序仪表板中，单击 **[!UICONTROL Rules]** 选项卡，然后 **[!UICONTROL Create New Rule]**.

1. 键入名称，例如， **移动核心 — 收集PII**.

1. 在 **[!UICONTROL Events]** 部分，单击 **[!UICONTROL Add]**.

1. 从 **[!UICONTROL Extension]** 下拉列表，选择 **[!UICONTROL Mobile Core]**. 然后， **[!UICONTROL Collect PII]** 在 **[!UICONTROL Event type]** 下拉菜单。

1. 单击 **[!UICONTROL Keep changes]**。

1. 在 **[!UICONTROL Actions]** 部分，单击 **[!UICONTROL Add]**.

1. 从 **[!UICONTROL Extension]** 下拉列表，选择 **[!UICONTROL Mobile Core]**. 然后， **[!UICONTROL Send PII]** 在 **[!UICONTROL Action type]** 下拉菜单。

1. 在 **[!UICONTROL URL]**，输入以下URL：

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. 选择 **[!UICONTROL Add Post Body]** 复选框。

1. 在 **[!UICONTROL Post Body]**，键入以下内容：

   ```
   {
   "marketingCloudId":
   "{%%mcid%%}",
   "pushPlatform":
   "{%contextdata.pushPlatform%}",
   "cusEmail":
   "{%contextdata.email%}",
   "cusFirstName":
   "{%contextdata.firstName%}",
   "cusLastName":
   "{%contextdata.lastName%}" }
   ```

   通过marketingCloudId，您可以协调应用程序订阅者与数据库中的收件人，因此是必需的。 您可以根据业务需求指定其他键值对。 在上面的示例中，正在从应用程序传递电子邮件、名字和姓氏。

   键（例如cusEmail、cusFirstName和cusLastName）应该与Adobe Campaign Standard实例的自定义资源中定义的字段ID匹配。 值变量（例如电子邮件、firstName和LastName）应与从应用程序代码调用AMS collectPII API时从移动应用程序发送的JSON数据中的键匹配。

   您还可以在Collect PII回发或其他回发中传递生命周期数据，具体取决于您的事件触发器。 以下是生命周期数据JSON的示例：

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "pushPlatform":"{%contextdata.pushPlatform%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   例如，数据收集UI中定义的数据元素应包含于双百分比中 `%%mcid%%`、和应用程序中的上下文变量应以单个百分比括起来，例如%contextdata.email%。

1. 在 **[!UICONTROL Content Type]**，类型 **application/json**.

1. 在 **[!UICONTROL Timeout]**，选择0。

   ![](assets/do-not-localize/rules_2.png)

您的用户数据现在已配置为发送到Campaign。

### 应用程序内跟踪回发 {#inapp-tracking-postback}

>[!NOTE]
>
>如果您使用的是Android ACPCore v1.4.0或更高版本/ iOS ACPCore v2.3.0或更高版本，则不需要配置跟踪回发。

要将跟踪数据发送至 [!DNL Adobe Campaign Standard] 要报告用户如何与移动应用程序中的应用程序内消息进行交互，请在数据收集UI中创建以下规则：

1. 在数据收集UI中，从移动应用程序仪表板中，选择 **[!UICONTROL Rules]** 选项卡，然后单击 **[!UICONTROL Add Rule]**.

1. 键入名称，例如， **Adobe Campaign — 应用程序内点击跟踪**.

1. 在 **[!UICONTROL Events]** 部分，单击 **[!UICONTROL Add]**.

1. 从 **[!UICONTROL Extension]** 下拉列表，选择 **[!UICONTROL Adobe Campaign Standard]**. 然后， **[!UICONTROL In-App click tracking]** 在 **[!UICONTROL Event type]** 下拉菜单。

1. 单击 **[!UICONTROL Keep changes]**。

1. 在 **[!UICONTROL Actions]** 部分，单击 **[!UICONTROL Add]**.

1. 从 **[!UICONTROL Extension]** 下拉列表，选择 **[!UICONTROL Mobile Core]**. 然后， **[!UICONTROL Send postback]** 在 **[!UICONTROL Event type]** 下拉菜单。

1. 在 **[!UICONTROL URL]**，键入以下URL：

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. 选择 **[!UICONTROL Add post body]** 复选框。

1. 在 **[!UICONTROL Post Body]**，类型 **{}**.

1. 在 **[!UICONTROL Content Type]**，类型 **application/json**.

1. 在 **[!UICONTROL Timeout]**，选择0。

   ![](assets/do-not-localize/rules_3.png)

### 推送通知跟踪回发 {#push-tracking-postback}

>[!NOTE]
>
>如果您使用的是Android ACPCore v1.4.0或更高版本/ iOS ACPCore v2.3.0或更高版本，则不需要配置跟踪回发。

要将跟踪数据发送至 [!DNL Adobe Campaign Standard]，有助于跟踪您的推送通知投放以及用户与移动应用程序的交互，您必须在数据收集UI中创建规则。

有关推送跟踪的详细信息，请参阅 [推送跟踪](../../administration/using/push-tracking.md).

要跟踪应用程序操作，请使用trackAction API。 有关更多信息，请参阅 [跟踪应用程序操作](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

1. 在数据收集UI中，从移动设备应用程序仪表板中，单击 **[!UICONTROL Rules]** 选项卡，然后单击 **[!UICONTROL Add Rule]**.

1. 键入名称，例如， **Adobe Campaign — 推送点击跟踪**.

1. 在 **[!UICONTROL Events]** 部分，单击 **[!UICONTROL Add]**.

1. 从 **[!UICONTROL Extension]** 下拉列表，选择 **[!UICONTROL Mobile Core]**. 然后， **[!UICONTROL Track Action]** 在 **[!UICONTROL Event type]** 下拉菜单。

1. 从 **[!UICONTROL Action]** 下拉列表，选择 **[!UICONTROL Action]**，选择 **[!UICONTROL equals]**，并键入 **跟踪**.

1. 单击 **[!UICONTROL Keep changes]**。然后，在 **[!UICONTROL Actions]** 部分，单击 **[!UICONTROL Add]**.

1. 从 **[!UICONTROL Extension]** 下拉列表，选择 **[!UICONTROL Mobile Core]**. 然后， **[!UICONTROL Send postback]** 在 **[!UICONTROL Action type]** 下拉菜单。

1. 在 **[!UICONTROL URL]**，输入以下URL：

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. 选择 **[!UICONTROL Add post body]** 复选框。

1. 添加您的帖子正文，例如，{ }。

1. 在 **[!UICONTROL Content Type]**，类型 **application/json**.

1. 在 **[!UICONTROL Timeout]**，选择0。

### 位置回发 {#location-postback}

1. 在数据收集UI中，从移动设备应用程序仪表板中，单击 **[!UICONTROL Rules]** 选项卡，然后单击 **[!UICONTROL Add Rule]**.

1. 键入名称，例如， **位置回发**.

1. 在 **[!UICONTROL Events]** 部分，单击 **[!UICONTROL Add]**.

1. 创建事件，例如，输入POI或退出POI。 从 **[!UICONTROL Extension]** 下拉列表，选择 **地点 — Beta版**. 然后， **输入POI** 或 **退出POI** 在 **[!UICONTROL Event type]** 下拉菜单。

1. 输入名称，例如， **Places - Beta — 输入POI** 或 **退出POI**.

1. 在 **[!UICONTROL Actions]** 部分，单击 **[!UICONTROL Add]**.

1. 从 **[!UICONTROL Extension]** 下拉列表，选择 **[!UICONTROL Mobile Core]**. 然后， **[!UICONTROL Send postback]** 从 **[!UICONTROL Action type]** 下拉菜单。

1. 输入名称，例如， **移动核心 — 发送位置回发**.

1. 在 **[!UICONTROL URL]**，输入以下URL：

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. 选择 **[!UICONTROL Add post body]** 复选框，并添加您的帖子正文，例如：

   ```
   {
   "locationData": {
       "distances": "{%%Distance%%}",
       "poiLabel": "{%%POILabel%%}",
       "latitude": "{%%Latitude%%}",
       "longitude": "{%%Longitude%%}",
       "appId": "{%%AppId%%}",
       "marketingCloudId": "{%%ECID%%}"
   }
   }
   ```

   >[!NOTE]
   >
   >在上面的示例中，必须利用中的步骤在数据收集UI中配置右侧的数据元素 [创建数据元素](../../administration/using/configuring-rules-launch.md#create-data-elements). 中支持左侧的数据元素 [!DNL Adobe Campaign Standard] 并且不需要任何配置。 如果您需要其他数据，则必须在中执行自定义资源扩展 [!DNL Adobe Campaign Standard].

1. 在 **[!UICONTROL Content Type]**，类型 **application/json**.

1. 在 **[!UICONTROL Timeout]**，选择5。

   ![](assets/do-not-localize/rules_4.png)
