---
title: 关于事务型消息传递
description: 了解您可以发送的各种事务型消息类型以及在 Adobe Campaign 中使用事务型消息的方法。
page-status-flag: never-activated
uuid: 8470e9e2-ee17-456f-9e4c-460e69c78a2c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: 71a4d5d5-fe2a-4ce5-b22b-a4736f7add83
internal: n
snippet: y
translation-type: ht
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb
workflow-type: ht
source-wordcount: '1147'
ht-degree: 100%

---


# 关于事务型消息传递{#about-transactional-messaging}

您可以在 Adobe Campaign 中创建和管理个性化事务型消息。

事务型消息是由提供者（如网站）发送给用户的个人通信且具有唯一性。

* 此类型的消息很重要，因为它包含需要收件人核实或确认的信息。例如，它可能是创建帐户后的欢迎消息，也可能是确认订单已发运的消息、账单的消息或确认密码更改的消息。
* 该消息的重要程度甚至足以决定客户关系：用户希望此类消息能够实时发送。从触发事件到收到相应消息之间的时间间隔必须非常短。
* 事务型消息通常具有高打开率。

Adobe Campaign 允许您将此功能与信息系统集成，将要转换为自定义事务型消息的事件发送给信息系统。

>[!NOTE]
>
>事务型消息可以通过电子邮件、短信或推送通知发送，具体取决于您的选择。请核实您的许可协议。

Adobe Campaign 提供两类事务型消息：

* 对应于事件的[事件事务型消息](../../channels/using/event-transactional-messages.md)。使用事件本身所包含的数据定义投放目标。
* 对应于 Adobe Campaign 营销数据库用户档案的[用户档案事务型消息](../../channels/using/profile-transactional-messages.md)。您可以使用来自 Adobe Campaign 数据库中的信息，发送基于客户营销用户档案的事务型消息。

在配置要转换为事件的事务型消息时，就决定了消息的类型。请参阅[事务型消息传递配置](../../administration/using/configuring-transactional-messaging.md)。

>[!NOTE]
>
>Adobe Campaign 会优先处理事务型消息，而不是任何其他投放。

Adobe Campaign Standard API 也可使用事务型消息传递。有关更多信息，请参阅[专用文档](../../api/using/managing-transactional-messages.md)。

>[!NOTE]
>
>现在，所有事务型消息都随 Adobe Campaign Enhanced MTA 一起发送，以提升投放能力、吞吐率和跳出处理能力。所有方面都与标准营销消息相同。有关更多信息，请参阅[此章节](../../administration/using/configuring-email-channel.md)。

## 事务型消息传递工作原理{#transactional-messaging-operating-principle}

以某个公司为例，该公司有一个网站，用户可以在这个网站上购买它的产品。

利用 Adobe Campaign，可向购物车中添加了产品的网站用户发送通知电子邮件：如果此类用户离开网站且未完成购买，则会自动向他们发送“购物车放弃”电子邮件。

要实现此功能，需要完成以下步骤：

