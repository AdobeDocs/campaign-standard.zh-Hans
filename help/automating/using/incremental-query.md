---
title: 增量查询
description: 利用增量查询活动，可筛选和提取 Adobe Campaign 数据库中的元素群体。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 18d6ffc0-cfc3-436e-8f0c-ea9c307541e4
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 98%

---

# 增量查询{#incremental-query}

## 说明 {#description}

![](assets/incremental.png)

利用 **[!UICONTROL Incremental query]** 活动，可筛选和提取 Adobe Campaign 数据库中的元素群体。每次执行此活动时，都会排除先前执行得出的结果。这样可让您仅定向新元素。

您可以通过专用选项卡定义针对定向群体的 **[!UICONTROL Additional data]**。此数据存储在附加的列中，并且只能用于正在进行的工作流。

此活动可使用查询编辑器工具。有关该工具的详情，可参见[专述章节](../../automating/using/editing-queries.md#about-query-editor)。

## 使用环境 {#context-of-use}

**[!UICONTROL Incremental query]** 必须链接到 **[!UICONTROL Scheduler]** 以定义工作流的执行频次，从而定义查询。

通过专用于此活动的 **[!UICONTROL Processed data]** 选项卡，可根据需要查看之前执行该活动所获的任何结果。

**[!UICONTROL Incremental query]** 活动可用于各种类型的应用：

* 对个体进行分段以定义消息的目标、受众等。

* 导出数据。

   您可以使用 **[!UICONTROL Incremental query]** 活动以文件格式定期导出新日志。例如，如果要在外部报告或 BI 工具中使用日志数据，则此功能非常有用。[导出日志](../../automating/using/exporting-logs.md)章节中提供了完整的示例。

**相关主题**

* [使用案例：對服務訂閱者的增量查詢](../../automating/using/incremental-query-on-subscribers.md)

## 配置 {#configuration}

1. 将 **[!UICONTROL Incremental query]** 活动拖放到工作流中。
1. 选择活动，然后使用所显示快捷操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。
1. 如果要在非用户档案资源上运行查询，请转至该活动的 **[!UICONTROL Properties]** 选项卡，然后选择 **[!UICONTROL Resource]** 和 **[!UICONTROL Targeting dimension]**。

   利用 **[!UICONTROL Resource]** 可微调面板中显示的过滤器，包括 **[!UICONTROL Targeting dimension]**、对应于所选资源的上下文、对应于您要获取的群体类型（已识别的用户档案、投放、链接到所选资源的数据等）。

1. 在 **[!UICONTROL Target]** 选项卡中，可通过定义和组合规则来运行查询。
1. 在 **[!UICONTROL Processed data]** 选项卡中，选择要用于工作流下一次执行的增量模式：

   * **[!UICONTROL Use the exclusion of the results of previous executions]**：每次新执行都会排除过往执行所获的结果。
   * **[!UICONTROL Use a date field]**：下一次执行只考虑其包含的选定日期字段大于或等于 **[!UICONTROL Incremental query]** 活动上次执行日期的结果。您可以选择与在 **[!UICONTROL Properties]** 选项卡所选资源有关的任何日期字段。此模式在查询大型资源（如日志数据）时表现更好。

      在第一次执行工作流后，您即可在此选项卡中看到将用于下一次执行的最后一次执行日期。每次执行工作流后，系统都会自动更新该日期。您仍然可以手动输入新值来覆盖此值，以使其符合您的需求。
   >[!NOTE]
   >
   >根据所选的日期字段，使用 **[!UICONTROL Use a date field]** 模式具有更大的灵活性。例如，如果所选字段对应于修改日期，则可利用日期字段模式，检索最近更新的数据，而其他模式只能简单地排除以前执行中已定向的记录，即使上次执行工作流后已修改这些记录也是如此。

   ![](assets/incremental_query_usedatefield.png)

1. 您可以通过专用选项卡定义针对定向群体的 **[!UICONTROL Additional data]**。此数据存储在附加的列中，并且只能用于正在进行的工作流。而且，您还可以从链接到查询定向维度的 Adobe Campaign 查询数据库表格添加数据。请参阅[扩充数据](../../automating/using/query.md#enriching-data)一节。
1. 确认活动的配置并保存工作流。

## 丰富数据 {#enriching-data}

就像查询一样，您可以扩充来自 **[!UICONTROL Incremental query]** 的数据。请参阅[扩充数据](../../automating/using/query.md#enriching-data)一节。
