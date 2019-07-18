---
title: 调度程序
seo-title: 调度程序
description: 调度程序
seo-description: 调度程序活动允许您预定工作流或活动的启动时间。
page-status-flag: 从未激活
uuid: f5e50a11-8dc9-4d98-951-024c0fb3f7da
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 执行活动
discoiquuid: fb16cCea-3941-404f-899c-33f81ed4ed5
context-tags: 计划，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: e3a627376a91eb394aea90b1d94c7958ad77fd40

---


# Scheduler{#scheduler}

## Description {#description}

![](assets/scheduler.png)

**[!UICONTROL Scheduler]** 活动允许您预定工作流或活动的启动时间。

## Context of use {#context-of-use}

**[!UICONTROL Scheduler]** 活动应被视为计划开始。The activity positioning rules within the chart are the same as for the **[!UICONTROL Start]** activity. 此活动不得具有入站过渡。

When building your workflow, only use one **[!UICONTROL Scheduler]** activity per branch and remember to set a time zone. 它将以其他方式设置以在服务器时区运行。

>[!CAUTION]
>
>The **[!UICONTROL Repetition frequency]** of the activity cannot be less than 10 minutes. 这意味着，每10分钟不能自动执行一次工作流。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Scheduler]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Specify the **[!UICONTROL Execution frequency]**:

   * **[!UICONTROL Once]**：将执行一次工作流。
   * **[!UICONTROL Several times a day]**：工作流每天定期执行多次。您可以在特定时间或定期设置执行。
   * **[!UICONTROL Daily]**：工作流在一个特定时间执行，每天一次。
   * **[!UICONTROL Weekly]**：工作流在一周或几天的指定时刻执行。
   * **[!UICONTROL Monthly]**：工作流在指定时刻执行一次或几次。您可以在需要执行工作流时选择月份。您还可以在指定的工作日(如月的第二个星期二)上设置执行。
   * **[!UICONTROL Yearly]**：工作流在指定时刻执行一次或几次。

1. 根据所选频率定义执行详细信息。详细信息字段可能因使用的频率(时间、重复频率、指定的天数等)而异。

   >[!NOTE]
   >
   >**[!UICONTROL Repetition frequency]** 该字段允许您留出工作流的时间。For example, if you select a daily execution period and the repetition frequency is set at **2** (days), the workflow will be triggered every two days. 不能少于10分钟。If the repetition frequency is set at **0** (also the default value), this option is not taken into account and the workflow will run according to the execution frequency specified.

1. 指定执行何时过期：

   * **[!UICONTROL Never]**：将根据指定的频率执行工作流，而不会限制时间帧或迭代数。
   * **[!UICONTROL After a certain number of iterations]**：将根据指定的频率执行工作流，直至达到 **X** 限制。**[!UICONTROL Number of iterations]** 因此需要指定。
   * **[!UICONTROL On a specific date]**：将根据指定的频率执行工作流，直至特定日期。因此，需要指定执行截止日期。

1. Check the schedule of the next ten executions of your workflow by clicking **[!UICONTROL Preview next executions]**.

1. In the **[!UICONTROL Execution options]** tab, set up the time zone for your scheduler in the **[!UICONTROL Time zone]** field. 这允许您在特定时区开始工作流，否则默认情况下，工作流将在服务器时区中运行。

   For more information on sending delivery depending on the recipient's time zone, refer to this [section](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) or this [example](../../automating/using/push-notification-delivery.md#sending-a-recurring-push-notification-with-a-workflow) of a recurring workflow.

1. 确认活动的配置并保存工作流。

## Example {#example}

在以下示例中，将配置活动，以便将工作流每周、每隔一周(星期一)启动，以确保持续时间不变。

![](assets/wkf_scheduler_example.png)

