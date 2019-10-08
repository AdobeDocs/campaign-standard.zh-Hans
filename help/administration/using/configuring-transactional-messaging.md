---
title: 配置事务消息传递
seo-title: 配置事务消息传递
description: 配置事务消息传递
seo-description: 了解如何配置交易消息传递。
page-status-flag: 从未激活
uuid: 4caeadbe-f4a7-43ce-986d-e99fa9ca0d0d
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 参考
topic-tags: 配置渠道
discoiquuid: 3f968556-e774-43dc-a0b8-7188d765fbc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 94c7649448aff859daaf2bbe9a4d17a5187ac71f

---


# 配置事务消息传递{#configuring-transactional-messaging}

要通过Adobe Campaign发送交易消息，您首先需要描述活动数据的结构。

活动配置必须由管理员 **执行** ，具体步骤如下：

配置可能因您要发送的事务消息类型而异。 有关此功能的详细信息，请参阅事 [务性事件特定配置](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations)

发布活动后，将自动创建相应的事务消息。 For more on transactional messaging, refer to [this page](../../channels/using/about-transactional-messaging.md).

## 创建活动 {#creating-an-event}

首先，创建与您的需求对应的活动。

1. 单击左 **[!UICONTROL Adobe Campaign]** 上角的标志，然后选择 **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]**。
1. Click the **[!UICONTROL Create]** button.
1. 为活 **[!UICONTROL Label]** 动提 **[!UICONTROL ID]** 供一个和一个。 字 **[!UICONTROL ID]** 段是必填字段，应以前缀“EVT”开头。 如果您不使用此前缀，则单击后会自动添加该前缀 **[!UICONTROL Create]**。

   ![](assets/message-center_1.png)

   >[!CAUTION]
   >
   >该ID不能超过64个字符，包括EVT前缀。

1. 选择用于发送交易消息的渠道， **[!UICONTROL Email]**&#x200B;或 **[!UICONTROL Mobile (SMS)]** ( **[!UICONTROL Mobile application]** 推送通知)。

   >[!NOTE]
   >
   >每个事件配置只能使用一个渠道。 创建活动后，便无法更改渠道。

1. 选择与所需事件配置对应的定位维度，然后单击 **[!UICONTROL Create]**。

   基于事件的事务性消息以事件本身包含的数据为目标，而基于配置文件的事务性消息以Adobe Campaign数据库中包含的数据为目标。 有关此功能的详细信息，请参 [阅事务性事件特定配置](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations)。

## 定义事件属性 {#defining-the-event-attributes}

在部 **[!UICONTROL Fields]** 分中，定义将集成到活动内容中的属性，然后使用这些属性个性化事务性消息。

添加和修改字段的步骤与自定义资源的步 [骤相同](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)。

![](assets/message-center_2.png)

>[!NOTE]
>
>如果要创建多语言事务消息，请使用 **[!UICONTROL AC_language]** ID定义其他事件属性。 这仅适用于活动事务消息。 活动发布后，编辑多语言交易消息内容的步骤与编辑多语言标准电子邮件的步骤相同。 请参阅 [创建多语言电子邮件](../../channels/using/creating-a-multilingual-email.md)。

## 定义数据集合 {#defining-data-collections}

您可以向活动内容添加元素的集合，每个元素本身包括多个属性。

此集合可用于交易电子邮件中，以将产品列表添加到邮件内容中，例如产品列表——价格、参考编号、数量等。 对于列表的每个产品。

1. 在部分 **[!UICONTROL Collections]** 中，单击该按 **[!UICONTROL Create element]** 钮。

   ![](assets/message-center_collection_create.png)

1. 为您的集合添加标签和ID。
1. 为列表的每个产品添加要在交易消息中显示的所有字段。

   在此示例中，我们添加了以下字段：

   ![](assets/message-center_collection_fields.png)

发布活动和消息后，您便可以在交易消息中使用此集合。

以下是此示例的API预览：

![](assets/message-center_collection_api-preview.png)

**相关主题：**

* [预览和发布活动](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)
* [在交易消息中使用产品列表](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)

## 丰富交易消息内容 {#enriching-the-transactional-message-content}

通过从Adobe Campaign数据库中丰富事务性消息内容，使您能够个性化消息。 例如，从每个收件人的姓氏或CRM ID中，您可以恢复数据（如其地址、出生日期或在“配置文件”表中添加的任何其他自定义字段），以个性化发送给他们的信息。

可以利用来自扩展或资源的信息来丰富事务性消息 **[!UICONTROL Profile]** 内容 **[!UICONTROL Service]** 。

