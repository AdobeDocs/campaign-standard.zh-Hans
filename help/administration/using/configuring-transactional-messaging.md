---
solution: Campaign Standard
product: campaign
title: 配置事务型消息传递
description: 了解如何配置事务消息传递。
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '3169'
ht-degree: 7%

---


# 配置事务型消息传递{#configuring-transactional-messaging}

要发送带有Adobe Campaign的事务性消息，您首先需要描述事件数据的结构。

事件配置必须由[administrator](../../administration/using/users-management.md#functional-administrators)按照以下步骤执行。

>[!NOTE]
>
>配置可能因您要发送的事务性消息类型而异。 有关详细信息，请参阅[事务事件特定配置](#transactional-event-specific-configurations)。

事件发布后：

* 将部署网站开发人员将使用的API，并且现在可以发送事务事件。 请参阅[在网站中集成事件的触发](#integrating-the-triggering-of-the-event-in-a-website)。

* 相应的事务性消息会自动创建。 请参阅[事务消息](../../channels/using/getting-started-with-transactional-msg.md)快速入门。

## 创建事件{#creating-an-event}

要开始，请创建与您的需求相对应的事件。

>[!IMPORTANT]
>
>只有具有&#x200B;**[!UICONTROL Administration]**&#x200B;角色并且是&#x200B;**[!UICONTROL All]** [组织单元](../../administration/using/organizational-units.md)的一部分的用户才具有创建事件配置的适当权限。

1. 单击左上角的 **[!UICONTROL Adobe Campaign]** 徽标，然后选择 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**。
1. 单击 **[!UICONTROL Create]** 按钮。
1. 为事件提供&#x200B;**[!UICONTROL Label]**&#x200B;和&#x200B;**[!UICONTROL ID]**。 **[!UICONTROL ID]**&#x200B;字段为必填字段，应以前缀“EVT”开头。 如果您不使用此前缀，则单击&#x200B;**[!UICONTROL Create]**&#x200B;后会自动添加该前缀。

   ![](assets/message-center_1.png)

   >[!IMPORTANT]
   >
   >ID不得超过64个字符，包括EVT前缀。

1. 选择将用于发送事务性消息&#x200B;**[!UICONTROL Email]**、**[!UICONTROL Mobile (SMS)]**&#x200B;或&#x200B;**[!UICONTROL Mobile application]**（推送通知）的渠道。

   >[!NOTE]
   >
   >每个事件配置只能使用一个渠道。创建事件后，便无法更改渠道。

1. 选择与所需定位维度配置对应的事件，然后单击&#x200B;**[!UICONTROL Create]**。

   基于事件的事务性消息目标数据包含在事件本身中，而基于用户档案的事务性消息目标数据包含在Adobe Campaign数据库中。 有关详细信息，请参阅[事务事件特定配置](#transactional-event-specific-configurations)。

>[!NOTE]
>
>创建的实时事件数量可能会影响您的平台。 为确保最佳性能，请确保删除不再需要的实时事件。 请参阅[删除事件](#deleting-an-event)。

## 定义事件属性{#defining-the-event-attributes}

在&#x200B;**[!UICONTROL Fields]**&#x200B;部分，定义将集成到事件内容中的属性，然后使用这些属性个性化事务性消息。

添加和修改字段的步骤与[自定义资源](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)的步骤相同。

![](assets/message-center_2.png)

>[!NOTE]
>
>如果要创建多语言事务性消息，请使用&#x200B;**[!UICONTROL AC_language]** ID定义一个附加的事件属性。 这仅适用于事件事务性消息。 发布事件后，编辑多语言事务性消息内容的步骤与编辑多语言标准电子邮件的步骤相同。 请参阅[创建多语言电子邮件](../../channels/using/creating-a-multilingual-email.md)。

## 定义数据集{#defining-data-collections}

您可以向事件内容添加元素集合，每个元素本身都包含多个属性。

此集合可用于交易电子邮件中，以将[产品列表](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)添加到邮件内容，例如产品列表-价格、参考编号、数量等。 列表的每个产品。

1. 在&#x200B;**[!UICONTROL Collections]**&#x200B;部分，单击&#x200B;**[!UICONTROL Create element]**&#x200B;按钮。

   ![](assets/message-center_collection_create.png)

1. 为您的集合添加标签和ID。
1. 为事务性消息的每个产品添加要在列表中显示的所有字段。

   在此示例中，我们添加了以下字段：

   ![](assets/message-center_collection_fields.png)

1. 使用&#x200B;**[!UICONTROL Enrichment]**&#x200B;选项卡可以丰富集合的每个项目。 这样，您就可以使用Adobe Campaign库或您创建的其他资源中的信息，个性化相应产品列表的元素。

>[!NOTE]
>
>富集集合元素的步骤与[富集事件](#enriching-the-transactional-message-content)一节中所述的步骤相同。 请注意，丰富事件不会允许您丰富集合：您需要在&#x200B;**[!UICONTROL Collections]**&#x200B;部分向集合本身添加扩充。

发布事件和消息后，您将能够在事务性消息中使用此集合。

以下是此示例的API预览:

![](assets/message-center_collection_api-preview.png)

**相关主题：**

* [预览和发布事件](#previewing-and-publishing-the-event)
* [在事务型消息中使用产品清单](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)

## 丰富事件{#enriching-the-transactional-message-content}

您可以使用事务性消息库中的信息丰富Adobe Campaign内容，从而个性化您的信息。 例如，从每个收件人的姓氏或CRM ID中，您可以恢复用户档案表中添加的数据（如其地址、出生日期或任何其他自定义字段），以个性化发送给他们的信息。

可以使用扩展&#x200B;**[!UICONTROL Profile and services Ext API]**&#x200B;中的信息丰富事务性消息内容。 有关详细信息，请参阅[扩展API:发布扩展](../../developing/using/step-2--publish-the-extension.md)

此信息也可以存储在新资源中。 在这种情况下，必须直接或通过其他表将资源链接到&#x200B;**[!UICONTROL Profile]**&#x200B;或&#x200B;**[!UICONTROL Service]**&#x200B;资源。 例如，在以下配置中，如果&#x200B;**[!UICONTROL Product]**&#x200B;资源链接到&#x200B;**[!UICONTROL Profile]**&#x200B;资源，则可以使用&#x200B;**[!UICONTROL Product]**&#x200B;资源(如产品类别或ID)中的信息来丰富事务性消息内容。

![](assets/message-center_usecaseschema.png)

有关资源创建和发布的详细信息，请参阅[此页](../../developing/using/key-steps-to-add-a-resource.md)。

1. 在&#x200B;**[!UICONTROL Enrichment]**&#x200B;部分，单击&#x200B;**[!UICONTROL Create element]**&#x200B;按钮。

   ![](assets/message-center_addenrichment.png)

1. 选择要将消息链接到的资源。 在这种情况下，请选择&#x200B;**[!UICONTROL Profile]**&#x200B;资源。

   ![](assets/message-center_new-enrichment.png)

1. 使用&#x200B;**[!UICONTROL Create element]**&#x200B;按钮将选定资源中的字段链接到之前添加到事件的某个字段(请参阅[定义事件属性](#defining-the-event-attributes))。

   ![](assets/message-center_enrichment-join.png)

1. 在此示例中，我们将&#x200B;**[!UICONTROL Last name]**&#x200B;和&#x200B;**[!UICONTROL First name]**&#x200B;字段与&#x200B;**[!UICONTROL Profile]**&#x200B;资源中的相应字段进行协调。

   ![](assets/message-center_enrichment-join-fields.png)

   您还可以使用&#x200B;**[!UICONTROL Service]**&#x200B;资源丰富事务性消息内容。 有关服务的详细信息，请参阅此[部分](../../audiences/using/creating-a-service.md)。

1. 如果创建或编辑基于用户档案的事件，请在&#x200B;**[!UICONTROL Targeting enrichment]**&#x200B;部分，选择将在投放执行过程中用作消息目标的扩充。

   ![](assets/message-center_marketing_targeting_enrichment.png)

   >[!NOTE]
   >
   >对于基于扩充的事件，必须根据&#x200B;**[!UICONTROL Profile]**&#x200B;资源选择定位用户档案。

发布事件和消息后，此链接将允许您丰富事务性消息的内容。

**相关主题：**

* [预览和发布事件](#previewing-and-publishing-the-event)。
* [个性化事务性消息](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)。

## 预览和发布事件{#previewing-and-publishing-the-event}

在能够使用事件之前，您必须预览并发布它。

1. 单击&#x200B;**[!UICONTROL API preview]**&#x200B;按钮，查看网站开发人员在发布前将使用的REST API的模拟。 发布事件后，此按钮还允许您在生产中查看API的预览。 请参阅[在网站中集成事件的触发](#integrating-the-triggering-of-the-event-in-a-website)。

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST API根据所选渠道和所选定位维度而有所不同。 有关各种配置的详细信息，请参阅[事务事件特定配置](#transactional-event-specific-configurations)。

1. 单击&#x200B;**[!UICONTROL Publish]**&#x200B;以开始发布。

   ![](assets/message-center_pub.png)

   将部署网站开发人员将使用的API，并且现在可以发送事务事件。

1. 您可以在相应的选项卡中视图发布日志。

   ![](assets/message-center_logs.png)

   >[!IMPORTANT]
   >
   >每次修改事件时，必须再次单击&#x200B;**[!UICONTROL Publish]**&#x200B;以生成将由网站开发人员使用的更新的REST API。

   事件发布后，将自动创建链接到新事件的事务性消息。

1. 您可以通过左侧区域的链接直接访问此事务性消息。

   ![](assets/message-center_messagegeneration.png)

要使事件触发发送事务性消息，您必须修改并发布刚创建的消息。 请参阅[事件事务型消息](../../channels/using/event-transactional-messages.md)。

您还必须将此触发事件集成到您的网站中。 请参阅[在网站中集成事件的触发](#integrating-the-triggering-of-the-event-in-a-website)。

Adobe Campaign开始收到与此事件配置相关的事件后，通过&#x200B;**[!UICONTROL History]**&#x200B;部分下的&#x200B;**[!UICONTROL Latest transactional events]**&#x200B;链接，可以访问第三方服务发送并由Adobe Campaign处理的最新事件。

![](assets/message-center_latest-events.png)

事件（JSON格式）从最新到最旧列出。 此列表允许您检查事件的内容或状态等数据，以便进行控制和调试。

### 取消发布事件{#unpublishing-an-event}

通过&#x200B;**[!UICONTROL Unpublish]**&#x200B;按钮可以取消事件的发布，该发布从REST API中删除与您先前创建的事件对应的资源。 现在，即使是通过您的网站触发了事件，也不再发送相应的消息，也不会将消息存储在数据库中。

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>如果您已发布相应的事务性消息，则事务性消息发布也会被取消。 请参阅[取消发布事务性消息](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message)。

单击&#x200B;**[!UICONTROL Publish]**&#x200B;按钮以生成新的REST API。

### 事务型消息传递发布流程 {#transactional-messaging-pub-process}

下图说明了事务型消息传递的发布流程。

![](assets/message-center_pub-process.png)

有关发布、暂停和取消发布事务性消息的详细信息，请参阅[此部分](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)。

### 删除事件{#deleting-an-event}

事件取消发布后，或者事件尚未发布后，您可以从事件配置列表中删除该。 操作步骤：

1. 单击左上角的 **[!UICONTROL Adobe Campaign]** 徽标，然后选择 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**。
1. 将鼠标悬停在您选择的事件配置上，然后选择&#x200B;**[!UICONTROL Delete element]**&#x200B;按钮。

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   >
   >确保事件配置具有&#x200B;**[!UICONTROL Draft]**&#x200B;状态，否则将无法删除它。 **[!UICONTROL Draft]**&#x200B;状态适用于尚未发布或已[未发布](#unpublishing-an-event)的事件。

1. 单击 **[!UICONTROL Confirm]** 按钮。

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
>
>删除已发布且已使用的事件配置也会删除相应的事务性消息及其发送和跟踪日志。

## 搜索事务事件{#searching-transactional-events}

要访问和搜索已创建的事务事件，请按照以下步骤操作。

1. 单击左上角的 **[!UICONTROL Adobe Campaign]** 徽标，然后选择 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**。
1. 单击 **[!UICONTROL Show search]** 按钮。

   ![](assets/message-center_search-events.png)

1. 可以在&#x200B;**[!UICONTROL Publication status]**&#x200B;上进行筛选。 这允许您仅显示已发布的事件（例如）。
1. 您还可以使用&#x200B;**[!UICONTROL Last event received]**&#x200B;筛选事件。 例如，如果输入10，则只显示上次事件在10天前或更久之前收到的事件配置。 这样，您就可以显示在给定期间中哪些事件处于非活动状态。

   ![](assets/message-center_last-event-received.png)

   >[!NOTE]
   >
   >默认值为0。 随后将显示所有事件。

## 在网站{#integrating-the-triggering-of-the-event-in-a-website}中集成事件的触发

创建事件后，您必须将触发此事件的操作集成到您的网站中。

在[交易消息操作原则](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)部分中描述的示例中，您希望当您的客户之一在购买购物车中的产品之前离开您的网站时，触发“购物车废弃”事件。 为此，您的网站Web开发人员必须使用Adobe Campaign StandardREST API。

请参阅[REST API文档](../../api/using/managing-transactional-messages.md)。

## 事务事件特定配置{#transactional-event-specific-configurations}

事务事件配置可能因您要发送的事务性消息类型(事件或用户档案)以及将使用的渠道而异。

以下各节详细介绍了根据所需事务性消息应设置哪些特定配置。 有关配置事件的一般步骤的详细信息，请参阅[创建事件](#creating-an-event)。

### 基于事件的事务性消息{#event-based-transactional-messages}

要发送基于事件的事务性消息，您首先需要创建和配置一个事件，以事件本身包含的数据为目标。
有关详细信息，请参阅[使用事务消息](https://helpx.adobe.com/cn/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)。

1. 创建事件配置时，选择&#x200B;**[!UICONTROL Real-time event]**&#x200B;定位维度(请参阅[创建事件](#creating-an-event))。
1. 为事件添加字段，以便能够个性化事务性消息(请参阅[定义事件属性](#defining-the-event-attributes))。
1. 如果要使用事务性消息库的其他信息，可以丰富Adobe Campaign内容(请参阅[丰富事务性消息内容](#enriching-the-transactional-message-content))。

   >[!NOTE]
   >
   >基于事件的事务型消息，应仅使用已发送事件中的数据来定义收件人和个性化消息内容。但是，您也可以使用 Adobe Campaign 数据库中的信息扩充事务型消息的内容。

1. 预览并发布事件(请参阅[预览和发布事件](#previewing-and-publishing-the-event))。

   预览事件时，REST API包含一个属性，该属性根据所选渠道指定电子邮件地址或移动电话。

   事件发布后，将自动创建链接到新事件的事务性消息。 要使事件触发发送事务性消息，您必须修改并发布刚创建的消息，请参阅[事件事务性消息](../../channels/using/event-transactional-messages.md)。

1. 将事件集成到您的网站中(请参阅[将事件的触发集成到网站](#integrating-the-triggering-of-the-event-in-a-website))。

### 基于用户档案的事务性消息{#profile-based-transactional-messages}

要发送基于用户档案的事务性消息，您首先需要创建和配置Adobe Campaign数据库中包含的事件定位数据。

1. 创建事件配置时，选择&#x200B;**[!UICONTROL Profile event]**&#x200B;定位维度(请参阅[创建事件](#creating-an-event))。
1. 为事件添加字段，以便能够个性化事务性消息(请参阅[定义事件属性](#defining-the-event-attributes))。 必须至少添加一个字段才能创建扩充。 您无需创建其他字段，如&#x200B;**名字**&#x200B;和&#x200B;**姓氏**，因为您将能够使用个性化字段库中的Adobe Campaign。
1. 创建扩充以将事件链接到&#x200B;**[!UICONTROL Profile]**&#x200B;资源(请参阅[丰富事务性消息内容](#enriching-the-transactional-message-content))。 使用&#x200B;**[!UICONTROL Profile]**&#x200B;扩充时，必须创建定位维度。
1. 预览并发布事件(请参阅[预览和发布事件](#previewing-and-publishing-the-event))。

   预览事件时，REST API不包含指定电子邮件地址或手机的属性，因为将从&#x200B;**[!UICONTROL Profile]**&#x200B;资源检索该属性。

   事件发布后，将自动创建链接到新事件的事务性消息。 要使事件触发发送事务性消息，您必须修改并发布刚创建的消息，请参阅[发送用户档案事务性消息](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message)。

1. 将事件集成到您的网站中(请参阅[将事件的触发集成到网站](#integrating-the-triggering-of-the-event-in-a-website))。

### 基于事件的事务推送通知{#event-based-transactional-push-notifications}

要能够发送事务推送通知，您需要相应地配置Adobe Campaign。 请参阅[推送配置](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdkv4.html)。

要向已选择接收移动应用程序通知的所有用户发送匿名交易推送通知，您首先需要创建并配置一个事件，以事件本身包含的数据为目标。 相应步骤如下。

事件必须包含以下三个元素：

* **注册令牌**，它是一个移动应用程序和一个设备的用户ID。 它可能不与来自用户档案库的任何Adobe Campaign对应。
* **移动应用程序名称**（所有设备均使用一个名称- Android和iOS）。 这是在Adobe Campaign中配置的用于在用户设备上接收推送通知的移动应用程序的ID。 有关详细信息，请参阅此[页面](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* **推送平台**（Android为“gcm”,iOS为“apns”）。

1. 创建事件配置时，选择&#x200B;**[!UICONTROL Mobile application]**&#x200B;渠道和&#x200B;**[!UICONTROL Real-time event]**&#x200B;定位维度(请参阅[创建事件](#creating-an-event))。
1. 为事件添加字段，以便能够个性化事务性消息(请参阅[定义事件属性](#defining-the-event-attributes))。
1. 如果要使用事务性消息数据库中的其他信息，请丰富Adobe Campaign内容(请参阅[丰富事务性消息内容](#enriching-the-transactional-message-content))。

   >[!NOTE]
   >
   >基于事件的事务型消息，应仅使用已发送事件中的数据来定义收件人和个性化消息内容。但是，您也可以使用 Adobe Campaign 数据库中的信息扩充事务型消息的内容。

1. 预览并发布事件(请参阅[预览和发布事件](#previewing-and-publishing-the-event))。

   预览事件时，REST API包含将用于目标投放的“registrationToken”、“application”和“pushPlatform”属性。

   ![](assets/message-center_push_api.png)

   事件发布后，将自动创建链接到新事件的事务推送通知。 要修改并发布刚刚创建的消息，请参阅[发送面向事件的事务推送通知](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-an-event)。

1. 将事件集成到您的网站中(请参阅[将事件的触发集成到网站](#integrating-the-triggering-of-the-event-in-a-website))。

### 基于用户档案的事务推送通知{#profile-based-transactional-push-notifications}

要向订阅了您的移动应用程序的Adobe Campaign用户档案发送事务推送通知，您首先需要创建并配置一个针对Adobe Campaign数据库的事件。

1. 创建事件配置时，选择&#x200B;**[!UICONTROL Mobile application]**&#x200B;渠道和&#x200B;**[!UICONTROL Profile]**&#x200B;定位维度(请参阅[创建事件](#creating-an-event))。

   默认情况下，事务推送通知将发送给收件人订阅的所有移动应用程序。 要将推送通知发送到特定移动应用程序，请在列表中选择它。 消息将瞄准其他移动应用程序，但将从发送中排除。

   ![](assets/message-center_push_appfilter.png)

1. 如果要个性化事件，请向事务性消息添加字段(请参阅[定义事件属性](#defining-the-event-attributes))。

   >[!NOTE]
   >
   >必须至少添加一个字段才能创建扩充。 您无需创建其他字段，如&#x200B;**名字**&#x200B;和&#x200B;**姓氏**，因为您将能够使用个性化字段库中的Adobe Campaign。

1. 创建扩充以将事件链接到&#x200B;**[!UICONTROL Profile]**&#x200B;资源(请参阅[丰富事务性消息内容](#enriching-the-transactional-message-content))。 使用&#x200B;**[!UICONTROL Profile]**&#x200B;扩充时，必须创建定位维度。
1. 预览并发布事件(请参阅[预览和发布事件](#previewing-and-publishing-the-event))。

   预览事件时，REST API不包含指定注册令牌、应用程序名称和推送平台的属性，因为它们将从&#x200B;**[!UICONTROL Profile]**&#x200B;资源中检索。

   事件发布后，将自动创建链接到新事件的事务推送通知。 要修改并发布刚刚创建的消息，请参阅[发送面向用户档案的事务推送通知](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile)。

1. 将事件集成到您的网站中(请参阅[将事件的触发集成到网站](#integrating-the-triggering-of-the-event-in-a-website))。

### 配置事件以发送后续消息{#configuring-an-event-to-send-a-follow-up-message}

后续消息是预定义的营销投放模板，可在工作流中用于向特定事务性消息的收件人发送消息。 有关详细信息，请参阅[后续消息](../../channels/using/follow-up-messages.md)。

1. 使用您创建的事件配置发送事件事务性消息。 请参阅[基于事件的事务性消息](#event-based-transactional-messages)。
1. 配置事件时，请在发布事件之前选中&#x200B;**[!UICONTROL Create follow-up delivery template for this event]**&#x200B;框。

   ![](assets/message-center_follow-up-checkbox.png)

1. 预览并发布事件(请参阅[预览和发布事件](#previewing-and-publishing-the-event))。

   发布事件后，将自动创建链接到新事件的事务性消息和后续投放模板。 有关使用跟进消息的详细信息，请参阅[发送跟进消息](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)。

## 用例：配置事件以发送事务性消息{#use-case--configuring-an-event-to-send-a-transactional-message}

在此示例中，我们要配置一个事件，以便在我们网站上的每次购买后，在满足以下先决条件的情况下发送确认消息：

当我们要通过其CRM ID来标识我们的客户端时，请首先确保&#x200B;**[!UICONTROL Profile]**&#x200B;资源已通过此新字段扩展。

同样，必须已创建并发布与购买对应的自定义资源，并且必须链接到&#x200B;**[!UICONTROL Profile]**&#x200B;资源。 这样，您将能够从此资源检索信息以丰富消息内容。

有关资源创建和发布的详细信息，请参阅[此页](../../developing/using/key-steps-to-add-a-resource.md)。

1. 使用&#x200B;**[!UICONTROL Email]**&#x200B;事件和&#x200B;**[!UICONTROL Profile]**&#x200B;定位维度创建新事件(请参阅[创建渠道](#creating-an-event))。
1. 定义可用于个性化事务性消息的属性。 在本例中，添加“CRM ID”和“产品标识符”字段(请参阅[定义事件属性](#defining-the-event-attributes))。

   ![](assets/message-center_usecase1.png)

1. 要使用有关客户端先前购买的信息丰富消息内容，请创建一个面向&#x200B;**[!UICONTROL Purchase]**&#x200B;资源的扩充(请参阅[丰富事务性消息内容](#enriching-the-transactional-message-content))。

   ![](assets/message-center_usecase2.png)

1. 在以前添加到消息的“产品标识符”字段和&#x200B;**[!UICONTROL Purchase]**&#x200B;资源中的相应字段之间创建连接条件。

   ![](assets/message-center_usecase3.png)

1. 预览并发布事件(请参阅[预览和发布事件](#previewing-and-publishing-the-event))。
1. 将事件集成到您的网站中(请参阅[将事件的触发集成到网站](#integrating-the-triggering-of-the-event-in-a-website))。

