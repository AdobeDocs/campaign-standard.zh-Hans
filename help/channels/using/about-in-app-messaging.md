---
title: 关于应用程序内消息传递
seo-title: 关于应用程序内消息传递
description: 关于应用程序内消息传递
seo-description: 在手机应用程序内显示消息或警报，并显示应用程序内消息。
page-status-flag: 从未激活
uuid: 6784cdfc-6db9-41dd-9fbb-2e756a5bcb5f
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 频道
content-type: 参考
topic-tags: 应用程序内消息传递
discoiquuid: a4168cfb-22bf-4ab3-b9d8-6e76e1bdc055
context-tags: 交付，触发器，返回
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 96001355220a9dd0cd3851d3f7de9f4dc8ea2782

---


# 关于应用程序内消息传递{#about-in-app-messaging}

应用程序内消息传递是一个消息传递渠道，当用户在移动应用程序中处于活动状态时，它允许您显示消息。 此消息类型对于发送到用户电话的通知中心的推送通知是免费的。 有关推送通知渠道的详细信息，请参阅此 [部分](../../channels/using/about-push-notifications.md)。

此渠道要求将移动应用程序与Adobe Experience Platform SDK集成。 这些应用程序必须先在Adobe Experience Platform Launch中激活，然后才能在Adobe Campaign中用于应用程序内交付。

![](assets/launch_campaign.png)

要开始在利用Experience Platform SDK的移动应用程序上发送应用程序内消息，您需要满足以下先决条件：

1. 在Adobe Campaign中，确保您可以访问该 **[!UICONTROL In-App]** 渠道。 如果您无法访问这些渠道，请与您的帐户团队联系。

1. 要将Adobe Campaign standard中的移动用例与Experience Cloud SDK应用程序结合使用，必须在Adobe Experience Platform Launch中创建移动应用程序，并在Adobe Campaign standard中进行配置。 有关分步指南，请参阅此 [页](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)。

1. 配置完成后，您现在可以准备应用程序内消息。 For more on this, refer to this [page](../../channels/using/preparing-and-sending-an-in-app-message.md#preparing-your-in-app-message).

1. 然后，您可以决定发送应 [用程序内消息](../../channels/using/customizing-an-in-app-message.md) ，或自定 [义本地通知消息类型](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)。

1. 您的送货现已准备好发送。 要了解更多信息，请参阅此 [页](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)。

**相关内容：**

* [应用程序内报告](../../reporting/using/in-app-report.md)
* [推送和应用程序内常见问题解答](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)
* [Adobe Campaign standard中支持的移动使用案例](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)
