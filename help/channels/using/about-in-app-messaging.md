---
solution: Campaign Standard
product: campaign
title: 关于应用程序内消息传递
description: 在具有应用程序内消息传递功能的移动应用程序中，显示消息或警报。
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 29%

---


# 关于应用程序内消息传递{#about-in-app-messaging}

利用应用程序内消息传递渠道，可向移动应用程序中的活动用户发送消息。这种消息类型可免费将通知推送到用户手机的通知中心。有关推送通知渠道的更多信息，请参阅此[章节](../../channels/using/about-push-notifications.md)。

此渠道要求将移动应用程序与 Adobe Experience Platform SDK 集成。这些应用程序必须先在 Adobe Experience Platform Launch 中激活，然后才能在 Adobe Campaign 中用于应用程序内投放。

![](assets/launch_campaign.png)

要在应用 Experience Platform SDK 的移动应用程序上发送应用程序内消息，您首先需要满足以下先决条件：

1. 在 Adobe Campaign 中，确保可以访问 **[!UICONTROL In-App]** 渠道。如果您无法访问这些渠道，请与帐户管理团队联系。

1. 要在 Adobe Campaign Standard 中使用与 Experience Cloud SDK 应用程序集成的移动使用案例，必须在 Adobe Experience Platform Launch 中创建移动应用，并在 Adobe Campaign Standard 中对其进行配置。有关分步指南，请参阅此[页面](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdk.html)。

1. 配置完毕后，您即可准备应用程序内消息。有关更多信息，请参见此[页面](../../channels/using/preparing-and-sending-an-in-app-message.md#preparing-your-in-app-message)。

1. 然后，您可以决定是发送[应用程序内消息](../../channels/using/customizing-an-in-app-message.md)还是[自定义本地通知消息类型](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)。

1. 您的投放现已准备就绪，可供发送。要了解更多信息，请参阅此[页面](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)。

**相关内容：**

* [应用程序内报告](../../reporting/using/in-app-report.md)
* [Adobe Campaign Standard 中支持的移动使用案例](https://helpx.adobe.com/cn/campaign/kb/configure-launch-rules-acs-use-cases.html)
* [Campaign Standard Mobile 指南](https://helpx.adobe.com/cn/campaign/kb/acs-mobile.html)

## 应用程序内常见问题解答{#in-app-faq}

### 要进一步了解Adobe Campaign Standard中的应用程序内渠道，有哪些有用的资源建议？{#resources-inapp}

查看以下资源：

* [视频Tutorials](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/mobile/in-app/in-app-message-overview.html)
* [博客文章](https://theblog.adobe.com/get-more-out-of-the-new-in-app-message-channel-from-adobe-campaign/)
* [社区页](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

### 活动扩展APIs setLinkageField和resetLinkageField的用途是什么？{#extensions-apis}

由于应用程序内消息是SDK从活动中提取的，因此我们希望提供一种安全机制，以确保包含PII数据的应用程序内消息不会落入恶意人手中。 因此，我们具有以下机制来确保消息安全地投放到设备：

* 如果客户希望确保安全地传递此特定信息，则将移动用户档案字段（appSubscriberRcp表）字段标记为“个人”和“敏感”。
* 标记为此类的字段只能用于内置其他安全机制的用户档案模板（不能在appSubscriber模板或广播模板中）。
* 仅当用户已登录应用程序时，才能提供使用用户档案模板生成的消息。
* 为了便于这种安全握手，移动应用程序开发人员应使用setLinkageField API传递其他身份验证详细信息。 请注意，链接字段是在扩展appSubscriberRcp表时标识为Mobile 用户档案和CRM用户档案之间的链接的字段。
* 当用户使用resetLinkageField注销应用程序时，他们应刷新存储在设备上的应用程序内消息和resetLinkagefield。 这可确保当其他用户登录到应用程序时，他们看不到针对前一用户的消息。
* 要实现此安全机制客户端，请参阅[Mobile SDK API](Https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference)。

### 要在活动中启用应用程序内报告，我必须做什么？{#enable-inapp-reporting}

您需要配置应用程序内跟踪回发。 可以在[此处](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#InApptrackingpostback)找到说明。

要实现本地通知跟踪，请参阅此[页](../../administration/using/local-tracking.md)。

### 哪些报表可用于应用程序内渠道?{#report-inapp}

Adobe Campaign中提供现成报告，用于应用程序内渠道。 请参阅此[文档](../../reporting/using/in-app-report.md)。

请参阅此[页](../../reporting/using/indicator-calculation.md#in-app-delivery)以了解如何计算每个应用程序内量度。

### 您是否支持与推送类似的应用程序内多语言内容变体？{#multilingual-inapp}

现在，应用程序内消息传递没有可用的多语言模板。

但是，如果目标是以非英语语言发送应用程序内消息，则内容可以直接粘贴到可用文本框中。

![](assets/faq_inapp.png)

### 是否可以将活动个性化字段添加到自定义HTML?{#custom-html-inapp}

否，尚不支持此功能。

### 我已配置了警报消息，但该消息不显示在设备上。{#alert-message}

对于警报消息，至少需要一个“取消”按钮（主或次应具有操作“取消”）。 否则，可以保存消息，但不会接收消息。

### 如果本地通知iOS自定义声音不播放；默认声音将改为播放吗？{#local-notification-sound}

对于iOS上的自定义声音，您需要在创建本地通知（例如sound.caf）时提供带扩展名的文件名。 如果未提供此扩展，则使用默认声音。

### 应用程序内消息中是否支持深层链接？{#inapp-deeplinks}

是，应用程序内消息支持深层链接。 深层链接应包括：

* 一种语言，该语言指明需要禁用投放跟踪才能使开发人员工作。
* Appsflyer与Branch合作，可以进行开发跟踪。 有关分支和Adobe Campaign Standard集成的详细信息，请参阅此[页面](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1)。

### 当用户从推送通知中启动应用程序时，是否可以触发应用程序内消息？{#inapp-push-trigger}

是的，这些消息也称为菊花链消息。 按照以下流程操作：

1. 创建应用程序内消息。

1. 定义自定义事件并将其选作此IAM的事件触发器，例如“从摔倒预览推送触发”。

1. 在创作推送消息时，请定义一个自定义变量，其值可设置为用于触发IAM的事件，例如Key = &quot;inappkey&quot;,value = &quot;Trigger from fall 预览 Push&quot;。

1. 在移动应用代码中，按如下方式实施事件触发器：

   ![](assets/faq_inapp_2.png)
