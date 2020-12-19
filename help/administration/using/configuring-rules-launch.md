---
solution: Campaign Standard
product: campaign
title: 配置Adobe Experience Platform Launch规则以支持Adobe Campaign Standard使用案例
description: 配置Adobe Experience Platform Launch规则以支持Adobe Campaign Standard使用案例
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 1%

---


# 配置 Launch 规则以支持 Adobe Campaign Standard 用例 {#configuring-rules-launch}

在[!DNL Adobe Experience Platform Launch]中，您需要创建数据元素和规则，以便将PII和其他数据从移动应用程序发送到[!DNL Adobe Campaign Standard]。

要确保[!DNL Adobe Experience Platform Launch]中的所有配置更改均生效，您必须发布这些更改。 有关详细信息，请参阅[发布](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration)。

要在[!DNL Experience Platform Launch]中创建规则，请执行以下步骤：

1. [创建数据元素](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [为要](../../administration/using/configuring-rules-launch.md#create-data-elements) 支持的用例创建规则：
   * [PII回传](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [应用程序内跟踪回传](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [推送通知跟踪回发](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [位置回传](../../administration/using/configuring-rules-launch.md#location-postback)

## 创建数据元素{#create-data-elements}

以下是建议您在[!DNL Experience Platform Launch]中创建的数据元素。
您可以根据需要创建其他数据元素。

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

要创建这些数据元素，请执行以下操作：

1. 在[!DNL Experience Platform Launch]中，从移动应用程序仪表板中单击&#x200B;**[!UICONTROL Data Elements]**&#x200B;选项卡。

1. 要创建&#x200B;**[!UICONTROL Experience Cloud ID]**&#x200B;数据元素，请单击&#x200B;**[!UICONTROL Create New Data Element]**。

1. 例如，在&#x200B;**[!UICONTROL Name]**&#x200B;字段中，键入&#x200B;**mcid**。

1. 从&#x200B;**[!UICONTROL Extension]**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL Mobile Core]**。 然后，在&#x200B;**[!UICONTROL Data element]**&#x200B;类型下拉框中输入&#x200B;**[!UICONTROL Experience Cloud ID]**。

   ![](assets/do-not-localize/rules_1.png)

1. 要创建Pkey数据元素，请单击&#x200B;**[!UICONTROL Add data element]**。

1. 例如，在&#x200B;**[!UICONTROL Name]**&#x200B;字段中，键入&#x200B;**pkey**。

1. 从&#x200B;**[!UICONTROL Extension]**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL Adobe Campaign Standard]**。 然后，在&#x200B;**[!UICONTROL Data element]**&#x200B;类型下拉框中输入&#x200B;**[!UICONTROL pkey]**。

1. 要创建活动服务器数据元素，请单击&#x200B;**[!UICONTROL Add data element]**。

1. 在&#x200B;**[!UICONTROL Name]**&#x200B;字段中，键入名称，例如&#x200B;**camp-server**。

1. 从&#x200B;**[!UICONTROL Extension]**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL Adobe Campaign Standard]**。 然后，在&#x200B;**[!UICONTROL Data element]**&#x200B;类型下拉框中，选择&#x200B;**[!UICONTROL Campaign Server]**。

## 创建规则{#creating-rules}

您需要为以下各项创建规则：

* [PII回传](../../administration/using/configuring-rules-launch.md#pii-postback)
* [应用程序内跟踪回传](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [推送通知跟踪回发](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [位置回传](../../administration/using/configuring-rules-launch.md#location-postback)

### PII回传{#pii-postback}

>[!NOTE]
>
>要将PII信息从移动应用程序发送到Adobe Campaign，您需要实施SDK API。 有关详细信息，请转至[CollectPII](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)。

要将PII数据发送到[!DNL Adobe Campaign Standard]，请在[!DNL Experience Platform Launch]中创建规则：

1. 在[!DNL Experience Platform Launch]中，从移动应用程序仪表板中，单击&#x200B;**[!UICONTROL Rules]**&#x200B;选项卡，然后单击&#x200B;**[!UICONTROL Create New Rule]**。

1. 键入名称，例如&#x200B;**Mobile Core - Collect PII**。

1. 在&#x200B;**[!UICONTROL Events]**&#x200B;部分，单击&#x200B;**[!UICONTROL Add]**。

1. 从&#x200B;**[!UICONTROL Extension]**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL Mobile Core]**。 然后，在&#x200B;**[!UICONTROL Event type]**&#x200B;下拉列表中显示&#x200B;**[!UICONTROL Collect PII]**。

1. 单击 **[!UICONTROL Keep changes]**.

1. 在&#x200B;**[!UICONTROL Actions]**&#x200B;部分，单击&#x200B;**[!UICONTROL Add]**。

1. 从&#x200B;**[!UICONTROL Extension]**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL Mobile Core]**。 然后，在&#x200B;**[!UICONTROL Action type]**&#x200B;下拉列表中显示&#x200B;**[!UICONTROL Send PII]**。

1. 在&#x200B;**[!UICONTROL URL]**&#x200B;中，输入以下URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. 选中&#x200B;**[!UICONTROL Add Post Body]**&#x200B;复选框。

1. 在&#x200B;**[!UICONTROL Post Body]**&#x200B;中，键入以下内容：

   ```
   {
   "marketingCloudId":
   "{%%mcid%%}",
   "cusEmail":
   "{%contextdata.email%}",
   "cusFirstName":
   "{%contextdata.firstName%}",
   "cusLastName":
   "{%contextdata.lastName%}" }
   ```

   marketingCloudId使您能够协调应用程序订阅者与收件人库中的，因此是必需的。 您可以根据业务需要指定其他键值对。 在上面的示例中，将从应用程序传递电子邮件、名字和姓氏。

   键（例如cusEmail、cusFirstName和cusLastName）应与在Adobe Campaign Standard实例的自定义资源中定义的字段ID匹配。 值变量（例如，email、firstName和LastName）应与从移动应用程序发送的JSON数据中的键匹配，同时从应用程序代码调用AMS collectPII API。

   您还可以根据事件触发器在Collect PII回传或其他回传中传递生命周期数据。 以下是生命周期数据JSON的示例：

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   [!DNL Experience Platform Launch]中定义的数据元素应以多次百分比（例如%mcid%%）括起来，应用程序的上下文变量应以单个百分比（例如%contextdata.email%）括起来。

1. 在&#x200B;**[!UICONTROL Content Type]**&#x200B;中，键入&#x200B;**application/json**。

1. 在&#x200B;**[!UICONTROL Timeout]**&#x200B;中，选择0。

   ![](assets/do-not-localize/rules_2.png)

您的用户数据现已配置为发送至活动。

### 应用程序内跟踪回传{#inapp-tracking-postback}

要向[!DNL Adobe Campaign Standard]发送跟踪数据，以报告用户如何与移动应用程序中的应用程序内消息交互，请在[!DNL Experience Platform Launch]中创建以下规则：

1. 在[!DNL Experience Platform Launch]中，从您的移动应用程序仪表板中，选择&#x200B;**[!UICONTROL Rules]**&#x200B;选项卡，然后单击&#x200B;**[!UICONTROL Add Rule]**。

1. 键入名称，例如&#x200B;**Adobe Campaign-应用程序内单击跟踪**。

1. 在&#x200B;**[!UICONTROL Events]**&#x200B;部分，单击&#x200B;**[!UICONTROL Add]**。

1. 从&#x200B;**[!UICONTROL Extension]**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL Adobe Campaign Standard]**。 然后，在&#x200B;**[!UICONTROL Event type]**&#x200B;下拉列表中显示&#x200B;**[!UICONTROL In-App click tracking]**。

1. 单击 **[!UICONTROL Keep changes]**.

1. 在&#x200B;**[!UICONTROL Actions]**&#x200B;部分，单击&#x200B;**[!UICONTROL Add]**。

1. 从&#x200B;**[!UICONTROL Extension]**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL Mobile Core]**。 然后，在&#x200B;**[!UICONTROL Event type]**&#x200B;下拉列表中显示&#x200B;**[!UICONTROL Send postback]**。

1. 在&#x200B;**[!UICONTROL URL]**&#x200B;中，键入以下URL:

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. 选中&#x200B;**[!UICONTROL Add post body]**&#x200B;复选框。

1. 在&#x200B;**[!UICONTROL Post Body]**&#x200B;中，键入&#x200B;**{}**。

1. 在&#x200B;**[!UICONTROL Content Type]**&#x200B;中，键入&#x200B;**application/json**。

1. 在&#x200B;**[!UICONTROL Timeout]**&#x200B;中，选择0。

   ![](assets/do-not-localize/rules_3.png)

### 推送通知跟踪回发{#push-tracking-postback}

要向[!DNL Adobe Campaign Standard]发送跟踪数据，以便跟踪推送通知投放和用户与移动应用程序的交互，您需要在[!DNL Experience Platform Launch]中创建规则。

有关推送跟踪的详细信息，请参阅[推送跟踪](../../administration/using/push-tracking.md)。

要跟踪应用程序操作，请使用trackAction API。 有关详细信息，请参阅[跟踪应用程序操作](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)。

1. 在[!DNL Experience Platform Launch]中，从移动应用程序仪表板中，单击&#x200B;**[!UICONTROL Rules]**&#x200B;选项卡，然后单击&#x200B;**[!UICONTROL Add Rule]**。

1. 键入名称，例如&#x200B;**Adobe Campaign-推送单击跟踪**。

1. 在&#x200B;**[!UICONTROL Events]**&#x200B;部分，单击&#x200B;**[!UICONTROL Add]**。

1. 从&#x200B;**[!UICONTROL Extension]**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL Mobile Core]**。 然后，在&#x200B;**[!UICONTROL Event type]**&#x200B;下拉列表中显示&#x200B;**[!UICONTROL Track Action]**。

1. 从&#x200B;**[!UICONTROL Action]**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL Action]**，选择&#x200B;**[!UICONTROL equals]**，然后键入&#x200B;**tracking**。

1. 单击 **[!UICONTROL Keep changes]**。然后，在&#x200B;**[!UICONTROL Actions]**&#x200B;部分，单击&#x200B;**[!UICONTROL Add]**。

1. 从&#x200B;**[!UICONTROL Extension]**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL Mobile Core]**。 然后，在&#x200B;**[!UICONTROL Action type]**&#x200B;下拉列表中显示&#x200B;**[!UICONTROL Send postback]**。

1. 在&#x200B;**[!UICONTROL URL]**&#x200B;中，输入以下URL:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. 选中&#x200B;**[!UICONTROL Add post body]**&#x200B;复选框。

1. 添加您的帖子正文，例如，{ }。

1. 在&#x200B;**[!UICONTROL Content Type]**&#x200B;中，键入&#x200B;**application/json**。

1. 在&#x200B;**[!UICONTROL Timeout]**&#x200B;中，选择0。

### 位置回传{#location-postback}

1. 在[!DNL Experience Platform Launch]中，从移动应用程序仪表板中，单击&#x200B;**[!UICONTROL Rules]**&#x200B;选项卡，然后单击&#x200B;**[!UICONTROL Add Rule]**。

1. 键入名称，例如&#x200B;**位置后退**。

1. 在&#x200B;**[!UICONTROL Events]**&#x200B;部分，单击&#x200B;**[!UICONTROL Add]**。

1. 创建事件，例如，输入POI或退出POI。 从&#x200B;**[!UICONTROL Extension]**&#x200B;下拉框中，选择&#x200B;**地点——测试版**。 然后，在&#x200B;**下拉框中输入POI**&#x200B;或&#x200B;**退出POI**。**[!UICONTROL Event type]**

1. 输入名称，例如，**Places - Beta - Enter POI**&#x200B;或&#x200B;**Exit POI**。

1. 在&#x200B;**[!UICONTROL Actions]**&#x200B;部分，单击&#x200B;**[!UICONTROL Add]**。

1. 从&#x200B;**[!UICONTROL Extension]**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL Mobile Core]**。 然后，从&#x200B;**[!UICONTROL Action type]**&#x200B;下拉框中选择&#x200B;**[!UICONTROL Send postback]**。

1. 输入名称，例如&#x200B;**Mobile Core - Send Location Postback**。

1. 在&#x200B;**[!UICONTROL URL]**&#x200B;中，输入以下URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. 选中&#x200B;**[!UICONTROL Add post body]**&#x200B;复选框并添加您的帖子正文，例如：

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
   >在上面的示例中，需要通过利用[创建数据元素](../../administration/using/configuring-rules-launch.md#create-data-elements)中的步骤在[!DNL Experience Platform Launch]中配置右侧的数据元素。 左侧的数据元素在[!DNL Adobe Campaign Standard]中受支持，不需要任何配置。 如果需要其他数据，您需要在[!DNL Adobe Campaign Standard]中执行自定义资源扩展。

1. 在&#x200B;**[!UICONTROL Content Type]**&#x200B;中，键入&#x200B;**application/json**。

1. 在&#x200B;**[!UICONTROL Timeout]**&#x200B;中，选择5。

   ![](assets/do-not-localize/rules_4.png)
