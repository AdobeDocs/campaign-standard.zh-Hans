---
solution: Campaign Standard
product: campaign
title: 事务型推送通知
description: 了解如何使用Adobe Campaign Standard发送交易推送通知。
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
source-wordcount: '1341'
ht-degree: 4%

---


# 事务型推送通知{#transactional-push-notifications}

您可以使用Adobe Campaign在iOS和Android移动设备上发送事务推送通知。 这些消息在您通过利用Adobe Campaign Mobile SDK在Experience Cloud中设置的移动应用程序上接收。

>[!NOTE]
>
>推送渠道为可选。 请核实您的许可协议。有关标准推送通知的详细信息，请参阅[关于推送通知](../../channels/using/about-push-notifications.md)。

要能够发送交易推送通知，您需要相应地配置Adobe Campaign。 请参阅[配置移动应用程序](../../administration/using/configuring-a-mobile-application.md)。

可以发送两种类型的事务推送通知：

* [面向事件的交易推送通知](#transactional-push-notifications-targeting-an-event)
* [事务推送通知定位](#transactional-push-notifications-targeting-a-profile) 来自Adobe Campaign数据库的配置文件

## 针对事件{#transactional-push-notifications-targeting-an-event}的事务推送通知

您可以使用Adobe Campaign将&#x200B;**匿名事务推送通知发送给已选择接收移动应用程序通知的所有用户**。

在这种情况下，仅使用&#x200B;**事件本身包含的数据来定义投放目标**。 没有利用来自Adobe Campaign集成用户档案数据库的数据。

### 配置基于事件的事务推送通知{#configuring-event-based-transactional-push-notification}

要向已选择从移动应用程序接收通知的所有用户发送交易推送通知，您首先需要创建并配置一个事件，以定位事件本身包含的数据。

>[!NOTE]
>
>您仍然可以使用[事件属性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)(来自事件的数据)和[事件扩充](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)(来自活动数据库的数据)个性化基于事件的事务推送通知的内容。 请参见[下面的示例](#sending-event-based-transactional-push-notification)。

事件必须包含以下三个元素：

* **注册令牌**，它是一个移动应用程序和一个设备的用户ID。 它可能与来自Adobe Campaign库的任何用户档案不对应。
* **移动应用程序名称**（所有设备均使用一个名称 — Android和iOS）。 这是在Adobe Campaign中配置的用于在用户设备上接收推送通知的移动应用程序的ID。 有关详细信息，请参阅[配置移动应用程序](../../administration/using/configuring-a-mobile-application.md)。
* **推送平台**（Android为&quot;gcm&quot;,iOS为&quot;apns&quot;）。

要配置事件，请按照以下步骤操作：

1. 创建事件配置时，请选择&#x200B;**[!UICONTROL Push notification]**&#x200B;渠道和&#x200B;**[!UICONTROL Real-time event]**&#x200B;定位维度(请参阅[创建事件](../../channels/using/configuring-transactional-event.md#creating-an-event))。
1. 向事件添加字段。 这将允许您对事务性消息进行个性化设置(请参阅[定义事件属性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes))。 在此示例中，定义“gateNumber”、“lastname”和“firstname”字段。
1. 您还可以丰富消息的内容。 为此，请从您链接到事件配置的表中添加字段(请参阅[丰富事件](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content))。

   <!--Event-based transactional messaging is supposed to use only the data that are in the sent event to define the recipient and the message content personalization. However, you can enrich the content of your transactional message using information from the Adobe Campaign database.-->

1. [预览并发布事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

   在预览事件时，REST API包含将用于目标投放的“registrationToken”、“application”和“pushPlatform”属性。

   ![](assets/message-center_push_api.png)

   发布事件后，将自动创建链接到新事件的交易推送通知。 您现在可以修改并发布刚创建的消息（请参阅[本节](#sending-event-based-transactional-push-notification)）。

1. 将事件集成到您的网站中(请参阅[集成触发的事件](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger))。

### 发送基于事件的事务推送通知{#sending-event-based-transactional-push-notification}

例如，航空公司公司希望邀请其移动应用程序用户前往相关登机口登机。

公司将使用一个移动应用程序通过一个设备为每个用户发送一个交易推送通知（用注册令牌标识）。

1. 请转至创建的事务型消息以对其进行编辑。请参阅[访问事务性消息](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)。

   ![](assets/message-center_push_message.png)

1. 单击&#x200B;**[!UICONTROL Content]**&#x200B;块以修改消息的标题和正文。

1. 您可以插入个性化字段以添加在创建事件时定义的元素(请参阅[定义事件属性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes))。

   ![](assets/message-center_push_content.png)

   要查找这些字段，请单击项目旁边的铅笔，单击&#x200B;**[!UICONTROL Insert personalization field]**&#x200B;并选择&#x200B;**[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**。

   ![](assets/message-center_push_personalization.png)

   有关编辑推送通知内容的详细信息，请参阅[准备和发送推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)。

1. 如果要使用事务性消息Adobe Campaign库的其他信息，还可以丰富事件内容（请参阅[丰富](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)）。

1. 保存更改并发布消息。请参阅[发布事务型消息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)。

1. 使用Adobe Campaign Standard REST API，在Android(gcm)上使用一个移动应用程序(WeFlight)将事件发送到注册令牌(ABCDEF123456789)，其中包含登记数据：

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

   有关将事件触发集成到外部系统的详细信息，请参阅[集成触发事件](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)。

如果存在注册令牌，则相应的用户接收包括以下内容的事务推送通知：

*“简·格林，你好，登机才刚开始！请转至B18门。&quot;*

## 针对用户档案{#transactional-push-notifications-targeting-a-profile}的事务推送通知

您可以向订阅了您的移动应用程序&#x200B;**的Adobe Campaign用户档案发送事务推送通知**。 此投放可以包含从Adobe Campaign库直接检索到的[个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)，如收件人的名。

在这种情况下，事件必须包含一些字段&#x200B;**，允许与Adobe Campaign数据库**&#x200B;中的用户档案进行协调。

定位用户档案时，每个移动应用程序和每个设备都会发送一个事务推送通知。 例如，如果Adobe Campaign用户订阅了两个应用程序，则此用户将收到两个通知。 如果用户订阅了具有两个不同设备的同一应用程序，则此用户将在每台设备上收到通知。

用户档案订阅的移动应用程序列在此用户档案的&#x200B;**[!UICONTROL Mobile App Subscriptions]**&#x200B;选项卡中。 要访问此选项卡，请选择用户档案，然后单击右侧的&#x200B;**[!UICONTROL Edit profile properties]**&#x200B;按钮。

![](assets/push_notif_subscriptions.png)

有关访问和编辑用户档案的详细信息，请参阅[关于用户档案](../../audiences/using/about-profiles.md)。

### 配置基于用户档案的事务推送通知{#configuring-profile-based-transactional-push-notification}

要向订阅了您的移动应用程序的Adobe Campaign用户档案发送事务推送通知，您首先需要创建并配置一个针对Adobe Campaign数据库的事件。

1. 创建事件配置时，请选择&#x200B;**[!UICONTROL Push notification]**&#x200B;渠道和&#x200B;**[!UICONTROL Profile]**&#x200B;定位维度(请参阅[创建事件](../../channels/using/configuring-transactional-event.md#creating-an-event))。

   默认情况下，事务推送通知将发送到收件人订阅的所有移动应用程序。 要向特定移动应用程序发送推送通知，请在列表中选择它。 消息将瞄准其他移动应用程序，但将从发送中排除。

   ![](assets/message-center_push_appfilter.png)

1. 如果要个性化事务性消息，请向事件添加字段(请参阅[定义事件属性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes))。

   >[!NOTE]
   >
   >必须至少添加一个字段才能创建扩充。 您无需创建其他字段，如&#x200B;**First name**&#x200B;和&#x200B;**Last name**，因为您将能够使用Adobe Campaign数据库中的个性化字段。

1. 创建扩充以将事件链接到&#x200B;**[!UICONTROL Profile]**&#x200B;资源(请参阅[丰富事件](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content))，并选择此扩充作为&#x200B;**[!UICONTROL Targeting enrichment]**。

   >[!IMPORTANT]
   >
   >对于基于用户档案的事件，此步骤是必需的。

1. [预览并发布事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

   预览事件时，REST API不包含指定注册令牌、应用程序名称和推送平台的属性，它们将从&#x200B;**[!UICONTROL Profile]**&#x200B;资源中检索。

   发布事件后，将自动创建链接到新事件的交易推送通知。 您现在可以修改并发布刚创建的消息（请参阅[本节](#sending-profile-based-transactional-push-notification)）。

1. 将事件集成到您的网站中(请参阅[集成触发的事件](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger))。

### 发送基于用户档案的事务推送通知{#sending-profile-based-transactional-push-notification}

例如，航空公司公司希望向订阅其移动应用程序的所有Adobe Campaign用户发送最后一次登机通知。

1. 请转至创建的事务型消息以对其进行编辑。请参阅[访问事务性消息](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)。

1. 单击&#x200B;**[!UICONTROL Content]**&#x200B;块以修改消息的标题和正文。

   与基于实时事件的配置不同，您可以直接访问所有用户档案信息，以个性化您的信息。 请参阅[插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)。

   有关编辑推送通知内容的详细信息，请参阅[准备和发送推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)。

1. 保存更改并发布消息。请参阅[发布事务型消息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)。
1. 使用Adobe Campaign Standard REST API将事件发送到用户档案:

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

有关将事件触发集成到外部系统的详细信息，请参阅[集成触发事件](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)。

相应的用户接收包括从Adobe Campaign数据库检索到的所有个性化元素的事务推送通知。

>[!NOTE]
>
>没有注册令牌、应用程序和推送平台字段。 在此示例中，对帐是使用电子邮件字段执行的。
