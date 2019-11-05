---
title: 交易推送通知
description: 了解如何创建和发布交易推送通知。
page-status-flag: 从未激活
uuid: ef31c1b6-9ef8-42e3-b49d-72f9eac8ea32
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 频道
content-type: 参考
topic-tags: 事务消息传递
discoiquuid: e645d4b9-001f-47d9-8a0f-b4696c75c5d3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 交易推送通知{#transactional-push-notifications}

您可以使用Adobe Campaign在iOS和Android移动设备上发送交易推送通知。 这些消息会在您在Adobe Campaign中设置的移动应用程序上通过利用Experience Cloud Mobile SDK接收。

>[!NOTE]
>
>推送渠道是可选的。 请检查您的许可协议。 有关标准推送通知的详细信息，请参阅 [推送通知](../../channels/using/about-push-notifications.md)。

您可以发送两种类型的事务推送通知：

* 针对活动的交易推送通知。
* Adobe Campaign数据库中的事务推送通知定位配置文件。

创建并发布活动(本节中介绍的购物车放弃 [情况](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle))后，将自动创建相应的交易推送通知。

配置事件以发送事务推送通 [知部分中介绍了配置步骤](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 。

为了使活动触发发送交易消息，您必须个性化消息，然后测试并发布消息。

>[!NOTE]
>
>要访问事务性消息，您必须是安全组的一 **[!UICONTROL Administrators (all units)]** 部分。

## 针对活动的交易推送通知 {#transactional-push-notifications-targeting-an-event}

您可以向已选择接收移动应用程序通知的所有用户发送匿名交易推送通知。

在这种情况下，仅使用事件本身包含的数据来定义交付目标。 Adobe Campaign集成配置文件数据库中没有数据被利用。

### 发送针对活动的交易推送通知 {#sending-a-transactional-push-notification-targeting-an-----------event}

例如，航空公司希望邀请其移动应用程序用户前往相关登机口登机。

公司将使用一个移动应用程序通过一个设备，为每个用户发送一个交易推送通知（用注册令牌标识）。

1. 转到为编辑而创建的交易消息。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).

   ![](assets/message-center_push_message.png)

1. 单击 **[!UICONTROL Content]** 该块可修改消息的标题和正文。

   您可以插入个性化字段以添加在创建活动时定义的元素。

   ![](assets/message-center_push_content.png)

   要查找这些字段，请单击项目旁边的铅笔，单 **[!UICONTROL Insert personalization field]** 击并选择 **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]**。

   ![](assets/message-center_push_personalization.png)

   有关编辑推送通知内容的详细信息，请参 [阅创建推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)。

1. 保存更改并发布消息。 请参 [阅发布交易消息](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)。
1. 使用Adobe Campaign Standard REST API，使用Android(gcm)上的一个移动应用程序(WeFlight)将事件发送到注册令牌(ABCDEF123456789)，其中包含登记数据。

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

   有关将事件触发集成到外部系统的详细信息，请参阅站 [点集成](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

如果存在注册令牌，则相应的用户接收包括以下内容的事务推送通知：

“简·格林，您好！ 请前往B18号门。”

## 针对个人资料的交易推送通知 {#transactional-push-notifications-targeting-a-profile}

您可以向订阅了移动应用程序的Adobe Campaign配置文件发送交易推送通知。 此分发可包含 [个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field) ，如收件人的名字。

在这种情况下，活动必须包含一些字段，以允许与Adobe Campaign数据库中的配置文件进行对帐。

定位配置文件时，每个移动应用程序和每个设备发送一个事务推送通知。 例如，如果Adobe Campaign用户订阅了两个应用程序，则此用户将收到两个通知。 如果用户订阅了具有两个不同设备的同一应用程序，则此用户将在每个设备上收到通知。

配置文件订阅的手机应用程序列在此配置文件 **[!UICONTROL Mobile App Subscriptions]** 的选项卡中。 要访问此选项卡，请选择一个配置文件，然后单 **[!UICONTROL Edit profile properties]** 击右侧的按钮。

![](assets/push_notif_subscriptions.png)

有关访问和编辑配置文件的详细信息，请参阅 [配置文件](../../audiences/using/creating-profiles.md)。

### 发送针对配置文件的交易推送通知 {#sending-a-transactional-push-notification-targeting-a-----------profile}

例如，某航空公司希望向订阅其移动应用程序的所有Adobe Campaign用户发送最后一次登机通知。

1. 转到为编辑而创建的交易消息。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).

   <!--![](assets/message-center_push_message_profile.png)-->

1. 单击 **[!UICONTROL Content]** 该块可修改消息的标题和正文。

   与基于实时事件的配置不同，您可以直接访问所有配置文件信息以个性化您的信息。 请参 [阅插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)。

   <!--![](assets/message-center_push_content_profile.png)-->

   有关编辑推送通知内容的更多信息。 请参 [阅创建推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)。

1. 保存更改并发布消息。 请参 [阅发布交易消息](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)。
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

   有关将事件触发集成到外部系统的详细信息，请参阅站 [点集成](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

   >[!NOTE]
   >
   >没有注册令牌、应用程序和推送平台字段。 在此示例中，对帐将与电子邮件字段一起执行。