1. 配置命名为“购物车放弃”的事件，并发布此事件配置，以自动创建事务型消息。创建和发布事件，可参阅[配置事件以发送事件事务型消息](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message)一节。
1. 必须对事务型消息进行个性化和测试，然后才能发布。请参阅[事件事务型消息](../../channels/using/event-transactional-messages.md)。
1. 此外，为了在客户放弃购物车时触发事件，必须使用 Adobe Campaign Standard REST API 从公司的网站发送此事件。请参阅[站点集成](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

完成所有这些步骤后，一旦用户离开网站而不订购购物车中的产品，就会自动向用户发送通知电子邮件。

## 事务型消息传递发布流程 {#transactional-messaging-pub-process}

下图说明了事务型消息传递的发布流程。

![](assets/message-center_pub-process.png)

有关事件配置步骤的更多信息，请参阅[事务型消息传递配置](../../administration/using/configuring-transactional-messaging.md)。

## 事务型消息传递限制{#transactional-messaging-limitations}

>[!NOTE]
>
>要访问事务型消息，您必须具有管理权限。

### 设计和发布{#design-and-publication}

设计和发布事务型消息时，需要执行的某些步骤无法恢复。您需要了解以下限制：

* 每个事件配置只能使用一个渠道。请参阅[创建事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* 创建事件后，便无法更改渠道。因此，您需要设计一种机制，在某个消息未成功发送时，允许通过某种工作流从其他渠道发送该消息。请参阅[工作流数据和流程](../../automating/using/get-started-workflows.md)。
* 创建事件后，就无法再更改定向维度（**[!UICONTROL Real-time event]** 或 **[!UICONTROL Profile]**）。请参阅[创建事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* 无法回滚发布，但您可以取消发布事件：此操作会使事件和相关的事务型消息变为无法访问状态。请参阅[取消发布事件](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event)。
* 唯一可以与事务型消息关联的事件，就是发布该事件时自动创建的消息。请参阅[预览和发布事件](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)。

### 个性化{#personalization}

个性化消息内容的方式，取决于事务型消息的类型。具体情况如下所示：

**基于事件的事务型消息**：

* 个性化信息来自事件本身包含的数据。请参阅[事件事务型消息](../../channels/using/event-transactional-messages.md)。
* 您不能在事件事务型消息中使用&#x200B;**退订链接**&#x200B;内容块。
* 基于事件的事务型消息，应仅使用已发送事件中的数据来定义收件人和个性化消息内容。但是，您也可以使用 Adobe Campaign 数据库中的信息扩充事务型消息的内容。请参阅[扩充事务型消息的内容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)。
* 由于事件事务型消息不包含用户档案信息，所以就算使用用户档案扩充了内容，也不兼容疲劳规则。请参阅[疲劳规则](../../sending/using/fatigue-rules.md)。

**基于用户档案的事务型消息**：

* 个性化信息可以来自事件中包含的数据，也可以来自协调的用户档案记录。请参阅[用户档案事务型消息](../../channels/using/profile-transactional-messages.md)。
* 您可以在用户档案事务型消息中使用&#x200B;**退订链接**&#x200B;内容块。请参阅[添加内容块](../../designing/using/personalization.md#adding-a-content-block)。
* 疲劳规则与用户档案事务型消息兼容。请参阅[疲劳规则](../../sending/using/fatigue-rules.md)。

请注意，产品清单仅可用在事务型电子邮件消息中。请参阅[在事务型消息中使用产品清单](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)。

### 权限和品牌策略 {#permissions-and-branding}

对于[品牌策略](../../administration/using/branding.md)的管理而言，事务型消息的灵活性低于标准消息。Adobe 建议将事务型消息中使用的所有品牌关联到 **[!UICONTROL All]** [组织单位](../../administration/using/organizational-units.md)。有关此方面的更多信息，请阅读下方的详细说明。

编辑事务型消息时，您可以将其链接到品牌以自动应用一些参数，例如品牌名称或品牌徽标。默认情况下，事务型消息属性中会选中 **[!UICONTROL Default brand]**。

![](assets/message-center_branding.png)

事务型消息中使用的所有对象（包括品牌）都必须在 **[!UICONTROL Message Center]** 组织单位中可见，这意味着这些对象必须在 **[!UICONTROL Message Center]** 或 **[!UICONTROL All]** 组织单位中。

但是，如果消息属性中选择的品牌链接到与 **[!UICONTROL Message Center]** 或 **[!UICONTROL All]** 不同的组织单位，则会导致错误，您将无法发送事务型消息。

因此，如果要在事务型消息的上下文中使用多品牌策略，您应将所有品牌关联到 **[!UICONTROL Message Center]** 组织单位或 **[!UICONTROL All]** 组织单位。

### 导出和导入事务型消息 {#exporting-and-importing-transactional-messages}

* 要导出事务型消息，您需要在[创建导出资源包](../../automating/using/managing-packages.md#creating-a-package)时包含相应的事件配置。
* [通过资源包导入](../../automating/using/managing-packages.md#importing-a-package)事务型消息后，该消息不会显示在事务型消息的列表中。您需要[发布](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)事件配置，以使关联的事务型消息可用。

