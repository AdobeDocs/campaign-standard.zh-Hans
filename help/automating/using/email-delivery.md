---
title: 电子邮件投放
description: 电子邮件发送活动允许您配置在工作流中发送单个发送电子邮件或循环电子邮件。
page-status-flag: never-activated
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-8010260554bb
context-tags: delivery,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b70e18be29fd48d102313f6d741e9ffe053cc34

---


# 电子邮件投放{#email-delivery}

## 说明 {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

该活 **[!UICONTROL Email delivery]** 动允许您配置在工作流中发送电子邮件。 这可以是单 **个发送电子邮件** ，只发送一次，也可以是循环 **电子邮件** 。

单发电子邮件是标准电子邮件，只发送一次。

重复的电子邮件允许您在定义的时间段内多次向不同目标发送同一电子邮件。 您可以汇总每个时段的交货数，以获得与您的需求对应的报表。

## 使用环境 {#context-of-use}

活动 **[!UICONTROL Email delivery]** 通常用于自动向同一工作流中计算的目标发送电子邮件。

链接到计划程序时，您可以定义循环电子邮件。

电子邮件收件人是在同一工作流中通过查询、交叉点等定位活动在活动上游定义的。

根据工作流执行参数触发消息准备。 在消息功能板中，您可以选择是否请求手动确认以发送消息（默认情况下为必需）。 您可以手动启动工作流，或将调度程序活动放入工作流中以自动执行。

## 配置 {#configuration}

1. 将活动拖放 **[!UICONTROL Email delivery]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。

   >[!NOTE]
   >
   >您可以通过活动快速操作中的按钮访问活动（而非交付本身）的 ![](assets/dlv_activity_params-24px.png) 常规属性和高级选项。 此按钮特定于活 **[!UICONTROL Email delivery]** 动。 电子邮件的属性可以通过电子邮件功能板中的操作栏进行访问。

1. 选择电子邮件发送模式：

   * **[!UICONTROL Email]**:电子邮件只发送一次。 您可以在此处指定是否要向活动添加出站过渡。 此过程的步骤7中详细介绍了不同的过渡类型。
   * **[!UICONTROL Recurring email]**:根据活动中定义的频率，电子邮件会多次发 **[!UICONTROL Scheduler]** 送。 选择发送的聚合期。 这样，您就可以重新分组在一个电子邮件(也称为“重复执行” **** )中定义的时间段内发生的所有发送，并且可以从应用程序的营销活动列表中访问这些发送。

      例如，对于每天发送的循环生日电子邮件，您可以选择每月汇总发送。 这样，尽管电子邮件每天都会发送，但您仍可以每月收到有关您发送的报告。

1. 选择电子邮件类型。 电子邮件类型来自在&gt; **[!UICONTROL Resources]** &gt;菜单中定义的 **[!UICONTROL Templates]** 电子邮件 **[!UICONTROL Delivery templates]** 模板。
1. 输入电子邮件的常规属性。 您还可以将其附加到现有营销活动。 工作流的交付活动的标签将更新为电子邮件标签。
1. 定义电子邮件内容。 请参阅有关内容编辑 [的部分](../../designing/using/designing-content-in-adobe-campaign.md)。
1. 默认情况下，活 **[!UICONTROL Email delivery]** 动不包括任何出站过渡。 如果要向活动添加出站过渡，请转到高级活动选项的选 **[!UICONTROL Email delivery]** 项卡( **[!UICONTROL General]**![](assets/dlv_activity_params-24px.png) 活动快速操作中的按钮)，然后选中以下选项之一：

   * **[!UICONTROL Add outbound transition without the population]**:这样，您就可以生成一个出站过渡，其中包含与入站过渡完全相同的人数。
   * **[!UICONTROL Add outbound transition with the population]**:这样，您就可以生成一个出站过渡，其中包含向其发送电子邮件的人群。 在交付准备过程中被排除的目标成员（隔离、无效电子邮件等）将被排除在此过渡之外。

1. 确认活动的配置并保存工作流。

重新打开活动后，您会直接转到电子邮件功能板。 只能编辑其内容。

默认情况下，启动传送工作流只会触发消息准备。 在工作流启动后，仍需要确认从工作流创建的消息的发送。 但是，在消息功能板中，并且仅当消息是从工作流创建的时候，您才能禁用该选 **[!UICONTROL Request confirmation before sending messages]** 项。 取消选中此选项后，准备完成后，消息将发送，无需进一步通知。

## 评论 {#remarks}

在工作流中创建的交货可以在应用程序的营销活动列表中访问。 您可以使用功能板查看工作流的执行状态。 电子邮件摘要窗格中的链接允许您直接访问链接的元素（在出现重复电子邮件时，工作流、营销活动、父交付）。

![](assets/wkf_display_recurrent_executions_2.png)

但是，循环提交的执行在默认情况下是遮罩的。 要查看它们，请选中 **[!UICONTROL Show recurring executions]** 营销活动搜索面板中的选项。

![](assets/wkf_display_recurrent_executions.png)

在可从营销活动列表访问或直接通过关联的重复执行访问的父分发中，您可以查看已处理的发送的总数（根据配置活动时指定的汇总期间）。 **[!UICONTROL Email delivery]** 为此，请选择以打开父分发块的详细信 **[!UICONTROL Deployment]** 息视图 ![](assets/wkf_dlv_detail_button.png)。

![](assets/wkf_display_recurrent_executions_3.png)

## Example {#example}

![](assets/wkf_delivery_example_1.png)

此示例是生日工作流。 每天都会向当天生日的个人资料发送电子邮件。 操作步骤：

* 您 **[!UICONTROL Scheduler]** 可以在每天上午8点开始工作流。

   ![](assets/wkf_delivery_example_2.png)

* 该活 **[!UICONTROL Query]** 动允许您计算每次执行工作流时，提供电子邮件且其生日在当天的配置文件。 生日计算是使用查询编辑工具调色板中可用的预定义过滤器执行的。

   ![](assets/wkf_delivery_example_3.png)

* 重复 **[!UICONTROL Email]** 出现。 发送按月汇总。 因此，一个月内发送的所有电子邮件都会汇总到一个视图中。 因此，在一年内，将执行365个提交，但会在Adobe Campaign界面中将其重新分组为12个视 **图(也称为重复执行**)。 历史记录和报告详细信息每月都会显示，而不是每次发送。

   ![](assets/wkf_delivery_example_4.png)

**相关主题**

* [用例：创建每周一次的电子邮件发送](../../automating/using/workflow-weekly-offer.md)
* [用例：创建按位置分段的交付](../../automating/using/workflow-segmentation-location.md)
* [用例：使用补充创建交付](../../automating/using/workflow-created-query-with-complement.md)
* [用例：重定向工作流向非打开者发送新分发](../../automating/using/workflow-cross-channel-retargeting.md)