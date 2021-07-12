---
solution: Campaign Standard
product: campaign
title: 应用程序内常见问题解答
description: 有关应用程序内消息传送的常见问题解答
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: 应用程序内
role: User
exl-id: 986646b1-42d5-4169-ac38-d8e612a9a6d3
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 2%

---


# 应用程序内常见问题解答 {#in-app-faq}

## 要了解有关Adobe Campaign Standard中应用程序内渠道的更多信息，需要推荐哪些有用资源？ {#resources-inapp}

请查看以下资源：

* [视频教程](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/in-app/in-app-message-overview.html)
* [博客帖子](https://theblog.adobe.com/get-more-out-of-the-new-in-app-message-channel-from-adobe-campaign/)
* [社区页面](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

## 促销活动扩展API setLinkageField和resetLinkageField的用途是什么？ {#extensions-apis}

由于应用程序内消息是由SDK从Campaign中提取的，因此我们希望提供一种安全机制，以确保包含PII数据的应用程序内消息不会落入恶意人手中。 因此，我们已建立以下机制来确保将消息安全地传递到设备：

* 如果客户希望确保安全地交付此特定信息，则将移动配置文件字段（appSubscriberRcp表）字段标记为“个人”和“敏感”。
* 标记为的字段只能在内置其他安全机制的配置文件模板（不能在appSubscriber模板或广播模板中）中使用。
* 仅当用户已登录应用程序时，才能提供使用用户档案模板构建的消息。
* 为了便于进行这种安全握手，移动应用程序开发人员应使用setLinkageField API传递其他身份验证详细信息。 请注意，链接字段是在扩展appSubscriberRcp表时被标识为移动用户档案和CRM用户档案之间链接的字段。
* 当用户使用resetLinkageField注销应用程序时，它们应刷新存储在设备上的应用程序内消息和resetLinkagefields。 这可确保当其他用户登录到应用程序时，他们看不到适用于前一用户的消息。
* 请参阅[Mobile SDK API](Https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference)以实施此安全机制客户端。

## 要在Campaign中启用应用程序内报告，我必须做什么？ {#enable-inapp-reporting}

您需要配置应用程序内跟踪回发。 有关说明，请参见[此处](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#InApptrackingpostback)。

要实施本地通知跟踪，请参阅此[页面](../../administration/using/local-tracking.md)。

## 哪些报表可用于应用程序内渠道？ {#report-inapp}

Adobe Campaign中为应用程序内渠道提供了现成报表。 请参阅此[文档](../../reporting/using/in-app-report.md)。

请参阅此[页面](../../reporting/using/indicator-calculation.md#in-app-delivery)以了解如何计算每个应用程序内量度。

## 应用程序内内容的多语言内容变体是否支持与推送类似？ {#multilingual-inapp}

现在没有可用于应用程序内消息传送的多语言模板。

但是，如果目标是使用英语以外的语言发送应用程序内消息，则可以将内容直接粘贴到可用文本框中。

![](assets/faq_inapp.png)

## Campaign个性化字段是否可以添加到自定义HTML? {#custom-html-inapp}

否，尚不支持此功能。

## 我已配置了警报消息，但该消息未在设备上显示。 {#alert-message}

对于警报消息，至少需要一个关闭按钮（主或次应具有关闭操作）。 否则，可能会保存消息，但不会收到该消息。

## 如果本地通知iOS自定义声音不播放；默认声音会改为播放吗？ {#local-notification-sound}

对于iOS上的自定义声音，在创建本地通知（例如sound.caf）时，需要提供扩展名为的文件名。 如果未提供此扩展，则使用默认声音。

## 应用程序内消息是否支持深层链接？ {#inapp-deeplinks}

是，应用程序内消息支持深层链接。 深层链接应包括：

* 声明投放跟踪需要禁用才能使深层链接正常工作的语言。
* Appsflyer与Branch合作，共同执行深层链接跟踪。 有关分支和Adobe Campaign Standard集成的更多信息，请参阅此[页面](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1)。

## 当用户从推送通知中启动应用程序时，是否可以触发应用程序内消息？ {#inapp-push-trigger}

是的，这些消息也称为菊花链消息。 按照以下流程操作：

1. 创建应用程序内消息。

1. 定义自定义事件并将其选作此IAM的事件触发器，例如“秋季预览推送触发器”。

1. 在创作推送消息时，定义一个自定义变量，其值可设置为用于触发IAM的事件，例如Key = &quot;inappkey&quot;,value = &quot;Trigger from fall preview Push&quot;。

1. 在移动设备应用程序代码中，按如下方式实施事件触发器：

   ![](assets/faq_inapp_2.png)
