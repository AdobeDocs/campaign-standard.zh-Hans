---
title: 跟进消息
description: 了解如何创建、管理和发送跟进消息。
audience: channels
content-type: reference
topic-tags: transactional-messaging
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 0a05cf20-7c8f-406b-acfd-7aece2c5dd26
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 2%

---

# 跟进消息 {#follow-up-messages}

跟进消息是一种预定义的营销投放模板，可用于工作流中，以向特定事务型消息的收件人发送其他通信。

让我们重复使用 [事务型消息传递工作原理](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) 部分：您的网站用户会收到一封放弃购买电子邮件，该电子邮件会将产品添加到购物车，但并未完成购买而离开了网站。

您希望向收到购物车放弃通知但三天后未打开该通知的所有客户发送友好提醒。 他们将收到一则后续消息，该消息所依据的数据与在发送的第一封电子邮件中使用的数据相同。

## 配置事件以发送跟进消息 {#configuring-an-event-to-send-a-follow-up-message}

要发送跟进消息，您首先需要相应地配置与已接收事务型消息对应的事件。

1. 使用创建的事件配置来发送事件事务型消息。 请参阅 [配置事务型事件](../../channels/using/configuring-transactional-event.md).
1. 配置事件时，请检查 **[!UICONTROL Create follow-up delivery template for this event]** 框中。

   ![](assets/message-center_follow-up-checkbox.png)

1. [预览和发布事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

发布事件后，将自动创建事务型消息和链接到新事件的后续投放模板。 有关发送跟进消息的详细步骤，请参见 [此部分](#sending-a-follow-up-message).

## 访问后续消息 {#accessing-the-follow-up-messages}

要处理工作流中的事件，需要投放模板。 但是，在发布事件时， [事务性消息](../../channels/using/editing-transactional-message.md) 创建的模板不能用作模板。 因此，您需要创建特定的后续投放模板，以支持此事件类型并用作工作流中的模板。

要访问此模板，请执行以下操作：

1. 单击 **Adobe** 徽标。
1. 选择 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. 检查 **[!UICONTROL Follow-up messages]** 框。

   ![](assets/message-center_follow-up-search.png)

只显示跟进消息。

>[!IMPORTANT]
>
>仅具有 [管理](../../administration/using/users-management.md#functional-administrators) 角色可以访问和编辑事务型消息。

## 发送跟进消息 {#sending-a-follow-up-message}

创建后续投放模板后，您可以在工作流中使用该模板来发送后续消息。

<!--You need to set up a workflow targeting the event corresponding to the transactional message that was already received.-->

1. 访问营销活动列表并创建新工作流。

   请参阅 [构建工作流](../../automating/using/building-a-workflow.md#creating-a-workflow).

1. 拖放 **[!UICONTROL Scheduler]** 活动并将其打开。 将执行频度设置为每天一次。

   调度程序活动显示在 [调度程序](../../automating/using/scheduler.md) 中。

1. 拖放 **[!UICONTROL Query]** 活动并将其打开。

   有关查询活动，请参阅 [查询](../../automating/using/query.md) 中。

1. 要对用户档案资源以外的资源运行查询，请转到活动的 **[!UICONTROL Properties]** ，然后单击 **[!UICONTROL Resource]** 下拉列表。

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >默认情况下，该活动预配置为搜索用户档案。

1. 选择要定位的事件，以便您仅访问此事件中的数据。

   ![](assets/message-center_follow-up-query-resource.png)

1. 转到活动的 **[!UICONTROL Target]** ，然后拖放 **[!UICONTROL Delivery logs (logs)]** 元素。

   ![](assets/message-center_follow-up-delivery-logs.png)

   选择 **[!UICONTROL Exists]** 定向收到该电子邮件的所有客户。

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. 移动 **[!UICONTROL Tracking logs (tracking)]** 元素，然后选择 **[!UICONTROL Does not exist]** 定向未打开电子邮件的所有客户。

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. 拖放要定位的事件(**放弃购买** 在本例中)从面板移入工作区。 然后，定义一个规则以定位三天前发送的所有消息。

   ![](assets/message-center_follow-up-created.png)

   这意味着在执行工作流三天前收到事务型消息，但尚未打开该消息的所有收件人都将成为目标。

   单击 **[!UICONTROL Confirm]** 来保存查询。

1. 拖放 **电子邮件投放** 活动。

   电子邮件投放活动，请参见 [电子邮件投放](../../automating/using/email-delivery.md) 中。

   ![](assets/message-center_follow-up-workflow.png)

   您还可以使用 [短信投放](../../automating/using/sms-delivery.md) 或 [推送通知投放](../../automating/using/push-notification-delivery.md) 活动。 在这种情况下，请确保选择 **[!UICONTROL Mobile (SMS)]** 或 **[!UICONTROL Mobile application]** 渠道。 请参阅[创建事件](../../channels/using/configuring-transactional-event.md#creating-an-event)。

1. 打开 **电子邮件投放** 活动。 在创建向导中，选中 **[!UICONTROL Follow-up messages]** 框中，选择发布事件后创建的后续投放模板。

   ![](assets/message-center_follow-up-template.png)

1. 在后续消息内容中，您可以通过添加个性化字段来利用事件的内容。

   ![](assets/message-center_follow-up-content.png)

1. 通过选择 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**. 请参阅 [个性化事务型消息](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

   ![](assets/message-center_follow-up-personalization.png)

   这意味着您可以利用首次发送事件时使用的相同内容（包括扩充数据）来创建个性化的友好提醒。

1. 保存活动并启动工作流。

工作流启动后，三天前收到购物车放弃通知但未打开的每位客户都将收到基于相同数据的跟进消息。

>[!NOTE]
>
>如果您选择了 **[!UICONTROL Profile]** 定向维度创建事件配置时，后续消息还将利用Adobe Campaign营销数据库。 请参阅[用户档案事务型消息](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities)。
