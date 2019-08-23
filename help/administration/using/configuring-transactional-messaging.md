---
title: 配置交易消息
seo-title: 配置交易消息
description: 配置交易消息
seo-description: 了解如何配置交易消息。
page-status-flag: 从未激活
uuid: caeadbe-f4 a7-43ce-986d-e99 fa9 ca0 d0 d
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: 配置渠道
discoiquuid: 3f968556-e774-43dc-a0 b8-7188d7665 fbc
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 8800562922e68d33cca93cd838c294198b630684

---


# 配置交易消息{#configuring-transactional-messaging}

要使用Adobe Campaign发送交易消息，您首先需要描述活动数据的结构。

活动配置必须 **由管理员** 执行，以下步骤如下：

配置可能因要发送的事务消息类型而异。有关此问题的详细信息，请参阅 [特定于事务的配置。](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations)

发布活动后，会自动创建相应的交易消息。有关交易消息的更多信息，请参阅 [此页](../../channels/using/about-transactional-messaging.md)。

## 创建活动 {#creating-an-event}

首先根据需要创建活动。

1. 单击左上角 **[!UICONTROL Adobe Campaign]** 的标志，然后选择 **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]**。
1. 单击 **[!UICONTROL Create]** 按钮。
1. 为活动提供一个 **[!UICONTROL Label]** 和一个 **[!UICONTROL ID]** 。**[!UICONTROL ID]** 字段为必填字段，应以前缀“EVT”开头。如果您不使用此前缀，单击 **[!UICONTROL Create]**&#x200B;后将自动添加该前缀。

   ![](assets/message-center_1.png)

   >[!CAUTION]
   >
   >ID不得超过64个字符，包括EVT前缀。

1. 选择将用于发送交易消息 **[!UICONTROL Email]**&#x200B;的渠道或 **[!UICONTROL Mobile (SMS)]****[!UICONTROL Mobile application]** (推送通知)。

   >[!NOTE]
   >
   >每个活动配置只能使用一个频道。创建活动后，您无法更改渠道。

1. 选择与所需活动配置对应的定位维度，然后单击 **[!UICONTROL Create]**。

   事件本身包含基于事件的交易消息目标数据，而基于个人资料的交易消息目标数据包含在Adobe Campaign数据库中。有关此问题的详细信息，请参阅 [Transactional事件特定配置](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations)。

## 定义活动属性 {#defining-the-event-attributes}

**[!UICONTROL Fields]** 在部分中，定义将集成到活动内容中的属性，然后可用于个性化交易消息。

添加和修改字段的步骤与 [自定义资源](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)相同。

![](assets/message-center_2.png)

>[!NOTE]
>
>如果要创建多语言交易消息，请使用 **[!UICONTROL AC_language]** ID定义其他事件属性。这仅适用于活动交易消息。发布活动后，编辑多语言事务消息内容的步骤与多语言标准电子邮件相同。请参阅 [创建多语言电子邮件](../../channels/using/creating-a-multilingual-email.md)。

## 定义数据集合 {#defining-data-collections}

您可以向活动内容添加一组元素，每个元素本身包括多个属性。

此集合可用于交易电子邮件中，将产品列表添加到消息内容(例如产品列表)中，例如价格、引用编号、数量等。列表的每个产品。

1. **[!UICONTROL Collections]** 在部分中，单击 **[!UICONTROL Create element]** 按钮。

   ![](assets/message-center_collection_create.png)

1. 为集合添加标签和ID。
1. 在列表的每个产品中添加要显示的所有字段。

   在此示例中，我们添加了以下字段：

   ![](assets/message-center_collection_fields.png)

活动和消息发布后，您将能够在您的交易消息中使用此集合。

以下是此示例的API预览：

![](assets/message-center_collection_api-preview.png)

**相关主题：**

* [预览和发布活动](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)
* [在交易消息中使用产品列表](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)

## 丰富交易消息内容 {#enriching-the-transactional-message-content}

利用Adobe Campaign数据库中的信息丰富交易消息内容使您能够个性化消息。例如，从每个收件人的姓氏或CRM ID，您可以恢复数据(例如，他们的地址或出生日期)或配置文件表中添加的任何其他自定义字段，以便个性化发送给他们的信息。

利用来自扩展 **[!UICONTROL Profile]** 或 **[!UICONTROL Service]** 资源的信息，可以丰富交易消息内容。

