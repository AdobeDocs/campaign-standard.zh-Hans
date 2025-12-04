---
title: 调度程序
description: 调度程序活动允许您安排何时启动工作流或活动。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: schedule,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 39f7b216-b3cd-4aa6-b5df-23e6805076df
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 52%

---

# 调度程序{#scheduler}

## 说明 {#description}

![](assets/scheduler.png)

**[!UICONTROL Scheduler]** 活动允许您安排何时启动工作流或活动。

## 使用环境 {#context-of-use}

**[!UICONTROL Scheduler]** 活动应视为排程开始的时间。图表中的活动定向规则与 **[!UICONTROL Start]** 活动相同。此活动不得包含集客过渡。

在构建工作流时，每个分支只能使用一个 **[!UICONTROL Scheduler]** 活动，同时别忘了设置时区。这样可让您以特定时区启动工作流，否则该工作流将以工作流属性中定义的时区运行（请参阅[构建工作流](../../automating/using/building-a-workflow.md)）。

>[!CAUTION]
>
>活动的 **[!UICONTROL Repetition frequency]** 不能少于 10 分钟。这意味着工作流不能每 10 分钟自动执行多次。

在设计包含多个活动的已计划工作流时，您需要确保在该工作流完成之前不会重新计划该工作流。 要实现此目的，您需要配置工作流，以防止在先前执行的一个或多个任务仍然等待执行时执行该工作流。 有关详细信息，请参见[此页面](../../automating/using/scheduled-workflows-execution.md)。

**相关主题：**

* [用例：在用户档案的创建日期创建投放](../../automating/using/workflow-creation-date-query.md)
* [用例：创建每个星期二发送的电子邮件投放](../../automating/using/workflow-weekly-offer.md)

## 配置 {#configuration}

1. 将 **[!UICONTROL Scheduler]** 活动拖放到工作流中。
1. 选择活动，然后使用所显示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。
1. 指定 **[!UICONTROL Execution frequency]**：

   * **[!UICONTROL Once]**：该工作流只执行一次。
   * **[!UICONTROL Several times a day]**：工作流每天定期执行多次。
   * **[!UICONTROL Daily]**：工作流在特定时间执行，每天执行一次。
   * **[!UICONTROL Weekly]**：工作流在指定的时间执行，每周执行一次或多次。
   * **[!UICONTROL Monthly]**：工作流在指定的时间执行，每月执行一次或多次。您可以选择需要执行工作流的月份。您还可以设置在月份的指定工作日（如每月的第二个星期二）执行。
   * **[!UICONTROL Yearly]**：工作流在指定的时间执行，每年执行一次或多次。

1. 根据需要配置执行设置。 可用选项可能因所选执行频率（执行时间或天数、重复频率等）而异。

   >[!NOTE]
   >
   >对每日和每月执行频率可用的&#x200B;**[!UICONTROL Repetition frequency]**&#x200B;字段允许您在触发工作流时指定间隔时间。 例如，如果您选择每天执行一次，而重复频率设置为 **2**（天），则会每两天触发一次工作流。间隔时间不能少于 10 分钟。如果重复频率设置为&#x200B;**0**（这也是默认值），则不会考虑此选项，工作流将根据指定的执行频率运行。

   将执行频率设置为&#x200B;**[!UICONTROL Several times a day]**&#x200B;时，您可以灵活选择在一天中的特定时间执行工作流还是在一天中定期执行工作流。

   +++ 了解如何配置&#x200B;**[!UICONTROL "Several times a day"]**&#x200B;执行频率

   * 要在一天中的特定时间多次执行工作流，请打开&#x200B;**[!UICONTROL Specific times]**&#x200B;选项，然后单击&#x200B;**[!UICONTROL Add an element]**&#x200B;以指定所需的执行时间。 根据需要添加任意次数以满足您的要求。

   * 要在一天中定期执行工作流，请打开&#x200B;**[!UICONTROL Periodic]**&#x200B;选项，然后配置执行周期：

      1. 在&#x200B;**[!UICONTROL Repeat processing according to the following frequency (e.g. 2h)]**&#x200B;字段中，指定工作流应执行的间隔（例如，每30分钟、每2小时）。

         >[!NOTE]
         >
         >此选项还允许每日、每月或每年重复频率。 请注意，在这种情况下，工作流不会每天执行多次，而是根据您在此字段中指定的频率执行。
         >
         > 如果您的工作流不需要在一天内多次执行，而是需要每天、每月或每年运行，则最好使用&#x200B;**[!UICONTROL Daily]**&#x200B;下拉列表中提供的&#x200B;**[!UICONTROL Monthly]**、**[!UICONTROL Yearly]**&#x200B;或&#x200B;**[!UICONTROL Execution frequency]**&#x200B;选项。

      1. 在&#x200B;**[!UICONTROL Start]**/**[!UICONTROL End]**&#x200B;时间字段中，定义工作流执行的开始和结束时间。

         如果未指定结束时间，则执行将在午夜00:00:00时终止，并在第二天指定的开始时间开始下一次执行。

      1. 在&#x200B;**[!UICONTROL Start]**&#x200B;日期字段中，选择第一次执行的开始日期。

   在下面的示例中，活动配置为从3月1日开始每隔2小时执行一次工作流，时间介于上午8点至下午5点。

   ![](assets/wkf_scheduler_day.png)

   +++

1. 指定执行的截止时间：

   * **[!UICONTROL Never]**：根据指定的频率执行工作流，对时间范围或迭代次数没有任何限制。
   * **[!UICONTROL After a certain number of iterations]**：根据指定的频率执行工作流，直到达到 **X** 的限制。因此需要指定 **[!UICONTROL Number of iterations]**。
   * **[!UICONTROL On a specific date]**：根据指定的频率执行工作流，直到达到特定日期为止。因此，需要指定执行截止日期。

1. 通过单击 **[!UICONTROL Preview next executions]** 检查您的工作流中安排的后续十次执行。

1. 在 **[!UICONTROL Execution options]** 选项卡中，在 **[!UICONTROL Time zone]** 字段中为调度程序设置时区。

   有关基于收件人时区进行投放的更多信息，请参阅[此章节](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)或定期工作流的[此示例](../../automating/using/recurring-push-notifications.md)。

1. 确认活动的配置并保存工作流。

## 示例 {#example}

下方的示例中已配置了活动，因此它将在每周的周一早上 7 点启动工作流，但持续时间不确定。

![](assets/wkf_scheduler_example.png)

