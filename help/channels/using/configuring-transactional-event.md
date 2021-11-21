---
title: 配置事务性事件
description: 了解如何在Adobe Campaign中配置事务事件。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 1b91fb97-fe97-4564-936c-438be7ea7bc0
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '1672'
ht-degree: 6%

---

# 配置事务性事件 {#configuring-transactional-event}

要使用Adobe Campaign发送事务型消息，您首先需要通过创建和配置事件来描述事件数据的结构。

>[!IMPORTANT]
>
>仅 [功能管理员](../../administration/using/users-management.md#functional-administrators) <!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) -->具有创建和编辑事件配置的适当权限。

配置因 [事务型消息类型](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types) 要发送，以及将使用的渠道上的。 有关此内容的更多信息，请参阅 [特定配置](#transactional-event-specific-configurations).

配置完成后，必须发布该事件。 请参阅 [发布事务型事件](../../channels/using/publishing-transactional-event.md).

## 创建事件 {#creating-an-event}

要开始配置，请创建与您的需求对应的事件。

1. 单击 **Adobe** 徽标，然后选择 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. 单击 **[!UICONTROL Create]** 按钮。
1. 输入 **[!UICONTROL Label]** 和 **[!UICONTROL ID]** 的值。 的 **[!UICONTROL ID]** 字段为必填字段，且应以前缀“EVT”开头。 如果不使用此前缀，则在单击 **[!UICONTROL Create]**.

   ![](assets/message-center_1.png)

   >[!IMPORTANT]
   >
   >ID不得超过64个字符，包括EVT前缀。

1. 选择用于发送事务型消息的渠道 **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** 或 **[!UICONTROL Push notification]**. 每个事件只能使用一个渠道，此后无法更改。

1. 选择与所需事件配置对应的定向维度，然后单击 **[!UICONTROL Create]**.

   基于事件的事务型消息以事件本身包含的数据为目标，而基于用户档案的事务型消息以Adobe Campaign数据库中包含的数据为目标。 有关更多信息，请参阅 [特定配置](#transactional-event-specific-configurations).

>[!NOTE]
>
>事务事件的数量可能会对您的平台产生影响。 为确保获得最佳性能，请确保删除未使用的事件。 请参阅 [删除事件](../../channels/using/publishing-transactional-event.md#deleting-an-event).

## 定义事件属性 {#defining-the-event-attributes}

在 **[!UICONTROL Fields]** 部分，定义将集成到事件内容中并随后可用于个性化事务型消息的属性。

添加和修改字段的步骤与 [自定义资源](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource).

![](assets/message-center_2.png)

>[!NOTE]
>
>如果要创建多语言事务型消息，请使用 **[!UICONTROL AC_language]** ID。 这仅适用于事件事务型消息。 发布事件后，编辑多语言事务型消息内容的步骤与编辑多语言标准电子邮件的步骤相同。 请参阅 [创建多语言电子邮件](../../channels/using/creating-a-multilingual-email.md).

## 定义数据集合 {#defining-data-collections}

您可以向事件内容添加元素集合，每个元素本身都包含多个属性。

此集合可在事务型电子邮件中用于添加 [产品清单](../../designing/using/using-product-listings.md) 消息内容，例如产品列表 — 包含价格、参考编号、数量等。 列表的每个产品。

1. 在 **[!UICONTROL Collections]** ，单击 **[!UICONTROL Create element]** 按钮。

   ![](assets/message-center_collection_create.png)

1. 为您的收藏集添加标签和ID。
1. 为列表的每个产品添加要在事务型消息中显示的所有字段。

   在本例中，我们添加了以下字段：

   ![](assets/message-center_collection_fields.png)

1. 的 **[!UICONTROL Enrichment]** 选项卡，以扩充集合的每个项目。 这样，您就可以使用来自Adobe Campaign数据库或您创建的其他资源的信息，将相应产品清单的元素个性化。

>[!NOTE]
>
>扩充集合元素的步骤与 [丰富活动内容](#enriching-the-transactional-message-content) 中。 请注意，扩充活动将不允许您扩充集合：您需要向 **[!UICONTROL Collections]** 中。

发布事件和消息后，您便能够在事务型消息中使用此集合。

以下是此示例的API预览：

![](assets/message-center_collection_api-preview.png)

**相关主题：**

* [预览和发布事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)
* [在事务型消息中使用产品清单](../../designing/using/using-product-listings.md)
* [发布事务型消息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)

## 丰富活动内容 {#enriching-the-transactional-message-content}

您可以使用Adobe Campaign数据库中的信息扩充事务型消息的内容，以便个性化您的消息。 例如，从每个收件人的姓氏或CRM ID中，您可以恢复诸如其地址、出生日期或在“用户档案”表中添加的任何其他自定义字段之类的数据，以便个性化发送给他们的信息。

可以使用来自扩展的信息扩充事务型消息的内容 **[!UICONTROL Profile and services Ext API]**. 有关更多信息，请参阅 [扩展API:发布扩展](../../developing/using/step-2--publish-the-extension.md)

此信息也可以存储在新资源中。 在这种情况下，资源必须链接到 **[!UICONTROL Profile]** 或 **[!UICONTROL Service]** 直接或通过其他表获取资源。 例如，在以下配置中，可以使用 **[!UICONTROL Product]** 资源（如产品类别或ID），如果 **[!UICONTROL Product]** 资源已链接到 **[!UICONTROL Profile]** 资源。

![](assets/message-center_usecaseschema.png)

有关创建和发布资源的更多信息，请参阅 [此部分](../../developing/using/key-steps-to-add-a-resource.md).

1. 在 **[!UICONTROL Enrichment]** ，单击 **[!UICONTROL Create element]** 按钮。

   ![](assets/message-center_addenrichment.png)

1. 选择要将消息链接到的资源。 在这种情况下，请选择 **[!UICONTROL Profile]** 资源。

   ![](assets/message-center_new-enrichment.png)

1. 使用 **[!UICONTROL Create element]** 按钮，将选定资源中的字段链接到您之前添加到事件的某个字段(请参阅 [定义事件属性](#defining-the-event-attributes))。

   ![](assets/message-center_enrichment-join.png)

1. 在本例中，我们将协调 **[!UICONTROL Last name]** 和 **[!UICONTROL First name]** 字段，其对应的字段位于 **[!UICONTROL Profile]** 资源。

   ![](assets/message-center_enrichment-join-fields.png)

   您还可以使用 **[!UICONTROL Service]** 资源。 有关服务的更多信息，请参阅 [此部分](../../audiences/using/creating-a-service.md).

1. 如果您创建或编辑 [基于用户档案的事件](#profile-based-transactional-messages)，在 **[!UICONTROL Targeting enrichment]** 部分，选择在投放执行期间用作消息目标的扩充。

   ![](assets/message-center_marketing_targeting_enrichment.png)

   >[!NOTE]
   >
   >创建扩充并根据 **[!UICONTROL Profile]** 基于用户档案的事件必须提供资源。

发布事件和消息后，此链接将允许您扩充事务型消息的内容。

**相关主题：**

* [预览和发布事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)
* [个性化事务型消息](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)
* [发布事务型消息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)

## 搜索事务事件 {#searching-transactional-events}

要访问和搜索已创建的事务型事件，请执行以下步骤。

1. 单击 **Adobe** 徽标，然后选择 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. 单击 **[!UICONTROL Show search]** 按钮。

   ![](assets/message-center_search-events.png)

1. 您可以在 **[!UICONTROL Publication status]**. 例如，这允许您仅显示已发布的事件。
1. 您还可以使用 **[!UICONTROL Last event received]**. 例如，如果输入10，则只会显示10天前或更久之前收到的最后一个事件的事件配置。 这样，您就可以显示在给定时间段内哪些事件处于非活动状态。

   ![](assets/message-center_last-event-received.png)

   >[!NOTE]
   >
   >默认值为0。 随后将显示所有事件。

## 特定配置 {#transactional-event-specific-configurations}

事务事件配置可能因 [事务型消息类型](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types) 要发送（事件或用户档案），以及将使用的渠道。

以下各节详细介绍了根据所需的事务型消息应设置哪些特定配置。 有关配置事件的常规步骤的更多信息，请参阅 [创建事件](#creating-an-event).

### 基于事件的事务型消息 {#event-based-transactional-messages}

您可以发送定向某个事件的事件事务型消息。此类事务型消息不包含用户档案信息：根据事件本身包含的数据定义投放目标。

要发送基于事件的事务型消息，您首先需要创建并配置以 **事件本身包含的数据**.

1. 创建事件配置时，选择 **[!UICONTROL Real-time event]** 定位维度(请参阅 [创建事件](#creating-an-event))。
1. 向事件添加字段，以便能够个性化事务型消息(请参阅 [定义事件属性](#defining-the-event-attributes))。
1. 基于事件的事务型消息，应仅使用已发送事件中的数据来定义收件人和个性化消息内容。

   但是，如果要使用Adobe Campaign数据库中的其他信息，则可以扩充事务型消息的内容(请参阅 [扩充事务型消息的内容](#enriching-the-transactional-message-content))。

1. 预览和发布事件(请参阅 [预览和发布事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event))。

   预览事件时，REST API包含一个属性，该属性根据所选渠道指定电子邮件地址、手机或推送通知特定属性。

   发布事件后，将自动创建链接到新事件的事务型消息。 要使事件触发发送事务型消息，您必须 [修改](../../channels/using/editing-transactional-message.md) 和 [发布](../../channels/using/publishing-transactional-message.md) 刚刚创建的消息。

1. 将事件集成到您的网站(请参阅 [集成事件触发](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger))。

### 基于用户档案的事务型消息 {#profile-based-transactional-messages}

您可以根据客户用户档案发送事务型消息，该消息允许您应用营销分类规则，包括取消订阅链接，将消息添加到全局投放报告并在客户历程中利用该消息。

要发送基于用户档案的事务型消息，您首先需要创建并配置事件定位 **来自Adobe Campaign数据库的数据**.

1. 创建事件配置时，选择 **[!UICONTROL Profile event]** 定位维度(请参阅 [创建事件](#creating-an-event))。
1. 向事件添加字段，以便能够个性化事务型消息(请参阅 [定义事件属性](#defining-the-event-attributes))。 必须至少添加一个字段才能创建扩充。 您无需创建其他字段，例如 **名字** 和 **姓氏** 因为您将能够使用Adobe Campaign数据库中的个性化字段。
1. 创建扩充，以将事件链接到 **[!UICONTROL Profile]** 资源(请参阅 [丰富活动内容](#enriching-the-transactional-message-content))并选择此扩充作为 **[!UICONTROL Targeting enrichment]**.

   >[!IMPORTANT]
   >
   >对于基于用户档案的事件，此步骤是必备的。

1. 预览和发布事件(请参阅 [预览和发布事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event))。

   预览事件时，REST API不包含指定电子邮件地址、手机或推送通知特定属性的属性，因为该属性将从 **[!UICONTROL Profile]** 资源。

   发布事件后，将自动创建链接到新事件的事务型消息。 要使事件触发发送事务型消息，您必须 [修改](../../channels/using/editing-transactional-message.md) 和 [发布](../../channels/using/publishing-transactional-message.md) 刚刚创建的消息……

1. 将事件集成到您的网站(请参阅 [集成事件触发](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger))。

<!--### Transactional SMS messages {#transactional-sms}

The steps to configure an  event to send an SMS transactional message are the same as for the email channel. The only differences are as follows:

* When creating the corresponding event, you need to select the **[!UICONTROL Mobile (SMS)]** channel.

* When previewing the event corresponding to an event-based transactional SMS, the REST API contains an attribute specifying the mobile phone instead of the email address.

* The specificities to edit the content of an SMS transactional message are the same as for a [standard SMS](../../channels/using/about-sms-and-push-content-design.md).-->

### 事务性推送通知 {#transactional-push-notifications}

您可以发送两种类型的事务推送通知：
* 向选择从移动应用程序接收通知的所有用户发送的匿名事务型推送通知。 请参阅 [配置基于事件的事务型推送通知](../../channels/using/transactional-push-notifications.md#event-based-transactional-push-notifications).
* 向订阅了您移动应用程序的Adobe Campaign用户档案的事务型推送通知。 请参阅 [配置基于用户档案的事务推送通知](../../channels/using/transactional-push-notifications.md#profile-based-transactional-push-notifications).

>[!IMPORTANT]
>
>要发送事务推送通知，您需要相应地配置Adobe Campaign。 请参阅 [配置移动应用程序](../../administration/using/configuring-a-mobile-application.md).

### 跟进消息 {#follow-up-messages}

您可以向收到特定事务型消息的客户发送跟进消息。

有关配置事件以发送跟进消息的详细步骤，请参见 [此部分](../../channels/using/follow-up-messages.md#configuring-an-event-to-send-a-follow-up-message).
