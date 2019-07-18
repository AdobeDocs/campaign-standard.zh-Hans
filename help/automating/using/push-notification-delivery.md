---
title: 推送通知交付
seo-title: 推送通知交付
description: 推送通知交付
seo-description: 推送通知交付活动允许您在工作流中配置单个发送推送通知或重复推送通知。
page-status-flag: 从未激活
uuid: 994d8fe3-29f0-4b5c-89ee-c6 be7 c60 a31 b
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 渠道活动
discoiquuid: e61bdaee-4b48-4845-a2 a5-574b577 ea796
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Push notification delivery{#push-notification-delivery}

## Description {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

**[!UICONTROL Push notification]** 活动允许您配置在工作流中发送推送通知。This can be a **single send** notification and sent just once, or it can be a **recurring** notification.

单个发送通知是标准移动应用推送通知交付，发送一次。

重复通知允许您在定义的时间段内将相同的移动应用推送通知发送多次发送到不同目标。您可以将分发汇总为每个时段，以获得符合您的需求的报表。

## Context of use {#context-of-use}

**[!UICONTROL Push notification]** 该活动通常用于自动向在同一工作流中计算的目标发送通知。

链接到计划程序时，您可以定义重复的推送通知。

收件人通过诸如查询、交叉点等定位活动在同一工作流程中定义活动上游。

消息准备会根据工作流执行参数触发。在消息仪表板中，您可以选择是请求还是不需要手动确认发送消息(默认情况下需要)。您可以手动启动工作流或在工作流中放置调度程序活动以自动执行执行。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Push notification]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button from the activity's quick actions. This button is specific to the **[!UICONTROL Push notification]** activity. 推送通知的属性可通过推送功能板中的操作栏进行访问。

1. 选择推送通知发送模式：

   * **[!UICONTROL Single notification]**：推送通知将发送一次。您可以在此处指定是否要为活动添加出站过渡。此过程的步骤中详细介绍了不同的过渡类型。
   * **[!UICONTROL Recurring notification]**：推送通知会根据 **[!UICONTROL Scheduler]** 活动中定义的频率多次发送。选择发送的汇总时间。This allows you to regroup all the sends that occur during the defined period in one single push notification that is also called **recurring execution** and can be accessed from the application's marketing activity list.

      例如，对于每天发送的重复生日通知，您可以选择将发送汇总每个月。这允许您按月接收提交报告，但每天发送通知。

1. 选择通知类型。These types come from push notifications templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** menu.
1. 输入推送通知的常规属性。您还可以将其附加到现有营销活动。使用推送通知标签更新工作流的交付活动的标签。
1. 定义推送通知内容。See [Creating a push notification](../../channels/using/preparing-and-sending-a-push-notification.md)
1. By default, the **[!UICONTROL Push notification]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL Push Notification]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**：这使您能够生成包含与入站过渡相同的相同人群的出站过渡。
   * **[!UICONTROL Add outbound transition with the population]**：这使您能够生成包含通知向其发送的人群的出站过渡。分发准备过程中排除的目标成员将从该过渡中排除。

1. 确认活动的配置并保存工作流。

重新打开活动时，您被直接转至推送通知仪表板。只能编辑其内容。

默认情况下，启动交付工作流只会触发消息准备。在启动工作流之后，仍需要确认从工作流创建的消息的发送。But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. 通过取消选中此选项，准备完成后无需进一步通知即可发送消息。

## Remarks {#remarks}

在工作流中创建的分发可以在应用程序的营销活动列表中访问。您可以使用仪表板查看工作流的执行状态。推送通知摘要窗格中的链接允许您直接访问链接的元素(工作流、营销活动等)。

In the parent deliveries, which can be accessed from the marketing activity list, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL Push notification]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).

## Sending a recurring push notification with a workflow {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

在此示例中，根据用户的时区，个性化推送通知将发送到移动应用程序订阅者的每日每的第一天。要执行此操作，请执行以下操作：

1. **[!UICONTROL Scheduler]** 活动允许您启动交付开始前的工作流程，以便在任何给定时区发送通知至每位订阅者：

   * In the **[!UICONTROL Execution frequency]** field, select Monthly.
   * Select 8 pm in the **[!UICONTROL Time]** field.
   * 选择每月发送的发送日期。
   * 为您的工作流选择一个开始日期，即交付开始前的一天。否则，如果选定的时间已经在其时区内传递，则某些收件人稍后可能收到消息。
   * In the **[!UICONTROL Execution options]** tab, select at which time zone your workflow will start in the **[!UICONTROL Time zone]** field. 例如，此工作流将于太平洋时间晚上点(太平洋时间)从月的第一天开始，为所有适用时区创建交付时间。
   ![](assets/wkf_push_example_5.png)

1. **通过查询** 活动，您可以定位20-30年间已订阅移动应用程序且未打开发送的电子邮件的VIP客户：

   * 选择受众(您的VIP客户)并在其年龄进行筛选。
   * Drag and drop the **Subscriptions to an application** element into the workspace. Select **Exists** and select the mobile application that you want to use.
   * 选择发送给客户的电子邮件。
   * Drag and drop the **Delivery logs (logs)** element into the workspace and select **Exists** to target all of the customers who received the email.
   * Drag and drop the **Tracking logs (tracking)** element into the workspace and select **Does not exist** to target all of the customers who did not open the email.

      ![](assets/wkf_push_example_2.png)

1. **推送通知** 活动允许您输入消息的内容，并选择要使用的个性化字段：

   * Select the **[!UICONTROL Recurring notification]** option.
   * 定义推送通知内容。For more information on push notification content, refer to this [section](../../channels/using/preparing-and-sending-a-push-notification.md).
   * In the **[!UICONTROL Schedule]** block, select **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Here, we chose the **[!UICONTROL Time zone of the contact date]** Pacific as in the workflow **[!UICONTROL Scheduler]**.
   * In the **[!UICONTROL Optimize the sending time per recipient]** field, select **[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Click the **[!UICONTROL Start]** button to start your recurring workflow.

   ![](assets/wkf_push_example_3.png)

您的工作流现在正在运行。It will start at the chosen start date of the **[!UICONTROL Scheduler]** at 8 pm Pacific time, the recurring push will then be sent every first day of the month at 8 pm depending on the customers time zone.
