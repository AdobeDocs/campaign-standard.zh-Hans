---
solution: Campaign Standard
product: campaign
title: 配置事务性事件
description: 了解如何在Adobe Campaign中配置交易事件。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 7%

---


# 配置事务性事件 {#configuring-transactional-event}

要发送带有Adobe Campaign的事务性消息，您首先需要通过创建和配置事件来描述事件数据的结构。

>[!IMPORTANT]
>
>只有[职能管理员](../../administration/using/users-management.md#functional-administrators) <!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) -->具有创建和编辑事件配置的适当权限。

配置因要发送的事务性消息](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types)的[类型和将使用的渠道而异。 有关详细信息，请参阅[特定配置](#transactional-event-specific-configurations)。

完成配置后，必须发布事件。 请参阅[发布事务事件](../../channels/using/publishing-transactional-event.md)。

## 创建一个事件 {#creating-an-event}

要开始，请创建与您的需求对应的事件。

1. 单击左上角的 **[!UICONTROL Adobe Campaign]** 徽标，然后选择 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**。
1. 单击 **[!UICONTROL Create]** 按钮。
1. 输入&#x200B;**[!UICONTROL Label]**&#x200B;和&#x200B;**[!UICONTROL ID]**&#x200B;作为事件。 **[!UICONTROL ID]**&#x200B;字段为必填字段，应以前缀“EVT”开头。 如果不使用此前缀，则单击&#x200B;**[!UICONTROL Create]**&#x200B;后会自动添加该前缀。

   ![](assets/message-center_1.png)

   >[!IMPORTANT]
   >
   >ID不能超过64个字符，包括EVT前缀。

1. 选择将用于发送事务性消息&#x200B;**[!UICONTROL Email]**、**[!UICONTROL Mobile (SMS)]**&#x200B;或&#x200B;**[!UICONTROL Push notification]**&#x200B;的渠道。 每个渠道只能使用一个事件，之后无法更改。

1. 选择与所需定位维度配置对应的事件，然后单击&#x200B;**[!UICONTROL Create]**。

   基于事件的事务性消息目标数据包含在事件本身中，而基于用户档案的事务性消息目标数据包含在Adobe Campaign数据库中。 有关详细信息，请参阅[特定配置](#transactional-event-specific-configurations)。

>[!NOTE]
>
>交易事件的数量可能会对您的平台产生影响。 要确保最佳性能，请确保删除未使用的事件。 请参阅[删除事件](../../channels/using/publishing-transactional-event.md#deleting-an-event)。

## 定义事件属性{#defining-the-event-attributes}

在&#x200B;**[!UICONTROL Fields]**&#x200B;部分中，定义将集成到事件内容中的属性，然后将能够用于个性化事务性消息。

添加和修改字段的步骤与[自定义资源](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)的步骤相同。

![](assets/message-center_2.png)

>[!NOTE]
>
>如果要创建多语种事务性消息，请使用&#x200B;**[!UICONTROL AC_language]** ID定义其他事件属性。 这仅适用于事件事务性消息。 发布事件后，编辑多语言事务性消息内容的步骤与编辑多语言标准电子邮件的步骤相同。 请参阅[创建多语言电子邮件](../../channels/using/creating-a-multilingual-email.md)。

## 定义数据集{#defining-data-collections}

您可以向事件内容添加一组元素，每个元素本身都包含若干属性。

此集合可在交易电子邮件中用于将[产品列表](../../designing/using/using-product-listings.md)添加到邮件内容，例如产品列表 — 价格、参考编号、数量等。 为列表的每个产品。

1. 在&#x200B;**[!UICONTROL Collections]**&#x200B;部分，单击&#x200B;**[!UICONTROL Create element]**&#x200B;按钮。

   ![](assets/message-center_collection_create.png)

1. 为您的集合添加标签和ID。
1. 为事务性消息的每个产品添加要在列表中显示的所有字段。

   在此示例中，我们添加了以下字段：

   ![](assets/message-center_collection_fields.png)

1. **[!UICONTROL Enrichment]**&#x200B;选项卡允许您丰富集合的每个项目。 这样，您就可以使用Adobe Campaign数据库或您创建的其他资源中的信息，对相应产品列表的元素进行个性化设置。

>[!NOTE]
>
>丰富集合元素的步骤与[富化事件](#enriching-the-transactional-message-content)部分中所述的步骤相同。 请注意，丰富事件不会允许您丰富集合：您需要在&#x200B;**[!UICONTROL Collections]**&#x200B;部分向集合本身添加扩充。

发布事件和消息后，您将能够在事务性消息中使用此集合。

以下是此示例的API预览:

![](assets/message-center_collection_api-preview.png)

**相关主题：**

* [预览和发布事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)
* [在事务型消息中使用产品清单](../../designing/using/using-product-listings.md)
* [发布事务型消息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)

## 丰富事件{#enriching-the-transactional-message-content}

您可以使用来自事务性消息数据库的信息丰富Adobe Campaign内容，以便个性化您的消息。 例如，从每个收件人的姓氏或CRM ID中，您可以恢复用户档案表中添加的数据（如其地址、出生日期或任何其他自定义字段），以便对发送给他们的信息进行个性化设置。

可以使用扩展&#x200B;**[!UICONTROL Profile and services Ext API]**&#x200B;中的信息来丰富事务性消息内容。 有关详细信息，请参阅[扩展API:发布扩展](../../developing/using/step-2--publish-the-extension.md)

此信息也可以存储在新资源中。 在这种情况下，必须直接或通过其他表将资源链接到&#x200B;**[!UICONTROL Profile]**&#x200B;或&#x200B;**[!UICONTROL Service]**&#x200B;资源。 例如，在以下配置中，如果&#x200B;**[!UICONTROL Product]**&#x200B;资源链接到&#x200B;**[!UICONTROL Profile]**&#x200B;资源，则可以使用&#x200B;**[!UICONTROL Product]**&#x200B;资源(如产品类别或ID)中的信息来丰富事务性消息内容。

![](assets/message-center_usecaseschema.png)

有关创建和发布资源的详细信息，请参阅[此部分](../../developing/using/key-steps-to-add-a-resource.md)。

1. 在&#x200B;**[!UICONTROL Enrichment]**&#x200B;部分，单击&#x200B;**[!UICONTROL Create element]**&#x200B;按钮。

   ![](assets/message-center_addenrichment.png)

1. 选择要将消息链接到的资源。 在这种情况下，请选择&#x200B;**[!UICONTROL Profile]**&#x200B;资源。

   ![](assets/message-center_new-enrichment.png)

1. 使用&#x200B;**[!UICONTROL Create element]**&#x200B;按钮将选定资源中的字段链接到之前添加到事件的字段之一(请参阅[定义事件属性](#defining-the-event-attributes))。

   ![](assets/message-center_enrichment-join.png)

1. 在此示例中，我们将&#x200B;**[!UICONTROL Last name]**&#x200B;和&#x200B;**[!UICONTROL First name]**&#x200B;字段与&#x200B;**[!UICONTROL Profile]**&#x200B;资源中的相应字段进行协调。

   ![](assets/message-center_enrichment-join-fields.png)

   您还可以使用&#x200B;**[!UICONTROL Service]**&#x200B;资源丰富事务性消息内容。 有关服务的详细信息，请参阅[此部分](../../audiences/using/creating-a-service.md)。

1. 如果要创建或编辑[基于用户档案的事件](#profile-based-transactional-messages)，请在&#x200B;**[!UICONTROL Targeting enrichment]**&#x200B;部分中选择将在投放执行期间用作消息目标的扩充。

   ![](assets/message-center_marketing_targeting_enrichment.png)

   >[!NOTE]
   >
   >对于基于扩充的扩充，必须创建事件并基于&#x200B;**[!UICONTROL Profile]**&#x200B;资源选择定位用户档案。

发布事件和消息后，此链接将允许您丰富事务性消息的内容。

**相关主题：**

* [预览和发布事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)
* [个性化事务型消息](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)
* [发布事务型消息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)

## 搜索事务事件{#searching-transactional-events}

要访问和搜索已创建的事务事件，请执行以下步骤。

1. 单击左上角的 **[!UICONTROL Adobe Campaign]** 徽标，然后选择 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**。
1. 单击 **[!UICONTROL Show search]** 按钮。

   ![](assets/message-center_search-events.png)

1. 可以在&#x200B;**[!UICONTROL Publication status]**&#x200B;上进行筛选。 这允许您仅显示已发布的事件（例如）。
1. 您还可以使用&#x200B;**[!UICONTROL Last event received]**&#x200B;筛选事件。 例如，如果输入10，则只会显示事件配置，该配置具有10天前或更久前收到的上次事件。 这样，您就可以显示哪些事件在指定期间处于非活动状态。

   ![](assets/message-center_last-event-received.png)

   >[!NOTE]
   >
   >默认值为0。 随后将显示所有事件。

## 特定配置{#transactional-event-specific-configurations}

事务事件配置可能因您要发送的事务性消息](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types)类型(事件或用户档案)和将使用的渠道而异。[

以下各节详细介绍了应根据所需事务性消息设置哪些特定配置。 有关配置事件的一般步骤的详细信息，请参阅[创建事件](#creating-an-event)。

### 基于事件的事务性消息{#event-based-transactional-messages}

您可以发送定向某个事件的事件事务型消息。此类事务型消息不包含用户档案信息：根据事件本身包含的数据定义投放目标。

要发送基于事件的事务性消息，您首先需要创建并配置一个事件，以事件本身包含的&#x200B;**数据为目标。**

1. 创建事件配置时，请选择&#x200B;**[!UICONTROL Real-time event]**&#x200B;定位维度(请参阅[创建事件](#creating-an-event))。
1. 为事件添加字段，以便能够个性化事务性消息(请参阅[定义事件属性](#defining-the-event-attributes))。
1. 基于事件的事务型消息，应仅使用已发送事件中的数据来定义收件人和个性化消息内容。

   但是，如果要使用Adobe Campaign事务性消息库中的其他信息，则可以丰富事务性消息内容（请参阅[丰富内容](#enriching-the-transactional-message-content)）。

1. 预览并发布事件(请参阅[预览和发布事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event))。

   在预览事件时，REST API包含一个属性，该属性根据所选渠道指定电子邮件地址、手机或推送通知特定属性。

   事件发布后，将自动创建链接到新事件的事务性消息。 要使事件触发发送事务性消息，您必须[modify](../../channels/using/editing-transactional-message.md)和[publish](../../channels/using/publishing-transactional-message.md)刚创建的消息。

1. 将事件集成到您的网站中(请参阅[集成触发的事件](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger))。

### 基于用户档案的事务性消息{#profile-based-transactional-messages}

您可以根据客户用户档案发送事务性消息，这允许您应用营销类型规则，包括取消订阅链接，将消息添加到全球投放报告，并在客户旅程中利用它。

要发送基于用户档案的事务性消息，您首先需要创建并配置Adobe Campaign数据库&#x200B;**中的事件目标**&#x200B;数据。

1. 创建事件配置时，请选择&#x200B;**[!UICONTROL Profile event]**&#x200B;定位维度(请参阅[创建事件](#creating-an-event))。
1. 为事件添加字段，以便能够个性化事务性消息(请参阅[定义事件属性](#defining-the-event-attributes))。 必须至少添加一个字段才能创建扩充。 您无需创建其他字段，如&#x200B;**First name**&#x200B;和&#x200B;**Last name**，因为您将能够使用Adobe Campaign数据库中的个性化字段。
1. 创建扩充以将事件链接到&#x200B;**[!UICONTROL Profile]**&#x200B;资源(请参阅[丰富事件](#enriching-the-transactional-message-content))，并选择此扩充作为&#x200B;**[!UICONTROL Targeting enrichment]**。

   >[!IMPORTANT]
   >
   >对于基于用户档案的事件，此步骤是必需的。

1. 预览并发布事件(请参阅[预览和发布事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event))。

   预览事件时，REST API不包含指定电子邮件地址、手机或推送通知特定属性的属性，因为将从&#x200B;**[!UICONTROL Profile]**&#x200B;资源检索该属性。

   事件发布后，将自动创建链接到新事件的事务性消息。 要使事件触发发送事务性消息，您必须[modify](../../channels/using/editing-transactional-message.md)和[publish](../../channels/using/publishing-transactional-message.md)刚创建的消息。

1. 将事件集成到您的网站中(请参阅[集成触发的事件](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger))。

<!--### Transactional SMS messages {#transactional-sms}

The steps to configure an  event to send an SMS transactional message are the same as for the email channel. The only differences are as follows:

* When creating the corresponding event, you need to select the **[!UICONTROL Mobile (SMS)]** channel.

* When previewing the event corresponding to an event-based transactional SMS, the REST API contains an attribute specifying the mobile phone instead of the email address.

* The specificities to edit the content of an SMS transactional message are the same as for a [standard SMS](../../channels/using/about-sms-and-push-content-design.md).-->

### 事务型推送通知 {#transactional-push-notifications}

可以发送两种类型的事务推送通知：
* 向已选择接收移动应用程序通知的所有用户发送的匿名交易推送通知。 请参阅[配置基于事件的事务推送通知](../../channels/using/transactional-push-notifications.md#event-based-transactional-push-notifications)。
* 向已订阅您的移动应用程序的Adobe Campaign用户档案发送的交易推送通知。 请参阅[配置基于用户档案的事务推送通知](../../channels/using/transactional-push-notifications.md#profile-based-transactional-push-notifications)。

>[!IMPORTANT]
>
>要能够发送交易推送通知，您需要相应地配置Adobe Campaign。 请参阅[配置移动应用程序](../../administration/using/configuring-a-mobile-application.md)。

### 跟进消息 {#follow-up-messages}

您可以向收到特定事务性消息的客户发送跟进消息。

配置允许发送后续消息的事件的步骤详见[本节](../../channels/using/follow-up-messages.md#configuring-an-event-to-send-a-follow-up-message)。