此信息也可存储在新资源中。在这种情况下，资源必须直接链接到或 **[!UICONTROL Profile]****[!UICONTROL Service]** 资源，或者通过其他表链接到资源。例如，在下面的配置中，如果资源链接到资源，则可以使用来自产品类别或ID等 **[!UICONTROL Product]** 资源的信息丰富 **[!UICONTROL Product]** 交易消息 **[!UICONTROL Profile]** 内容。

![](assets/message-center_usecaseschema.png)

有关资源创建和发布的更多信息，请参阅 [此页面](../../developing/using/key-steps-to-add-a-resource.md)。

1. **[!UICONTROL Enrichment]** 在部分中，单击 **[!UICONTROL Create element]** 按钮。

   ![](assets/message-center_addenrichment.png)

1. 选择要与之链接的资源。在这种情况下，请选择 **[!UICONTROL Profile]** 资源。

   ![](assets/message-center_new-enrichment.png)

1. 使用 **[!UICONTROL Create element]** 该按钮将一个字段从选定资源链接到之前添加到活动中的一个字段(请参阅 [定义活动属性](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes))。

   ![](assets/message-center_enrichment-join.png)

1. 在此示例中，我们将与 **[!UICONTROL Last name]** 资源中相应字段的 **[!UICONTROL First name]** 字段和解调整 **[!UICONTROL Profile]** 。

   ![](assets/message-center_enrichment-join-fields.png)

1. **[!UICONTROL Targeting enrichment]** 在部分中，选择将在提交执行过程中用作消息目标的丰富化。在此示例中，选择 **[!UICONTROL Profile]**。对于基于个人资料的活动，必须选择定位丰富化。

   ![](assets/message-center_marketing_targeting_enrichment.png)

活动和消息发布后，包含 **[!UICONTROL Profile]** 资源的链接将允许您丰富交易消息的内容。

**相关主题：**

* [预览和发布活动](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)。
* [个性化交易消息](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)。

## 预览和发布活动 {#previewing-and-publishing-the-event}

在使用活动之前，您必须预览并发布该活动。

1. 单击 **[!UICONTROL API preview]** 该按钮可查看REST API的模拟，网站开发人员在发布之前将使用该API。发布活动后，此按钮还允许您查看生产中API的预览。请参阅 [将活动的触发集成到网站](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)中。

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST API根据选定的渠道和选定的定位维度而异。有关各种配置的详细信息，请参阅 [Transactional事件特定配置](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations)。

1. 单击 **[!UICONTROL Publish]** 以开始发布。

   ![](assets/message-center_pub.png)

1. 您可以通过选择相应的选项卡来查看发布日志。

   ![](assets/message-center_logs.png)

   您还可以通过选择选项卡来查阅以前的出版物。

>[!NOTE]
>
>每次修改活动时，必须再次单击 **[!UICONTROL Publish]** 以生成由网站开发人员使用的更新的REST API。

活动发布后，将自动创建链接到新活动的事务消息。为了使此活动触发发送交易消息，您必须修改并发布刚刚创建的消息。请参阅 [活动交易消息](../../channels/using/event-transactional-messages.md)。

您可以访问直接从左侧区域的链接创建的事务消息。

![](assets/message-center_messagegeneration.png)

您还必须将此触发器事件集成到您的网站中。请参阅 [将活动的触发集成到网站](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)中。

### 取消发布活动 {#unpublishing-an-event}

**[!UICONTROL Unpublish]** 该按钮允许您取消活动的发布，该活动从REST API中删除与您先前创建的事件对应的资源。现在，即使活动通过您的网站触发，相应的消息也不会再发送，而且它们不会存储在数据库中。

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>如果您已经发布了相应的交易消息，则交易消息发布也会被取消。请参阅 [取消发布交易消息](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message)。

单击 **[!UICONTROL Publish]** 按钮以生成新的REST API。

## 将活动触发集成到网站 {#integrating-the-triggering-of-the-event-in-a-website}

创建活动后，您必须将此事件的触发集成到网站中。

在 [Transactional Messaging操作原理](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) 部分所述的示例中，您希望在客户在购物车购买产品之前离开网站时触发“购物车废弃”事件。为此，网站Web开发人员必须使用Adobe Campaign Standard REST API。

