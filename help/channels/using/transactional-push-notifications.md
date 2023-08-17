---
title: 事务性推送通知
description: 了解如何使用Adobe Campaign Standard发送事务性推送通知。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 61988c1d-d538-47b1-94c1-f3fbdf314b65
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1451'
ht-degree: 4%

---

# 事务性推送通知{#transactional-push-notifications}

您可以使用Adobe Campaign在iOS和Android移动设备上发送事务推送通知。 通过利用Experience CloudMobile SDK在Adobe Campaign中设置的移动应用程序，可接收此类消息。

>[!NOTE]
>
>推送渠道是可选的。 请核实您的许可协议。有关标准推送通知的更多信息，请参阅 [关于推送通知](../../channels/using/about-push-notifications.md).

要发送事务性推送通知，您需要相应地配置Adobe Campaign。 请参阅 [配置移动应用程序](../../administration/using/configuring-a-mobile-application.md).

您可以发送两种类型的事务型推送通知：

* [针对事件的事务性推送通知](#transactional-push-notifications-targeting-an-event)
* [定向用户档案的事务性推送通知](#transactional-push-notifications-targeting-a-profile) 从Adobe Campaign数据库中

## 针对事件的事务性推送通知 {#transactional-push-notifications-targeting-an-event}

您可以使用Adobe Campaign发送 **向所有用户发送匿名事务性推送通知** 选择接收来自您的移动应用程序的通知的用户。

在这种情况下，仅 **使用事件本身包含的数据来定义投放目标**. 不会利用Adobe Campaign集成用户档案数据库中的数据。

### 配置基于事件的事务型推送通知 {#configuring-event-based-transactional-push-notification}

要向所有选择接收来自移动应用程序的通知的用户发送事务型推送通知，您首先需要创建并配置一个以事件本身包含的数据为定向的事件。

>[!NOTE]
>
>您仍然可以使用对基于事件的事务型推送通知的内容进行个性化 [事件属性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes) （来自事件的数据）和 [事件扩充](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) （来自Campaign数据库的数据）。 请参阅 [以下示例](#sending-event-based-transactional-push-notification).

事件必须包含以下三个元素：

* A **注册令牌**，即一个移动应用程序和一台设备的用户ID。 它可能与Adobe Campaign数据库中的任何配置文件不对应。
* A **移动应用程序名称** (适用于所有设备 — Android和iOS)。 这是在Adobe Campaign中配置的移动应用程序的ID，该ID将用于接收用户设备上的推送通知。 有关详细信息，请参见 [配置移动应用程序](../../administration/using/configuring-a-mobile-application.md).
* A **推送平台** (对于Android，为“gcm”；对于iOS，为“apns”)。

要配置事件，请执行以下步骤：

1. 创建事件配置时，选择 **[!UICONTROL Push notification]** 渠道和 **[!UICONTROL Real-time event]** 定位维度(请参阅 [创建事件](../../channels/using/configuring-transactional-event.md#creating-an-event))。
1. 向事件添加字段。 这将允许您个性化事务型消息(请参阅 [定义事件属性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes))。 在此示例中，定义“gateNumber”、“lastname”和“firstname”字段。
1. 您还可以扩充消息的内容。 要实现此目的，请从链接到事件配置的表中添加字段(请参阅 [丰富活动](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content))。

   <!--Event-based transactional messaging is supposed to use only the data that are in the sent event to define the recipient and the message content personalization. However, you can enrich the content of your transactional message using information from the Adobe Campaign database.-->

1. [预览和发布事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

   在预览事件时，REST API包含将用于定位投放的“registrationToken”、“application”和“pushPlatform”属性。

   ![](assets/message-center_push_api.png)

   发布事件后，将自动创建链接到新事件的事务型推送通知。 您现在可以修改并发布之前创建的消息(请参阅 [本节](#sending-event-based-transactional-push-notification))。

1. 将事件集成到您的网站(请参阅 [集成事件触发](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger))。

### 发送基于事件的事务型推送通知 {#sending-event-based-transactional-push-notification}

例如，一家航空公司希望邀请其移动应用程序用户前往相关登机口进行登机。

公司将通过单个设备，使用一个移动应用程序，为每个用户发送一个事务性推送通知（通过注册令牌进行标识）。

1. 请转至创建的事务型消息以对其进行编辑。请参阅 [访问事务型消息](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

   ![](assets/message-center_push_message.png)

1. 单击 **[!UICONTROL Content]** 块以修改消息的标题和正文。

1. 您可以插入个性化字段以添加在创建事件时定义的元素(请参阅 [定义事件属性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes))。

   ![](assets/message-center_push_content.png)

   要查找这些字段，请单击项目旁边的铅笔，然后单击 **[!UICONTROL Insert personalization field]** 并选择 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   有关编辑推送通知内容的更多信息，请参阅 [准备和发送推送通知](../../channels/using/preparing-and-sending-a-push-notification.md).

1. 如果要使用Adobe Campaign数据库中的其他信息，您还可以扩充事务型消息的内容(请参阅 [丰富活动](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content))。

1. 保存更改并发布消息。请参阅[发布事务型消息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)。

1. 使用Adobe Campaign Standard REST API，使用一个移动应用程序(WeFlight)将事件发送到包含登机数据的Android (gcm)上的注册令牌(ABCDEF123456789)：

   ```
   {
     "registrationToken":"ABCDEF123456789",
     "application":"WeFlight",
     "pushPlatform":"gcm",
     "ctx":
     {
       "gateNumber":"Gate B18",
       "lastname":"Green",
       "firstname":"Jane"
     }
   }
   ```

   有关将事件的触发集成到外部系统中的更多信息，请参阅 [集成事件触发](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

如果存在注册令牌，则相应的用户会收到包含以下内容的事务性推送通知：

*“你好，简·格林，刚刚开始登机！ 请前往B18门。”*

## 定向用户档案的事务性推送通知 {#transactional-push-notifications-targeting-a-profile}

您可以发送事务型推送通知 **订阅了您的移动应用程序的Adobe Campaign用户档案**. 此投放可包含 [个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)直接从Adobe Campaign数据库中检索到的名称（如收件人的名字）。

在这种情况下，事件必须包含一些字段 **允许与Adobe Campaign数据库中的用户档案进行协调**.

定向用户档案时，会为每个移动应用程序和设备发送一个事务性推送通知。 例如，如果某个Adobe Campaign用户订阅了两个应用程序，则此用户将收到两个通知。 如果用户使用两个不同的设备订阅了相同的应用程序，则此用户将在每个设备上收到通知。

用户档案订阅的移动应用程序在 **[!UICONTROL Mobile App Subscriptions]** 选项卡中。 要访问此选项卡，请选择一个配置文件，然后单击 **[!UICONTROL Edit profile properties]** 按钮。

![](assets/push_notif_subscriptions.png)

有关访问和编辑用户档案的详细信息，请参阅 [关于用户档案](../../audiences/using/about-profiles.md).

### 配置基于用户档案的事务型推送通知 {#configuring-profile-based-transactional-push-notification}

要向订阅了移动应用程序的Adobe Campaign用户档案发送事务型推送通知，您首先需要创建和配置针对Adobe Campaign数据库的事件。

1. 创建事件配置时，选择 **[!UICONTROL Push notification]** 渠道和 **[!UICONTROL Profile]** 定位维度(请参阅 [创建事件](../../channels/using/configuring-transactional-event.md#creating-an-event))。

   默认情况下，事务推送通知将发送到收件人订阅的所有移动应用程序。 要将推送通知发送到特定的移动应用程序，请在列表中选择该应用程序。 其他移动设备应用程序将被消息定向，但将从发送中排除。

   ![](assets/message-center_push_appfilter.png)

1. 如果要个性化事务型消息，请向事件添加字段(请参阅 [定义事件属性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes))。

   >[!NOTE]
   >
   >您必须至少添加一个字段才能创建扩充。 您无需创建其他字段，例如 **名字** 和 **姓氏** 因为您将能够使用Adobe Campaign数据库中的个性化字段。

1. 创建扩充以将事件链接到 **[!UICONTROL Profile]** 资源(请参阅 [丰富活动](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content))并选择此扩充作为 **[!UICONTROL Targeting enrichment]**.

   >[!IMPORTANT]
   >
   >对于基于用户档案的事件，此步骤是必需的。

1. [预览和发布事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

   预览事件时，REST API不包含指定注册令牌、应用程序名称和推送平台的属性，因为将从中检索它们 **[!UICONTROL Profile]** 资源。

   发布事件后，将自动创建链接到新事件的事务型推送通知。 您现在可以修改并发布之前创建的消息(请参阅 [本节](#sending-profile-based-transactional-push-notification))。

1. 将事件集成到您的网站(请参阅 [集成事件触发](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger))。

### 发送基于用户档案的事务性推送通知 {#sending-profile-based-transactional-push-notification}

例如，一家航空公司希望向所有已订阅其移动应用程序的Adobe Campaign用户发送登机通知。

1. 请转至创建的事务型消息以对其进行编辑。请参阅 [访问事务型消息](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

1. 单击 **[!UICONTROL Content]** 块以修改消息的标题和正文。

   与基于实时事件的配置不同，您可以直接访问所有用户档案信息，以个性化您的消息。 请参阅[插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)。

   有关编辑推送通知内容的更多信息，请参阅 [准备和发送推送通知](../../channels/using/preparing-and-sending-a-push-notification.md).

1. 保存更改并发布消息。请参阅[发布事务型消息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)。
1. 使用Adobe Campaign Standard REST API向配置文件发送事件：

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

有关将事件的触发集成到外部系统中的更多信息，请参阅 [集成事件触发](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

相应的用户接收事务性推送通知，该通知包括从Adobe Campaign数据库检索的所有个性化元素。

>[!NOTE]
>
>没有注册令牌、应用程序和推送平台字段。 在此示例中，使用email字段执行协调。

## 更改事务性推送通知中的目标映射 {#change-target-mapping}

事务型推送通知使用特定的 [目标映射](../../administration/using/target-mappings-in-campaign.md) 其中包含发送此类投放所需的技术设置。

要更改此目标映射，请执行以下步骤：

1. 从事务型消息列表中，选择推送通知。

1. 在消息仪表板中，单击 **[!UICONTROL Edit properties]** 按钮。

   ![](assets/message-center_push_edit.png)

1. 展开 **[!UICONTROL Advanced parameters]** 部分。

1. 单击 **[!UICONTROL Select a 'Target mapping' element]**。

   ![](assets/message-center_push_target-mapping.png)

1. 从列表中选择目标映射。

   >[!NOTE]
   >
   >为了在发送时优化投放准备时间和性能 **基于配置文件** 事务型推送通知，请使用 **[!UICONTROL Profile - Real-time event for Push (mapRtEventAppSubRcp)]** 目标映射。

   ![](assets/message-center_push_target-mapping_change.png)

1. 确认更改并发布消息。 请参阅[发布事务型消息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)。

   >[!IMPORTANT]
   >
   >必须再次发布消息才能使更改生效，否则仍将使用以前的目标映射。


