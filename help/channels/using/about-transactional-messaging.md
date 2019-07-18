---
title: 关于交易消息
seo-title: 关于交易消息
description: 关于交易消息
seo-description: 发现您可以发送的不同类型的交易消息，以及如何在Adobe Campaign中使用这些消息。
page-status-flag: 从未激活
uuid: 8470e9e2-ee17-456f-9e4 c-460e69 c78 a2 c
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: 交易消息传递
discoiquuid: 71a4d5d5-fe2 a-4ce5-b22 b-a4736 f7 add83
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: d93c2600299a8d2ec3672b3d82222f423878034c

---


# About transactional messaging{#about-transactional-messaging}

您可以在Adobe Campaign中创建和管理个性化的交易消息。

事务消息是由提供商(如网站)发送给用户的个人和唯一通信。

* 这种类型的消息尤其期望，因为它包含收件人希望检查或确认的信息。在创建帐户后，它可能是欢迎消息，也可能是订单已发运、账单或确认密码更改的消息。
* 它是定义客户关系的重要消息：用户希望实时发送它。触发事件与到达消息之间的延迟必须非常简短。
* 交易消息通常具有高的打开率。

Adobe Campaign允许您将此功能与信息系统集成，后者发送要转换为自定义交易消息的活动。

>[!NOTE]
>
>交易消息可通过电子邮件、SMS或推送通知发送，具体取决于您的选择。请检查您的许可协议。

Adobe Campaign中提供了两种类型的交易消息：

* [针对活动的活动交易消息](../../channels/using/event-transactional-messages.md) 。事件本身中包含的数据用于定义交付目标。
* [个人资料信息消息](../../channels/using/profile-transactional-messages.md) 定位来自Adobe Campaign营销数据库的档案。您可以使用Adobe Campaign数据库中的信息发送基于客户营销档案的交易消息。

在配置将转换为交易消息的事件时，将定义消息类型。See [Transactional messaging configuration](../../administration/using/configuring-transactional-messaging.md).

>[!NOTE]
>
>Adobe Campaign优先级在任何其他交付过程中处理交易消息。

Adobe Campaign Standard API也提供交易消息传递。For more on this, refer to the [dedicated documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#about-transactional-messaging).

## Transactional messaging operating principle {#transactional-messaging-operating-principle}

让我们来示例一家拥有网站的公司，它的用户可以购买产品。

Adobe Campaign允许您向已向其购物车中添加产品的站点用户发送通知电子邮件：当其中一人离开网站时，不会通过购买，会自动向他们发送放弃的电子邮件。

将此置于位置的步骤包括：

1. 配置将被命名为“购物车废弃”并发布此活动配置的活动，该活动自动创建交易消息。Creating and publishing an event are presented in the [Configuring an event to send an event transactional message](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.
1. 交易消息必须经过个性化、测试，然后发布。See [Event transactional messages](../../channels/using/event-transactional-messages.md).
1. 此外，为了在客户端放弃购物车时触发事件，必须使用Adobe Campaign Standard REST API从公司的网站发送此事件。See [Site integration](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

执行所有这些步骤后，一旦用户不在购物车中订购产品，他们就会自动收到通知电子邮件。

## Transactional messaging limitations {#transactional-messaging-limitations}

### Design and publication {#design-and-publication}

在设计和发布事务消息时，执行的某些步骤无法恢复。您需要了解以下限制：

* 每个活动配置只能使用一个频道。See [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* 创建活动后，您无法更改渠道。因此，如果消息未成功发送，您需要设计允许使用工作流从其他渠道发送它的机制。See [Workflow data and processes](../../automating/using/workflow-data-and-processes.md).
* You cannot change the targeting dimension ( **[!UICONTROL Real-time event]** or **[!UICONTROL Profile]** ) after the event is created. See [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* 无法回滚出版物，但可以取消发布活动：此操作使活动和关联的事务消息无法访问。See [Unpublishing an event](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* 可以与活动关联的唯一事务消息是在发布该活动时自动创建的消息。See [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

### Personalization {#personalization}

个性化消息内容的方式取决于交易消息的类型。具体情况如下所示：

**基于事件的交易消息**：

* 个性化信息来自活动本身包含的数据。See [Event transactional messages](../../channels/using/event-transactional-messages.md).
* You cannot use **Unsubscription link** content blocks in an event transactional message.
* 基于事件的交易消息应仅使用已发送事件中的数据来定义接收者和消息内容个性化。但是，您可以使用Adobe Campaign数据库中的信息丰富交易消息的内容。See [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).
* 因为事件交易消息不包含配置文件信息，因此它们与疲劳规则不兼容，即使是使用配置文件丰富的情况也是如此。See [Fatigue rules](../../administration/using/fatigue-rules.md).

**基于个人资料的交易消息**：

* 个性化信息可能来自活动中包含的数据或已调解的档案记录。See [Profile transactional messages](../../channels/using/profile-transactional-messages.md).
* You can use **Unsubscription link** content blocks in a profile transactional message. See [Adding a content block](../../designing/using/adding-a-content-block.md).
* 疲劳规则与个人资料信息消息兼容。See [Fatigue rules](../../administration/using/fatigue-rules.md).

请注意，产品列表仅在交易电子邮件中可用。See [Using product listings in a transactional message](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

### Permissions and branding {#permissions-and-branding}

[谈到品牌](../../administration/using/branding.md) 管理，交易消息的灵活性比标准消息更低。Adobe recommends linking all brands used in transactional messages to the **[!UICONTROL All]** organizational unit. 有关此问题的详细信息，请阅读下面的详细说明。

编辑交易消息时，您可以将其链接到品牌，以自动应用品牌名称或品牌徽标等参数。The **[!UICONTROL Default brand]** is selected by default in the transactional message properties.

![](assets/message-center_branding.png)

To access the transactional messages, you must be part of the **[!UICONTROL Message Center agents]** (mcExec) security group, which is linked to the **[!UICONTROL Message Center]** [organizational unit](../../administration/using/organizational-units.md). Therefore, all objects (including branding) used in a transactional message must be visible from the **[!UICONTROL Message Center]** organizational unit, meaning that these objects must be in the **[!UICONTROL Message Center]** or **[!UICONTROL All]** organizational units.

However, if the brand selected in the message properties is linked to an organizational unit which is different from **[!UICONTROL Message Center]** or **[!UICONTROL All]**, this will cause an error and you will not be able to send the transactional message.

Therefore, if you want to use multi-branding in the context of transactional messaging, you should link all brands either to the **[!UICONTROL Message Center]** organizational unit or to the **[!UICONTROL All]** organizational unit.

### Exporting and importing transactional messages {#exporting-and-importing-transactional-messages}

* To export a transactional message, you need to include the corresponding event configuration when [creating the package export](../../automating/using/managing-packages.md#creating-a-package).
* Once the transactional message is [imported through a package](../../automating/using/managing-packages.md#importing-a-package), it is not displayed in the transactional message list. You need to [publish](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) the event configuration in order to make the associated transactional message available.

