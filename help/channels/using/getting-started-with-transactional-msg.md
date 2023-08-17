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
source-git-commit: 0e486e87c94e273442de23d6eb65c99f065e5a71
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 9%

---

# 事务性消息传递入门 {#getting-started-with-transactional-messaging}

事务型消息是由提供程序（如网站）实时发送的单个且唯一的通信。 由于它包含收件人要检查或确认的重要信息，因此尤其需要使用。

* **什么时候到期？** 由于此消息包含重要信息，因此用户希望实时发送该消息。 因此，触发的事件与收到消息之间的延迟必须非常短。

* **为什么这很重要？** 通常，事务型消息的打开率较高。 因此，应仔细设计，因为它在定义客户关系时可能会对客户行为产生强烈的影响。

* **例如？** 它可能是创建帐户后的欢迎消息、确认订单已发运的消息、发票、确认密码更改的消息或客户浏览您的网站后的通知等。

Adobe Campaign允许您将此功能与信息系统集成，该信息系统发送要转换为自定义事务型消息的事件。

事务型消息可以通过电子邮件、短信或电子邮件发送。 [推送通知](../../channels/using/transactional-push-notifications.md)，具体取决于您的选择。 请核实您的许可协议。

>[!NOTE]
>
>Adobe Campaign会优先处理事务型消息，而不是任何其他投放。

<!--Guidelines to implement transactional messaging capabilities in your website are detailed in [this section](../../api/using/managing-transactional-messages.md).-->

开始使用事务型消息之前，请确保已阅读相应的 [最佳实践和限制](../../channels/using/transactional-messaging-limitations.md).

## 事务型消息传递工作原理 {#transactional-messaging-operating-principle}

事务型消息传递的总体过程可描述如下：

![](assets/message-center-process.png)

例如，假设您是一家设有网站的公司，您的客户可以在其中购买产品。

Adobe Campaign允许您向将产品添加到购物车的客户发送通知电子邮件。 当其中某个访客离开您的网站而未完成购买（触发营销活动事件的外部事件）时，会自动向他们发送购物车放弃电子邮件（事务性消息投放）。

要实现该目标，主要步骤详见以下内容： [本节](#key-steps).

## 事务性消息类型 {#transactional-message-types}

Adobe Campaign提供两种类型的事务型消息。

**事件事务型消息** 事件本身中包含的目标数据。 这些消息：
* 不包含配置文件信息，因此无法包含退订链接。
* 与疲劳规则不兼容（即使在用户档案扩充的情况下也是如此）。
* 根据事件本身包含的数据定义其投放目标。

例如，您可能需要向需要检索忘记密码或确认订单的客户发送事件事务型消息。 事实上，您不希望收件人取消订阅此类通信，并且不应将此通知作为疲劳规则的一部分添加到营销消息柜台。

**用户档案事务型消息** 从Campaign营销数据库定位用户档案。 对于此类消息，您可以：
* 利用Adobe Campaign数据库中包含的数据。
* 通过添加用户档案信息，个性化您的消息 [扩充](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) 到事件配置。
* 应用 [营销类型规则](../../sending/using/managing-typology-rules.md) 或 [疲劳规则](../../sending/using/fatigue-rules.md).
* 在消息中包含退订链接。
* 将事务型消息添加到全局投放报告。
* 在客户历程中使用事务型消息。

例如，您可以在客户在您的网站上放弃购物车后联系客户时使用此类型的消息，以鼓励他们继续购买。 这样，您就可以更轻松地通过直接访问用户档案数据库中的所有信息来个性化消息、应用营销规则并将此消息包含到全局客户历程和报告中，以便更好地查看客户行为。

在配置要转换为事件的事务型消息时，就决定了消息的类型。请参阅 [基于事件的事务型消息](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages) 和 [基于用户档案的事务型消息](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages) 配置部分。

## 关键步骤 {#key-steps}

以下架构概述了在Adobe Campaign中创建和管理个性化事务型消息的主要步骤。

![](assets/message-center-overview.png)

下面将进一步详细介绍每个步骤。

>[!IMPORTANT]
>
>仅限具有下列属性的用户： [管理](../../administration/using/users-management.md#functional-administrators) 角色可以配置事务性事件并访问事务性消息。

### 步骤1 — 创建和发布事件配置 {#create-event-configuration}

<!--<img src="assets/do-not-localize/icon_config.svg" width="60px">-->

| 创建事件 | 用户 | 操作 | 结果 |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_config.svg" width="60px"> | 此步骤必须由具有以下权限的管理员执行 [管理权限](../../administration/using/users-management.md#functional-administrators). | 配置将命名为“购物车放弃”的事件，并发布此事件配置。 | 将部署您的网站开发人员使用的API，并自动创建事务型消息。 |

创建和发布事件可参见 [配置事务性事件](../../channels/using/configuring-transactional-event.md) 和 [发布事务性事件](../../channels/using/publishing-transactional-event.md) 部分。

### 步骤2 — 编辑和发布事务型消息 {#create-transactional-message}

<!--<img src="assets/do-not-localize/icon_notification.svg" width="40px">-->

| 编辑消息 | 用户 | 操作 | 结果 |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_notification.svg" width="40px"> | 此步骤可由具有以下权限的营销用户执行： [管理权限](../../administration/using/users-management.md#functional-administrators). | 编辑并个性化事务型消息，对其进行测试，然后发布。 | 然后，即可发送事务型消息。 |

有关编辑和发布事务型消息的更多信息，请参阅 [编辑事务型消息](../../channels/using/editing-transactional-message.md) 和 [事务性消息生命周期](../../channels/using/publishing-transactional-message.md).

### 步骤3 — 集成事件触发 {#integrate-event-trigger}

<!--<img src="assets/do-not-localize/icon_api.svg" width="55px">-->

创建事件后，您需要将此事件的触发集成到您的网站中。<!--In this example, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart.--> 为此，您的网站Web开发人员必须使用 **ADOBE CAMPAIGN STANDARD REST API**.

| 实施触发器 | 用户 | 操作 | 结果 |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_api.svg" width="55px"> | 此步骤由网站的开发人员执行。 | 使用REST事务型消息API将事件集成到您的网站中。 | 当客户端放弃购物车时，将触发该事件。 |

有关使用Campaign REST API管理事务型消息的更多信息，请参阅 [REST API文档](../../api/using/managing-transactional-messages.md).

### 步骤4 — 消息投放 {#message-delivery}

<!--<img src="assets/do-not-localize/icon_channels.svg" width="60px">-->

执行上述所有步骤后，即可发送消息。

| 传递消息 | 用户 | 操作 | 结果 |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_channels.svg" width="60px"> | 此步骤由访问您网站的客户执行。 | 一旦用户离开网站而没有订购购物车中的产品，就会触发相应的Campaign事件。 | 用户会自动收到通知电子邮件。 |

## 相关主题

* [发送消息的关键步骤](../../channels/using/key-steps-to-send-a-message.md)
* [通信渠道入门](../../channels/using/get-started-communication-channels.md)
* [事务性推送通知](../../channels/using/transactional-push-notifications.md)
* [跟进消息](../../channels/using/follow-up-messages.md)
