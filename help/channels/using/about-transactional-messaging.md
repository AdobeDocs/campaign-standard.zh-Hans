---
title: 关于交易消息传递
description: 了解可发送的不同事务性消息类型以及Adobe Campaign中如何使用它们。
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
translation-type: tm+mt
source-git-commit: 72366d56e21933bcd79e907e5f8d5a9ad5281725

---


# 关于交易消息传递{#about-transactional-messaging}

您可以创建和管理Adobe Campaign中的个性化事务性消息。

事务性消息是由提供者（例如网站）发送给用户的个人和唯一的通信。

* 此类型的消息尤其需要，因为它包含收件人要检查或确认的信息。 例如，创建帐户后，它可能是欢迎消息，也可能是确认订单已发运的确认消息、帐单或确认密码更改的消息。
* 它是定义客户端关系的一条重要消息：用户希望实时发送它。 因此，所触发的事件和消息到达之间的延迟必须非常短。
* 事务性消息通常有较高的开放率。

Adobe Campaign允许您将此功能与信息系统集成，该信息系统将要转换为自定义事务性消息的事件发送给该系统。

>[!NOTE]
>
>事务性消息可以通过电子邮件、短信或推送通知发送，具体取决于您的选项。 请检查您的许可协议。

Adobe Campaign中提供两种事务性消息:

* [事件事务性消息](../../channels/using/event-transactional-messages.md) ，目标是事件。 包含在事件本身中的数据用于定义投放目标。
* [用户档案事务性消息](../../channels/using/profile-transactional-messages.md) ，定位Adobe Campaign营销数据库中的用户档案。 您可以使用Adobe Campaign数据库中的信息根据客户营销用户档案发送事务性消息。

在配置要转换为事件的事务性消息时，会定义消息类型。 请参阅 [事务消息传递配置](../../administration/using/configuring-transactional-messaging.md)。

>[!NOTE]
>
>Adobe Campaign优先处理事务性消息，而不是处理任何其他投放。

交易消息传递也可从Adobe Campaign标准API中获取。 有关详细信息，请参阅专 [用文档](../../api/using/managing-transactional-messages.md)。

>[!IMPORTANT]
>
>所有事务性消息现在都随Adobe Campaign增强的MTA一起发送，以改进交付性、吞吐量和弹回处理。 所有影响与标准营销消息相同。

## 交易消息传递操作原则 {#transactional-messaging-operating-principle}

让我们举一个公司的例子，它有一个网站，在这个网站上其用户可以购买产品。

Adobe Campaign允许您向已将产品添加到其购物车的站点用户发送通知电子邮件：当其中一人离开网站而未完成购买时，购物车放弃电子邮件会自动发送给他们。

落实这些步骤包括：

1. 配置将命名为“放弃购物车”的事件，并发布此事件配置，该配置会自动创建事务性消息。 创建和发布事件在配置事件以 [发送事件事务性消息部分中显示](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 。
1. 事务性消息必须经过个性化测试，然后发布。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).
1. 此外，为了在客户端放弃其购物车时触发事件，必须使用Adobe Campaign标准REST API从公司网站发送此事件。 请参阅 [站点集成](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

执行所有这些步骤后，一旦用户离开站点而未在其购物车中订购产品，他们将自动收到通知电子邮件。

## 交易消息发布流程 {#transactional-messaging-pub-process}

下图说明了事务性消息发布过程。

![](assets/message-center_pub-process.png)

有关事件配置步骤的详细信息，请参阅 [事务消息配置](../../administration/using/configuring-transactional-messaging.md)。

## 交易消息传递限制 {#transactional-messaging-limitations}

>[!NOTE]
>
>要访问事务性消息，您必须拥有管理权限。

### 设计和发布 {#design-and-publication}

在设计和发布事务性消息时，您需要执行的某些步骤无法还原。 您需要注意以下限制：

* 每个渠道配置只能使用一个事件。 请参 [阅创建事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* 创建事件后，便无法更改渠道。 因此，如果消息未成功发送，您需要设计一种机制，以允许使用工作流从其他渠道发送消息。 See [Workflow data and processes](../../automating/using/workflow-data-and-processes.md).
* 在创建定位维度后， **[!UICONTROL Real-time event]** 您无 **[!UICONTROL Profile]** 法更改事件（或）。 请参 [阅创建事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* 无法回滚发布，但可以取消发布事件:此操作使事件和关联的事务性消息无法访问。 请参 [阅取消发布事件](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event)。
* 唯一可以与事件关联的事务性消息是发布该事件时自动创建的消息。 请参 [阅预览和发布事件](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)。

### 个性化 {#personalization}

个性化消息内容的方式取决于事务性消息的类型。 具体情况如下：

**事件事务性消息**:

* 个性化信息来自事件本身包含的数据。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).
* 不能在退订 **事务性消息中使用事件** ，链接内容块。
* 基于事件的交易消息传递应仅使用发送事件中的数据来定义收件人和消息内容个性化。 但是，您可以使用事务性消息数据库中的信息丰富Adobe Campaign的内容。 请参 [阅丰富事务性消息内容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)。
* 由于事件事务性消息不包含用户档案信息，因此即使与用户档案扩充，也不能与疲劳规则兼容。 请参阅 [疲劳规则](../../sending/using/fatigue-rules.md)。

**用户档案事务性消息**:

* 个性化信息可以来自包含在事件中的数据或已调节的用户档案记录。 See [Profile transactional messages](../../channels/using/profile-transactional-messages.md).
* 您可以在 **退订事务性消息中** ，使用用户档案链接内容块。 请参 [阅添加内容块](../../designing/using/personalization.md#adding-a-content-block)。
* 疲劳规则与用户档案事务性消息兼容。 请参阅 [疲劳规则](../../sending/using/fatigue-rules.md)。

请注意，产品列表仅在交易电子邮件中可用。 请参 [阅在事务性消息中使用产品列表](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)。

### 权限和品牌 {#permissions-and-branding}

在品牌管理方面 [](../../administration/using/branding.md) ，交易消息传递比标准消息传递带来的灵活性要小。 Adobe建议将事务性消息中使用的所有品牌关联到组 **[!UICONTROL All]** 织 [单位](../../administration/using/organizational-units.md)。 有关此方面的更多信息，请阅读下面的详细说明。

编辑事务性消息时，您可以将其链接到品牌以自动应用一些参数，如品牌名称或品牌徽标。 默认 **[!UICONTROL Default brand]** 情况下，事务性消息属性中会选中该选项。

![](assets/message-center_branding.png)

事务性消息中使用的所有对象（包括品牌）必须从组织单位中可见，这意味着这些对象必须位于或组 **[!UICONTROL Message Center]** 织单 **[!UICONTROL Message Center]****[!UICONTROL All]** 位中。

但是，如果消息属性中选择的品牌链接到的组织单元与或不同 **[!UICONTROL Message Center]** , **[!UICONTROL All]**&#x200B;则这将导致错误，您将无法发送事务性消息。

因此，如果要在交易消息的上下文中使用多品牌，您应将所有品牌关联到组织单 **[!UICONTROL Message Center]** 位或组织单 **[!UICONTROL All]** 位。

### 导出和导入事务性消息 {#exporting-and-importing-transactional-messages}

* 要导出事务性消息，您需要在创建包导出时包含相 [应的事件配置](../../automating/using/managing-packages.md#creating-a-package)。
* 通过包导入 [事务性消息后](../../automating/using/managing-packages.md#importing-a-package),事务性消息列表中不显示。 您需要发 [布事件配置](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) ，才能使关联的事务性消息可用。

