---
title: 交易推送通知
seo-title: 交易推送通知
description: 交易推送通知
seo-description: 了解如何创建和发布交易推送通知。
page-status-flag: 从未激活
uuid: ef31c1b6-9ef8-42e3-b49 d-72f9 eac8 ea32
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: 交易消息传递
discoiquuid: e645d4b9-001f-47d-47a0f-b4696 c75 c5 d3
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Transactional push notifications{#transactional-push-notifications}

可使用Adobe Campaign在iOS和Android移动设备上发送交易推送通知。通过利用Experience Cloud Mobile SDK，您可以在Adobe Campaign中设置的移动应用程序上收到这些消息。

>[!NOTE]
>
>推送渠道为可选渠道。请检查您的许可协议。For more information on standard push notifications, see [Push notifications](../../channels/using/about-push-notifications.md).

您可以发送两种类型的交易推送通知：

* 事件的交易推送通知。
* 来自Adobe Campaign数据库的交易推送通知定位配置文件。

Once you have created and published an event (the cart abandonment explained in [this section](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)), the corresponding transactional push notification is created automatically.

[配置事件中显示配置步骤以发送交易推送通知](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 部分。

要使活动触发发送交易消息，您必须个性化消息，然后对其进行测试并发布。

>[!NOTE]
>
>To access the transactional messages, you must have administration rights or appear in the **[!UICONTROL Message Center agents]** (mcExec) security group.

## Transactional push notifications targeting an event {#transactional-push-notifications-targeting-an-event}

您可以向选择接收移动应用程序通知的所有用户发送匿名交易推送通知。

在这种情况下，仅活动本身中包含的数据用于定义交付目标。没有利用Adobe Campaign集成配置文件数据库中的数据。

### Sending a transactional push notification targeting an event {#sending-a-transactional-push-notification-targeting-an-----------event}

例如，一家航空公司希望邀请其移动应用程序用户进入相关门户，进行登机。

公司将通过一台设备使用一个手机应用程序向每位用户发送一个交易推送通知(使用注册令牌标识)。

1. 转到为编辑而创建的交易消息。See [Event transactional messages](../../channels/using/event-transactional-messages.md).

   ![](assets/message-center_push_message.png)

1. Click the **[!UICONTROL Content]** block to modify your message's title and body.

   您可以插入个性化字段，以添加您在创建活动时定义的元素。

   ![](assets/message-center_push_content.png)

   To find these fields, click the pencil next to an item, click **[!UICONTROL Insert personalization field]** and select **[!UICONTROL Transactional event]** &gt; **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   For more on editing a push notification content, see [Creating a push notification](../../channels/using/preparing-and-sending-a-push-notification.md).

1. 保存更改并发布消息。See [Publishing a transactional message](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).
1. 使用Adobe Campaign Standard REST API，在Android(gcm)上使用一个移动应用程序(Weflight)发送一个事件至注册令牌(ABCDEF12345689)，其中包含培训数据。

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

   For more on integrating the triggering of an event into an external system, see [Site integration](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

如果存在注册令牌，相应的用户将收到一个交易推送通知，其中包括以下内容：

“你好Jane Green，滑板刚开始！请转到B18”。

## Transactional push notifications targeting a profile {#transactional-push-notifications-targeting-a-profile}

您可以向订阅了移动应用程序的Adobe Campaign配置文件发送交易推送通知。This delivery can contain [personalization](../../designing/using/inserting-a-personalization-field.md) fields, such as the recipient's first name.

在这种情况下，活动必须包含一些允许与Adobe Campaign数据库中的配置文件进行核对的字段。

定位配置文件时，每个移动应用程序和每台设备发送一个事务推送通知。例如，如果Adobe Campaign用户订阅了两个应用程序，则此用户将收到两个通知。如果用户已使用两种不同设备订阅同一应用程序，则此用户将在每台设备上收到通知。

The mobile applications a profile has subscribed to are listed in the **[!UICONTROL Mobile App Subscriptions]** tab of this profile. To access this tab, select a profile and click the **[!UICONTROL Edit profile properties]** button on the right.

![](assets/push_notif_subscriptions.png)

For more information on accessing and editing profiles, see [Profiles](../../audiences/using/creating-profiles.md).

### Sending a transactional push notification targeting a profile {#sending-a-transactional-push-notification-targeting-a-----------profile}

例如，一家航空公司想要向所有订阅其移动应用程序的Adobe Campaign用户发送最后一次展示板。

1. 转到为编辑而创建的交易消息。See [Event transactional messages](../../channels/using/event-transactional-messages.md).

   ![](assets/message-center_push_message_profile.png)

1. Click the **[!UICONTROL Content]** block to modify your message's title and body.

   与基于实时事件的配置不同，您可以直接访问所有配置文件信息以个性化您的消息。See [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md).

   ![](assets/message-center_push_content_profile.png)

   有关编辑推送通知内容的更多信息。See [Creating a push notification](../../channels/using/preparing-and-sending-a-push-notification.md).

1. 保存更改并发布消息。See [Publishing a transactional message](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).
1. 使用Adobe Campaign Standard REST API将活动发送到配置文件。

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

   For more on integrating the triggering of an event into an external system, see [Site integration](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

   >[!NOTE]
   >
   >没有注册令牌、应用程序和推送平台字段。在此示例中，对电子邮件字段执行了排序。

