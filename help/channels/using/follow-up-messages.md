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

跟进消息是预定义的营销投放模板，可在工作流中使用它向特定事务型消息的收件人发送其他通信。

让我们重用[事务性消息传递工作原理](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)部分中描述的示例：向向将产品添加到购物车但没有完成购买就离开网站的网站用户发送购物车放弃电子邮件。

您希望向所有收到购物车放弃通知但在三天后未打开该通知的客户发送友好的提醒。 他们将会收到一封跟进邮件，其内容与所发送的第一封电子邮件中所用的数据相同。

## 配置事件以发送跟进消息 {#configuring-an-event-to-send-a-follow-up-message}

要发送跟进消息，您首先需要相应地配置与已收到事务型消息对应的事件。

1. 使用您创建的相同事件配置发送事件事务型消息。 请参阅[配置事务性事件](../../channels/using/configuring-transactional-event.md)。
1. 配置事件时，请在发布事件之前选中&#x200B;**[!UICONTROL Create follow-up delivery template for this event]**&#x200B;框。

   ![](assets/message-center_follow-up-checkbox.png)

1. [预览和发布事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

发布事件后，将自动创建事务型消息和链接到新事件的跟进投放模板。 在[此部分](#sending-a-follow-up-message)中详细介绍了发送跟进消息的步骤。

## 访问跟进消息 {#accessing-the-follow-up-messages}

要在工作流中处理事件，需要投放模板。 但是，在发布事件时，创建的[事务型消息](../../channels/using/editing-transactional-message.md)不能用作模板。 因此，您需要创建一个特定的跟进投放模板，专门用于支持此事件类型，并用作工作流中的模板。

要访问此模板，请执行以下操作：

1. 单击左上角的&#x200B;**Adobe**&#x200B;徽标。
1. 选择&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**。
1. 选中左窗格中的&#x200B;**[!UICONTROL Follow-up messages]**&#x200B;框。

   ![](assets/message-center_follow-up-search.png)

只显示跟进消息。

>[!IMPORTANT]
>
>只有具有[管理](../../administration/using/users-management.md#functional-administrators)角色的用户才能访问和编辑事务型消息。

## 发送跟进消息 {#sending-a-follow-up-message}

创建跟进投放模板后，您可以在工作流中使用它来发送跟进消息。

<!--You need to set up a workflow targeting the event corresponding to the transactional message that was already received.-->

1. 访问营销活动列表并创建新工作流。

   请参阅[构建工作流](../../automating/using/building-a-workflow.md#creating-a-workflow)。

1. 将&#x200B;**[!UICONTROL Scheduler]**&#x200B;活动拖放到工作流中并将其打开。 将执行频率设置为每天一次。

   调度程序活动显示在[调度程序](../../automating/using/scheduler.md)部分中。

1. 将&#x200B;**[!UICONTROL Query]**&#x200B;活动拖放到工作流中并将其打开。

   查询活动显示在[查询](../../automating/using/query.md)部分中。

1. 要在非用户档案资源上运行查询，请转到活动的&#x200B;**[!UICONTROL Properties]**&#x200B;选项卡，然后单击&#x200B;**[!UICONTROL Resource]**&#x200B;下拉列表。

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >默认情况下，该活动预配置为搜索用户档案。

1. 选择要定向的事件，以便仅访问此事件的数据。

   ![](assets/message-center_follow-up-query-resource.png)

1. 转到活动的&#x200B;**[!UICONTROL Target]**&#x200B;选项卡，并将&#x200B;**[!UICONTROL Delivery logs (logs)]**&#x200B;元素从面板拖放到工作区中。

   ![](assets/message-center_follow-up-delivery-logs.png)

   选择&#x200B;**[!UICONTROL Exists]**&#x200B;以定向收到电子邮件的所有客户。

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. 将&#x200B;**[!UICONTROL Tracking logs (tracking)]**&#x200B;元素从面板移到工作区，然后选择&#x200B;**[!UICONTROL Does not exist]**&#x200B;以定向所有未打开电子邮件的客户。

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. 将您定位的事件（本例中为&#x200B;**购物车放弃**）从面板拖放到工作区中。 然后，定义规则以定向三天前发送的所有消息。

   ![](assets/message-center_follow-up-created.png)

   这意味着所有在工作流执行前三天收到事务型消息且仍未打开该消息的收件人都会被定向。

   单击&#x200B;**[!UICONTROL Confirm]**&#x200B;保存查询。

1. 将&#x200B;**电子邮件投放**&#x200B;活动拖放到您的工作流中。

   电子邮件投放活动显示在[电子邮件投放](../../automating/using/email-delivery.md)部分。

   ![](assets/message-center_follow-up-workflow.png)

   您还可以使用[短信投放](../../automating/using/sms-delivery.md)或[推送通知投放](../../automating/using/push-notification-delivery.md)活动。 在这种情况下，请确保在创建事件配置时选择&#x200B;**[!UICONTROL Mobile (SMS)]**&#x200B;或&#x200B;**[!UICONTROL Mobile application]**&#x200B;渠道。 请参阅[创建事件](../../channels/using/configuring-transactional-event.md#creating-an-event)。

1. 打开&#x200B;**电子邮件投放**&#x200B;活动。 在创建向导中，选中&#x200B;**[!UICONTROL Follow-up messages]**&#x200B;框并选择发布事件后创建的后续投放模板。

   ![](assets/message-center_follow-up-template.png)

1. 在跟进消息内容中，您可以通过添加个性化字段来利用事件的内容。

   ![](assets/message-center_follow-up-content.png)

1. 通过选择&#x200B;**[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**，查找在创建事件时定义的字段。 请参阅[个性化事务型消息](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)。

   ![](assets/message-center_follow-up-personalization.png)

   这意味着您可以利用首次发送事件时使用的相同内容（包括扩充数据）来创建个性化的友好提醒。

1. 保存活动并启动工作流。

启动工作流后，三天前收到购物车放弃通知但未打开该通知的每个客户都会收到基于相同数据的跟进消息。

>[!NOTE]
>
>如果您在创建事件配置时选择了&#x200B;**[!UICONTROL Profile]**&#x200B;定向维度，则后续消息还将利用Adobe Campaign营销数据库。 请参阅[用户档案事务型消息](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities)。
