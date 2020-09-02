---
title: 设置事务性消息的主要步骤
description: 了解什么是交易消息，并了解在Adobe Campaign Standard建立事务性消息的主要步骤。
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 07adae5bac947df794520e48361fd3c20eba5ff8
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 27%

---


# 交易消息快速入门 {#getting-started-with-transactional-messaging}

## 概述


<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

<table>
<tr>
<td ><br><p>交易消息使您能够 <b>实时向客户发送</b> 个人和独特的消息。</p></td>
<td>它可以是欢迎邮件、订单发运确认、密码修改等。</td>
</tr>
</table>

Adobe Campaign允许您将此功能与信息系统集成，该信息系统会发送要转换为自定义事务性消息的事件。

>[!NOTE]
>
>事务型消息可以通过电子邮件、短信或推送通知发送，具体取决于您的选择。请核实您的许可协议。

Adobe Campaign优先处理事务性消息，而不是任何其他投放。

Adobe Campaign Standard API 也可使用事务型消息传递。有关更多信息，请参阅[专用文档](../../api/using/managing-transactional-messages.md)。

>[!NOTE]
>
>现在，所有事务型消息都随 Adobe Campaign Enhanced MTA 一起发送，以提升投放能力、吞吐率和跳出处理能力。所有方面都与标准营销消息相同。有关更多信息，请参阅[此章节](../../administration/using/configuring-email-channel.md)。

## 事务消息定义 {#transactional-messaging-definition}

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_concepts.svg" width="60px"><br><p><b>什么是事务性消息?</b></p></td>
<td><p>它是由提供商（如网站）发送的个人和唯一通信。</p></td>
<td><p>特别需要，因为它包含收件人要检查或确认的重要信息。</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_channels.svg" width="60px"><br><p><b>什么时候到？</b></p></td>
<td><p> 由于此消息包含重要信息，因此用户希望实时发送该消息。</p></td>
<td><p>因此，所触发的事件与到达的消息之间的延迟必须非常短。</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_important.svg" width="60px"><br><p><b>为什么这很重要？</b></p></td>
<td><p>一般而言，事务性消息的开放率很高。 因此，它应当精心设计。</p></td>
<td><p>事实上，当它定义客户关系时，它会对客户行为产生强烈影响。</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_example.svg" width="60px"><br><p><b>比如说？</b></p></td>
<td><p>它可能是创建帐户后的欢迎消息、已发运订单的确认、发票……</p></td>
<td><p>它也可以是确认密码更改的消息，或者客户浏览您的网站后的通知……</p></td>
</tr>
</table>

## 事务性消息类型

Adobe Campaign 提供两类事务型消息：

<!--[Event transactional messages](../../channels/using/event-transactional-messages.md) targeting an **event**. The data contained in the event itself is used to define the delivery target.-->

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_event.svg" width="60px"><br><p><a href="../../channels/using/event-transactional-messages.md">事件事</a><br>务消息化 <b>事件</b></p></td>
<td><p><ul><li>它们不包含用户档案信息。</li><li>它们与疲劳规 <a href="../../sending/using/fatigue-rules.md">则不兼容</a> (即使是与用户档案扩充)。</li><li>投放目标由事件本身包含的数据定义。</li></ul></p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_profile.svg" width="60px"><br><p><a href="../../channels/using/profile-transactional-messages.md">用户档案事</a><br>务性消息 <b>从Adobe Campaign营销数据库获取用户档案</b></p></td>
<td><p>用户档案事务性消息允许您：<ul><li>应用营销类型规则，如 <b>阻止列表或疲劳规</b> 则 <a href="../../sending/using/fatigue-rules.md">的地址</a>。</li><li>在消息中包含退订链接。</li><li>将事务型消息添加到全局投放报告。</li><li>在客户历程中使用事务型消息。</li></ul></p></td>
</tr>
</table>

<!--[Profile transactional messages](../../channels/using/profile-transactional-messages.md) targeting **profiles from the Adobe Campaign marketing database**. You can use information from the Adobe Campaign database to send a transactional message based on customer marketing profiles.-->

