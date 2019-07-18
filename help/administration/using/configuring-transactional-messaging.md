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
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Configuring transactional messaging{#configuring-transactional-messaging}

要使用Adobe Campaign发送交易消息，您首先需要描述活动数据的结构。

Event configuration must be performed by an **administrator** by following the steps below:

配置可能因要发送的事务消息类型而异。For more on this, refer to [Transactional event specific configurations](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations)

发布活动后，会自动创建相应的交易消息。For more on transactional messaging, refer to [this page](../../channels/using/about-transactional-messaging.md).

## Creating an event {#creating-an-event}

首先根据需要创建活动。

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]**.
1. Click the **[!UICONTROL Create]** button.
1. Give a **[!UICONTROL Label]** and an **[!UICONTROL ID]** to the event. **[!UICONTROL ID]** 字段为必填字段，应以前缀“EVT”开头。If you do not use this prefix, it is automatically added once you click **[!UICONTROL Create]**.

   ![](assets/message-center_1.png)

1. Select the channel that will be used to send your transactional messages **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** or **[!UICONTROL Mobile application]** (push notification).

   >[!NOTE]
   >
   >每个活动配置只能使用一个频道。创建活动后，您无法更改渠道。

1. Select the targeting dimension corresponding to the desired event configuration and click **[!UICONTROL Create]**.

   事件本身包含基于事件的交易消息目标数据，而基于个人资料的交易消息目标数据包含在Adobe Campaign数据库中。For more on this, refer to [Transactional event specific configurations](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations).

## Defining the event attributes {#defining-the-event-attributes}

**[!UICONTROL Fields]** 在部分中，定义将集成到活动内容中的属性，然后可用于个性化交易消息。

The steps for adding and modifying fields are the same as for [custom resources](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource).

![](assets/message-center_2.png)

>[!NOTE]
>
>If you want to create a multilingual transactional message, define an additional event attribute with the **[!UICONTROL AC_language]** ID. 这仅适用于活动交易消息。发布活动后，编辑多语言事务消息内容的步骤与多语言标准电子邮件相同。See [Creating a multilingual email](../../channels/using/creating-a-multilingual-email.md).

## Defining data collections {#defining-data-collections}

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

## Enriching the transactional message content {#enriching-the-transactional-message-content}

利用Adobe Campaign数据库中的信息丰富交易消息内容使您能够个性化消息。例如，从每个收件人的姓氏或CRM ID，您可以恢复数据(例如，他们的地址或出生日期)或配置文件表中添加的任何其他自定义字段，以便个性化发送给他们的信息。

It is possible to enrich the transactional message content with information from extended **[!UICONTROL Profile]** or **[!UICONTROL Service]** resources.

此信息也可存储在新资源中。In that case, the resource must be linked to the **[!UICONTROL Profile]** or **[!UICONTROL Service]** resources either directly, or via another table. For example, in the configuration below, it is possible to enrich the transactional message content with information from the **[!UICONTROL Product]** resource like the product category or ID, if the **[!UICONTROL Product]** resource is linked to the **[!UICONTROL Profile]** resource.

![](assets/message-center_usecaseschema.png)

For more on resource creation and publishing, refer to [this page](../../developing/using/key-steps-of-adding-a-resource.md).

1. **[!UICONTROL Enrichment]** 在部分中，单击 **[!UICONTROL Create element]** 按钮。

   ![](assets/message-center_addenrichment.png)

1. 选择要与之链接的资源。In this case, choose the **[!UICONTROL Profile]** resource.

   ![](assets/message-center_new-enrichment.png)

