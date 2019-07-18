---
title: SMS交付
seo-title: SMS交付
description: SMS交付
seo-description: SMS交付活动允许您配置在工作流中发送单个发送SMS或重复SMS。
page-status-flag: 从未激活
uuid: 736078c6-ac91-4440-825b-4a6 ae31894 ef
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 渠道活动
discoiquuid: 978592b8-989a-446a-44-12b7fecfc130
context-tags: sms，main；交付，SMSContent，返回
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# SMS delivery{#sms-delivery}

## Description {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

**[!UICONTROL SMS delivery]** 活动允许您配置在工作流中发送SMS。This can be a **single send** SMS and sent just once, or it can be a **recurring** SMS.

单一发送SMS消息是标准SMS，发送一次。

重复SMS消息允许您在定义的时间段内多次将相同的SMS发送到不同的目标。您可以将分发汇总为每个时段，以获得符合您的需求的报表。

## Context of use {#context-of-use}

**[!UICONTROL SMS delivery]** 该活动通常用于自动向在同一工作流中计算的目标发送SMS。

链接到调度程序时，您可以定义重复的SMS消息。

SMS收件人是通过在同一工作流程中通过查询活动(如查询、交叉点等)来定义的。

消息准备会根据工作流执行参数触发。在消息仪表板中，您可以选择是请求还是不需要手动确认发送消息(默认情况下需要)。您可以手动启动工作流或在工作流中放置调度程序活动以自动执行执行。

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL SMS delivery]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button in the workflow's action bar. This button is specific to the **[!UICONTROL SMS delivery]** activity. SMS属性可通过SMS仪表板中的操作栏进行访问。

1. 选择SMS发送模式：

   * **[!UICONTROL SMS]**：SMS将发送一次。您可以在此处指定是否要为活动添加出站过渡。此过程的步骤中详细介绍了不同的过渡类型。
   * **[!UICONTROL Recurring SMS]**：SMS会根据 **[!UICONTROL Scheduler]** 活动中定义的频率多次发送。选择发送的汇总时间。This allows you to regroup all the sends that occur during the defined period into one single view that is also called **Recurring execution** and can be accessed from the application's marketing activity list.

      例如，对于每天发送的连续生日SMS，您可以选择将发送汇总每个月。这允许您按月接收报告，但每天发送SMS。

1. 选择SMS类型。The SMS types come from SMS templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** menu.
1. 输入SMS的常规属性。您还可以将其附加到现有营销活动。使用SMS标签更新工作流的交付活动的标签。
1. 定义SMS内容。Refer to the section concerning [Creating an SMS message](../../channels/using/creating-an-sms-message.md).
1. By default, the **[!UICONTROL SMS delivery]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL SMS delivery]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**：这使您能够生成包含与入站过渡相同的相同人群的出站过渡。
   * **[!UICONTROL Add outbound transition with the population]**：这使您能够生成包含SMS被发送人群的出站过渡。在交付准备过程中排除的目标成员(隔离、无效编号等)已排除在此过渡中。

1. 确认活动的配置并保存工作流。

重新打开活动时，您被直接转至SMS仪表板。只能编辑其内容。

默认情况下，启动交付工作流只会触发消息准备。在启动工作流之后，仍需要确认从工作流创建的消息的发送。But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. 通过取消选中此选项，准备完成后无需进一步通知即可发送消息。

## Remarks {#remarks}

在工作流中创建的分发可以在应用程序的营销活动列表中访问。您可以使用仪表板查看工作流的执行状态。SMS摘要窗格中的链接允许您直接访问链接元素(工作流、营销活动、父交付情况以出现重复的SMS)。

但是，默认情况下会掩盖重复分发的执行。To view them, check the **[!UICONTROL Show recurring executions]** option in the marketing activities' search panel.

In the parent deliveries, which can be accessed from the marketing activity list or directly via the associated recurring executions, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL SMS delivery]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).

## Example {#example}

![](assets/wkf_sms_example_1.png)

此示例为生日工作流程。每天都将SMS发送到生日所在的个人资料。要执行此操作，请执行以下操作：

* The **[!UICONTROL Scheduler]** allows you to start the workflow every day at 8am.

   ![](assets/wkf_delivery_example_2.png)

* **[!UICONTROL Query]** 通过活动，您可以计算提供移动电话号码和生日的配置文件，每次执行工作流时都是如此。生日计算使用查询编辑工具中调色板中提供的预定义过滤器进行。

   ![](assets/wkf_delivery_example_3.png)

* **[!UICONTROL SMS]** 重复。发送按月汇总。因此，一个月内发送的所有SMS信息将汇总到单个视图中。In one year, 365 deliveries are therefore executed but they are regrouped into 12 views (also called **recurring executions**) in the Adobe Campaign interface. 历史记录和报告详细信息每月显示，而不是每次发送。

   ![](assets/wkf_sms_example_4.png)

