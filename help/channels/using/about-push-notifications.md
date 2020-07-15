---
title: 关于推送通知
description: 发现Adobe Campaign中推送通知渠道的主要特性。
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f9632e88b49c2280c76e709376cfb7a7a27abc1f
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 2%

---


# 关于推送通知{#about-push-notifications}

>[!CAUTION]
>
>推送通知实施必须由专家用户执行。 如果您需要协助，请与您的Adobe客户经理或专业服务合作伙伴联系。 推送通知是可选功能。 请检查您的许可协议并联系您的帐户管理员以激活它。

Adobe Campaign允许您向iOS和Android移动设备发送个性化的分段推送通知。

这些消息在您通过利用Adobe CampaignSDK以Experience Platform设置的移动应用程序上接收。 有关此信息，请参阅使 [用Adobe Experience PlatformSDK配置移动应用程序](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)。

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications&#39; subscribers.

需要扩展此资源以收集您打算从移动设备发送到Adobe Campaign的数据。 要执行此操作，请参阅 [本页](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) ，了解详细步骤。

Adobe Campaign中提供两种类型的推送通知：

* **[!UICONTROL Alert/Message/Badge]** 类型通知允许您发送包含其他内容（声音、徽章、幻灯片等）的基于文本的标准消息。 在部分中定 **[!UICONTROL Advanced options]** 义。

   此通知类型允许您添加标题和消息，在其中可以使用个性化字段。 要能够个性化您的消息，请确保您选择了 **[!UICONTROL Send push on profiles]** 模板。

* **[!UICONTROL Silent push]** 类型通知用于无提示通知应用程序，不会向最终用户发送任何消息或内容。 此类消息的典型用例是让应用程序知道服务器上有可供下载的内容。

可以设置某些特定配置来定义通知行为。 如需详细信息，请参阅[此部分](../../channels/using/customizing-a-push-notification.md)。