1. Use the **[!UICONTROL Create element]** button to link a field from the selected resource to one of the fields you previously added to the event (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   ![](assets/message-center_enrichment-join.png)

1. In this example, we reconcile the **[!UICONTROL Last name]** and the **[!UICONTROL First name]** fields with the corresponding fields in the **[!UICONTROL Profile]** resource.

   ![](assets/message-center_enrichment-join-fields.png)

1. **[!UICONTROL Targeting enrichment]** 在部分中，选择将在提交执行过程中用作消息目标的丰富化。In this example, select **[!UICONTROL Profile]**. 对于基于个人资料的活动，必须选择定位丰富化。

   ![](assets/message-center_marketing_targeting_enrichment.png)

Once the event and the message are published, the link with the **[!UICONTROL Profile]** resource will allow you to enrich the content of the transactional message.

**相关主题：**

* [预览和发布活动](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)。
* [个性化交易消息](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)。

## Previewing and publishing the event {#previewing-and-publishing-the-event}

在使用活动之前，您必须预览并发布该活动。

1. Click the **[!UICONTROL API preview]** button to see a simulation of the REST API that will be used by your website developer before it is published. 发布活动后，此按钮还允许您查看生产中API的预览。See [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST API根据选定的渠道和选定的定位维度而异。For more details on the various configurations, refer to [Transactional event specific configurations](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations).

1. Click **[!UICONTROL Publish]** to start publication.

   ![](assets/message-center_pub.png)

1. 您可以通过选择相应的选项卡来查看发布日志。

   ![](assets/message-center_logs.png)

   您还可以通过选择选项卡来查阅以前的出版物。

>[!NOTE]
>
>Each time you modify the event, you must click **[!UICONTROL Publish]** again to generate the updated REST API that will be used by your website developer.

活动发布后，将自动创建链接到新活动的事务消息。为了使此活动触发发送交易消息，您必须修改并发布刚刚创建的消息。See [Event transactional messages](../../channels/using/event-transactional-messages.md).

您可以访问直接从左侧区域的链接创建的事务消息。

![](assets/message-center_messagegeneration.png)

您还必须将此触发器事件集成到您的网站中。See [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

### Unpublishing an event {#unpublishing-an-event}

**[!UICONTROL Unpublish]** 该按钮允许您取消活动的发布，该活动从REST API中删除与您先前创建的事件对应的资源。现在，即使活动通过您的网站触发，相应的消息也不会再发送，而且它们不会存储在数据库中。

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>如果您已经发布了相应的交易消息，则交易消息发布也会被取消。See [Unpublishing a transactional message](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message).

Click the **[!UICONTROL Publish]** button to generate a new REST API.

## Integrating the triggering of the event in a website {#integrating-the-triggering-of-the-event-in-a-website}

创建活动后，您必须将此事件的触发集成到网站中。

In the example described in the [Transactional messaging operating principle](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) section, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart. 为此，网站Web开发人员必须使用Adobe Campaign Standard REST API。

See the [REST API Documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#transactional-messages-api) .

## Transactional event specific configurations {#transactional-event-specific-configurations}

交易活动配置可能因您要发送的交易消息类型(活动或配置文件)以及将使用的渠道而异。

以下部分详细介绍了应根据所需的交易消息设置特定配置的详细信息。For more on the general steps to configure an event, refer to [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event).

### Event-based transactional messages {#event-based-transactional-messages}

要发送基于事件的交易消息，您首先需要创建和配置一个事件，以定位活动本身包含的数据。

1. When creating the event configuration, select the **[!UICONTROL Real-time event]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Add fields to the event, in order to be able to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).
1. Enrich the transactional message content if you want to use additional information from the Adobe Campaign database (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >基于事件的交易消息应仅使用已发送事件中的数据来定义接收者和消息内容个性化。但是，您可以使用Adobe Campaign数据库中的信息丰富交易消息的内容。

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   预览事件时，REST API包含根据选定频道指定电子邮件地址或手机的属性。

   活动发布后，将自动创建链接到新活动的事务消息。In order for the event to trigger sending a transactional message, you must modify and publish the message that was just created, see [Event transactional messages](../../channels/using/event-transactional-messages.md).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Profile-based transactional messages {#profile-based-transactional-messages}

要发送基于个人资料的交易消息，您首先需要创建和配置Adobe Campaign数据库中包含的活动定位数据。

1. When creating the event configuration, select the **[!UICONTROL Profile event]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Add fields to the event, in order to be able to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)). 您必须添加至少一个字段才能创建丰富内容。You do not need to create other fields such as **First name** and **Last name** as you will be able to use personalization fields from the Adobe Campaign database.
1. Create an enrichment in order to link the event to the **[!UICONTROL Profile]** resource (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)). Creating an enrichment is mandatory when using a **[!UICONTROL Profile]** targeting dimension.
1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   When previewing the event, the REST API does not contain an attribute specifying the email address or the mobile phone as it will be retrieved from the **[!UICONTROL Profile]** resource.

   活动发布后，将自动创建链接到新活动的事务消息。In order for the event to trigger sending a transactional message, you must modify and publish the message that was just created, see [Sending a profile transactional message](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Event-based transactional push notifications {#event-based-transactional-push-notifications}

要发送交易推送通知，您需要相应地配置Adobe Campaign。See [Push configuration](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

要向选择接收移动应用程序接收通知的所有用户发送匿名交易推送通知，您首先需要创建并配置一个事件定位活动中包含的数据。以下步骤如下所示。

该事件必须包含以下三个元素：

* **注册令牌**，它是一个手机应用程序和一个设备的用户ID。它可能与Adobe Campaign数据库中的任何配置文件不对应。
* **移动应用程序名称** (适用于所有设备- Android和iOS)。这是在Adobe Campaign中配置的移动应用程序的ID，用于接收用户设备上的推送通知。For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* **推送平台** (“gcm”for Android或“apns”for iOS)。

1. When creating the event configuration, select the **[!UICONTROL Mobile application]** channel and the **[!UICONTROL Real-time event]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Add fields to the event, in order to be able to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).
1. Enrich the transactional message content if you want to use additional information from Adobe Campaign database (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >基于事件的交易消息应仅使用已发送事件中的数据来定义接收者和消息内容个性化。但是，您可以使用Adobe Campaign数据库中的信息丰富交易消息的内容。

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   预览事件时，REST API包含将用于定位交付的“registrationToken”、“application”和“pushPlatform”属性。

   ![](assets/message-center_push_api.png)

   发布活动后，将自动创建链接到新活动的事务推送通知。To modify and publish the message that was just created, see [Sending a transactional push notification targeting an event](/channels/using/transactional-push-notifications.html#sending-a-transactional-push-notification-targeting-an
----------event#sending-a-transactional-push-notification-targeting-an
----------event#sending-a-transactional-push-notification-targeting-an
----------event#sending-a-transactional-push-notification-targeting-an
----------event).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Profile-based transactional push notifications {#profile-based-transactional-push-notifications}

要向已订阅移动应用程序的Adobe Campaign配置文件发送交易推送通知，您首先需要创建和配置一个定位Adobe Campaign数据库的活动。

1. When creating the event configuration, select the **[!UICONTROL Mobile application]** channel and the **[!UICONTROL Profile]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).

   默认情况下，交易推送通知将发送到接收订阅的所有移动应用程序。要将推送通知发送到特定的手机应用程序，请在列表中选择该通知。其他移动应用程序将被消息锁定，但将从发送中排除。

   ![](assets/message-center_push_appfilter.png)

1. Add fields to the event, if you want to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   >[!NOTE]
   >
   >您必须添加至少一个字段才能创建丰富内容。You do not need to create other fields such as **First name** and **Last name** as you will be able to use personalization fields from the Adobe Campaign database.

1. Create an enrichment in order to link the event to the **[!UICONTROL Profile]** resource (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)). Creating an enrichment is mandatory when using a **[!UICONTROL Profile]** targeting dimension.
1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   When previewing the event, the REST API does not contain an attribute specifying the registration token, the application name and the push platform as they will be retrieved from the **[!UICONTROL Profile]** resource.

   发布活动后，将自动创建链接到新活动的事务推送通知。To modify and publish the message that was just created, see [Sending a transactional push notification targeting a profile](/channels/using/transactional-push-notifications.html#sending-a-transactional-push-notification-targeting-a
----------profile#sending-a-transactional-push-notification-targeting-a
----------profile#sending-a-transactional-push-notification-targeting-a
----------profile#sending-a-transactional-push-notification-targeting-a
----------profile).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Configuring an event to send a follow-up message {#configuring-an-event-to-send-a-follow-up-message}

后续消息是预定义的营销交付模板，可在工作流中使用该模板向收件人发送特定交易消息的消息。For more on this, see [Follow-up messages](../../channels/using/follow-up-messages.md).

1. 使用您创建的与发送活动事务消息相同的事件配置。See [Event-based transactional messages](../../administration/using/configuring-transactional-messaging.md#event-based-transactional-messages).
1. When configuring your event, check the **[!UICONTROL Create follow-up delivery template for this event]** box before publishing the event.

   ![](assets/message-center_follow-up-checkbox.png)

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   发布活动后，将自动创建与新活动关联的事务消息和后续交付模板。For more on using follow-up messages, see [Sending a follow-up message](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).

## Use case: configuring an event to send a transactional message {#use-case--configuring-an-event-to-send-a-transactional-message}

在此示例中，我们希望配置一个活动，以便在我们网站上每次购买后发送确认消息，并具有以下prerequi站点：

As we want to identify our client via his CRM ID, first make sure that the **[!UICONTROL Profile]** resource has been extended with this new field.

In the same way, a custom resource corresponding to purchases must have been created and published, and must be linked to the **[!UICONTROL Profile]** resource. 这样，您就可以从该资源检索信息以丰富消息内容。

For more on resource creation and publishing, refer to [this page](../../developing/using/key-steps-of-adding-a-resource.md).

1. Create a new event using the **[!UICONTROL Email]** channel and the **[!UICONTROL Profile]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. 定义可用于个性化交易消息的属性。In our case, add the "CRM ID" and the "Product identifier" fields (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   ![](assets/message-center_usecase1.png)

1. To enrich the message content with information regarding the client's previous purchases, create an enrichment targeting the **[!UICONTROL Purchase]** resource (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   ![](assets/message-center_usecase2.png)

1. Create a join condition between the "Product identifier" field that was previously added to the message, and the corresponding field from the **[!UICONTROL Purchase]** resource

   ![](assets/message-center_usecase3.png)

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).
1. Integrate the event in your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

