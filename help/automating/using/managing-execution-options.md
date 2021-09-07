---
solution: Campaign Standard
product: campaign
title: 管理执行选项
description: 了解如何管理工作流执行选项。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: b0cc38fe-cf71-4350-8b4e-7daf0bf94066
source-git-commit: 8092eda6241e83a9bb4c23d8955cd12b6509432a
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 6%

---

# 管理执行选项 {#managing-execution-options}

要修改工作流的执行选项，请使用![](assets/edit_darkgrey-24px.png)按钮访问工作流属性并选择&#x200B;**[!UICONTROL Execution]**&#x200B;部分。

![](assets/wkf_execution_6.png)

可能的选项包括：

* **[!UICONTROL Default affinity]**:利用此字段，可强制在特定计算机上执行工作流或工作流活动。

* **[!UICONTROL History in days]**:指定必须清除历史记录的间隔天数。历史记录包含与工作流相关的元素：日志、任务、事件（链接到工作流操作的技术对象），以及由&#x200B;**[!UICONTROL Transfer file]**&#x200B;活动下载的文件。 对于现成的工作流模板，默认值为30天。

   清除历史记录由数据库清理技术工作流执行，默认每天执行该工作流（请参阅[技术工作流列表](../../administration/using/technical-workflows.md)）。

   >[!IMPORTANT]
   >
   >如果将&#x200B;**[!UICONTROL History in days]**&#x200B;字段留空，则其值将被视为“1”，这意味着历史记录将在1天后清除。

* **[!UICONTROL Save SQL queries in the log]**:用于将工作流中的SQL查询保存到日志中。

* **[!UICONTROL Diagnostic mode (Log execution plan of long running queries and give recommendations)]**:如果希望记录整个执行计划，请勾选此选项。默认情况下，该复选框处于禁用状态。

   有关此选项的更多信息，请参阅此[部分](#diagnostic-mode)。

* **[!UICONTROL Keep interim results]**:如果希望能够查看过渡的详细信息，请勾选此选项。

   >[!CAUTION]
   >
   >使用此选项会占用大量磁盘空间，其目的在于帮助您构建工作流并确保配置和行为正确。在制作实例中，请不要勾选该选项。

* **[!UICONTROL Execute in the engine (do not use in production)]**:允许您在本地执行工作流，以便进行开发环境测试。

* **[!UICONTROL Severity]**:允许您指定在Adobe Campaign实例中执行工作流的优先级。此字段仅供Adobe团队用于监控目的。

**[!UICONTROL Error management]**&#x200B;部分提供了其他选项，可用于管理工作流在发生错误时的行为方式。 [错误管理](../../automating/using/monitoring-workflow-execution.md#error-management)部分详细介绍了这些选项。

## 诊断模式 {#diagnostic-mode}

>[!CAUTION]
>
>此选项可以显着影响您的工作流性能，应谨慎使用。

启用后，如果查询需要超过一分钟，工作流属性的&#x200B;**[!UICONTROL Execution]**&#x200B;部分中的&#x200B;**[!UICONTROL Diagnostic mode (Log execution plan of long running queries and give recommendations)]**&#x200B;选项会记录整个执行计划。

![](assets/wkf_diagnostic.png)

启用此选项并启动工作流后，如果查询超过一分钟，则执行计划将被记录。 然后，可以使用“解释分析”(EXPLAIN ANALYZE)来检索您的执行计划。

有关此内容的详细信息，请参阅[PostgreSQL文档](https://www.postgresql.org/docs/9.4/using-explain.html)。

如果此查询中有序列扫描，**[!UICONTROL Diagnostic mode]**&#x200B;还将提供建议，借助过滤器表达式创建索引。

>[!NOTE]
>
> 这些建议仅供参考，应根据您的用例仔细使用。

![](assets/wkf_diagnostic_4.png)

在执行工作流时必须满足以下两个条件才能触发推荐：

* 序列扫描占用查询40%以上的时间。

* 序列扫描后生成的行少于表中总行数的1 %。

您可以通过选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**，从高级菜单中管理选项：

* **[!UICONTROL Time of query execution (in milliseconds)(DiagnosticModeQueryTime)]**:在字段 **[!UICONTROL Value]** 中，您可以为查询执行设置新的时间。如果查询执行超过此值，则执行计划将被记录。

   ![](assets/wkf_diagnostic_2.png)

* **[!UICONTROL Percentage of seq scan time (DiagnosticModeSeqScanPercentage)]**:在字 **[!UICONTROL Value]** 段中，您可以更改序列扫描为生成推荐而必须花费的查询时间百分比。

   ![](assets/wkf_diagnostic_3.png)
