---
title: 调度程序
description: 调度程序活动允许您在工作流或活动启动时进行计划。
page-status-flag: never-activated
uuid: f5e50a11-8dc9-4d98-9531-024c0fb3f7da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 0fb16cea-3941-404f-899c-33f81ced4ed5
context-tags: schedule,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d994d85f126951215f1227301599c554c1f12c8
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 0%

---


# 调度程序{#scheduler}

## 说明 {#description}

![](assets/scheduler.png)

活动 **[!UICONTROL Scheduler]** 允许您在工作流或活动启动时进行计划。

## 使用环境 {#context-of-use}

该 **[!UICONTROL Scheduler]** 活动应被视为计划开始。 图表中的活动定位规则与活动相同。 **[!UICONTROL Start]** 此活动不得具有入站过渡。

在构建工作流时，每个分支只 **[!UICONTROL Scheduler]** 使用一个活动，并记住设置时区。 这允许您在特定时区开始工作流，否则该工作流将在工作流属性中定义的时区中运行(请参 [阅构建工作流](../../automating/using/building-a-workflow.md))。

>[!CAUTION]
>
>活动 **[!UICONTROL Repetition frequency]** 的时间不能少于10分钟。 这意味着工作流不能每10分钟自动执行一次以上。

**相关主题：**

* [用例： 在投放创建日期创建用户档案](../../automating/using/workflow-creation-date-query.md)
* [用例： 每周二创建电子邮件投放](../../automating/using/workflow-weekly-offer.md)

## Configuration {#configuration}

1. 将活动拖放 **[!UICONTROL Scheduler]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。
1. 指定 **[!UICONTROL Execution frequency]**:

   * **[!UICONTROL Once]**: 该工作流只执行一次。
   * **[!UICONTROL Several times a day]**: 该工作流每天定期执行多次。 您可以在特定时间或定期设置执行。
   * **[!UICONTROL Daily]**: 工作流在特定时间执行，每天执行一次。
   * **[!UICONTROL Weekly]**: 工作流在指定的时间执行，每周执行一次或多次。
   * **[!UICONTROL Monthly]**: 工作流在指定的时间执行，每月执行一次或多次。 您可以在需要执行工作流时选择月份。 您还可以在月份的指定工作日（如月份的第二个星期二）设置执行。
   * **[!UICONTROL Yearly]**: 工作流在指定的时间执行，每年执行一次或多次。

1. 根据所选频率定义执行详细信息。 详细信息字段可能会因所使用的频率（时间、重复频率、指定天数等）而不同。

   >[!NOTE]
   >
   >该字 **[!UICONTROL Repetition frequency]** 段允许您在触发工作流时留出时间。 例如，如果您选择每日执行期，而重复频率设置为 **2** （天），则每两天将触发工作流。 不能少于10分钟。 如果重复频率设置为 **0** （也是默认值），则不考虑此选项，工作流将根据指定的执行频率运行。

1. 指定执行将于何时过期：

   * **[!UICONTROL Never]**: 将根据指定的频率执行工作流，而不限制时间帧或迭代次数。
   * **[!UICONTROL After a certain number of iterations]**: 将根据指定的频率执行工作流，直到达到X的 **限制** 。 因 **[!UICONTROL Number of iterations]** 此需要指定。
   * **[!UICONTROL On a specific date]**: 将根据指定的频率执行该工作流，直到特定日期。 因此，需要指定执行截止日期。

1. 通过单击检查您的工作流接下来十个执行的计划 **[!UICONTROL Preview next executions]**。

1. 在选 **[!UICONTROL Execution options]** 项卡中，在字段中为调度程序设置时 **[!UICONTROL Time zone]** 区。

   有关根据投放的时区发送收件人的详细信息，请参 [阅本](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) 节 [或重复工](../../automating/using/recurring-push-notifications.md) 作流的此示例。

1. 确认活动的配置并保存工作流。

## Example {#example}

在以下示例中，活动已配置，因此它将每周（每隔周一）早上7点开始工作流，时间不确定。

![](assets/wkf_scheduler_example.png)