此信息也可以存储在新资源中。 在这种情况下，必须直接或通过其他表 **[!UICONTROL Profile]** 将资 **[!UICONTROL Service]** 源链接到或资源。 例如，在下面的配置中，如果资源链接到资源，则可以使用资源（如产品类别或ID）中的信息来丰富 **[!UICONTROL Product]** 事务消息内 **[!UICONTROL Product]****[!UICONTROL Profile]** 容。

![](assets/message-center_usecaseschema.png)

有关资源创建和发布的详细信息，请参阅 [本页](../../developing/using/key-steps-to-add-a-resource.md)。

1. 在部分 **[!UICONTROL Enrichment]** 中，单击该按 **[!UICONTROL Create element]** 钮。

   ![](assets/message-center_addenrichment.png)

1. 选择要将消息链接到的资源。 在这种情况下，请选择资 **[!UICONTROL Profile]** 源。

   ![](assets/message-center_new-enrichment.png)

1. 使用 **[!UICONTROL Create element]** 按钮将选定资源中的字段链接到您之前添加到事件的某个字段(请参阅 [定义事件属性](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes))。

   ![](assets/message-center_enrichment-join.png)

1. 在此示例中，我们将字段和 **[!UICONTROL Last name]** 字段 **[!UICONTROL First name]** 与资源中的相应字段进行协调 **[!UICONTROL Profile]** 。

   ![](assets/message-center_enrichment-join-fields.png)

   您还可以使用资源丰富事务性消息 **[!UICONTROL Service]** 内容。 有关此问题的详细信息，请参见。

1. 在部 **[!UICONTROL Targeting enrichment]** 分中，选择将在传送执行过程中用作消息目标的丰富内容。 在此示例中，选择 **[!UICONTROL Profile]**。 对于基于配置文件的事件，必须选择定位扩充。

   ![](assets/message-center_marketing_targeting_enrichment.png)

发布活动和消息后，与资源的链 **[!UICONTROL Profile]** 接将允许您丰富事务消息的内容。

**相关主题：**

* [预览和发布活动](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)。
* [个性化交易信息](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)。

## 预览和发布活动 {#previewing-and-publishing-the-event}

在能够使用活动之前，您必须预览并发布该活动。