在配置要转换为事件的事务型消息时，就决定了消息的类型。请参阅[事务型消息传递配置](../../administration/using/configuring-transactional-messaging.md)。

>[!IMPORTANT]
>
>To access all transactional messages, you must be part of the **[!UICONTROL Administrators (all units)]** security group.

<!--Event transactional messages do not contain profile information, therefore they are not compatible with fatigue rules (even in the case of an enrichment with profiles). However, profile transactional messages are compatible. For more on fatigue rules, see [this section](../../sending/using/fatigue-rules.md#choosing-the-channel).-->

## 事务型消息传递工作原理{#transactional-messaging-operating-principle}

让我们举一个公司的例子，它有一个网站，在这个网站上，客户可以购买产品。

利用 Adobe Campaign，可向购物车中添加了产品的网站用户发送通知电子邮件：如果此类用户离开网站且未完成购买，则会自动向他们发送“购物车放弃”电子邮件。

将其投入使用的步骤如下。

### 第1步——创建和发布事件配置 {#create-event-configuration}

<!--<img src="assets/do-not-localize/icon_config.svg" width="60px">

Configure an event that will be named "Cart abandonment" and publish this event configuration.

The API that will be used by your website developer is deployed and a transactional message is automatically created.-->

<img src="assets/do-not-localize/icon_config.svg" width="60px">

<table>
<tr>
<td><br><p>配置将命名为“购物车废弃”的事件并发布此事件配置。</p></td>
<td>将部署网站开发人员将使用的API并自动创建事务性消息。</td>
</tr>
</table>

创建和发布事件，可参阅[配置事件以发送事件事务型消息](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message)一节。

### 第2步——编辑和发布事务性消息 {#create-transactional-message}

<!--<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

Edit and personalize the transactional message, test it, and then publish it.-->

<img src="assets/do-not-localize/icon_notification.svg" width="45px">

<table>
<tr>
<td><br><p>编辑和个性化事务性消息，测试它，然后发布它。</p></td>
<td>事务性消息将随时可以发送。</td>
</tr>
</table>

For more on editing and publishing a transactional message, see [Event transactional messages](../../channels/using/event-transactional-messages.md).

### 第3步——集成事件触发 {#integrate-event-trigger}

<!--<img src="assets/do-not-localize/icon_api.svg" width="60px">

Use the REST Transactional Messages API to integrate the event into your website.

The event will be triggered when a client abandons their cart.-->

<img src="assets/do-not-localize/icon_api.svg" width="60px">

<table>
<tr>
<td><br><p>使用REST事务性消息API将事件集成到您的网站中。</p></td>
<td>事件将在客户端放弃其购物车时触发。</td>
</tr>
</table>

有关将事件集成到网站的更多信息，请参阅 [网站集成](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

### 第4步——消息投放 {#message-delivery}

<!--Once all of these steps have been carried out, the message can be delivered:

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

As soon as a user leaves the site without ordering the products in their cart, they automatically receive a notification email.-->

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

<table>
<tr>
<td><br><p>执行所有这些步骤后，即可发送消息。</p></td>
<td>一旦用户离开网站而不订购购物车中的产品，他们就会自动收到通知电子邮件。</td>
</tr>
</table>

## 关键步骤 {#key-steps}

在Adobe Campaign中创建和管理个性化事务性消息的主要步骤概述在下表中。

![](assets/message-center-overview.png)

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the whole transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on the event configuration steps, see [Transactional messaging configuration](../../administration/using/configuring-transactional-messaging.md).

Read more:

* [About transactional messaging](../../channels/using/about-transactional-messaging.md)
* [Event transactional messages](../../channels/using/event-transactional-messages.md)
* [Profile transactional messages](../../channels/using/profile-transactional-messages.md)
* [Transactional push notifications](../../channels/using/transactional-push-notifications.md)
* [Follow-up messages](../../channels/using/follow-up-messages.md)-->

**相关主题：**

* [发送消息的关键步骤](../../channels/using/key-steps-to-send-a-message.md)
* [通信渠道快速入门](../../channels/using/get-started-communication-channels.md)