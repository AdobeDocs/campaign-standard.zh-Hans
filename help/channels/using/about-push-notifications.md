---
title: 关于推送通知
description: 了解Adobe Campaign中推送通知渠道的主要特性。
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
source-git-commit: 8111dfd2fd3cf254f73d0b01917d606b0a70aa84

---


# 关于推送通知{#about-push-notifications}

>[!CAUTION]
>
>推送通知实施必须由专家用户执行。 如果需要协助，请与您的Adobe客户主管或专业服务合作伙伴联系。 推送通知是可选功能。 请检查您的许可协议，并联系您的帐户管理员以激活它。

Adobe Campaign允许您向iOS和Android移动设备发送个性化的分段推送通知。

这些消息会在您通过利用Experience Platform SDK在Adobe Campaign中设置的移动应用程序上接收。 有关此功能的详细信息，请参 [阅使用Adobe Experience Platform SDK配置移动应用程序](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)。

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications&#39; subscribers.

需要扩展此资源以收集您打算从移动设备发送到Adobe Campaign的数据。 要执行此操作，请参阅本 [页](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) ，了解详细步骤。

Adobe Campaign中提供两种类型的推送通知：

* **[!UICONTROL Alert/Message/Badge]** 键入通知使您能够发送包含其他内容（声音、徽章、深层链接等）的基于文本的标准消息。在部分中定义的 **[!UICONTROL Advanced options]** 值。

   此通知类型允许您添加标题和消息，在其中可以使用个性化字段。 要能够个性化您的消息，请确保您选择了模 **[!UICONTROL Send push on profiles]** 板。

* **[!UICONTROL Silent push]** 类型通知用于无提示通知应用程序，不会向最终用户发送任何消息或内容。 此类消息的典型用例是使应用程序知道服务器上有可供下载的内容。

可以设置某些特定配置来定义通知行为。 如需详细信息，请参阅[此部分](../../channels/using/customizing-a-push-notification.md)。

作为专家用户，要定义这些特定配置，请参阅移动应用程序技 [术说明](https://helpx.adobe.com/campaign/kb/acs-article-list.html)。

>[!NOTE]
>
>有关隐私权的法律因国家／地区而异。 有些国家／地区要求您将移动应用程序收集的数据类型告知用户。 请查看您所在国家／地区与移动应用程序相关的法律。 确保发送到移动应用程序的推送通知符合Apple（Apple推送通知服务）和Google（Google Cloud Messaging或Firebase Cloud Messaging）指定的先决条件和条件。

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

1. 在Adobe Campaign中，确保可以访问该 **[!UICONTROL Push notification]** 渠道。 如果您无法访问这些渠道，请与您的帐户团队联系。

1. 验证您的用户是否具有Adobe Campaign标准版和体验平台启动中所需的权限。

1. 在Experience Platform Launch中，创建移动属性。 有关详细信息，请 [参阅设置移动属性](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)。

1. 在Experience Platform Launch中，安装该扩 **[!UICONTROL Adobe Campaign Standard]** 展。

1. 在Adobe Campaign标准版中，配置您在Experience Platform Launch中创建的移动属性。 有关详细信息，请参 [阅在Adobe Campaign中设置Experience Platform Launch应用程序](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeExperiencePlatformLaunchapplicationinAdobeCampaign)。

1. 将特定于渠道的配置添加到您的移动应用程序设置中。 有关详细信息，请参阅 [Adobe Campaign中特定于渠道的应用程序配置](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign)。

1. 要支持移动用例实施，请参阅有关使用Adobe Experience Platform SDK在Adobe Campaign标准中支持的扩展、Experience Platform Launch规则和移动用例中的SDK实施的详细说明 [](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)。