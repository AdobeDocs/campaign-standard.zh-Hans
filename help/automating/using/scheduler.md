---
title: 调度程序
description: “调度程序”活动允许您计划工作流或活动的启动时间。
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
source-git-commit: 41ba6fa44807541dd749f4effca44ae2b4d147ae

---


# 调度程序{#scheduler}

## 说明 {#description}

![](assets/scheduler.png)

活动 **[!UICONTROL Scheduler]**允许您计划何时启动工作流或活动。

## 使用环境 {#context-of-use}

活 **[!UICONTROL Scheduler]**动应视为预定开始。 图表中的活动定位规则与活动的定位规**[!UICONTROL Start]** 则相同。 此活动不得具有入站过渡。

在构建工作流时，每个分支只 **[!UICONTROL Scheduler]**使用一个活动，并记住设置时区。 这允许您在特定时区启动工作流，否则该工作流将在工作流属性中定义的时区中运行(请参阅构[建工作流](../../automating/using/building-a-workflow.md))。

>[!CAUTION]
>
>活 **[!UICONTROL Repetition frequency]**动的时间不能少于10分钟。 这意味着工作流不能每10分钟自动执行多次。

## 配置 {#configuration}

1. 将活动拖放 **[!UICONTROL Scheduler]**到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。
1. 指定 **[!UICONTROL Execution frequency]**:

   * **[!UICONTROL Once]**:该工作流只执行一次。
   * **[!UICONTROL Several times a day]**:该工作流每天定期执行多次。 您可以在特定时间或定期设置执行。
   * **[!UICONTROL Daily]**:该工作流在每天一次的特定时间执行。
   * **[!UICONTROL Weekly]**:该工作流在指定的时刻执行，每周执行一次或多次。
   * **[!UICONTROL Monthly]**:该工作流在指定的时刻执行，每月执行一次或多次。 您可以在需要执行工作流时选择月份。 您还可以在月份的指定工作日（如月份的第二个星期二）设置执行。
   * **[!UICONTROL Yearly]**:该工作流在指定的时间执行，每年执行一次或多次。

1. 根据所选频率定义执行详细信息。 细节字段可能会因所使用的频率（时间、重复频率、指定天数等）而不同。

   >[!NOTE]
   >
   >该 **[!UICONTROL Repetition frequency]**字段允许您在触发工作流时留出时间。 例如，如果您选择每日执行期，而重复频率设置为** 2 **（天），则每两天将触发一次工作流。 时间不能少于10分钟。 如果重复频率设置为** 0 **（也是默认值），则不考虑此选项，并且工作流将根据指定的执行频率运行。

1. 指定执行何时过期：

   * **[!UICONTROL Never]**:将根据指定的频率执行该工作流，而不限制时间帧或迭代次数。
   * **[!UICONTROL After a certain number of iterations]**:将根据指定的频率执行工作流，直到达到** X的限制&#x200B;**。 因**[!UICONTROL Number of iterations]** 此需要指定。
   * **[!UICONTROL On a specific date]**:将根据指定的频率执行该工作流，直到特定日期。 因此，需要指定执行截止日期。

1. 单击以检查您的工作流的下一个十个执行的计划 **[!UICONTROL Preview next executions]**。

1. 在选 **[!UICONTROL Execution options]**项卡中，在字段中为调度程序设置时**[!UICONTROL Time zone]** 区。

   有关根据收件人的时区发送交付的详细信息，请参阅此 [部分](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) ，或循环 [工作流的此示例](../../automating/using/push-notification-delivery.md#sending-a-recurring-push-notification-with-a-workflow) 。

1. 确认活动的配置并保存工作流。

## Example {#example}

在以下示例中，活动已配置好，以便每隔周一的清晨7点，在不确定的持续时间内以每周为单位启动工作流。

![](assets/wkf_scheduler_example.png)

