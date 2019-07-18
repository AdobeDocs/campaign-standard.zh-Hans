---
title: 电子邮件发送
seo-title: 电子邮件发送
description: 电子邮件发送
seo-description: 通过电子邮件发送活动，您可以配置在工作流中发送单个发送电子邮件或重复电子邮件。
page-status-flag: 从未激活
uuid: de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 渠道活动
discoiquuid: 5f288cf6-f8 ff-4ac9-9c1 a-8010260554bb
context-tags: 交付，工作流程，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Email delivery{#email-delivery}

## Description {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

**[!UICONTROL Email delivery]** 活动允许您配置在工作流中发送电子邮件。This can be a **single send** email and sent just once, or it can be a **recurring** email.

单发送电子邮件是标准电子邮件，发送一次。

重复电子邮件允许您在定义的时间段内将相同的电子邮件多次发送到不同的目标。您可以将分发汇总为每个时段，以获得符合您的需求的报表。

## Context of use {#context-of-use}

**[!UICONTROL Email delivery]** 该活动通常用于自动向在同一工作流程中计算的目标发送电子邮件。

链接到计划程序时，您可以定义重复的电子邮件。

通过定向活动(如查询、交叉点等)，电子邮件收件人在同一工作流程中的活动上游进行定义。

消息准备会根据工作流执行参数触发。在消息仪表板中，您可以选择是请求还是不需要手动确认发送消息(默认情况下需要)。您可以手动启动工作流或在工作流中放置调度程序活动以自动执行执行。

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Email delivery]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button from the activity's quick actions. This button is specific to the **[!UICONTROL Email delivery]** activity. 电子邮件的属性可通过电子邮件仪表板中的操作栏进行访问。

1. 选择电子邮件发送模式：

   * **[!UICONTROL Email]**：电子邮件将发送一次。您可以在此处指定是否要为活动添加出站过渡。此过程的步骤中详细介绍了不同的过渡类型。
   * **[!UICONTROL Recurring email]**：电子邮件会根据 **[!UICONTROL Scheduler]** 活动中定义的频率多次发送。选择发送的汇总时间。This allows you to regroup all the sends that occur during the defined period in one single email that is also called **Recurring execution** and can be accessed from the application's marketing activity list.

      例如，对于每天发送的重复生日电子邮件，您可以选择将发送汇总每个月。这允许您按月接收提交报告，但每天发送电子邮件。

1. 选择电子邮件类型。The email types come from email templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** menu.
1. 输入电子邮件的常规属性。您还可以将其附加到现有营销活动。工作流的交付活动的标签会使用电子邮件标签进行更新。
1. 定义电子邮件内容。Refer to the section concerning [content editing](../../designing/using/about-email-content-design.md).
1. By default, the **[!UICONTROL Email delivery]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL Email delivery]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**：这使您能够生成包含与入站过渡相同的相同人群的出站过渡。
   * **[!UICONTROL Add outbound transition with the population]**：这使您能够生成包含电子邮件发送人群的出站过渡。在交付准备过程中排除的目标成员(隔离、无效电子邮件等)已排除在此过渡中。

1. 确认活动的配置并保存工作流。

重新打开活动时，您会被直接转至电子邮件仪表板。只能编辑其内容。

默认情况下，启动交付工作流只会触发消息准备。在启动工作流之后，仍需要确认从工作流创建的消息的发送。But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. 通过取消选中此选项，准备完成后无需进一步通知即可发送消息。

## Remarks {#remarks}

在工作流中创建的分发可以在应用程序的营销活动列表中访问。您可以使用仪表板查看工作流的执行状态。通过电子邮件摘要窗格中的链接，您可以直接访问链接的元素(工作流、营销活动、父交付以出现重复的电子邮件)。

![](assets/wkf_display_recurrent_executions_2.png)

但是，默认情况下会掩盖重复分发的执行。To view them, check the **[!UICONTROL Show recurring executions]** option in the marketing activities' search panel.

![](assets/wkf_display_recurrent_executions.png)

In the parent deliveries, which can be accessed from the marketing activity list or directly via the associated recurring executions, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL Email delivery]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3.png)

## Example {#example}

![](assets/wkf_delivery_example_1.png)

此示例为生日工作流程。每天都将收到一封电子邮件，其中包含当天生日的配置文件。要执行此操作，请执行以下操作：

* The **[!UICONTROL Scheduler]** allows you to start the workflow every day at 8am.

   ![](assets/wkf_delivery_example_2.png)

* **[!UICONTROL Query]** 通过活动，您可以计算提供电子邮件的配置文件，以及每次执行工作流时的生日。生日计算使用查询编辑工具中调色板中提供的预定义过滤器进行。

   ![](assets/wkf_delivery_example_3.png)

* **[!UICONTROL Email]** 重复。发送按月汇总。因此，一个月内发送的所有电子邮件都会汇总到单个视图中。In one year, 365 deliveries are therefore executed but they are regrouped into 12 views (also called **recurring executions**) in the Adobe Campaign interface. 历史记录和报告详细信息每月显示，而不是每次发送。

   ![](assets/wkf_delivery_example_4.png)

