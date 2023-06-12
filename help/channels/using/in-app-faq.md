---
title: 应用程序内常见问题解答
description: 有关应用程序内消息传送的常见问题解答
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: In App
role: User
exl-id: 0101773d-b109-49a3-89d4-b4bb226d9ebd
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 1%

---

# 应用程序内常见问题解答 {#in-app-faq}

## 要详细了解Adobe Campaign Standard中的应用程序内渠道，有哪些有用的资源推荐？ {#resources-inapp}

查看以下资源：

* [视频教程](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/in-app/in-app-message-overview.html)
* [博客帖子](https://theblog.adobe.com/get-more-out-of-the-new-in-app-message-channel-from-adobe-campaign/)
* [社区页面](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

## Campaign扩展API setLinkageField和resetLinkageField有何用途？ {#extensions-apis}

由于SDK会从Campaign中提取应用程序内消息，因此我们希望提供一种安全机制，以确保包含PII数据的应用程序内消息不会落入恶意用户手中。 因此，我们制定了以下机制来确保将消息安全地传递到设备：

* 如果客户希望确保安全地提交此特定信息，则他们会将移动配置文件字段（appSubscriberRcp表）字段标记为“个人”和“敏感”。
* 此类标记字段只能在具有内置附加安全机制的配置文件模板（不在appSubscriber模板或广播模板中）中使用。
* 仅当用户登录应用程序时，才能提供使用配置文件模板构建的消息。
* 为了促进此安全握手，移动应用程序开发人员应使用setLinkageField API传递其他身份验证详细信息。 请注意，关联字段是在扩展appSubscriberRcp表时标识为移动配置文件和CRM配置文件之间的链接字段。
* 当用户使用resetLinkageField注销应用程序时，他们应该刷新存储在设备上的应用程序内消息和resetLinkagefields 。 这可确保当其他用户登录到应用程序时，他们不会看到发送给之前用户的消息。
* 请参阅 [Mobile SDK API](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/) 实现此安全机制客户端。

## 在Campaign中启用应用程序内报告需要做什么？ {#enable-inapp-reporting}

您需要配置应用程序内跟踪回发。 可以找到说明 [此处](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback).

要实施本地通知跟踪，请参阅此 [页面](../../administration/using/local-tracking.md).

## 哪些报表适用于应用程序内渠道？ {#report-inapp}

Adobe Campaign中提供了用于应用程序内渠道的现成报表。 请参阅此 [文档](../../reporting/using/in-app-report.md).

查看此 [页面](../../reporting/using/indicator-calculation.md#in-app-delivery) 以了解每个应用程序内量度的计算方式。

## 是否支持与推送类似的应用程序内多语言内容变体？ {#multilingual-inapp}

目前没有可用于应用程序内消息传送的多语言模板。

但是，如果目标是以英语以外的语言发送应用程序内消息，则可以将内容直接粘贴到可用的文本框中。

![](assets/faq_inapp.png)

## 能否将Campaign个性化字段添加到自定义HTML？ {#custom-html-inapp}

否，尚不支持此操作。

## 我已配置警报消息，但该消息未显示在设备上。 {#alert-message}

对于警报消息，至少需要一个关闭按钮（主按钮或辅助按钮应具有操作关闭）。 否则，可以保存消息，但不会收到消息。

## 如果本地通知iOS自定义声音未播放；是否改为播放默认声音？ {#local-notification-sound}

对于iOS上的自定义声音，您需要在创建本地通知时提供扩展名为的文件名（例如sound.caf）。 如果未提供此扩展，则使用默认声音。

## 应用程序内消息是否支持深层链接？ {#inapp-deeplinks}

是，应用程序内消息支持深层链接。 深层链接应包括：

* 一种语言，说明需要禁用投放跟踪才能使深层链接正常工作。
* Appsflyer ，其中Branch是可执行深层链接跟踪的合作伙伴。 有关Branch与Adobe Campaign Standard集成的详细信息，请参阅此 [页面](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).

## 当用户从推送通知启动应用程序时，是否可以触发应用程序内消息？ {#inapp-push-trigger}

是的，这些消息也称为菊花链消息。 请遵循以下流程：

1. 创建应用程序内消息。

1. 定义一个自定义事件，并将其选为此IAM的事件触发器，例如“从秋季预览推送触发事件”。

1. 在创作推送消息时，请定义一个自定义变量，其值可以设置为用于触发IAM的事件，例如，键=“inappkey”和值=“从秋季预览推送触发”。

1. 在移动设备应用程序代码中，按如下方式实施事件触发器：

   ![](assets/faq_inapp_2.png)