作为专家用户，要定义这些特定配置，请参阅移动应用程序 [技术说明](https://helpx.adobe.com/campaign/kb/acs-article-list.html)。

>[!NOTE]
>
>有关隐私的法律因国家而异。 有些国家／地区要求您向用户通知移动应用程序收集的数据类型。 请查看您所在国家／地区与移动应用程序相关的法律。 确保发送到移动应用程序的推送通知符合Apple（Apple推送通知服务）和Google（Google Cloud Messaging或Firebase Cloud Messaging）指定的先决条件和条件。

**相关内容：**

* [准备和发送推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)
* [创建多语言推送通知](../../channels/using/creating-a-multilingual-push-notification.md)
* [推送通知报告](../../reporting/using/push-notification-report.md)
* [Campaign Standard移动指南](https://helpx.adobe.com/campaign/kb/acs-mobile.html)

## 先决条件 {#prerequisites}

>[!NOTE]
>要利用活动的推送通知功能，您需要提供。pem格式的有效推送证书，且无密码。
如果您有有效的p12证书，则可以使用联机资源将其轻松转换为。pem文件。

在发送推送通知之前，您应：

1. 在Adobe Campaign中，确保可以访问 **[!UICONTROL Push notification]** 渠道。 如果您无法访问这些渠道，请与您的帐户团队联系。

1. 验证您的用户是否具有Adobe Campaign Standard和Experience Platform Launch中的必要权限。

1. 在Experience Platform Launch中，创建移动属性。 有关详细信息，请 [参阅设置移动属性](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)。

1. 在Experience Platform Launch中，安装 **[!UICONTROL Adobe Campaign Standard]** 扩展。

1. 在Adobe Campaign Standard中，配置您在Experience Platform Launch中创建的移动设备属性。 有关详细信息，请参 [阅在Adobe Campaign中设置Experience Platform Launch应用程序](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeExperiencePlatformLaunchapplicationinAdobeCampaign)。

1. 将特定于渠道的配置添加到您的移动应用程序设置中。 有关详细信息，请参 [阅Adobe Campaign中特定于渠道的应用程序配置](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)。

1. 要支持移动用例实施，请参阅有关使用Experience Platform LaunchSDK在移动用例中支持的扩展、Adobe Experience Platform [规则和SDK实施的详细说明，这些SDK在Adobe Campaign Standard中受支持](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)。

## 推送通知常见问题解答 {#push-faq}

### 一些有用的资源建议是什么来进一步了解推送渠道? {#resource-push}

查看以下资源：

* [视频教程](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/mobile/push/creating-a-push-notification.html)
* [产品文档](../../channels/using/about-push-notifications.md)
* 使用AEP SDK文档进行 [配置](../../administration/using/configuring-a-mobile-application.md)
* [社区页](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

### 我必须做什么才能获得活动中的推送令牌？ {#push-token-acquisition}

确保供应团队已在Adobe Campaign Standard中完成推送渠道的供应。 从SDK实施setPushIdentifier API。 For more on this, refer to this [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#set-up-push-messaging).

### 将推送令牌和ECID活动后，我还需要发送推送通知吗？ {#sending-push}

客户需要提供。pem格式的有效推送证书才能发送推送通知。 您不需要此证书的口令。

### 如果我有。p12证书而不是。pem证书怎么办？ {#certificates}

通过在终端中运行以下命令，可以将。p12证书转换为。pem证书。 还提供几个在线资源，用于转换说明。

```
openssl pkcs12 -in pushcert.p12 -out pushcert.pem -nodes -clcerts
```

### 如何确定证书上传是否成功？ {#certificate-upload}

您将看到以下消息。

![](assets/faq_2.png)

### 我是否可以同时为iOS应用程序上传生产和沙箱证书（对于Android，为N/A）? {#prod-sandbox-certificate}

否，应用程序在沙箱或生产模式下工作，一旦设置，将无法更改到其他模式（即沙箱到生产应用程序）。 建议您先在沙箱模式下测试应用程序，然后过渡到生产模式。

要更改为生产模式，您必须创建其他应用程序。 另外，请务必不要选中沙箱复选框并上传生产证书。

### 我是否可以同时上传iOS和Android凭据？ {#ios-android-credentials}

是的，活动同时支持两个平台，并允许您上传两个平台的凭据。

### 我已成功上传推送证书，但未发送推送消息。 {#push-certificates-upload}

请通过此处测试您的推送证书，确保它们 [有效](https://pushtry.com/)。

### 我可以从pushtry.com成功发送推送通知，但不能通过活动。 {#push-not-sending}

请确保遵循此处提供的推送有效负荷 [说明](../../administration/using/push-payload.md)。

请注意，对于Android,活动仅支持数据有效负荷，不支持通知有效负荷

### 我已在Adobe Campaign Standard的“管理”部分配置了应用程序，但移动应用程序在投放属性中不可用。 {#mobile-app-unavailable}

应用程序还必须上传有效的推送证书，才能在投放属性中使用它。

### 我已尝试了此页上的所有说明，但无法从活动发送推送。 {#push-troubleshoot}

请打开客服票。

### 推送通知从活动传送，但媒体文件未显示。{#media-file-unavailable}

移动应用程序开发人员需要处理应用程序中媒体文件的支持。 有时，网络带宽也可能阻止媒体文件渲染。 有关其他指 [针](../../administration/using/image-push-notification.md) ，请参阅此页。

### 我必须做什么才能启用活动中的推送报告? {#push-reporting-enable}

按照以下步骤操作：

* 配置推送跟踪回发。 此处可找到说 [明](../../administration/using/configuring-a-mobile-application.md)。
* 从Mobile Core实施trackAction API。 Refer to this [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference) for more information.

有关更多详细说明，请参阅本 [页](../../administration/using/push-tracking.md)。

### 哪些报告可用于推送渠道? {#push-report-available}

现成报告以Adobe Campaign形式提供，用于推送渠道。 请参阅此 [文档](../../reporting/using/push-notification-report.md)。

请参阅 [本页](../../reporting/using/indicator-calculation.md#push-notification-delivery) ，了解如何计算每个推送量度。

### 推送和应用程序内消息中是否支持深层链接？ {#deeplink-push}

是，推送消息中支持深层链接。 深层链接应包括：

* 一种语言，该语言规定需要禁用投放跟踪才能使开发人员工作。
* Appsflyer与Branch合作，可进行开发跟踪。 有关分支和Adobe Campaign Standard集成的详细信息，请参阅 [本页](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1)。