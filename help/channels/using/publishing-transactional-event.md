---
title: 发布事务性事件
description: 了解如何预览、发布、取消发布和删除事务事件配置。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 6bcd8dcd-d710-4ca3-937d-bf4339f36069
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 6%

---

# 发布事务性事件 {#publishing-transactional-event}

完成[配置](../../channels/using/configuring-transactional-event.md)后，该事件即可发布。 下面介绍了预览、发布、取消发布和删除事件的步骤。

>[!IMPORTANT]
>
>只有[功能管理员](../../administration/using/users-management.md#functional-administrators) <!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) -->拥有发布事件配置的适当权限。

[此部分](../../channels/using/publishing-transactional-message.md)中提供了一个图表，用于说明整个事务型消息传递发布过程，包括发布和取消发布事件配置。

完成发布后：
* 将自动创建相应的事务型消息。 请参阅[编辑事务型消息](../../channels/using/editing-transactional-message.md)。
* 将部署网站开发人员使用的API，并且现在可以发送事务事件。 请参阅[集成触发](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)的事件。

## 预览和发布事件 {#previewing-and-publishing-the-event}

必须先预览和发布事件，然后才能使用事件。

1. 单击&#x200B;**[!UICONTROL API preview]**&#x200B;按钮可查看网站开发人员在发布之前将使用的REST API模拟。

   发布事件后，此按钮还允许您在生产中查看API预览。 请参阅[集成触发](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)的事件。

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST API会根据所选渠道和所选定向维度而有所不同。 有关各种配置的更多详细信息，请参阅[此部分](../../channels/using/configuring-transactional-event.md#transactional-event-specific-configurations)。

1. 单击&#x200B;**[!UICONTROL Publish]**&#x200B;以开始发布。

   ![](assets/message-center_pub.png)

   将部署网站开发人员使用的API，并且现在可以发送事务事件。

1. 您可以在相应的选项卡中查看发布日志。

   ![](assets/message-center_logs.png)

   >[!IMPORTANT]
   >
   >每次修改事件时，必须再次单击&#x200B;**[!UICONTROL Publish]**&#x200B;以生成更新的REST API，该REST API将由网站开发人员使用。

   发布事件后，将自动创建链接到新事件的[事务型消息](../../channels/using/editing-transactional-message.md)。

1. 您可以通过左侧区域的链接直接访问此事务型消息。

   ![](assets/message-center_messagegeneration.png)

   >[!NOTE]
   >
   >为了让事件触发发送事务型消息，您必须修改并发布之前创建的消息。 请参阅[编辑](../../channels/using/editing-transactional-message.md)和[发布事务型消息](../../channels/using/publishing-transactional-message.md)部分。 您还必须[将此触发器事件](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)集成到您的网站中。

1. Adobe Campaign开始接收与此事件配置相关的事件后，您可以单击&#x200B;**[!UICONTROL History]**&#x200B;部分下的&#x200B;**[!UICONTROL Latest transactional events]**&#x200B;链接，以访问由第三方服务发送并由Adobe Campaign处理的最新事件。

![](assets/message-center_latest-events.png)

事件（JSON格式）从最近到最旧都列出。 利用此列表，可检查内容或事件状态等数据，以进行控制和调试。

## 取消发布事件 {#unpublishing-an-event}

通过&#x200B;**[!UICONTROL Unpublish]**&#x200B;按钮可取消事件的发布，从REST API中删除与之前创建的事件对应的资源。

现在，即使是通过您的网站触发了事件，也不再发送相应的消息，也不会将消息存储在数据库中。

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>如果已发布相应的事务型消息，则事务型消息发布也会被取消。 请参阅[取消发布事务型消息](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message)。

单击&#x200B;**[!UICONTROL Publish]**&#x200B;按钮以生成新的REST API。

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on publishing, pausing and unpublishing a transactional message, see [this section](../../channels/using/publishing-transactional-message.md).-->

## 删除事件 {#deleting-an-event}

取消发布事件后，或尚未发布事件时，可以从事件配置列表中将其删除。 操作步骤：

1. 单击左上角的&#x200B;**Adobe**&#x200B;徽标，然后选择&#x200B;**[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**。
1. 将鼠标悬停在所选事件配置上，然后选择&#x200B;**[!UICONTROL Delete element]**&#x200B;按钮。

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   >
   >确保事件配置具有&#x200B;**[!UICONTROL Draft]**&#x200B;状态，否则您将无法删除它。 **[!UICONTROL Draft]**&#x200B;状态适用于尚未发布或已[取消发布的事件](#unpublishing-an-event)。

1. 单击 **[!UICONTROL Confirm]** 按钮。

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
>
>删除已发布且已使用的事件配置，也会删除相应的事务型消息及其发送和跟踪日志。
