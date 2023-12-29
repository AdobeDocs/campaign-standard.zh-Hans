---
title: 预定工作流的重叠执行
description: 了解如何防止计划工作流的重叠执行。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8d9820a4-3c44-45f5-815e-4ed48a96276d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 1%

---

# 预定工作流的重叠执行{#preventing-overlapping-execution-of-scheduled-workflows}

## 关于计划的工作流执行

在Campaign Standard中，工作流引擎确保工作流实例仅由一个进程执行。 阻止活动（如导入、长时间运行查询或写入数据库）会在运行时阻止执行任何其他任务。

另一方面，非阻塞活动不会阻止执行其他任务(通常是等待事件的活动，例如 **[!UICONTROL Scheduler]** 活动)。

这可能会导致出现以下情况：基于计划的工作流可以开始执行，即使同一工作流的上一次运行尚未完成，从而可能导致意外的数据问题。

因此，在设计包含多个活动的已计划工作流时，您需要确保在该工作流完成之前不会重新计划该工作流。 要实现此目的，您需要配置工作流，以防止在先前执行的一个或多个任务仍然等待执行时执行该工作流。

## 配置工作流

要检查先前工作流执行中的一个或多个任务是否仍然挂起，您需要使用 **[!UICONTROL Query]** 和 **[!UICONTROL Test]** 活动。

1. 添加 **[!UICONTROL Query]** 活动之后 **[!UICONTROL Scheduler]** 活动，然后按照以下方式对其进行配置。

1. 将活动的资源更改为 **[!UICONTROL WorkflowTaskDetail]**，这意味着它将定向工作流的当前任务。

   ![](assets/scheduled-wkf-resource.png)

1. 使用以下规则配置查询：

   ![](assets/scheduled-wkf-query.png)

   * 第一个规则筛选出当前任务(query2)以及属于当前工作流的下一个计划任务(schedule2)。

     >[!NOTE]
     >
     >当 **[!UICONTROL Scheduler]** 活动开始，会立即添加另一个计划任务以在下一个计划时间运行并启动工作流。 因此，在从上一个执行中查找待处理任务时，筛选查询和计划任务非常重要。

   * 第二个规则确定先前运行的工作流中的任何任务是否仍处于活动状态（待处理），这与0执行状态相对应。

1. 添加 **[!UICONTROL Test]** 活动，以检查返回的待处理任务数量 **[!UICONTROL Query]** 活动。 为此，请配置两个叫客过渡。

   ![](assets/scheduled-wkf-test.png)

   * 如果没有待处理任务，则第一个过渡将继续执行工作流，
   * 如果存在任何待处理任务，则第二个过渡将取消工作流执行。

   ![](assets/scheduled-wkf-workflow.png)

您现在可以根据需要配置工作流的其余部分。 如果由于挂起的任务而取消工作流执行，则当工作流根据计划再次运行时，它可以完成这些步骤。 这将确保仅当先前执行中没有活动（挂起）任务时，工作流执行才会继续。
