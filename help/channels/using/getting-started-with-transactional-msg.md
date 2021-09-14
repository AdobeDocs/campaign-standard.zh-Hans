---
title: 事务性消息传递入门
description: 了解什么是事务型消息传递，并了解在Adobe Campaign Standard中设置事务型消息的主要步骤。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Beginner
exl-id: 49fba1af-3c99-45b7-bcbb-b9b9678eedcd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '963'
ht-degree: 8%

---

# 事务性消息传递入门 {#getting-started-with-transactional-messaging}

## 概述 {#overview}

<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

事务型消息是由提供商（如网站）实时发送的个人通信和唯一通信。 特别需要，因为它包含收件人要检查或确认的重要信息。

* **什么时候到？** 由于此消息包含重要信息，因此用户希望该消息能够实时发送。因此，触发事件与收到消息之间的延迟必须非常短。

* **为什么这很重要？** 通常，事务型消息的打开率很高。因此，应当仔细设计它，因为它定义客户关系时会对客户行为产生重大影响。

* **例如？** 它可以是创建帐户后的欢迎消息、确认订单已发运的消息、发票、确认密码更改的消息或客户浏览您的网站后的通知等。

Adobe Campaign允许您将此功能与信息系统集成，该信息系统会发送要转换为自定义事务型消息的事件。

事务型消息可通过电子邮件、短信或[推送通知](../../channels/using/transactional-push-notifications.md)发送，具体取决于您的选项。 请核实您的许可协议。

>[!NOTE]
>
>Adobe Campaign优先处理事务型消息而不是任何其他投放。

<!--Guidelines to implement transactional messaging capabilities in your website are detailed in [this section](../../api/using/managing-transactional-messages.md).-->

在开始事务型消息传递之前，请确保阅读相应的[最佳实践和限制](../../channels/using/transactional-messaging-limitations.md)。

## 事务型消息传递工作原理 {#transactional-messaging-operating-principle}

事务型消息传递的整个过程可描述如下：

![](assets/message-center-process.png)

例如，假设您是一家拥有网站的公司，客户可以在该网站购买产品。

Adobe Campaign允许您向将产品添加到购物车的客户发送通知电子邮件。 如果其中某人离开您的网站但未完成购买（触发促销活动事件的外部事件），则会自动向他们发送购物车放弃电子邮件（事务型消息投放）。

[此部分](#key-steps)中详细介绍了实施此功能的主要步骤。

## 事务型消息类型 {#transactional-message-types}

Adobe Campaign中提供了两种类型的事务型消息。

**事件事** 务型消息集事件本身包含的数据。这些消息：
* 不包含用户档案信息，因此不能包含退订链接。
* 与疲劳规则不兼容（即使对于具有用户档案的扩充也是如此）。
* 由事件本身包含的数据定义其投放目标。

您可能希望向需要检索忘记的密码或确认订单的客户发送事件事务型消息。 事实上，您不希望收件人取消订阅此类通信，并且不应将此通知作为疲劳规则的一部分添加到营销消息的计数器中。

**Campaign营销数** 据库中的用户档案事务型消息目标用户档案。通过此类型的消息，您可以：
* 利用Adobe Campaign数据库中包含的数据。
* 通过向事件配置添加[扩充](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)，使用用户档案信息对消息进行个性化设置。
* 应用[营销分类规则](../../sending/using/managing-typology-rules.md)或[疲劳规则](../../sending/using/fatigue-rules.md)。
* 在消息中包含退订链接。
* 将事务型消息添加到全局投放报告。
* 在客户历程中使用事务型消息。

例如，在客户放弃购物车访问您的网站后联系客户时，您可以使用此类消息来鼓励他们继续购买。 这样，您就可以更轻松地将消息个性化，从用户档案数据库直接访问所有信息，应用营销规则，并将此消息包含到全球客户历程和报表中，以便更好地查看客户行为。

在配置要转换为事件的事务型消息时，就决定了消息的类型。请参阅[基于事件的事务型消息](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages)和[基于用户档案的事务型消息](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages)配置部分。

## 关键步骤 {#key-steps}

在Adobe Campaign中创建和管理个性化事务型消息时，主要步骤概述如下架构中。

![](assets/message-center-overview.png)

下面进一步详细介绍了这些步骤。

>[!IMPORTANT]
>
>只有具有[Administration](../../administration/using/users-management.md#functional-administrators)角色的用户才能配置事务事件和访问事务型消息。

### 第1步 — 创建和发布事件配置 {#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

| 用户 | 操作 | 结果 |
|--- |--- |--- |
| 此步骤必须由拥有[管理权限](../../administration/using/users-management.md#functional-administrators)的管理员执行。 | 配置将命名为“购物车放弃”的事件，并发布此事件配置。 | 部署网站开发人员将使用的API，并自动创建事务型消息。 |

创建和发布事件请参见[配置事务事件](../../channels/using/configuring-transactional-event.md)和[发布事务事件](../../channels/using/publishing-transactional-event.md)一节。

### 第2步 — 编辑和发布事务型消息 {#create-transactional-message}

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

| 用户 | 操作 | 结果 |
|--- |--- |--- |
| 此步骤可由拥有[管理权限](../../administration/using/users-management.md#functional-administrators)的营销用户执行。 | 编辑和个性化事务型消息，对其进行测试，然后发布。 | 事务型消息随后即可发送。 |

有关编辑和发布事务型消息的更多信息，请参阅[编辑事务型消息](../../channels/using/editing-transactional-message.md)和[事务型消息生命周期](../../channels/using/publishing-transactional-message.md)。

### 步骤3 — 集成事件触发 {#integrate-event-trigger}

<img src="assets/do-not-localize/icon_api.svg" width="55px">

<!--**Event triggering integration**-->

| 用户 | 操作 | 结果 |
|--- |--- |--- |
| 此步骤由您网站的开发人员执行。 | 使用REST事务型消息API将事件集成到您的网站中。 | 客户放弃购物车时将触发该事件。 |

创建事件后，您需要将此事件的触发集成到您的网站中。<!--In this example, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart.--> 要实现此目的，您的网站Web开发人员必须使 **用Adobe Campaign Standard REST API**。

有关使用Campaign REST API管理事务型消息的更多信息，请参阅[REST API文档](../../api/using/managing-transactional-messages.md)。

### 步骤4 — 消息投放 {#message-delivery}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

执行所有这些步骤后，即可发送消息。

用户离开网站且未在购物车中订购产品时，会立即触发相应的促销活动事件。 用户自动接收通知电子邮件。

## 相关主题

* [发送消息的关键步骤](../../channels/using/key-steps-to-send-a-message.md)
* [通信渠道入门](../../channels/using/get-started-communication-channels.md)
* [事务性推送通知](../../channels/using/transactional-push-notifications.md)
* [跟进消息](../../channels/using/follow-up-messages.md)
