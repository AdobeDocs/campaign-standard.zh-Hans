---
title: 事务性消息生命周期
description: 了解如何发布、暂停、取消发布和删除事务型消息。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 12fe13c2-899d-4c85-8381-ba812ff26f54
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 70%

---

# 事务性消息生命周期 {#publishing-transactional-message}

当 [事务性消息](../../channels/using/editing-transactional-message.md) 已准备好发送，可以发布。

发布、暂停、取消发布和删除事务型消息的步骤详见下文。

>[!IMPORTANT]
>
>仅限具有下列属性的用户： [管理](../../administration/using/users-management.md#functional-administrators) 角色可以访问和发布事务性消息。

## 事务型消息传递发布流程 {#transactional-messaging-pub-process}

下图说明了整个事务型消息传递发布流程。

![](assets/message-center_pub-process.png)

**相关主题：**
* [发布事务型消息](#publishing-a-transactional-message)
* [暂停事务型消息](#suspending-a-transactional-message-publication)
* [取消发布事务型消息](#unpublishing-a-transactional-message)
* [发布事件](../../channels/using/publishing-transactional-event.md)

<!--## Testing a transactional message {#testing-a-transactional-message}

You first need to create a specific test profile that will allow you to properly check the transactional message.

### Defining a specific test profile {#defining-specific-test-profile}

Define a test profile that will be linked to your event, which will allow you to preview your message and send a relevant proof.

1. From the transactional message dashboard, click the **[!UICONTROL Create test profile]** button.

   ![](assets/message-center_test-profile.png)

1. Specify the information to send in JSON format in the **[!UICONTROL Event data used for personalization]** section. This is the content that will be used when previewing the message and when the test profile receives the proof.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >You can also enter the information relating to the profile table. See [Enriching the event](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) and [Personalizing a transactional message](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

1. Once created, the test profile will be pre-specified in the transactional message. Click the **[!UICONTROL Test profiles]** block of the message to check the target of your proof.

   ![](assets/message-center_5.png)

You can also create a new test profile or use one that already exists in the **[!UICONTROL Test profiles]** menu. To do this:

1. Click the **Adobe** logo, in the top-left corner, then select **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. In the **[!UICONTROL Event]** section, select the event that you have just created. In this example, select "Cart abandonment (EVTcartAbandonment)".
1. Specify the information to send in JSON format in the **[!UICONTROL Event data]** text box.

   ![](assets/message-center_3.png)

1. Save your changes.
1. Access the message that you created and select the updated test profile.

**Related topics:**

* [Managing test profiles](../../audiences/using/managing-test-profiles.md)
* [Creating audiences](../../audiences/using/creating-audiences.md)

### Sending the proof {#sending-proof}

Once you have created one or more specific test profiles and saved your transactional message, you can send a proof to test it.

![](assets/message-center_10.png)

The steps for sending a proof are detailed in the [Sending proofs](../../sending/using/sending-proofs.md) section.-->

## 发布事务型消息 {#publishing-a-transactional-message}

编辑并测试事务型消息后，即可发布该消息。 只需单击 **[!UICONTROL Publish]** 按钮。

![](assets/message-center_12.png)

现在，一旦触发“购物车废弃”事件，就会自动提示发送消息，其中包含收件人的头衔和姓氏、购物车 URL、查看的最后一个产品或产品清单（如果您定义了产品清单）以及购物车总金额。

要访问有关事务型消息的报告，请使用 **[!UICONTROL Reports]** 按钮。请参阅 [动态报告](../../reporting/using/about-dynamic-reports.md).

![](assets/message-center_13.png)

**相关主题**：
* [编辑事务性消息](../../channels/using/editing-transactional-message.md)
* [测试事务性消息](../../channels/using/testing-transactional-message.md)
* [集成事件触发](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)

## 暂停事务型消息发布 {#suspending-a-transactional-message-publication}

例如，可以使用 **[!UICONTROL Pause]** 按钮暂停发布事务型消息，以修改消息中包含的数据。这样，就不会再处理事件，而是将其保留在 Adobe Campaign 数据库的队列中。

排队事件的保留期限，在REST API中定义(请参阅 [REST API文档](../../api/using/managing-transactional-messages.md))或在trigger事件中（如果您使用的是Triggers核心服务）(请参阅 [关于Adobe Experience Cloud Triggers](../../integrating/using/about-adobe-experience-cloud-triggers.md))。

![](assets/message-center_pause.png)

单击 **[!UICONTROL Resume]** 后，将继续处理所有排队的事件（前提是它们未过期）。现在，它们包含暂停模板发布时执行的所有修改。

## 取消发布事务型消息 {#unpublishing-a-transactional-message}

单击 **[!UICONTROL Unpublish]** 可取消事务型消息发布，但也会取消相应事件的发布，从 REST API 中删除与之前创建的事件对应的资源。

![](assets/message-center_unpublish-template.png)

现在，即使是通过您的网站触发了事件，也不再发送相应的消息，也不会将消息存储在数据库中。

>[!NOTE]
>
>要再次发布消息，您需要返回到相应的事件配置， [发布事件](../../channels/using/publishing-transactional-event.md)，然后 [发布消息](#publishing-a-transactional-message).

如果取消发布已暂停的事务型消息，则可能需要等待最多 24 小时，才能再次发布该消息。这是为了让 **[!UICONTROL Database cleanup]** 工作流清理发送到队列的所有事件。

有关暂停消息的详细步骤，请参阅[暂停事务型消息发布](#suspending-a-transactional-message-publication)一节。

**[!UICONTROL Database cleanup]** 工作流每天凌晨 4 点运行，可通过 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Workflows]** 访问。

## 删除事务型消息 {#deleting-a-transactional-message}

取消发布某条事务型消息后，或尚未发布该事务型消息时，可以从事务型消息列表中删除该消息。操作步骤：

1. 单击 **Adobe** 徽标，位于左上角，然后选择 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.
1. 将鼠标指针悬停在您选择的消息上。
1. 单击 **[!UICONTROL Delete element]** 按钮。

![](assets/message-center_delete-template.png)

但是，删除事务型消息只能在特定条件下完成：

* 确保事务型消息具有 **[!UICONTROL Draft]** 状态，否则您将无法删除它。**[!UICONTROL Draft]** 状态适用于尚未发布或[已取消发布](#unpublishing-a-transactional-message)（且[未暂停](#suspending-a-transactional-message-publication)）的消息。

* **事务型消息**：除非将其他事务型消息链接到相应的事件，否则如果事务型消息已取消发布，则还需要取消发布事件配置才能成功删除事务型消息。有关更多信息，请参阅[取消发布事件](../../channels/using/publishing-transactional-event.md#unpublishing-an-event)。

  >[!IMPORTANT]
  >
  >删除已发送通知的事务型消息，也会删除其发送和跟踪日志。

* **来自现成事件模板的事务型消息（内部事务型消息）**：如果内部事务型消息是唯一与相应内部事件关联的消息，则无法删除该消息。首先必须复制事务型消息或通过 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Transactional message templates]** 菜单创建另一个事务型消息。

<!--## Monitoring transactional message delivery {#monitoring-transactional-message-delivery}

Once the message is published and your site integration is done, you can monitor the delivery.

To monitor transactional messaging, you need to access **execution deliveries**. An execution delivery is a non-actionable and non-functional technical message created once a month for each transactional message, and each time a transactional message is edited and published again.

1. To view the message delivery log, click the icon at the bottom right of the **[!UICONTROL Deployment]** block.

   ![](assets/message-center_access_logs.png)

1. Click the **[!UICONTROL Execution list]** tab.

   ![](assets/message-center_execution_tab.png)

1. Select the execution delivery of your choice.

   ![](assets/message-center_execution_delivery.png)

1. Click again the icon at the bottom right of the **[!UICONTROL Deployment]** block.

   ![](assets/message-center_execution_access_logs.png)

   For each execution delivery, you can consult the delivery logs as you would do for a standard delivery. For more on accessing and using the logs, see [Monitoring a delivery](../../sending/using/monitoring-a-delivery.md).

**Related topics**:
* [Publishing a transactional message](#publishing-a-transactional-message)
* [Integrate the event triggering](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)

### Profile-based transactional message specificities {#profile-transactional-message-monitoring}

For profile-based transactional messages, you can monitor the following profile information.

Select the **[!UICONTROL Sending logs]** tab. In the **[!UICONTROL Status]** column, **[!UICONTROL Sent]** indicates that a profile has opted in.

![](assets/message-center_marketing_sending_logs.png)

Select the **[!UICONTROL Exclusions logs]** tab to view recipients who have been excluded from the message target, such as addresses on denylist.

![](assets/message-center_marketing_exclusion_logs.png)

For any profile that has opted out, the **[!UICONTROL Address on denylist]** typology rule excluded the corresponding recipient.

This rule is part of a specific typology that applies to all transactional messages based on the **[!UICONTROL Profile]** table.

![](assets/message-center_marketing_typology.png)

**Related topics**:

* [About typologies and typology rules](../../sending/using/about-typology-rules.md)
* [Monitoring a delivery](../../sending/using/monitoring-a-delivery.md)

## Transactional message retry process {#transactional-message-retry-process}

A temporarily undelivered transactional message is subject to automatic retries that are performed until the delivery expires. For more on the delivery duration, see [Validity period parameters](../../administration/using/configuring-email-channel.md#validity-period-parameters).

When a transactional message fails to be sent, there are two retry systems:

* At the transactional messaging level, a transactional message can fail before the event is assigned to an execution delivery, meaning between the event reception and the delivery preparation. See [Event processing retry process](#event-processing-retry-process).
* At the sending process level, once the event has been assigned to an execution delivery, the transactional message can fail due to a temporary error. See [Message sending retry process](#message-sending-retry-process).

The definition of **execution delivery** can be found in the [Monitoring transactional message delivery](#monitoring-transactional-message-delivery) section.

### Event processing retry process {#event-processing-retry-process}

When an event is triggered, it is assigned to an execution delivery.

If the event cannot be assigned to an execution delivery, the event processing is postponed. Retries are then performed until it is assigned to a new execution delivery.

>[!NOTE]
>
>A postponed event does not appear in the transactional message sending logs, because it is not assigned to an execution delivery yet.

For example, the event could not be assigned to an execution delivery because its content was not correct, there was an issue with access rights or branding, an error was detected on applying typology rules, etc. In this case, you can pause the message, edit it to fix the problem and publish it again. The retry system will then assign it to a new execution delivery.

### Message sending retry process {#message-sending-retry-process}

Once the event has been assigned to an execution delivery, the transactional message can fail due to a temporary error, if the recipient's mailbox is full for example. For more on this, see [Retries after a delivery temporary failure](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>When an event is assigned to an execution delivery, it appears in the sending logs of this execution delivery, and only at this time. The failed deliveries are displayed in the **[!UICONTROL Execution list]** tab of the transactional message sending logs.

### Retry process limitations {#limitations}

**Sending logs update**

In the retry process, the sending logs of the new execution delivery are not immediately updated (the update is performed through a scheduled workflow). It means that the message could be in **[!UICONTROL Pending]** status even if the transactional event has been processed by the new execution delivery.

**Failed execution delivery**

You cannot stop an execution delivery. However, if the current execution delivery fails, a new one is created as soon as a new event is received, and all new events are processed by this new execution delivery. No new events are processed by the failed execution delivery.

If some events already assigned to an execution delivery have been postponed as part of the retry process and if that execution delivery fails, the retry system does not assign the postponed events to the new execution delivery, which means that these events are lost. Check the [delivery logs](#monitoring-transactional-message-delivery) to see the recipients that may have been impacted.-->
