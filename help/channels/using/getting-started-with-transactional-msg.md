---
solution: Campaign Standard
product: campaign
title: 事务性消息传递入门
description: 了解什么是交易消息传递，并了解在Adobe Campaign Standard中设置事务性消息的主要步骤。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: 交易消息传递
role: 业务从业者
level: 初学者
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 8%

---


# 事务性消息传递入门 {#getting-started-with-transactional-messaging}

## 概述 {#overview}

<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

事务性消息是由提供商（如网站）实时发送的个人独特通信。 它尤其值得期待，因为它包含收件人要检查或确认的重要信息。

* **什么时候到？** 由于此消息包含重要信息，因此用户希望实时发送该消息。因此，所触发的事件与消息到达之间的延迟必须非常短。

* **为什么这很重要？** 一般而言，事务性消息的开放率很高。因此，它应当经过仔细的设计，因为它定义了客户关系，对客户行为产生了很大的影响。

* **比如？** 它可以是创建帐户后的欢迎邮件、订单已发运的确认邮件、发票、密码更改确认邮件或客户浏览您的网站后的通知等。

Adobe Campaign允许您将此功能与信息系统集成，该信息系统发送要转换为自定义事务性消息的事件。

事务性消息可以通过电子邮件、SMS或[推送通知](../../channels/using/transactional-push-notifications.md)发送，具体取决于您的选项。 请核实您的许可协议。

>[!NOTE]
>
>Adobe Campaign优先处理事务性消息，而非任何其他投放。

<!--Guidelines to implement transactional messaging capabilities in your website are detailed in [this section](../../api/using/managing-transactional-messages.md).-->

在开始处理事务性消息之前，请确保阅读相应的[最佳实践和限制](../../channels/using/transactional-messaging-limitations.md)。

## 事务型消息传递工作原理{#transactional-messaging-operating-principle}

交易消息传递的整个过程可以描述如下：

![](assets/message-center-process.png)

例如，假设您是一个公司，您的客户可以在其中购买产品的网站。

Adobe Campaign允许您向已将产品添加到购物车的客户发送通知电子邮件。 当其中一人离开您的网站而未进行购买(外部事件触发活动事件)时，购物车放弃率电子邮件会自动发送给他们(事务性消息投放)。

将其置于[本节](#key-steps)的主要步骤详述如下。

## 事务性消息类型{#transactional-message-types}

在Adobe Campaign中提供两种事务性消息。

**事件事** 务messagestarget事件本身包含的数据。这些消息：
* 不要包含用户档案信息，因此不能包含退订链接。
* 与疲劳规则不兼容(即使是与用户档案的扩充)。
* 让其投放目标由事件本身包含的数据定义。

您可能希望向需要检索忘记的密码或确认订单的客户发送事件事务性消息。 事实上，您不希望您的收件人退订此类通信，并且不应将此通知添加到营销消息计数器作为疲劳规则的一部分。

**用户档案事** 务消息从活动营销用户档案库。使用此类消息，您可以：
* 利用Adobe Campaign数据库中包含的数据。
* 通过向用户档案配置中添加[扩充](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)，使用事件信息个性化您的消息。
* 应用[营销类型规则](../../sending/using/managing-typology-rules.md)或[疲劳规则](../../sending/using/fatigue-rules.md)。
* 在消息中包含退订链接。
* 将事务型消息添加到全局投放报告。
* 在客户历程中使用事务型消息。

例如，在客户放弃购物车到您网站上后与客户联系时，您可以使用此类消息来鼓励他们继续购买。 这样，您就可以更轻松地个性化您的信息，直接访问您的用户档案数据库中的所有信息，应用营销规则并将此信息包含到全球客户旅程和报告中，以便更好地视图您的客户行为。

在配置要转换为事件的事务型消息时，就决定了消息的类型。请参阅[基于事件的事务性消息](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages)和[基于用户档案的事务性消息](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages)配置部分。

## 关键步骤{#key-steps}

在Adobe Campaign中创建和管理个性化事务性消息的主要步骤在以下模式中进行了概述。

![](assets/message-center-overview.png)

以下进一步详细介绍了这些步骤中的每个步骤。

>[!IMPORTANT]
>
>只有具有[管理](../../administration/using/users-management.md#functional-administrators)角色的用户才能配置事务事件和访问事务性消息。

### 步骤1 — 创建并发布事件配置{#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

| 用户 | 操作 | 结果 |
|--- |--- |--- |
| 此步骤必须由持有[管理权限](../../administration/using/users-management.md#functional-administrators)的管理员执行。 | 配置名为“放弃购物车”的事件并发布此事件配置。 | 将部署网站开发人员将使用的API，并自动创建事务性消息。 |

创建和发布事件在[配置事务事件](../../channels/using/configuring-transactional-event.md)和[发布事务事件](../../channels/using/publishing-transactional-event.md)部分中介绍。

### 第2步 — 编辑并发布事务性消息{#create-transactional-message}

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

| 用户 | 操作 | 结果 |
|--- |--- |--- |
| 此步骤可由持有[管理权限](../../administration/using/users-management.md#functional-administrators)的营销用户执行。 | 编辑和个性化事务性消息，测试，然后发布。 | 然后，事务性消息即可发送。 |

有关编辑和发布事务性消息的详细信息，请参阅[编辑事务性消息](../../channels/using/editing-transactional-message.md)和[事务性消息生命周期](../../channels/using/publishing-transactional-message.md)。

### 步骤3 — 集成触发{#integrate-event-trigger}的事件

<img src="assets/do-not-localize/icon_api.svg" width="55px">

<!--**Event triggering integration**-->

| 用户 | 操作 | 结果 |
|--- |--- |--- |
| 此步骤由您网站的开发人员执行。 | 使用REST事务性消息API将事件集成到您的网站中。 | 事件将在客户端放弃其购物车时触发。 |

创建事件后，您需要将触发此事件集成到您的网站中。<!--In this example, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart.--> 为此，您的网站Web开发人员必须使用 **Adobe Campaign Standard REST API**。

有关使用活动 REST API管理事务性消息的详细信息，请参阅[REST API文档](../../api/using/managing-transactional-messages.md)。

### 步骤4 — 消息投放{#message-delivery}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

执行所有这些步骤后，即可传递信息。

一旦用户离开网站而未在购物车中订购产品，将触发相应的活动事件。 用户自动接收通知电子邮件。

## 相关主题

* [发送消息的关键步骤](../../channels/using/key-steps-to-send-a-message.md)
* [通信渠道入门](../../channels/using/get-started-communication-channels.md)
* [事务型推送通知](../../channels/using/transactional-push-notifications.md)
* [跟进消息](../../channels/using/follow-up-messages.md)
