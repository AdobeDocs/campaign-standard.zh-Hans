---
solution: Campaign Standard
product: campaign
title: 设置事务性消息的主要步骤
description: 了解什么是交易消息，并了解在Adobe Campaign Standard建立事务性消息的主要步骤。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: 00032b1a8bfef301d1a87750695ba1670b2eed6c
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 17%

---


# 事务性消息传递入门 {#getting-started-with-transactional-messaging}

## 概述 {#overview}

### 什么是事务性消息?

它是由网站等提供商实时发送的个人和独特的通信。 特别需要，因为它包含收件人要检查或确认的重要信息。

* **什么时候到？** 由于此消息包含重要信息，因此用户希望实时发送该消息。因此，所触发的事件与到达的消息之间的延迟必须非常短。

* **为什么这很重要？** 一般而言，事务性消息的开放率很高。因此，它应该进行仔细的设计，因为它定义客户关系时会对客户行为产生强烈的影响。

* **比如说？** 它可能是创建帐户后的欢迎邮件、已发运订单的确认信、发票、确认密码更改的消息或客户浏览您的网站后的通知……

### 事务性消息发送

Adobe Campaign允许您将此功能与信息系统集成，该信息系统会发送要转换为自定义事务性消息的事件。

事务型消息可以通过电子邮件、短信或推送通知发送，具体取决于您的选择。请核实您的许可协议。

>[!NOTE]
>
>Adobe Campaign优先处理事务性消息，而不是任何其他投放。

Adobe Campaign Standard API 也可使用事务型消息传递。有关详细信息，请参阅[专用文档](../../api/using/managing-transactional-messages.md)。

>[!NOTE]
>
>现在，所有事务型消息都随 Adobe Campaign Enhanced MTA 一起发送，以提升投放能力、吞吐率和跳出处理能力。所有方面都与标准营销消息相同。有关更多信息，请参阅[此章节](../../administration/using/configuring-email-channel.md)。

### 事务性消息类型{#transactional-message-types}

Adobe Campaign 提供两类事务型消息：

**事件事** 务消息以事件为目标：
* 它们不包含用户档案信息。
* 它们与疲劳规则不兼容(即使是与用户档案扩充)。
* 投放目标由事件本身包含的数据定义。

**用户档案事务** 消息是针对活动营销数据库中的用户档案。通过此类消息，您可以：
* 应用[营销类型规则](../../sending/using/managing-typology-rules.md)或[疲劳规则](../../sending/using/fatigue-rules.md)。
* 在消息中包含退订链接。
* 将事务型消息添加到全局投放报告。
* 在客户历程中使用事务型消息。

在配置要转换为事件的事务型消息时，就决定了消息的类型。请参阅[此章节](../../channels/using/configuring-transactional-event.md#transactional-event-specific-configurations)。

>[!IMPORTANT]
>
>要访问所有事务性消息，您必须是&#x200B;**[!UICONTROL Administrators (all units)]**&#x200B;安全组的一部分。

## 事务型消息传递工作原理{#transactional-messaging-operating-principle}

事务消息传递整个过程可描述如下：

![](assets/message-center-process.png)

例如，假设您是公司，您的客户可以在网站上购买产品。

Adobe Campaign允许您向已将产品添加到购物车的客户发送通知电子邮件：当其中一人离开您的网站而未进行购买(外部事件触发活动事件)时，购物车废弃电子邮件会自动发送给他们(事务性消息投放)。

<!--The steps for putting this into place are detailed below.-->

### 关键步骤{#key-steps}

在Adobe Campaign中创建和管理个性化事务性消息的主要步骤概述在下表中。

![](assets/message-center-overview.png)

下面进一步详细介绍了这些步骤中的每个步骤。

### 第1步——创建并发布事件配置{#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

| 用户 | 操作 | 结果 |
|--- |--- |--- |
| 此步骤必须由具有[管理权限](../../administration/using/users-management.md#functional-administrators)的用户执行。 | 配置将命名为“购物车废弃”的事件并发布此事件配置。 | 将部署网站开发人员将使用的API并自动创建事务性消息。 |

在[配置事务事件](../../channels/using/configuring-transactional-event.md)和[发布事务事件](../../channels/using/publishing-transactional-event.md)部分中，将显示创建和发布事件。

### 第2步——编辑并发布事务性消息{#create-transactional-message}

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

| 用户 | 操作 | 结果 |
|--- |--- |--- |
| 此步骤可由具有[标准用户访问权限](../../administration/using/users-management.md#basic-users)的任何营销用户执行。 | 编辑和个性化事务性消息，测试它，然后发布它。 | 事务性消息即可发送。 |

有关编辑和发布事务性消息的详细信息，请参阅[编辑事务性消息](../../channels/using/editing-transactional-message.md)和[事务性消息生命周期](../../channels/using/publishing-transactional-message.md)。

### 第3步——集成触发{#integrate-event-trigger}的事件

<img src="assets/do-not-localize/icon_api.svg" width="55px">

<!--**Event triggering integration**-->

| 用户 | 操作 | 结果 |
|--- |--- |--- |
| 此步骤由网站的开发人员执行。 | 使用REST事务性消息API将事件集成到您的网站中。 | 事件将在客户端放弃其购物车时触发。 |

创建事件后，您需要将触发此事件的操作集成到您的网站中。<!--In this example, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart.--> 为此，您的网站Web开发人员必须使用 **Adobe Campaign StandardREST API**。

有关使用活动REST API管理事务性消息的详细信息，请参阅[REST API文档](../../api/using/managing-transactional-messages.md)。

### 第4步——消息投放{#message-delivery}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

执行所有这些步骤后，即可发送消息。

一旦用户离开网站而不订购其购物车中的产品，将触发相应的活动事件。 用户自动接收通知电子邮件。

## 相关主题

* [发送消息的关键步骤](../../channels/using/key-steps-to-send-a-message.md)
* [通信渠道入门](../../channels/using/get-started-communication-channels.md)
* [事务型推送通知](../../channels/using/transactional-push-notifications.md)
* [跟进消息](../../channels/using/follow-up-messages.md)
