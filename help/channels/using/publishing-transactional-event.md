---
title: 发布事务性事件
description: 了解如何预览、发布、取消发布和删除事务性事件配置。
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

一次 [配置](../../channels/using/configuring-transactional-event.md) 完成，事件准备就绪，可供发布。 预览、发布、取消发布和删除事件的步骤如下所示。

>[!IMPORTANT]
>
>仅 [功能管理员](../../administration/using/users-management.md#functional-administrators) <!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) -->具有发布事件配置的适当权限。

中提供了用于说明整个事务型消息传递发布流程（包括发布和取消发布事件配置）的图表 [本节](../../channels/using/publishing-transactional-message.md).

发布完成后：
* 将自动创建相应的事务型消息。 请参阅 [编辑事务型消息](../../channels/using/editing-transactional-message.md).
* 将部署您的网站开发人员使用的API，现在可以发送事务性事件。 请参阅 [集成事件触发](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

## 预览和发布事件 {#previewing-and-publishing-the-event}

必须先预览并发布该事件，然后才能使用它。

1. 单击 **[!UICONTROL API preview]** 按钮以查看您的网站开发人员在发布之前使用的REST API的模拟。

   发布事件后，此按钮还允许您查看生产环境中API的预览。 请参阅 [集成事件触发](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST API会根据所选渠道和所选定向维度而有所不同。 有关各种配置的更多详细信息，请参阅 [本节](../../channels/using/configuring-transactional-event.md#transactional-event-specific-configurations).

1. 单击 **[!UICONTROL Publish]** 以开始发布。

   ![](assets/message-center_pub.png)

   将部署您的网站开发人员使用的API，现在可以发送事务性事件。

1. 您可以在相应的选项卡中查看发布日志。

   ![](assets/message-center_logs.png)

   >[!IMPORTANT]
   >
   >每次修改事件时，都必须单击 **[!UICONTROL Publish]** 再次生成将由网站开发人员使用的更新REST API。

   发布事件后， [事务性消息](../../channels/using/editing-transactional-message.md) 链接到新事件的链接会自动创建。

1. 您可以通过位于左侧区域的链接直接访问此事务型消息。

   ![](assets/message-center_messagegeneration.png)

   >[!NOTE]
   >
   >为了让事件触发发送事务型消息，您必须修改并发布刚刚创建的消息。 请参阅 [编辑](../../channels/using/editing-transactional-message.md) 和 [发布事务型消息](../../channels/using/publishing-transactional-message.md) 部分。 您还必须 [集成此触发器事件](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) 放到您的网站中。

1. 在Adobe Campaign开始接收与此事件配置相关的事件后，您可以单击 **[!UICONTROL Latest transactional events]** 链接位于 **[!UICONTROL History]** 部分，用于访问由第三方服务发送并由Adobe Campaign处理的最新事件。

![](assets/message-center_latest-events.png)

事件（以JSON格式）按从最近到最旧的顺序列出。 此列表允许您检查数据（如内容或事件的状态），以便进行控制和调试。

## 取消发布事件 {#unpublishing-an-event}

此 **[!UICONTROL Unpublish]** 按钮允许您取消事件的发布，从REST API中删除与之前创建的事件对应的资源。

现在，即使是通过您的网站触发了事件，也不再发送相应的消息，也不会将消息存储在数据库中。

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>如果已经发布相应的事务型消息，则事务型消息的发布也会被取消。 请参阅 [取消发布事务型消息](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message).

单击 **[!UICONTROL Publish]** 按钮以生成新的REST API。

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on publishing, pausing and unpublishing a transactional message, see [this section](../../channels/using/publishing-transactional-message.md).-->

## 删除事件 {#deleting-an-event}

取消发布事件后，或尚未发布事件时，您可以从事件配置列表中删除事件。 操作步骤：

1. 单击 **Adobe** 徽标，位于左上角，然后选择 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. 将鼠标悬停在您选择的事件配置上，然后选择 **[!UICONTROL Delete element]** 按钮。

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   >
   >确保事件配置具有 **[!UICONTROL Draft]** 状态，否则您将无法删除它。 此 **[!UICONTROL Draft]** 状态适用于尚未发布或已经发布的事件 [已取消发布](#unpublishing-an-event).

1. 单击 **[!UICONTROL Confirm]** 按钮。

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
>
>删除已发布并已使用的事件配置也将删除相应的事务型消息及其发送和跟踪日志。
