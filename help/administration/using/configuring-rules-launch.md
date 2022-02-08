---
title: 配置Adobe Experience Platform Launch规则以支持Adobe Campaign Standard用例
description: 了解如何配置Adobe Experience Platform Launch规则以支持Adobe Campaign Standard用例
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b5f4f612-ea23-4007-b427-069777ecdd58
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '949'
ht-degree: 1%

---

# 配置 Launch 规则以支持 Adobe Campaign Standard 用例 {#configuring-rules-launch}

在 [!DNL Adobe Experience Platform Launch]，创建数据元素和规则以将PII和其他数据从移动应用程序发送到 [!DNL Adobe Campaign Standard].

确保 [!DNL Adobe Experience Platform Launch] 生效后，必须发布这些更改。 有关更多信息，请参阅 [发布](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration).

在中创建规则 [!DNL Experience Platform Launch]，请执行以下步骤：

1. [创建数据元素](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [创建规则](../../administration/using/configuring-rules-launch.md#create-data-elements) 对于要支持的用例：
   * [PII回发](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [应用程序内跟踪回发](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [推送通知跟踪回发](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [位置回发](../../administration/using/configuring-rules-launch.md#location-postback)

## 创建数据元素 {#create-data-elements}

以下是我们建议您在中创建的数据元素 [!DNL Experience Platform Launch].
您可以根据需要创建其他数据元素。

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

要创建这些数据元素，请执行以下操作：

1. 在 [!DNL Experience Platform Launch]，在移动应用程序仪表板中，单击 **[!UICONTROL Data Elements]** 选项卡。

1. 创建 **[!UICONTROL Experience Cloud ID]** 数据元素，单击 **[!UICONTROL Create New Data Element]**.

1. 在 **[!UICONTROL Name]** 例如，键入 **mcid**.

1. 从 **[!UICONTROL Extension]** 下拉列表，选择 **[!UICONTROL Mobile Core]**. 然后 **[!UICONTROL Experience Cloud ID]** 在 **[!UICONTROL Data element]** 类型下拉列表。

   ![](assets/do-not-localize/rules_1.png)

1. 要创建Pkey数据元素，请单击 **[!UICONTROL Add data element]**.

1. 在 **[!UICONTROL Name]** 例如，键入 **pkey**.

1. 从 **[!UICONTROL Extension]** 下拉列表，选择 **[!UICONTROL Adobe Campaign Standard]**. 然后 **[!UICONTROL pkey]** 在 **[!UICONTROL Data element]** 类型下拉列表。

1. 要创建Campaign服务器数据元素，请单击 **[!UICONTROL Add data element]**.

1. 在 **[!UICONTROL Name]** 字段中键入名称，例如， **camp-server**.

1. 从 **[!UICONTROL Extension]** 下拉列表，选择 **[!UICONTROL Adobe Campaign Standard]**. 然后， **[!UICONTROL Campaign Server]** 在 **[!UICONTROL Data element]** 类型下拉列表。

## 创建规则 {#creating-rules}

您必须为以下项创建规则：

* [PII回发](../../administration/using/configuring-rules-launch.md#pii-postback)
* [应用程序内跟踪回发](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [推送通知跟踪回发](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [位置回发](../../administration/using/configuring-rules-launch.md#location-postback)

### PII回发 {#pii-postback}

>[!NOTE]
>
>要将PII信息从移动设备应用程序发送到Adobe Campaign，您必须实施SDK API。 有关更多信息，请转到 [CollectPII](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii).

将PII数据发送到 [!DNL Adobe Campaign Standard]，在中创建规则 [!DNL Experience Platform Launch]:

1. 在 [!DNL Experience Platform Launch]，在移动应用程序仪表板中，单击 **[!UICONTROL Rules]** 选项卡 **[!UICONTROL Create New Rule]**.

1. 键入一个名称，例如 **移动核心 — 收集PII**.

1. 在 **[!UICONTROL Events]** ，单击 **[!UICONTROL Add]**.

1. 从 **[!UICONTROL Extension]** 下拉列表，选择 **[!UICONTROL Mobile Core]**. 然后， **[!UICONTROL Collect PII]** 在 **[!UICONTROL Event type]** 下拉菜单。

1. 单击 **[!UICONTROL Keep changes]**。

1. 在 **[!UICONTROL Actions]** ，单击 **[!UICONTROL Add]**.

1. 从 **[!UICONTROL Extension]** 下拉列表，选择 **[!UICONTROL Mobile Core]**. 然后， **[!UICONTROL Send PII]** 在 **[!UICONTROL Action type]** 下拉菜单。

1. 在 **[!UICONTROL URL]**，输入以下URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. 选择 **[!UICONTROL Add Post Body]** 复选框。

1. 在 **[!UICONTROL Post Body]**，请键入以下内容：

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

   MarketingCloudId允许您将应用程序订阅者与数据库中的收件人进行协调，因此需要使用。 您可以根据业务需要指定其他键值对。 在以上示例中，正在从应用程序传递电子邮件、名字和姓氏。

   键（例如cusEmail、cusFirstName和cusLastName）应与在Adobe Campaign Standard实例的自定义资源中定义的字段ID匹配。 值变量（例如email、firstName和LastName）应与移动设备应用程序在从应用程序代码调用AMS collectPII API时发送的JSON数据中的键值匹配。

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

   中定义的数据元素 [!DNL Experience Platform Launch] 应以双个百分比包含在内，例如%%mcid%%，而来自应用程序的上下文变量应以单个百分比包含在内，例如%contextdata.email%。

1. 在 **[!UICONTROL Content Type]**，类型 **application/json**.

1. 在 **[!UICONTROL Timeout]**，选择0。

   ![](assets/do-not-localize/rules_2.png)

您的用户数据现已配置为发送到Campaign。

### 应用程序内跟踪回发 {#inapp-tracking-postback}

>[!NOTE]
>
>如果您使用的是Android ACPCore v1.4.0或更高版本/ iOS ACPCore v2.3.0或更高版本，则无需配置跟踪回发。

将跟踪数据发送到 [!DNL Adobe Campaign Standard] 要报告用户与移动应用程序中应用程序内消息的交互方式，请在 [!DNL Experience Platform Launch]:

1. 在 [!DNL Experience Platform Launch]，从移动应用程序仪表板中，选择 **[!UICONTROL Rules]** 选项卡，单击 **[!UICONTROL Add Rule]**.

1. 键入一个名称，例如 **Adobe Campaign — 应用程序内点击跟踪**.

1. 在 **[!UICONTROL Events]** ，单击 **[!UICONTROL Add]**.

1. 从 **[!UICONTROL Extension]** 下拉列表，选择 **[!UICONTROL Adobe Campaign Standard]**. 然后， **[!UICONTROL In-App click tracking]** 在 **[!UICONTROL Event type]** 下拉菜单。

1. 单击 **[!UICONTROL Keep changes]**。

1. 在 **[!UICONTROL Actions]** ，单击 **[!UICONTROL Add]**.

1. 从 **[!UICONTROL Extension]** 下拉列表，选择 **[!UICONTROL Mobile Core]**. 然后， **[!UICONTROL Send postback]** 在 **[!UICONTROL Event type]** 下拉菜单。

1. 在 **[!UICONTROL URL]**，请键入以下URL:

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
>如果您使用的是Android ACPCore v1.4.0或更高版本/ iOS ACPCore v2.3.0或更高版本，则无需配置跟踪回发。

将跟踪数据发送到 [!DNL Adobe Campaign Standard]，这有助于跟踪推送通知投放以及用户与移动应用程序的交互，您必须在 [!DNL Experience Platform Launch].

有关推送跟踪的更多信息，请参阅 [推送跟踪](../../administration/using/push-tracking.md).

要跟踪应用程序操作，请使用trackAction API。 有关更多信息，请参阅 [跟踪应用程序操作](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

1. 在 [!DNL Experience Platform Launch]，在移动应用程序仪表板中，单击 **[!UICONTROL Rules]** 选项卡，单击 **[!UICONTROL Add Rule]**.

1. 键入一个名称，例如 **Adobe Campaign — 推送点击跟踪**.

1. 在 **[!UICONTROL Events]** ，单击 **[!UICONTROL Add]**.

1. 从 **[!UICONTROL Extension]** 下拉列表，选择 **[!UICONTROL Mobile Core]**. 然后， **[!UICONTROL Track Action]** 在 **[!UICONTROL Event type]** 下拉菜单。

1. 从 **[!UICONTROL Action]** 下拉列表，选择 **[!UICONTROL Action]**，选择 **[!UICONTROL equals]**&#x200B;和类型 **跟踪**.

1. 单击 **[!UICONTROL Keep changes]**。然后，在 **[!UICONTROL Actions]** ，单击 **[!UICONTROL Add]**.

1. 从 **[!UICONTROL Extension]** 下拉列表，选择 **[!UICONTROL Mobile Core]**. 然后， **[!UICONTROL Send postback]** 在 **[!UICONTROL Action type]** 下拉菜单。

1. 在 **[!UICONTROL URL]**，输入以下URL:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. 选择 **[!UICONTROL Add post body]** 复选框。

1. 添加您的帖子正文，例如{ }。

1. 在 **[!UICONTROL Content Type]**，类型 **application/json**.

1. 在 **[!UICONTROL Timeout]**，选择0。

### 位置回发 {#location-postback}

1. 在 [!DNL Experience Platform Launch]，在移动应用程序仪表板中，单击 **[!UICONTROL Rules]** 选项卡，单击 **[!UICONTROL Add Rule]**.

1. 键入一个名称，例如 **位置回发**.

1. 在 **[!UICONTROL Events]** ，单击 **[!UICONTROL Add]**.

1. 创建一个事件，例如，进入POI或退出POI。 从 **[!UICONTROL Extension]** 下拉列表，选择 **Places — 测试版**. 然后， **进入POI** 或 **退出POI** 在 **[!UICONTROL Event type]** 下拉菜单。

1. 输入名称，例如 **Places — 测试版 — 进入POI** 或 **退出POI**.

1. 在 **[!UICONTROL Actions]** ，单击 **[!UICONTROL Add]**.

1. 从 **[!UICONTROL Extension]** 下拉列表，选择 **[!UICONTROL Mobile Core]**. 然后， **[!UICONTROL Send postback]** 从 **[!UICONTROL Action type]** 下拉菜单。

1. 输入名称，例如 **移动核心 — 发送位置回发**.

1. 在 **[!UICONTROL URL]**，输入以下URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. 选择 **[!UICONTROL Add post body]** 复选框并添加帖子正文，例如：

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
   >在以上示例中，必须在 [!DNL Experience Platform Launch] 通过利用 [创建数据元素](../../administration/using/configuring-rules-launch.md#create-data-elements). 左侧的数据元素在 [!DNL Adobe Campaign Standard] 和不需要任何配置。 如果需要其他数据，则必须在 [!DNL Adobe Campaign Standard].

1. 在 **[!UICONTROL Content Type]**，类型 **application/json**.

1. 在 **[!UICONTROL Timeout]**，选择5。

   ![](assets/do-not-localize/rules_4.png)