1. 单击 **[!UICONTROL API preview]** 该按钮可查看网站开发人员在发布REST API之前将使用的模拟REST API。 发布活动后，此按钮还允许您查看生产中API的预览。 请参 [阅集成网站中事件的触发](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST API会根据所选渠道和所选定位维度而不同。 有关各种配置的更多详细信息，请参阅事 [务性事件特定配置](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations)。

1. 单击 **[!UICONTROL Publish]** 以开始发布。

   ![](assets/message-center_pub.png)

1. 您可以通过选择相应的选项卡来查看发布日志。

   ![](assets/message-center_logs.png)

   您还可以通过选择选项卡来查阅以前的出版物。

>[!NOTE]
>
>每次修改活动时，您必须再次单 **[!UICONTROL Publish]** 击以生成将由网站开发人员使用的更新的REST API。

发布活动后，将自动创建链接到新活动的交易消息。 要使此事件触发发送交易消息，您必须修改并发布刚创建的消息。 请参阅 [活动事务消息](../../channels/using/event-transactional-messages.md)。

您可以直接从左侧区域的链接访问创建的事务消息。

![](assets/message-center_messagegeneration.png)

您还必须将此触发事件集成到您的网站中。 请参 [阅集成网站中事件的触发](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

### 取消发布活动 {#unpublishing-an-event}

通过 **[!UICONTROL Unpublish]** 该按钮可以取消事件的发布，该发布从REST API中删除与您先前创建的事件对应的资源。 现在，即使事件通过您的网站触发，相应的消息也不再发送，也不会存储在数据库中。

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>如果您已发布相应的事务消息，则事务消息发布也会被取消。 请参 [阅取消发布交易消息](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message)。

单击该 **[!UICONTROL Publish]** 按钮可生成新的REST API。

## 集成网站中事件的触发 {#integrating-the-triggering-of-the-event-in-a-website}

创建活动后，您必须将此事件的触发集成到您的网站中。

在“交易消息传递操作原则 [](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) ”部分中描述的示例中，您希望在客户之一离开您的网站后，在购买其购物车中的产品之前，触发“购物车放弃”事件。 为此，您的网站Web开发人员必须使用Adobe Campaign Standard REST API。

请参阅 [REST API文档](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#transactional-messages-api) 。

## 事务性事件特定配置 {#transactional-event-specific-configurations}

事务事件配置可能因您要发送的事务消息类型（事件或配置文件）以及将使用的渠道而异。

以下各节详细介绍了根据所需的事务消息应设置哪些特定配置。 有关配置事件的常规步骤的详细信息，请参阅 [创建事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。

### 基于事件的交易消息 {#event-based-transactional-messages}

要发送基于事件的交易消息，您首先需要创建和配置一个事件，以该事件本身包含的数据为目标。
有关详细信息，请参 [阅使用交易消息](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)。

1. 在创建事件配置时，选择定 **[!UICONTROL Real-time event]** 位维(请参 [阅创建事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event))。
1. 为活动添加字段，以便能够个性化交易消息(请参 [阅定义活动属性](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes))。
1. 如果您希望使用Adobe Campaign数据库中的其他信息，可以丰富事务消息内容(请参 [阅丰富事务消息内容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content))。

   >[!NOTE]
   >
   >基于事件的交易消息应仅使用发送事件中的数据来定义收件人和消息内容个性化。 但是，您可以使用Adobe Campaign数据库中的信息丰富事务性消息的内容。

1. 预览和发布活动(请参 [阅预览和发布活动](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event))。

   预览活动时，REST API包含一个属性，该属性根据所选渠道指定电子邮件地址或手机。

   发布活动后，将自动创建链接到新活动的交易消息。 要使事件触发发送交易消息，您必须修改并发布刚创建的消息，请参阅事 [务消息](../../channels/using/event-transactional-messages.md)。

1. 将事件集成到您的网站中(请参 [阅将事件的触发集成到网站](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website))。

### 基于档案的交易消息 {#profile-based-transactional-messages}

要发送基于配置文件的交易消息，您首先需要创建和配置Adobe Campaign数据库中包含的活动定位数据。

1. 在创建事件配置时，选择定 **[!UICONTROL Profile event]** 位维(请参 [阅创建事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event))。
1. 为活动添加字段，以便能够个性化交易消息(请参 [阅定义活动属性](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes))。 您必须添加至少一个字段才能创建丰富内容。 您无需创建其他字段(如名 **字** 、姓氏 **** )，因为您将能够使用Adobe Campaign数据库中的个性化字段。
1. 创建丰富内容以将事件链接到资源(请参 **[!UICONTROL Profile]** 阅丰 [富事务消息内容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content))。 使用定位维度时，必须创建丰 **[!UICONTROL Profile]** 富化内容。
1. 预览和发布活动(请参 [阅预览和发布活动](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event))。

   预览活动时，REST API不包含指定从资源检索电子邮件地址或手机的属 **[!UICONTROL Profile]** 性。

   发布活动后，将自动创建链接到新活动的交易消息。 要使事件触发发送交易消息，您必须修改并发布刚刚创建的消息，请参阅发送 [个人资料交易消息](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message)。

1. 将事件集成到您的网站中(请参 [阅将事件的触发集成到网站](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website))。

### 基于事件的交易推送通知 {#event-based-transactional-push-notifications}

要能够发送交易推送通知，您需要相应地配置Adobe Campaign。 请参阅 [推送配置](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)。

要向已选择从移动应用程序接收通知的所有用户发送匿名交易推送通知，您首先需要创建并配置针对活动本身包含的数据的活动。 相应步骤如下。

该事件必须包含以下三个元素：

* 注 **册令牌**，它是一个移动应用程序和一个设备的用户ID。 它可能与Adobe Campaign数据库中的任何配置文件不对应。
* 移动 **应用程序名称** （适用于所有设备的名称- android和iOS）。 这是Adobe Campaign中配置的用于在用户设备上接收推送通知的移动应用程序的ID。 For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* 推 **送平台** （Android为“gcm”,iOS为“apns”）。

1. 创建事件配置时，选择渠 **[!UICONTROL Mobile application]** 道和定位 **[!UICONTROL Real-time event]** 维(请参阅 [创建事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event))。
1. 为活动添加字段，以便能够个性化交易消息(请参 [阅定义活动属性](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes))。
1. 如果您希望使用Adobe Campaign数据库中的其他信息，可以丰富事务消息内容(请参 [阅丰富事务消息内容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content))。

   >[!NOTE]
   >
   >基于事件的交易消息应仅使用发送事件中的数据来定义收件人和消息内容个性化。 但是，您可以使用Adobe Campaign数据库中的信息丰富事务性消息的内容。

1. 预览和发布活动(请参 [阅预览和发布活动](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event))。

   预览活动时，REST API包含“registrationToken”、“application”和“pushPlatform”属性，这些属性将用于定位交付。

   ![](assets/message-center_push_api.png)

   发布活动后，将自动创建链接到新活动的交易推送通知。 要修改并发布刚刚创建的消息，请参阅发 [送面向活动的事务推送通知](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-an-event)。

1. 将事件集成到您的网站中(请参 [阅将事件的触发集成到网站](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website))。

### 基于档案的交易推送通知 {#profile-based-transactional-push-notifications}

要向订阅了移动应用程序的Adobe Campaign配置文件发送交易推送通知，您首先需要创建和配置针对Adobe Campaign数据库的活动。

1. 创建事件配置时，选择渠 **[!UICONTROL Mobile application]** 道和定位 **[!UICONTROL Profile]** 维(请参阅 [创建事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event))。

   默认情况下，事务推送通知将发送到接收方订阅的所有移动应用程序。 要将推送通知发送到特定移动应用程序，请在列表中选择该通知。 其他移动应用程序将被消息定位，但将被排除在发送之外。

   ![](assets/message-center_push_appfilter.png)

1. 如果要个性化事务性消息，请向活动添加字段(请参 [阅定义事件属性](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes))。

   >[!NOTE]
   >
   >您必须添加至少一个字段才能创建丰富内容。 您无需创建其他字段(如名 **字** 、姓氏 **** )，因为您将能够使用Adobe Campaign数据库中的个性化字段。

1. 创建丰富内容以将事件链接到资源(请参 **[!UICONTROL Profile]** 阅丰 [富事务消息内容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content))。 使用定位维度时，必须创建丰 **[!UICONTROL Profile]** 富化内容。
1. 预览和发布活动(请参 [阅预览和发布活动](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event))。

   预览活动时，REST API不包含指定注册令牌、应用程序名称和推送平台的属性，如同从资源中检索它们一样 **[!UICONTROL Profile]** 。

   发布活动后，将自动创建链接到新活动的交易推送通知。 要修改并发布刚刚创建的消息，请参阅发 [送针对配置文件的交易推送通知](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile)。

1. 将事件集成到您的网站中(请参 [阅将事件的触发集成到网站](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website))。

### 配置活动以发送跟进消息 {#configuring-an-event-to-send-a-follow-up-message}

后续消息是预定义的营销交付模板，可在工作流中用于向特定交易消息的收件人发送消息。 有关此方面的详细信息，请 [参阅后续消息](../../channels/using/follow-up-messages.md)。

1. 使用您创建的事件配置来发送事件事务消息。 请参 [阅基于事件的交易消息](../../administration/using/configuring-transactional-messaging.md#event-based-transactional-messages)。
1. 配置活动时，请在发布活 **[!UICONTROL Create follow-up delivery template for this event]** 动之前选中该框。

   ![](assets/message-center_follow-up-checkbox.png)

1. 预览和发布活动(请参 [阅预览和发布活动](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event))。

   发布活动后，将自动创建与新活动链接的交易消息和后续交付模板。 有关使用跟进消息的详细信息，请 [参阅发送跟进消息](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)。

## 用例：配置事件以发送事务消息 {#use-case--configuring-an-event-to-send-a-transactional-message}

在此示例中，我们要配置一个事件，以便在我们网站上的每次购买后发送确认消息，但前提条件如下：

由于我们希望通过其CRM ID识别我们的客户端，因此，首先，请确保已使用 **[!UICONTROL Profile]** 此新字段扩展了资源。

同样，必须已创建并发布与购买对应的自定义资源，并且必须将其链接到该资 **[!UICONTROL Profile]** 源。 这样，您就可以从该资源检索信息以丰富消息内容。

有关资源创建和发布的详细信息，请参阅 [本页](../../developing/using/key-steps-to-add-a-resource.md)。

1. 使用渠道和定位维度 **[!UICONTROL Email]** 创建新 **[!UICONTROL Profile]** 事件(请参 [阅创建事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event))。
1. 定义可用于个性化交易消息的属性。 在我们的情况下，添加“CRM ID”和“产品标识符”字段(请参 [阅定义事件属性](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes))。

   ![](assets/message-center_usecase1.png)

1. 要使用有关客户先前购买的信息丰富消息内容，请创建针对资源的丰富 **[!UICONTROL Purchase]** 内容(请参 [阅丰富事务消息内容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content))。

   ![](assets/message-center_usecase2.png)

1. 在以前添加到消息的“产品标识符”字段与资源中的相应字段之间创建连接条 **[!UICONTROL Purchase]** 件

   ![](assets/message-center_usecase3.png)

1. 预览和发布活动(请参 [阅预览和发布活动](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event))。
1. 在网站中集成事件(请参 [阅集成网站中事件的触发](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website))。

