---
title: 增量查询
description: 增量查询活动允许您过滤和提取Adobe Campaign数据库中的元素集合。
page-status-flag: never-activated
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: incremental,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 0%

---


# 增量查询{#incremental-query}

## 说明 {#description}

![](assets/incremental.png)

活动 **[!UICONTROL Incremental query]** 允许您过滤和提取Adobe Campaign数据库中的元素集合。 每次执行此活动时，都会排除先前执行的结果。 这允许您仅目标新元素。

您可以通过 **[!UICONTROL Additional data]** 专用选项卡为目标人群定义。 此数据存储在其他列中，并且只能用于进行中的工作流。

活动使用查询编辑器工具。 此工具在专用部分 [中详述](../../automating/using/editing-queries.md#about-query-editor)。

## 使用环境 {#context-of-use}

必 **[!UICONTROL Incremental query]** 须链接到某个工 **[!UICONTROL Scheduler]** 作流，以定义工作流的执行频率，从而定义查询。

该选 **[!UICONTROL Processed data]** 项卡特定于此活动，允许您根据需要视图活动先前执行的任何结果。

该 **[!UICONTROL Incremental query]** 活动可用于各种类型的使用：

* 对个人进行细分以定义消息的目标、受众等。

* 导出数据.

   您可以使用 **[!UICONTROL Incremental query]** 活动定期导出文件中的新日志。 例如，如果要在外部报告或BI工具中使用日志数据，则此功能非常有用。 导出日志部分提供了 [完整示例](../../automating/using/exporting-logs.md) 。

**相关主题**

* [用例： 增量查询服务的订户](../../automating/using/incremental-query-on-subscribers.md)

## Configuration {#configuration}

1. 将活动拖放 **[!UICONTROL Incremental query]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。
1. 如果要在查询资源以外的资源上运行用户档案，请转到活动的选项卡， **[!UICONTROL Properties]** 然后选择 **[!UICONTROL Resource]** 一个和 **[!UICONTROL Targeting dimension]**。

   该 **[!UICONTROL Resource]** 选项允许您细化调色板中显示的过滤器，而与所选资源相关的 **[!UICONTROL Targeting dimension]**&#x200B;上下文选项与您要获取的人口类型(标识的用户档案、投放、链接到所选资源的数据等)相对应。

1. 在选项卡 **[!UICONTROL Target]** 中，通过定义和组合规则来运行查询。
1. 在选 **[!UICONTROL Processed data]** 项卡中，选择要用于工作流的下一个执行的增量模式：

   * **[!UICONTROL Use the exclusion of the results of previous executions]**: 每个新执行的先前执行结果都被排除。
   * **[!UICONTROL Use a date field]**: 下一个执行只考虑具有选定日期字段的结果大于或等于活动的最后执行日 **[!UICONTROL Incremental query]** 期。 您可以选择与在选项卡中选择的资源相关的任何日期 **[!UICONTROL Properties]** 字段。 此模式在查询大资源（如日志数据）时具有更好的性能。

      在工作流的第一次执行之后，您可以在此选项卡中看到将用于下一次执行的最后一个执行日期。 每次执行工作流时，系统都会自动更新它。 您仍然可以手动输入新值来覆盖此值，以便它符合您的需求。
   >[!NOTE]
   >
   >根据 **[!UICONTROL Use a date field]** 所选的日期字段，该模式具有更大的灵活性。 例如，如果所选字段与修改日期相对应，则日期字段模式将允许您检索最近更新的数据，而其他模式将仅排除以前执行中已定位的录制内容，即使这些录制内容自上次执行工作流后已被修改也是如此。

   ![](assets/incremental_query_usedatefield.png)

1. 您可以通过 **[!UICONTROL Additional data]** 专用选项卡为目标人群定义。 此数据存储在其他列中，并且只能用于进行中的工作流。 特别是，您可以从链接到Adobe Campaign定位维度的查询数据库表中添加数据。 请参阅 [丰富数据](../../automating/using/query.md#enriching-data) 部分。
1. 确认活动的配置并保存工作流。

## 丰富数据 {#enriching-data}

就像查询一样，您可以丰富来自的数据 **[!UICONTROL Incremental query]**。 请参阅 [丰富数据](../../automating/using/query.md#enriching-data) 部分。
