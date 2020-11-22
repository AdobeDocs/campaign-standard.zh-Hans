---
solution: Campaign Standard
product: campaign
title: 调度程序
description: 调度程序活动允许您安排何时启动工作流或活动。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: schedule,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 97%

---


# 调度程序{#scheduler}

## 说明{#description}

![](assets/scheduler.png)

**[!UICONTROL Scheduler]** 活动允许您安排何时启动工作流或活动。

## 使用环境{#context-of-use}

**[!UICONTROL Scheduler]** 活动应视为排程开始的时间。图表中的活动定向规则与 **[!UICONTROL Start]** 活动相同。此活动不得包含集客过渡。

在构建工作流时，每个分支只能使用一个 **[!UICONTROL Scheduler]** 活动，同时别忘了设置时区。这样可让您以特定时区启动工作流，否则该工作流将以工作流属性中定义的时区运行（请参阅[构建工作流](../../automating/using/building-a-workflow.md)）。

>[!CAUTION]
>
>活动的 **[!UICONTROL Repetition frequency]** 不能少于 10 分钟。这意味着工作流不能每 10 分钟自动执行多次。

**相关主题：**

* [用例：在投放创建日期创建用户档案](../../automating/using/workflow-creation-date-query.md)
* [用例：每周二创建电子邮件投放](../../automating/using/workflow-weekly-offer.md)

## 配置{#configuration}

1. 将 **[!UICONTROL Scheduler]** 活动拖放到工作流中。
1. 选择活动，然后使用所显示快捷操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。
1. 指定 **[!UICONTROL Execution frequency]**：

   * **[!UICONTROL Once]**：该工作流只执行一次。
   * **[!UICONTROL Several times a day]**：该工作流每天定期执行多次。您可以设置在特定时间执行或定期执行。
   * **[!UICONTROL Daily]**：工作流在特定时间执行，每天执行一次。
   * **[!UICONTROL Weekly]**：工作流在指定的时间执行，每周执行一次或多次。
   * **[!UICONTROL Monthly]**：工作流在指定的时间执行，每月执行一次或多次。您可以选择需要执行工作流的月份。您还可以设置在月份的指定工作日（如每月的第二个星期二）执行。
   * **[!UICONTROL Yearly]**：工作流在指定的时间执行，每年执行一次或多次。

1. 根据所选频率定义执行详情。详情字段可能会因所使用的频率（时间、重复频率、指定天数等）而不同。

   >[!NOTE]
   >
   >利用 **[!UICONTROL Repetition frequency]** 字段，可指定触发工作流的间隔时间。例如，如果您选择每天执行一次，而重复频率设置为 **2**（天），则会每两天触发一次工作流。间隔时间不能少于 10 分钟。如果重复频率设置为 **0**（这也是默认值），则不会考虑间隔时间选项，工作流将根据指定的执行频率运行。

1. 指定执行的截止时间：

   * **[!UICONTROL Never]**：根据指定的频率执行工作流，对时间范围或迭代次数没有任何限制。
   * **[!UICONTROL After a certain number of iterations]**：根据指定的频率执行工作流，直到达到 **X** 的限制。因此需要指定 **[!UICONTROL Number of iterations]**。
   * **[!UICONTROL On a specific date]**：根据指定的频率执行工作流，直到达到特定日期为止。因此，需要指定执行截止日期。

1. 通过单击 **[!UICONTROL Preview next executions]** 检查您的工作流中安排的后续十次执行。

1. 在 **[!UICONTROL Execution options]** 选项卡中，在 **[!UICONTROL Time zone]** 字段中为调度程序设置时区。

   有关基于收件人时区进行投放的更多信息，请参阅[此章节](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)或定期工作流的[此示例](../../automating/using/recurring-push-notifications.md)。

1. 确认活动的配置并保存工作流。

## 示例{#example}

下方的示例中已配置了活动，因此它将在每周的周一早上 7 点启动工作流，但持续时间不确定。

![](assets/wkf_scheduler_example.png)