请参阅 [REST API文档](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#transactional-messages-api) 。

## 特定于活动的活动配置 {#transactional-event-specific-configurations}

交易活动配置可能因您要发送的交易消息类型(活动或配置文件)以及将使用的渠道而异。

以下部分详细介绍了应根据所需的交易消息设置特定配置的详细信息。有关配置活动的一般步骤，请参阅 [创建活动](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。

### 基于事件的交易消息 {#event-based-transactional-messages}

要发送基于事件的交易消息，您首先需要创建和配置一个事件，以定位活动本身包含的数据。
有关更多信息，请参阅 [使用事务性消息传递](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)。

1. 创建活动配置时，请选择 **[!UICONTROL Real-time event]** 定位维度(请参阅 [创建活动](../../administration/using/configuring-transactional-messaging.md#creating-an-event))。
1. 为活动添加字段，以便能够个性化事务消息(请参阅 [定义活动属性](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes))。
1. 如果您希望使用来自Adobe Campaign数据库的其他信息(请参阅 [丰富交易消息内容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content))，请丰富交易消息内容。

   >[!NOTE]
   >
   >基于事件的交易消息应仅使用已发送事件中的数据来定义接收者和消息内容个性化。但是，您可以使用Adobe Campaign数据库中的信息丰富交易消息的内容。

1. 预览并发布活动(请参阅 [预览和发布活动](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event))。

   预览事件时，REST API包含根据选定频道指定电子邮件地址或手机的属性。

   活动发布后，将自动创建链接到新活动的事务消息。要使活动触发发送事务消息，您必须修改并发布刚刚创建的消息，请参阅 [活动事务消息](../../channels/using/event-transactional-messages.md)。

1. 将活动集成到您的网站中(请参阅 [集成网站中的活动触发](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website))。

### 基于个人资料的交易消息 {#profile-based-transactional-messages}

要发送基于个人资料的交易消息，您首先需要创建和配置Adobe Campaign数据库中包含的活动定位数据。

1. 创建活动配置时，请选择 **[!UICONTROL Profile event]** 定位维度(请参阅 [创建活动](../../administration/using/configuring-transactional-messaging.md#creating-an-event))。
1. 为活动添加字段，以便能够个性化事务消息(请参阅 [定义活动属性](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes))。您必须添加至少一个字段才能创建丰富内容。您无需创建其他字段(如 **名字** 和 **姓氏)，** 因为您能够使用Adobe Campaign数据库中的个性化字段。
1. 创建丰富性，以便将活动链接到 **[!UICONTROL Profile]** 资源(请参阅 [丰富交易消息内容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content))。在使用 **[!UICONTROL Profile]** 定位维度时，创建丰富是必需的。
1. 预览并发布活动(请参阅 [预览和发布活动](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event))。

   预览事件时，REST API不包含指定电子邮件地址或手机将从 **[!UICONTROL Profile]** 资源检索的属性。

   活动发布后，将自动创建链接到新活动的事务消息。要使活动触发发送事务消息，您必须修改并发布刚才创建的消息，请参阅 [发送配置文件事务消息](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message)。

1. 将活动集成到您的网站中(请参阅 [集成网站中的活动触发](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website))。

### 基于事件的交易推送通知 {#event-based-transactional-push-notifications}

要发送交易推送通知，您需要相应地配置Adobe Campaign。请参阅 [推送配置](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)。

要向选择接收移动应用程序接收通知的所有用户发送匿名交易推送通知，您首先需要创建并配置一个事件定位活动中包含的数据。以下步骤如下所示。

该事件必须包含以下三个元素：

* **注册令牌**，它是一个手机应用程序和一个设备的用户ID。它可能与Adobe Campaign数据库中的任何配置文件不对应。
* **移动应用程序名称** (适用于所有设备- Android和iOS)。这是在Adobe Campaign中配置的移动应用程序的ID，用于接收用户设备上的推送通知。有关此操作的详细信息，请参阅此 [页面](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* **推送平台** (“gcm”for Android或“apns”for iOS)。

1. 创建活动配置时，选择 **[!UICONTROL Mobile application]** 渠道和 **[!UICONTROL Real-time event]** 定位维度(请参阅 [创建活动](../../administration/using/configuring-transactional-messaging.md#creating-an-event))。
1. 为活动添加字段，以便能够个性化事务消息(请参阅 [定义活动属性](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes))。
1. 如果您希望使用来自Adobe Campaign数据库的其他信息(请参阅 [丰富交易消息内容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content))，请丰富交易消息内容。

   >[!NOTE]
   >
   >基于事件的交易消息应仅使用已发送事件中的数据来定义接收者和消息内容个性化。但是，您可以使用Adobe Campaign数据库中的信息丰富交易消息的内容。

1. 预览并发布活动(请参阅 [预览和发布活动](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event))。

   预览事件时，REST API包含将用于定位交付的“registrationToken”、“application”和“pushPlatform”属性。

   ![](assets/message-center_push_api.png)

   发布活动后，将自动创建链接到新活动的事务推送通知。要修改和发布刚刚创建的消息，请参阅 [发送面向活动](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-an-event)的交易推送通知。

1. 将活动集成到您的网站中(请参阅 [集成网站中的活动触发](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website))。

### 基于个人资料的交易推送通知 {#profile-based-transactional-push-notifications}

要向已订阅移动应用程序的Adobe Campaign配置文件发送交易推送通知，您首先需要创建和配置一个定位Adobe Campaign数据库的活动。

1. 创建活动配置时，选择 **[!UICONTROL Mobile application]** 渠道和 **[!UICONTROL Profile]** 定位维度(请参阅 [创建活动](../../administration/using/configuring-transactional-messaging.md#creating-an-event))。

   默认情况下，交易推送通知将发送到接收订阅的所有移动应用程序。要将推送通知发送到特定的手机应用程序，请在列表中选择该通知。其他移动应用程序将被消息锁定，但将从发送中排除。

   ![](assets/message-center_push_appfilter.png)

1. 如果要个性化事务消息，请向活动中添加字段(请参阅 [定义活动属性](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes))。

   >[!NOTE]
   >
   >您必须添加至少一个字段才能创建丰富内容。您无需创建其他字段(如 **名字** 和 **姓氏)，** 因为您能够使用Adobe Campaign数据库中的个性化字段。

1. 创建丰富性，以便将活动链接到 **[!UICONTROL Profile]** 资源(请参阅 [丰富交易消息内容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content))。在使用 **[!UICONTROL Profile]** 定位维度时，创建丰富是必需的。
1. 预览并发布活动(请参阅 [预览和发布活动](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event))。

   预览事件时，REST API不包含指定注册令牌、应用程序名称和推送平台的属性，因为它们将从 **[!UICONTROL Profile]** 资源中检索。

   发布活动后，将自动创建链接到新活动的事务推送通知。要修改和发布刚刚创建的消息，请参阅 [发送面向配置文件的交易推送通知](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile)。

1. 将活动集成到您的网站中(请参阅 [集成网站中的活动触发](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website))。

### 配置活动以发送后续消息 {#configuring-an-event-to-send-a-follow-up-message}

后续消息是预定义的营销交付模板，可在工作流中使用该模板向收件人发送特定交易消息的消息。有关此操作的详细信息，请参阅 [跟进消息](../../channels/using/follow-up-messages.md)。

1. 使用您创建的与发送活动事务消息相同的事件配置。请参阅 [基于事件的交易消息](../../administration/using/configuring-transactional-messaging.md#event-based-transactional-messages)。
1. 配置活动时，请在发布活动之前选中 **[!UICONTROL Create follow-up delivery template for this event]** 该框。

   ![](assets/message-center_follow-up-checkbox.png)

1. 预览并发布活动(请参阅 [预览和发布活动](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event))。

   发布活动后，将自动创建与新活动关联的事务消息和后续交付模板。有关使用跟进消息的详细信息，请参阅 [发送后续消息](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)。

## 使用案例：配置活动以发送交易消息 {#use-case--configuring-an-event-to-send-a-transactional-message}

在此示例中，我们希望配置一个活动，以便在我们网站上每次购买后发送确认消息，并具有以下prerequi站点：

当我们希望通过他的CRM ID识别我们的客户端时，首先确保 **[!UICONTROL Profile]** 通过此新字段扩展资源。

同样，与购买对应的自定义资源必须已创建并发布，并且必须链接 **[!UICONTROL Profile]** 到资源。这样，您就可以从该资源检索信息以丰富消息内容。

有关资源创建和发布的更多信息，请参阅 [此页面](../../developing/using/key-steps-to-add-a-resource.md)。

1. 使用 **[!UICONTROL Email]** 渠道和 **[!UICONTROL Profile]** 定位维度创建新活动(请参阅 [创建活动](../../administration/using/configuring-transactional-messaging.md#creating-an-event))。
1. 定义可用于个性化交易消息的属性。在我们的情况下，添加“CRM ID”和“产品标识符”字段(请参阅 [定义事件属性](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes))。

   ![](assets/message-center_usecase1.png)

1. 要利用有关客户先前购买的信息丰富消息内容，请创建资源丰富定位( **[!UICONTROL Purchase]** 请参阅 [丰富交易消息内容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content))。

   ![](assets/message-center_usecase2.png)

1. 在之前添加到消息的“产品标识符”字段之间创建连接条件，并在 **[!UICONTROL Purchase]** 资源中创建相应的字段

   ![](assets/message-center_usecase3.png)

1. 预览并发布活动(请参阅 [预览和发布活动](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event))。
1. 将活动集成到网站中(请参阅 [集成网站](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)中的活动)。

