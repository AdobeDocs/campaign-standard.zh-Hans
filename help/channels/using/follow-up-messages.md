---
solution: Campaign Standard
product: campaign
title: 跟进消息
description: 了解如何创建和发布后续消息。
audience: channels
content-type: reference
topic-tags: transactional-messaging
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 4%

---


# 跟进消息{#follow-up-messages}

您可以向收到特定事务性消息的客户发送跟进消息。 为此，您需要设置一个针对相应事件的工作流。

让我们重用Transactional messaging操作原则部分 [中描述的示例](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) :购物车废弃电子邮件将发送给将产品添加到购物车的网站用户，但他们离开网站时并未进行购买。

您希望向收到购物车放弃通知但三天后未打开通知的所有客户发送友好提醒。

然后，每个相关客户将收到一条基于第一封电子邮件中所使用数据的跟进消息。

## 访问后续消息 {#accessing-the-follow-up-messages}

Once you have created and published an event (the cart abandonment as per the [example](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) above), the corresponding transactional message and follow-up message are created automatically.

The configuration steps are presented in the [Configuring an event to send a follow-up message](../../administration/using/configuring-transactional-messaging.md#configuring-an-event-to-send-a-follow-up-message) section.

要处理工作流中的事件，需要投放模板。 但是，在发布事件时， [创建](../../channels/using/event-transactional-messages.md) 的事务性消息不能用作模板。 因此，您需要创建特定的后续投放模板，该事件类型旨在支持此并用作工作流中的模板。

要访问此模板，请执行以下操作：

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner.
1. Select **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. 选中 **[!UICONTROL Follow-up messages]** 左窗格中的框。

   ![](assets/message-center_follow-up-search.png)

仅显示后续消息。

>[!NOTE]
>
>要访问事务型消息，您必须归属于 **[!UICONTROL Administrators (all units)]** 安全组。

## 发送跟进消息 {#sending-a-follow-up-message}

创建后续投放模板后，您可以在工作流中使用它发送后续消息。

1. 访问营销活动列表并创建新工作流。

   See [Creating a workflow](../../automating/using/building-a-workflow.md#creating-a-workflow).

1. Drag and drop a **[!UICONTROL Scheduler]** activity into your workflow and open it. 将执行频率设置为每天一次。

   调度程序活动在 [调度程序](../../automating/using/scheduler.md) 。

1. Drag and drop a **[!UICONTROL Query]** activity into your workflow and open it.

   查询活动在 [查询](../../automating/using/query.md) 。

1. 要对查询资源以外的资源运行用户档案，请转到活动的选 **[!UICONTROL Properties]** 项卡，然后单 **[!UICONTROL Resource]** 击下拉列表。

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >默认情况下，该活动预配置为搜索用户档案。

1. 选择要目标的事件，以便仅访问此事件中的数据。

   ![](assets/message-center_follow-up-query-resource.png)

1. 转到活动的选 **[!UICONTROL Target]** 项卡，并将元素从调 **[!UICONTROL Delivery logs (logs)]** 色板拖放到工作区中。

   ![](assets/message-center_follow-up-delivery-logs.png)

   选 **[!UICONTROL Exists]** 择以目标收到此电子邮件的所有客户。

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. 将元素 **[!UICONTROL Tracking logs (tracking)]** 从调色板移到工作区，然后选 **[!UICONTROL Does not exist]** 择以目标所有未打开电子邮件的客户。

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. 将您定位的事件(本例中&#x200B;**的** “放弃购物车”)从调色板拖放到工作区中。 然后定义一个规则，以目标三天前发送的所有消息。

   ![](assets/message-center_follow-up-created.png)

   这意味着在执行工作流三天前收到事务性消息但尚未打开该工作流的所有收件人都将成为目标。

   Click **[!UICONTROL Confirm]** to save the query.

1. Drag and drop an **Email delivery** activity into your workflow.

   “电子邮件投放”活动显示在“电 [子邮件投放](../../automating/using/email-delivery.md) ”部分。

   ![](assets/message-center_follow-up-workflow.png)

   您还可以使用 [SMS投放](../../automating/using/sms-delivery.md) 或移 [动应用投放](../../automating/using/push-notification-delivery.md) 活动。 在这种情况下，请确保在创建渠道配 **[!UICONTROL Mobile (SMS)]** 置时 **[!UICONTROL Mobile application]** 选择该事件或。 请参阅[创建事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。

1. 打开电子 **邮件投放** 活动。 在创建向导中，选 **[!UICONTROL Follow-up messages]** 中该框并选择发布投放模板后创建的后续事件。

   ![](assets/message-center_follow-up-template.png)

1. 在后续消息内容中，您可以通过添加事件来利用个性化字段的内容。

   ![](assets/message-center_follow-up-content.png)

1. 通过选择> >，查找在创建事件时定义 **[!UICONTROL Context]** 的 **[!UICONTROL Real-time event]** 字段 **[!UICONTROL Event context]**。 See [Personalizing a transactional message](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

   ![](assets/message-center_follow-up-personalization.png)

   这意味着您可以利用第一次发送事件时使用的相同内容（包括丰富数据）来创建个性化的友好提醒。

1. 保存活动并开始工作流。

工作流一旦启动，每位在三天前收到购物车放弃通知但没有打开的客户，都会收到一条基于相同数据的跟进消息。

>[!NOTE]
>
>如果您在创建 **[!UICONTROL Profile]** 定位维度配置时选择了事件，则后续消息还将利用Adobe Campaign营销数据库。 请参阅[用户档案事务型消息](../../channels/using/profile-transactional-messages.md)。
