---
solution: Campaign Standard
product: campaign
title: 预定工作流的重叠执行
description: 了解如何防止重叠执行计划工作流。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: 工作流
role: 数据架构师
level: 中间
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 2%

---


# 预定工作流的重叠执行{#preventing-overlapping-execution-of-scheduled-workflows}

## 关于计划的工作流执行

在Campaign Standard中，工作流引擎保证工作流实例只由一个进程执行。 阻止活动(如导入、长时间运行的查询或写入数据库)可防止在运行时执行任何其他任务。

另一方面，非阻塞活动不会阻止其他任务(通常是等待事件的活动，如&#x200B;**[!UICONTROL Scheduler]**&#x200B;活动)的执行。

这可能导致基于计划的工作流可以开始执行，即使该工作流的上一运行尚未完成，也可能导致意外数据问题。

因此，在设计包含多个活动的计划工作流时，您需要确保在工作流完成之前不会重新计划该工作流。 为此，您需要配置工作流，以防止在先前执行的一个或多个任务仍处于挂起状态时执行工作流。

## 配置工作流

要检查上一个工作流执行中的一个或多个任务是否仍在挂起，您需要使用&#x200B;**[!UICONTROL Query]**&#x200B;和&#x200B;**[!UICONTROL Test]**&#x200B;活动。

1. 在&#x200B;**[!UICONTROL Scheduler]**&#x200B;活动后添加&#x200B;**[!UICONTROL Query]**&#x200B;活动，然后按如下配置它。

1. 将活动的资源更改为&#x200B;**[!UICONTROL WorkflowTaskDetail]**，这意味着它将目标工作流的当前任务。

   ![](assets/scheduled-wkf-resource.png)

1. 使用以下规则配置查询:

   ![](assets/scheduled-wkf-query.png)

   * 第一个规则过滤器当前任务(查询2)和属于当前工作流的下一个计划任务(计划2)。

      >[!NOTE]
      >
      >当&#x200B;**[!UICONTROL Scheduler]**&#x200B;活动开始时，它会立即添加另一个计划任务以在下一个计划时间运行并开始工作流。 因此，在从上一个执行中查找待处理的查询时，务必过滤任务和计划任务。

   * 第二规则确定工作流上次运行中的任何任务是否仍处于活动状态（待定），这与0执行状态相对应。

1. 添加&#x200B;**[!UICONTROL Test]**&#x200B;活动，以检查&#x200B;**[!UICONTROL Query]**&#x200B;活动返回的挂起任务数。 为此，请配置两个出站过渡。

   ![](assets/scheduled-wkf-test.png)

   * 如果没有挂起的过渡，则第一个任务将继续执行工作流
   * 如果存在任何待处理过渡，则第二个任务将取消工作流执行。

   ![](assets/scheduled-wkf-workflow.png)

您现在可以根据需要配置其余工作流。 如果由于挂起的任务而取消了工作流执行，则当工作流根据计划再次运行时，它可以完成这些步骤。 这将确保仅当前一个执行没有活动（待定）任务时，工作流执行才会继续。
