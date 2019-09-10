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
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# 电子邮件发送{#email-delivery}

## 描述 {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

**[!UICONTROL Email delivery]** 活动允许您配置在工作流中发送电子邮件。这可以是 **一次发送** 电子邮件，只发送一次，也可以重复 **** 发送电子邮件。

单发送电子邮件是标准电子邮件，发送一次。

重复电子邮件允许您在定义的时间段内将相同的电子邮件多次发送到不同的目标。您可以将分发汇总为每个时段，以获得符合您的需求的报表。

## 使用情境 {#context-of-use}

**[!UICONTROL Email delivery]** 该活动通常用于自动向在同一工作流程中计算的目标发送电子邮件。

链接到计划程序时，您可以定义重复的电子邮件。

通过定向活动(如查询、交叉点等)，电子邮件收件人在同一工作流程中的活动上游进行定义。

消息准备会根据工作流执行参数触发。在消息仪表板中，您可以选择是请求还是不需要手动确认发送消息(默认情况下需要)。您可以手动启动工作流或在工作流中放置调度程序活动以自动执行执行。

## 配置 {#configuration}

1. 将 **[!UICONTROL Email delivery]** 活动拖放到工作流中。
1. 选择活动，然后使用出现的快速操作中 ![](assets/edit_darkgrey-24px.png) 的按钮打开该活动。

   >[!NOTE]
   >
   >您可以通过活动快速操作 ![](assets/dlv_activity_params-24px.png) 中的按钮访问活动的一般属性和高级选项(而不是交付本身)。此按钮特定于 **[!UICONTROL Email delivery]** 活动。电子邮件的属性可通过电子邮件仪表板中的操作栏进行访问。

1. 选择电子邮件发送模式：

   * **[!UICONTROL Email]**：电子邮件将发送一次。您可以在此处指定是否要为活动添加出站过渡。此过程的步骤中详细介绍了不同的过渡类型。
   * **[!UICONTROL Recurring email]**：电子邮件会根据 **[!UICONTROL Scheduler]** 活动中定义的频率多次发送。选择发送的汇总时间。这允许您将在定义的时间段内发生的所有发送重新合并到一封也称为 **重复执行** 的电子邮件中，并可从应用程序的营销活动列表中访问。

      例如，对于每天发送的重复生日电子邮件，您可以选择将发送汇总每个月。这允许您按月接收提交报告，但每天发送电子邮件。

1. 选择电子邮件类型。电子邮件类型来自 **[!UICONTROL Resources]** 于&gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** 菜单中定义的电子邮件模板。
1. 输入电子邮件的常规属性。您还可以将其附加到现有营销活动。工作流的交付活动的标签会使用电子邮件标签进行更新。
1. 定义电子邮件内容。请参阅有关 [内容编辑](../../designing/using/about-email-content-design.md)的部分。
1. 默认情况下 **[!UICONTROL Email delivery]** ，活动不包括任何出站过渡。如果要向 **[!UICONTROL Email delivery]** 活动中添加出站过渡，请转到高级活动选项 **[!UICONTROL General]** (活动快速操作中 ![](assets/dlv_activity_params-24px.png) 的按钮)选项卡，然后检查以下任一选项：

   * **[!UICONTROL Add outbound transition without the population]**：这使您能够生成包含与入站过渡相同的相同人群的出站过渡。
   * **[!UICONTROL Add outbound transition with the population]**：这使您能够生成包含电子邮件发送人群的出站过渡。在交付准备过程中排除的目标成员(隔离、无效电子邮件等)已排除在此过渡中。

1. 确认活动的配置并保存工作流。

重新打开活动时，您会被直接转至电子邮件仪表板。只能编辑其内容。

默认情况下，启动交付工作流只会触发消息准备。在启动工作流之后，仍需要确认从工作流创建的消息的发送。但是，通过消息仪表板，并且只有在使用工作流创建消息时，您可以禁用 **[!UICONTROL Request confirmation before sending messages]** 该选项。通过取消选中此选项，准备完成后无需进一步通知即可发送消息。

## 注释 {#remarks}

在工作流中创建的分发可以在应用程序的营销活动列表中访问。您可以使用仪表板查看工作流的执行状态。通过电子邮件摘要窗格中的链接，您可以直接访问链接的元素(工作流、营销活动、父交付以出现重复的电子邮件)。

![](assets/wkf_display_recurrent_executions_2.png)

但是，默认情况下会掩盖重复分发的执行。要查看这些内容，请在营销活动的搜索面板中检查 **[!UICONTROL Show recurring executions]** 该选项。

![](assets/wkf_display_recurrent_executions.png)

在父分发中，可从营销活动列表中访问，或直接通过关联的重复执行进行访问，您可以查看已处理的发送总数(根据配置 **[!UICONTROL Email delivery]** 活动时指定的汇总时间)。为此，请通过选择来打开父交付 **[!UICONTROL Deployment]** 块的详细信息视图 ![](assets/wkf_dlv_detail_button.png)。

![](assets/wkf_display_recurrent_executions_3.png)

## 示例 {#example}

![](assets/wkf_delivery_example_1.png)

此示例为生日工作流程。每天都将收到一封电子邮件，其中包含当天生日的配置文件。要执行此操作，请执行以下操作：

* 允许 **[!UICONTROL Scheduler]** 您在上午点开始工作流。

   ![](assets/wkf_delivery_example_2.png)

* **[!UICONTROL Query]** 通过活动，您可以计算提供电子邮件的配置文件，以及每次执行工作流时的生日。生日计算使用查询编辑工具中调色板中提供的预定义过滤器进行。

   ![](assets/wkf_delivery_example_3.png)

* **[!UICONTROL Email]** 重复。发送按月汇总。因此，一个月内发送的所有电子邮件都会汇总到单个视图中。在一年内，执行了365种分发，但在Adobe Campaign界面中将其重新嵌入12个视图(也称为 **重复执行)**。历史记录和报告详细信息每月显示，而不是每次发送。

   ![](assets/wkf_delivery_example_4.png)

**相关主题**

* [使用案例：创建一次每周一次的电子邮件分发](../../automating/using/workflow-weekly-offer.md)
* [使用案例：在位置上创建分发分段](../../automating/using/workflow-segmentation-location.md)
* [使用案例：通过补充创建交付](../../automating/using/workflow-created-query-with-complement.md)
* [使用案例：重定向向非Opener发送新交付的工作流](../../automating/using/workflow-cross-channel-retargeting.md)