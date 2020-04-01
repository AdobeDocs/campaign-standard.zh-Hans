---
title: 配置交易消息传递
description: 了解如何配置交易消息传递。
page-status-flag: never-activated
uuid: 4caeadbe-f4a7-43ce-986d-e99fa9ca0d0d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 3f968556-e774-43dc-a0b8-7188d7665fbc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 34f4bbf7b7913cfb1833379c963b590961f7de73

---


# 配置交易消息传递{#configuring-transactional-messaging}

要发送带有Adobe Campaign的事务性消息，您首先需要描述事件数据的结构。

事件配置必须由管理员 **执行** ，具体步骤如下：

配置可能因您要发送的事务性消息类型而异。 有关详细信息，请参阅交易 [事件特定配置](#transactional-event-specific-configurations)

发布事件后，将自动创建相应的事务性消息。 For more on transactional messaging, refer to [this page](../../channels/using/about-transactional-messaging.md).

## 创建事件 {#creating-an-event}

开始，即创建与您的需求对应的事件。

1. 单击左 **[!UICONTROL Adobe Campaign]** 上角的标志，然后选择 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**。
1. Click the **[!UICONTROL Create]** button.
1. 给 **[!UICONTROL Label]** 事件 **[!UICONTROL ID]** 一个。 字 **[!UICONTROL ID]** 段是必填字段，应以前缀“EVT”开头。 如果您不使用此前缀，则单击后会自动添加该前缀 **[!UICONTROL Create]**。

   ![](assets/message-center_1.png)

   >[!IMPORTANT]
   >
   >ID不得超过64个字符，包括EVT前缀。

1. 选择将用于发送渠道的事务性消息或 **[!UICONTROL Email]**(推 **[!UICONTROL Mobile (SMS)]****[!UICONTROL Mobile application]** 送通知)。

   >[!NOTE]
   >
   >每个渠道配置只能使用一个事件。 创建事件后，便无法更改渠道。

1. 选择与所需的定位维度配置对应的事件，然后单击 **[!UICONTROL Create]**。

   事件本身包含的基于事务性消息的目标数据，而Adobe Campaign数据库中包含的基于用户档案的目标数据。 有关详细信息，请参阅 [交易事件特定配置](#transactional-event-specific-configurations)。

## 定义事件属性 {#defining-the-event-attributes}

在部 **[!UICONTROL Fields]** 分中，定义将集成到事件内容中并随后可用于个性化事务性消息的属性。

添加和修改字段的步骤与自定义资源的步 [骤相同](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)。

![](assets/message-center_2.png)

>[!NOTE]
>
>如果要创建多语言事务性消息，请使用该 **[!UICONTROL AC_language]** ID定义其他事件属性。 这仅适用于事件事务性消息。 发布事件后，编辑多语言事务性消息内容的步骤与编辑多语言标准电子邮件的步骤相同。 See [Creating a multilingual email](../../channels/using/creating-a-multilingual-email.md).

## 定义数据集合 {#defining-data-collections}

您可以向事件内容添加元素的集合，每个元素本身包括多个属性。

此集合可用于交易电子邮件中，以将产品列表添加到邮件内容中，例如产品列表-价格、参考编号、数量等。 为列表的每个产品。

1. 在部分 **[!UICONTROL Collections]** 中，单击该按 **[!UICONTROL Create element]** 钮。

   ![](assets/message-center_collection_create.png)

1. 为您的集合添加标签和ID。
1. 为事务性消息的每个产品添加要在列表中显示的所有字段。

   在此示例中，我们添加了以下字段：

   ![](assets/message-center_collection_fields.png)

发布事件和消息后，您便可以在事务性消息中使用此集合。

以下是此示例的API预览:

![](assets/message-center_collection_api-preview.png)

**相关主题：**

* [预览和发布事件](#previewing-and-publishing-the-event)
* [在事务性消息中使用产品列表](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)

## 丰富事务性消息内容 {#enriching-the-transactional-message-content}

通过从事务性消息数据库中丰富Adobe Campaign内容，使您能够个性化消息。 例如，从每个收件人的姓氏或CRM ID中，您可以恢复数据(如其地址、出生日期或用户档案表中添加的任何其他自定义字段)，以便对发送给他们的信息进行个性化设置。

可以利用来自扩展或资源的信息来丰富事务性消息 **[!UICONTROL Profile]** 内容 **[!UICONTROL Service]** 。

此信息也可以存储在新资源中。 在这种情况下，必须直接或通过其他表 **[!UICONTROL Profile]** 将资 **[!UICONTROL Service]** 源链接到或资源。 例如，在以下配置中，如果资源已链接到资源，则可以使用资源(如产品事务性消息或ID)中的信息来丰富 **[!UICONTROL Product]** 内容，如产品类别或 **[!UICONTROL Product]****[!UICONTROL Profile]** ID。

![](assets/message-center_usecaseschema.png)

有关资源创建和发布的详细信息，请参阅 [本页](../../developing/using/key-steps-to-add-a-resource.md)。

1. 在部分 **[!UICONTROL Enrichment]** 中，单击该按 **[!UICONTROL Create element]** 钮。

   ![](assets/message-center_addenrichment.png)

1. 选择要将消息链接到的资源。 在这种情况下，请选择资 **[!UICONTROL Profile]** 源。

   ![](assets/message-center_new-enrichment.png)

1. 使用 **[!UICONTROL Create element]** 按钮将选定资源中的字段链接到您之前添加到事件的某个字段(请参阅 [定义事件属性](#defining-the-event-attributes))。

   ![](assets/message-center_enrichment-join.png)

1. 在此示例中，我们将字段和 **[!UICONTROL Last name]** 字段 **[!UICONTROL First name]** 与资源中的相应字段进行协调 **[!UICONTROL Profile]** 。

   ![](assets/message-center_enrichment-join-fields.png)

   您还可以使用资源丰富事务性消息 **[!UICONTROL Service]** 内容。 有关服务的更多信息，请参阅此 [部分](../../audiences/using/creating-a-service.md)。

1. 如果要创建或编辑基于用户档案的事件，请在部 **[!UICONTROL Targeting enrichment]** 分中选择将在执行投放期间用作消息目标的扩充。

   ![](assets/message-center_marketing_targeting_enrichment.png)

   >[!NOTE]
   >
   >对于基于扩充的用户档案，必 **[!UICONTROL Profile]** 须根据资源选择定位事件。

发布事件和消息后，此链接将允许您丰富事务性消息的内容。

**相关主题：**

* [预览和发布事件](#previewing-and-publishing-the-event)。
* [个性化事务性消息](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)。

## 预览和发布事件 {#previewing-and-publishing-the-event}

在能够使用事件之前，您必须预览并发布它。

1. 单击 **[!UICONTROL API preview]** 该按钮可查看发布前网站开发人员将使用的REST API模拟。 发布事件后，此按钮还允许您在生产中查看API的预览。 请参 [阅在网站中集成事件的触发](#integrating-the-triggering-of-the-event-in-a-website)。

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST API会因所选渠道和所选定位维度而异。 有关各种配置的更多详细信息，请参阅 [Transactional事件特定配置](#transactional-event-specific-configurations)。

1. 单击 **[!UICONTROL Publish]** 以开始发布。

   ![](assets/message-center_pub.png)

1. 您可以视图相应选项卡中的发布日志。

   ![](assets/message-center_logs.png)

   >[!IMPORTANT]
   >
   >每次修改事件时，您必须再次单 **[!UICONTROL Publish]** 击以生成将由网站开发人员使用的更新的REST API。

   发布事件后，将自动创建链接到新事件的事务性消息。

1. 您可以通过位于左侧区域的链接直接访问此事务性消息。

   ![](assets/message-center_messagegeneration.png)

要使事件触发发送事务性消息，您必须修改并发布刚刚创建的消息。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).

您还必须将此触发事件集成到您的网站中。 请参 [阅在网站中集成事件的触发](#integrating-the-triggering-of-the-event-in-a-website)。

Adobe Campaign开始收到与此事件配置相关的事件后，通 **[!UICONTROL Latest transactional events]****[!UICONTROL History]** 过部分下方的链接，您可以访问第三方服务发送并由Adobe Campaign处理的最新事件。

![](assets/message-center_latest-events.png)

事件（JSON格式）从最新到最旧列出。 此列表允许您检查数据(如事件的内容或状态)，以便进行控制和调试。

### 取消发布事件 {#unpublishing-an-event}

通 **[!UICONTROL Unpublish]** 过该按钮可以取消事件的发布，该发布从REST API中删除与您先前创建的事件对应的资源。 现在，即使事件是通过您的网站触发的，相应的消息也不再发送，也不会存储在数据库中。

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>如果您已发布相应的事务性消息，则事务性消息发布也将被取消。 请参 [阅取消发布事务性消息](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message)。

单击该 **[!UICONTROL Publish]** 按钮可生成新的REST API。

### 删除事件 {#deleting-an-event}

事件取消发布后，或者事件尚未发布后，您可以从事件配置列表中删除该。 操作步骤：

1. 单击左 **[!UICONTROL Adobe Campaign]** 上角的标志，然后选择 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**。
1. 将鼠标悬停在您选择的事件配置上，然后选择按 **[!UICONTROL Delete element]** 钮。

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   >
   >确保事件配置具有状 **[!UICONTROL Draft]** 态，否则您将无法删除它。 状 **[!UICONTROL Draft]** 态适用于尚未发布或已取消发布的 [事件](#unpublishing-an-event)。

1. Click the **[!UICONTROL Confirm]** button.

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
>
>删除已发布且已使用的事件配置也会删除相应的事务性消息及其发送和跟踪日志。

## 集成网站中的事件触发 {#integrating-the-triggering-of-the-event-in-a-website}

创建事件后，您必须将此事件的触发集成到您的网站中。

在“交易消息传递操作原则 [](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) ”部分中描述的示例中，您希望当您的客户之一在购买购物车中的产品之前离开您的网站时，会触发“购物车放弃”事件。 为此，您的网站Web开发人员必须使用Adobe Campaign标准REST API。

请参阅 [REST API文档](../../api/using/managing-transactional-messages.md) 。

## 交易事件特定配置 {#transactional-event-specific-configurations}

交易事件配置可能因您要发送的事务性消息类型(事件或用户档案)以及将使用的渠道而异。

以下各节详细介绍了根据所需事务性消息应设置哪些特定配置。 有关配置事件的常规步骤的详细信息，请参阅 [创建事件](#creating-an-event)。

### 基于事件的事务性消息 {#event-based-transactional-messages}

要发送基于事件的事务性消息，您首先需要创建和配置一个事件，以定位事件本身包含的数据。
有关详细信息，请参 [阅使用交易消息](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)。

1. 创建事件配置时，选择定位维度(请 **[!UICONTROL Real-time event]** 参阅 [创建事件](#creating-an-event))。
1. 为事件添加字段，以便能够个性化事务性消息(请参阅定 [义事件属性](#defining-the-event-attributes))。
1. 如果要使用事务性消息数据库中的其他信息，可以丰富Adobe Campaign内容(请参 [阅丰富事务性消息内容](#enriching-the-transactional-message-content))。

   >[!NOTE]
   >
   >基于事件的交易消息传递应仅使用发送事件中的数据来定义收件人和消息内容个性化。 但是，您可以使用事务性消息数据库中的信息丰富Adobe Campaign的内容。

1. 预览并发布事件(请参 [阅预览和发布事件](#previewing-and-publishing-the-event))。

   预览事件时，REST API包含一个属性，该属性根据所选渠道指定电子邮件地址或手机。

   发布事件后，将自动创建链接到新事件的事务性消息。 要使事件触发发送事务性消息，您必须修改并发布刚刚创建的消息，请参阅 [事件事务性消息](../../channels/using/event-transactional-messages.md)。

1. 将事件集成到您的网站中(请 [参阅将事件的触发集成到网站](#integrating-the-triggering-of-the-event-in-a-website))。

### 基于用户档案的事务性消息 {#profile-based-transactional-messages}

要发送基于用户档案的事务性消息，您首先需要创建和配置Adobe Campaign数据库中包含的事件定位数据。

1. 创建事件配置时，选择定位维度(请 **[!UICONTROL Profile event]** 参阅 [创建事件](#creating-an-event))。
1. 为事件添加字段，以便能够个性化事务性消息(请参阅定 [义事件属性](#defining-the-event-attributes))。 您必须至少添加一个字段才能创建扩充。 您无需创建其他字段(如 **名** 、姓 **** )，因为您将能够使用Adobe Campaign数据库中的个性化字段。
1. 创建扩充以将事件链接到资源(请参 **[!UICONTROL Profile]** 阅丰 [富事务性消息内容](#enriching-the-transactional-message-content))。 使用扩充时，必须创建定位维度。 **[!UICONTROL Profile]**
1. 预览并发布事件(请参 [阅预览和发布事件](#previewing-and-publishing-the-event))。

   预览事件时，REST API不包含指定从资源检索电子邮件地址或手机的属 **[!UICONTROL Profile]** 性。

   发布事件后，将自动创建链接到新事件的事务性消息。 要使事件触发发送事务性消息，您必须修改并发布刚创建的消息，请参阅发 [送用户档案事务性消息](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message)。

1. 将事件集成到您的网站中(请 [参阅将事件的触发集成到网站](#integrating-the-triggering-of-the-event-in-a-website))。

### 基于事件的交易推送通知 {#event-based-transactional-push-notifications}

要能够发送交易推送通知，您需要相应地配置Adobe Campaign。 请参阅 [推送配置](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)。

要向已选择接收移动应用程序通知的所有用户发送匿名交易推送通知，您首先需要创建并配置一个事件，以定位事件本身包含的数据。 相应步骤如下。

事件必须包含以下三个元素：

* 注 **册令牌**，它是一个移动应用程序和一个设备的用户ID。 它可能与来自Adobe Campaign数据库的任何用户档案不对应。
* 移动 **应用程序名称** （适用于所有设备的名称- Android和iOS）。 这是在Adobe Campaign中配置的移动应用程序的ID，用于在用户设备上接收推送通知。 For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* 推 **送平台** （Android为“gcm”,iOS为“apns”）。

1. 创建事件配置时，选择 **[!UICONTROL Mobile application]** 渠道和定位维度 **[!UICONTROL Real-time event]** (请参 [阅创建事件](#creating-an-event))。
1. 为事件添加字段，以便能够个性化事务性消息(请参阅定 [义事件属性](#defining-the-event-attributes))。
1. 如果要使用事务性消息数据库中的其他信息，可以丰富Adobe Campaign内容(请参 [阅丰富事务性消息内容](#enriching-the-transactional-message-content))。

   >[!NOTE]
   >
   >基于事件的交易消息传递应仅使用发送事件中的数据来定义收件人和消息内容个性化。 但是，您可以使用事务性消息数据库中的信息丰富Adobe Campaign的内容。

1. 预览并发布事件(请参 [阅预览和发布事件](#previewing-and-publishing-the-event))。

   在预览事件时，REST API包含用于目标投放的“registrationToken”、“application”和“pushPlatform”属性。

   ![](assets/message-center_push_api.png)

   发布事件后，将自动创建链接到新事件的交易推送通知。 要修改并发布刚刚创建的消息，请参阅发 [送面向事件的交易推送通知](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-an-event)。

1. 将事件集成到您的网站中(请 [参阅将事件的触发集成到网站](#integrating-the-triggering-of-the-event-in-a-website))。

### 基于用户档案的交易推送通知 {#profile-based-transactional-push-notifications}

要向订阅了您的移动应用程序的Adobe Campaign用户档案发送交易推送通知，您首先需要创建和配置针对Adobe Campaign数据库的事件。

1. 创建事件配置时，选择 **[!UICONTROL Mobile application]** 渠道和定位维度 **[!UICONTROL Profile]** (请参 [阅创建事件](#creating-an-event))。

   默认情况下，事务推送通知将发送到收件人订阅的所有移动应用程序。 要将推送通知发送到特定移动应用程序，请在列表中选择它。 其他移动应用程序将被消息定位，但将被排除在发送之外。

   ![](assets/message-center_push_appfilter.png)

1. 如果要个性化事件，请向事务性消息添加字段(请参阅 [定义事件属性](#defining-the-event-attributes))。

   >[!NOTE]
   >
   >您必须至少添加一个字段才能创建扩充。 您无需创建其他字段(如 **名** 、姓 **** )，因为您将能够使用Adobe Campaign数据库中的个性化字段。

1. 创建扩充以将事件链接到资源(请参 **[!UICONTROL Profile]** 阅丰 [富事务性消息内容](#enriching-the-transactional-message-content))。 使用扩充时，必须创建定位维度。 **[!UICONTROL Profile]**
1. 预览并发布事件(请参 [阅预览和发布事件](#previewing-and-publishing-the-event))。

   预览事件时，REST API不包含指定注册令牌、应用程序名称和推送平台的属性，就像从资源检索它们一样 **[!UICONTROL Profile]** 。

   发布事件后，将自动创建链接到新事件的交易推送通知。 要修改并发布刚刚创建的消息，请参阅发 [送面向用户档案的交易推送通知](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile)。

1. 将事件集成到您的网站中(请 [参阅将事件的触发集成到网站](#integrating-the-triggering-of-the-event-in-a-website))。

### 配置事件以发送跟进消息 {#configuring-an-event-to-send-a-follow-up-message}

后续消息是预定义的营销投放模板，可用于在工作流中向特定事务性消息的收件人发送消息。 有关此方面的详细信息，请 [参阅后续消息](../../channels/using/follow-up-messages.md)。

1. 使用您创建的事件配置来发送事件事务性消息。 请参 [阅基于事件的事务性消息](#event-based-transactional-messages)。
1. 配置事件时，请在发布 **[!UICONTROL Create follow-up delivery template for this event]** 事件之前选中该框。

   ![](assets/message-center_follow-up-checkbox.png)

1. 预览并发布事件(请参 [阅预览和发布事件](#previewing-and-publishing-the-event))。

   发布事件后，将自动创建一个事务性消息和一个链接到新事件的后续投放模板。 有关使用跟进消息的详细信息，请 [参阅发送跟进消息](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)。

## 用例：配置事件以发送事务性消息 {#use-case--configuring-an-event-to-send-a-transactional-message}

在此示例中，我们要配置一个事件，以便在我们网站上的每次购买后发送确认消息，但前提条件如下：

由于我们希望通过其CRM ID识别我们的客户端，因此，首先，请确保已使用 **[!UICONTROL Profile]** 此新字段扩展了资源。

同样，必须已创建并发布与购买对应的自定义资源，并且必须将其链接到该资 **[!UICONTROL Profile]** 源。 这样，您就可以从该资源检索信息以丰富消息内容。

有关资源创建和发布的详细信息，请参阅 [本页](../../developing/using/key-steps-to-add-a-resource.md)。

1. 使用事件和渠道创建 **[!UICONTROL Email]** 新定位维度 **[!UICONTROL Profile]** (请参 [阅创建事件](#creating-an-event))。
1. 定义可用于个性化事务性消息的属性。 在我们的情况下，添加“CRM ID”和“产品标识符”字段(请参 [阅定义事件属性](#defining-the-event-attributes))。

   ![](assets/message-center_usecase1.png)

1. 要使用有关客户先前购买的信息丰富消息内容，请创建面向资源的扩充(请参 **[!UICONTROL Purchase]** 阅丰 [富事务性消息内容](#enriching-the-transactional-message-content))。

   ![](assets/message-center_usecase2.png)

1. 在以前添加到消息的“产品标识符”字段与资源中的相应字段之间创建连接条 **[!UICONTROL Purchase]** 件。

   ![](assets/message-center_usecase3.png)

1. 预览并发布事件(请参 [阅预览和发布事件](#previewing-and-publishing-the-event))。
1. 将事件集成到您的网站中(请 [参阅将事件的触发集成到网站](#integrating-the-triggering-of-the-event-in-a-website))。

