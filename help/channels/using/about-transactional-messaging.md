---
title: 关于交易消息传递
description: 了解您可以发送的不同类型的事务性消息以及它们在Adobe Campaign中的使用方式。
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
source-git-commit: b06edadfa963881403328c4ab37d25d701bc8237

---


# 关于交易消息传递{#about-transactional-messaging}

您可以在Adobe Campaign中创建和管理个性化的交易消息。

交易消息是由诸如网站的提供者发送给用户的个人和唯一通信。

* 此类型的消息尤其需要，因为它包含收件人要检查或确认的信息。 例如，创建帐户后，它可能是欢迎消息，也可能是确认订单已发运的确认消息、帐单或确认密码更改的消息。
* 它是定义客户端关系的一条重要消息：用户希望实时发送它。 因此，所触发的事件与到达的消息之间的延迟必须非常短。
* 交易消息通常具有高打开率。

Adobe Campaign允许您将此功能与信息系统集成，该信息系统会发送要转换为自定义事务消息的事件。

>[!NOTE]
>
>交易消息可以通过电子邮件、短信或推送通知发送，具体取决于您的选项。 请检查您的许可协议。

Adobe Campaign中提供两种类型的交易消息：

* [以活动为目标的活动](../../channels/using/event-transactional-messages.md) 、事务性消息。 事件本身包含的数据用于定义交付目标。
* [从Adobe Campaign营销数据库](../../channels/using/profile-transactional-messages.md) ，概要分析事务性消息定位配置文件。 您可以使用Adobe Campaign数据库中的信息根据客户营销档案发送交易消息。

在配置将转换为事务消息的事件时，会定义消息类型。 请参阅 [事务消息传递配置](../../administration/using/configuring-transactional-messaging.md)。

>[!NOTE]
>
>Adobe Campaign优先处理事务性消息，而不是处理任何其他交付。

Adobe Campaign Standard API也提供交易消息传递。 有关详细信息，请参阅专 [用文档](../../api/using/managing-transactional-messages.md)。

## 交易消息传递操作原则 {#transactional-messaging-operating-principle}

让我们举一个公司的例子，它有一个网站，在这个网站上，它的用户可以购买产品。

Adobe Campaign允许您向已将产品添加到其购物车的站点用户发送通知电子邮件：当其中一人离开网站而未完成购买时，购物车放弃电子邮件会自动发送给他们。

落实这些步骤包括：

1. 配置将命名为“购物车放弃”的活动并发布此活动配置，该配置会自动创建交易消息。 在配置活动以发送活动事务消息部分 [中，将显示创建和发布活动](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 。
1. 交易信息必须经过个性化、测试和发布。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).
1. 此外，为了在客户端放弃购物车时触发该事件，必须使用Adobe Campaign Standard REST API从公司网站发送该事件。 请参阅 [站点集成](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

执行所有这些步骤后，一旦用户离开站点而未在其购物车中订购产品，他们将自动收到通知电子邮件。

## 交易消息发布流程 {#transactional-messaging-pub-process}

下图说明了事务性消息发布过程。

![](assets/message-center_pub-process.png)

有关事件配置步骤的详细信息，请参阅 [事务消息配置](../../administration/using/configuring-transactional-messaging.md)。

## 交易消息传递限制 {#transactional-messaging-limitations}

>[!NOTE]
>
>要访问事务性消息，您必须具有管理权限。

### 设计和发布 {#design-and-publication}

在设计和发布事务性消息时，您需要执行的某些步骤无法恢复。 您需要注意以下限制：

* 每个事件配置只能使用一个渠道。 请参 [阅创建活动](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* 创建活动后，便无法更改渠道。 因此，如果消息未成功发送，您需要设计一种机制，以允许使用工作流从其他渠道发送消息。 See [Workflow data and processes](../../automating/using/workflow-data-and-processes.md).
* 在创建活动后，您无 **[!UICONTROL Real-time event]** 法更改 **[!UICONTROL Profile]** 定位维度（或）。 请参 [阅创建活动](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* 无法回滚发布，但可以取消发布事件：此操作使事件和关联的事务消息无法访问。 请参阅 [取消发布活动](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event)。
* 唯一可与活动关联的事务消息是发布该活动时自动创建的消息。 请参 [阅预览和发布活动](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)。

### 个性化 {#personalization}

您个性化消息内容的方式取决于交易消息的类型。 具体情况如下：

**基于事件的交易消息**:

* 个性化信息来自活动本身包含的数据。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).
* 在活动事 **务消息中** ，不能使用取消订阅链接内容块。
* 基于事件的交易消息应仅使用发送事件中的数据来定义收件人和消息内容个性化。 但是，您可以使用Adobe Campaign数据库中的信息丰富事务性消息的内容。 请参 [阅丰富交易消息内容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)。
* 由于事件事务消息不包含配置文件信息，因此即使对配置文件进行了扩充，它们也与疲劳规则不兼容。 请参阅 [疲劳规则](../../administration/using/fatigue-rules.md)。

**基于档案的交易消息**:

* 个性化信息可以来自活动中包含的数据，也可以来自已调节的配置文件记录。 See [Profile transactional messages](../../channels/using/profile-transactional-messages.md).
* 您可以在个人资料 **事务性消息中使用** “取消订阅”链接内容块。 请参 [阅添加内容块](../../designing/using/personalization.md#adding-a-content-block)。
* 疲劳规则与个人资料事务性消息兼容。 请参阅 [疲劳规则](../../administration/using/fatigue-rules.md)。

请注意，产品列表仅在交易电子邮件中可用。 请参 [阅在交易消息中使用产品列表](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)。

### 权限和品牌 {#permissions-and-branding}

在品牌管理方面 [](../../administration/using/branding.md) ，交易消息传递比标准消息传递带来的灵活性要小。 Adobe建议将交易消息中使用的所有品牌关联到组 **[!UICONTROL All]** 织 [单位](../../administration/using/organizational-units.md)。 有关此问题的详细信息，请阅读下面的详细说明。

编辑交易消息时，您可以将其链接到品牌以自动应用一些参数，如品牌名称或品牌徽标。 默认 **[!UICONTROL Default brand]** 情况下，会在事务消息属性中选择该选项。

![](assets/message-center_branding.png)

交易消息中使用的所有对象（包括品牌）必须从组织单位中可见，这 **[!UICONTROL Message Center]** 意味着这些对象必须位于或组 **[!UICONTROL Message Center]** 织单 **[!UICONTROL All]** 位中。

但是，如果消息属性中选择的品牌链接到的组织单元与或不同 **[!UICONTROL Message Center]** , **[!UICONTROL All]**&#x200B;则这将导致错误，并且您将无法发送交易消息。

因此，如果要在交易消息的上下文中使用多品牌，您应将所有品牌关联到组织单 **[!UICONTROL Message Center]** 位或组织单 **[!UICONTROL All]** 位。

### 导出和导入事务性消息 {#exporting-and-importing-transactional-messages}

* 要导出事务消息，您需要在创建包导出时包含相 [应的事件配置](../../automating/using/managing-packages.md#creating-a-package)。
* 通过包导入事务 [消息后](../../automating/using/managing-packages.md#importing-a-package)，事务消息不会显示在事务消息列表中。 您需要发 [布活动配置](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) ，才能使关联的事务消息可用。

