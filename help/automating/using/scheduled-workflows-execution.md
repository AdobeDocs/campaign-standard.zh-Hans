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
source-wordcount: '422'
ht-degree: 1%

---

# 预定工作流的重叠执行{#preventing-overlapping-execution-of-scheduled-workflows}

## 关于计划工作流执行

在Campaign Standard中，工作流引擎保证只有一个进程执行工作流实例。 阻止活动（如导入、长时间运行的查询或写入数据库）会阻止在运行时执行任何其他任务。

另一方面，无阻塞活动不会阻止执行其他任务(通常是等待事件的活动，例如 **[!UICONTROL Scheduler]** 活动)。

这可能会导致一种情况，即使上次运行同一工作流尚未完成，基于计划的工作流仍可以开始执行，这可能会导致意外的数据问题。

因此，在设计包含多个活动的计划工作流时，您需要确保在工作流完成之前不会重新计划该工作流。 为此，您需要配置工作流，以在先前执行中的一个或多个任务仍处于挂起状态时阻止其执行。

## 配置工作流

要检查上一个工作流执行中的一个或多个任务是否仍处于挂起状态，您需要使用 **[!UICONTROL Query]** 和 **[!UICONTROL Test]** 活动。

1. 添加 **[!UICONTROL Query]** 活动之后 **[!UICONTROL Scheduler]** 活动，然后按如下方式对其进行配置。

1. 将活动的资源更改为 **[!UICONTROL WorkflowTaskDetail]**，这意味着它将定位工作流的当前任务。

   ![](assets/scheduled-wkf-resource.png)

1. 使用以下规则配置查询：

   ![](assets/scheduled-wkf-query.png)

   * 第一个规则过滤掉当前任务（查询2）以及属于当前工作流的下一个计划任务（调度2）。

      >[!NOTE]
      >
      >当 **[!UICONTROL Scheduler]** 活动启动后，它会立即添加另一个计划任务以在下一个计划时间运行并启动工作流。 因此，在从上一次执行中查找待定任务时，务必要筛选查询和计划任务。

   * 第二条规则确定上次运行工作流中的任何任务是否仍然处于活动状态（待处理），该状态与0个执行状态相对应。

1. 添加 **[!UICONTROL Test]** 活动，以检查 **[!UICONTROL Query]** 活动。 为此，请配置两个叫客过渡。

   ![](assets/scheduled-wkf-test.png)

   * 如果没有待定任务，则第一个过渡会继续执行工作流，
   * 如果存在任何待定任务，则第二个过渡会取消工作流执行。

   ![](assets/scheduled-wkf-workflow.png)

您现在可以根据需要配置工作流的其余部分。 如果由于待定任务而取消了工作流执行，则当工作流按照计划再次运行时，它可以完成这些步骤。 这将确保仅当上次执行中没有活动（待定）任务时，工作流才会继续执行。
