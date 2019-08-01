---
title: 关于应用程序内消息传递
seo-title: 关于应用程序内消息传递
description: 关于应用程序内消息传递
seo-description: 使用应用程序内消息传递在移动应用程序中显示消息或警告。
page-status-flag: 从未激活
uuid: 6784dfc-6db9-41dd-9fbb-2e756a5bcb5f
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: 应用程序内消息传递
discoiquuid: A4168bdf-22bf-4ab3-b9 d8-6e76 e116 e1 bdc055
context-tags: 交付，触发器，返回
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 74f037ba618639ab61edfb8311adeb44a7a99ebd

---


# About In-App messaging{#about-in-app-messaging}

应用程序内消息传递是一个消息通道，它允许您在用户在移动应用程序中处于活动状态时显示消息。此消息类型免费推送到用户手机通知中心的推送通知。For more information on the push notification channel, refer to this [section](../../channels/using/about-push-notifications.md).

此渠道需要将移动应用程序与Adobe Experience Platform SDK集成。这些应用程序必须在Adobe Experience Platform Launch中激活，然后才能在Adobe Campaign中用于应用程序内交付。

![](assets/launch_campaign.png)

要在利用Experience Platform SDK的移动应用程序上开始发送应用程序内消息，您需要满足以下先决条件：

1. In Adobe Campaign, make sure you can access the **[!UICONTROL In-App]** channel. 如果您无法访问这些渠道，请与您的帐户团队联系。
1. 在Experience Platform Launch中，创建移动应用程序并使用Experience Platform SDK创建移动应用程序，创建移动应用程序。

   For more information, refer to the [Set up a mobile property](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property) section in Adobe Launch documentation.

1. In Experience Platform Launch, install the **[!UICONTROL Adobe Campaign Standard]** extension for your mobile application in Experience Platform Launch:

   For more on extensions, refer to the [Configure Campaign Standard Extension in Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) in Experience Platform Launch documentation.

1. In Experience Platform Launch, configure rules and data elements for your application, see [Configuring your application in Experience Platform Launch](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)

1. Configure your Experience Platform Launch application in Adobe Campaign Standard, see [Setting up your Experience Platform Launch application in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign) .

To learn how to configure Experience Platform SDKs, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

**相关内容：**

* [准备和发送应用程序内消息](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [自定义应用程序内消息](../../channels/using/customizing-an-in-app-message.md)
* [自定义本地通知消息类型](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)
* [在工作流中发送应用程序内消息](../../automating/using/in-app-delivery.md)
* [推送和应用程序内常见问题解答](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)