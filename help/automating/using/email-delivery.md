---
title: 电子邮件投放
description: 电子邮件投放活动允许您配置在工作流中发送单个发送电子邮件或循环电子邮件。
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
source-git-commit: 15e5aebdd67e8f5ddee89506c0469a101d94d2e8
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 0%

---


# 电子邮件投放{#email-delivery}

## 说明 {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

活动 **[!UICONTROL Email delivery]** 允许您配置在工作流中发送电子邮件。 这可以是单 **个发送电** 子邮件，只发送一次，也可以是循环 **电子邮件** 。

单一发送电子邮件是标准电子邮件，只发送一次。

重复的电子邮件允许您在定义的时间段内多次向不同目标发送同一电子邮件。 您可以聚合每个时段的投放，以获得与您的需求对应的报告。

## 使用环境 {#context-of-use}

该活动 **[!UICONTROL Email delivery]** 通常用于自动向在同一工作流中计算的目标发送电子邮件。

链接到调度程序时，您可以定义重复的电子邮件。

电子邮件收件人是在同一工作流中通过定位活动(如查询、交叉点等)在活动的上游定义的。

根据工作流执行参数触发消息准备。 在消息仪表板中，您可以选择是否请求手动确认以发送消息（默认情况下为必需）。 您可以手动开始工作流，或在工作流中放置调度程序活动以自动执行。

**相关主题：**

* [用例： 创建每周一次的电子邮件投放](../../automating/using/workflow-weekly-offer.md)
* [用例： 在位置创建投放分段](../../automating/using/workflow-segmentation-location.md)
* [用例： 使用补充创建投放](../../automating/using/workflow-created-query-with-complement.md)
* [用例： 重定向工作流向非打开者发送新投放](../../automating/using/workflow-cross-channel-retargeting.md)
* [用例： 生日投放](../../automating/using/birthday-delivery.md)

## Configuration {#configuration}

1. 将活动拖放 **[!UICONTROL Email delivery]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。

   >[!NOTE]
   >
   >您可以通过活动快速操作中的按钮访问投放(而非活动本身)的常规属 ![](assets/dlv_activity_params-24px.png) 性和高级选项。 此按钮特定于 **[!UICONTROL Email delivery]** 活动。 可以通过电子邮件仪表板中的操作栏访问电子邮件的属性。

1. 选择电子邮件发送模式：

   * **[!UICONTROL Email]**: 电子邮件只发送一次。 您可以在此处指定是否要向活动添加出站过渡。 不同的过渡类型在此过程的步骤7中详细介绍。
   * **[!UICONTROL Recurring email]**: 根据活动中定义的频率，电子邮件会发送多次 **[!UICONTROL Scheduler]** 。 选择发送的聚合期间。 这样，您就可以重新分组在一个电子邮件（也称为“重复执行”）中定义的时间段内发 **送的所有** ，并可以从应用程序的营销活动列表访问这些发送。

      例如，对于每天发送的循环生日电子邮件，您可以选择聚合每月发送的生日电子邮件。 这样，尽管每天都会发送电子邮件，您仍可以按月收到有关投放的报告。
   >[!NOTE]
   >
   >循环投放根据聚合期 **间编制**。 例如，如果聚合期为“按天”，则每天只重新准备一次投放。 如果您计划每天多次调用此工作流，请使用 [!UICONTROL No aggregation]。

1. 选择电子邮件类型。 电子邮件类型来自在> >菜单中定义 **[!UICONTROL Resources]** 的 **[!UICONTROL Templates]** 电子邮件 **[!UICONTROL Delivery templates]** 模板。
1. 输入电子邮件的常规属性。 您还可以将其附加到现有活动。 工作流的投放活动的标签将更新为电子邮件标签。
1. 定义电子邮件内容。 请参阅有关内容编 [辑的部分](../../designing/using/designing-content-in-adobe-campaign.md)。
1. 默认情况下， **[!UICONTROL Email delivery]** 活动不包含任何出站过渡。 如果要向过渡添加出站活动，请转 **[!UICONTROL Email delivery]** 到高级活动 **[!UICONTROL General]** 选项的选项卡( ![](assets/dlv_activity_params-24px.png) 活动快速操作中的按钮)，然后选中以下选项之一：

   * **[!UICONTROL Add outbound transition without the population]**: 这样，您就可以生成一个出站过渡，其包含与入站过渡完全相同的人口。
   * **[!UICONTROL Add outbound transition with the population]**: 这样，您就可以生成一个出站过渡，其中包含接收电子邮件的人群。 在目标准备过程中被排除的投放成员(隔离、无效电子邮件等) 排除在此过渡。

1. 确认活动的配置并保存工作流。

重新打开活动时，您将直接转到电子邮件仪表板。 只能编辑其内容。

默认情况下，启动投放工作流只会触发消息准备。 在工作流启动后，仍需要确认从工作流创建的消息的发送。 但是，从消息仪表板中，并且仅当消息是通过工作流创建的，您才能禁用该 **[!UICONTROL Request confirmation before sending messages]** 选项。 取消选中此选项后，消息在准备完成后即发送，无需进一步通知。

## 备注 {#remarks}

在工作流中创建的投放可以在应用程序的营销活动列表中访问。 您可以使用视图仪表板来工作流的执行状态。 电子邮件摘要窗格中的链接允许您直接访问链接的元素(如果出现重复的电子邮件，则为工作流、活动、父投放)。

![](assets/wkf_display_recurrent_executions_2.png)

但是，默认情况下，重复投放的执行会被遮罩。 要对其进行视图，请选 **[!UICONTROL Show recurring executions]** 中营销活动搜索面板中的选项。

![](assets/wkf_display_recurrent_executions.png)

在父投放中(可从营销活动列表访问，或直接通过关联的重复执行访问)，您可以视图已处理的发送总数(根据配置活动时指定的汇总期 **[!UICONTROL Email delivery]** 间)。 为此，请通过选择打开父投放块的详细 **[!UICONTROL Deployment]** 视图 ![](assets/wkf_dlv_detail_button.png)。

![](assets/wkf_display_recurrent_executions_3.png)
