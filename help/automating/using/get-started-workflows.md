---
title: 流程和数据管理入门
description: 利用工作流实现流程自动化、管理数据和受众、发送消息等。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Workflows
role: Data Architect
level: Beginner
exl-id: 26be942a-c252-458f-a590-eb235567ca67
source-git-commit: 6ca3ffe3ba2cf7629e511e4ba035b170b25ad79e
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 37%

---

# 流程和数据管理入门 {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">工作流活动</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">用例</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">筛选数据</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">导入/导出数据</a></p></td></tr>
</table>

Adobe Campaign 提供了一个全面的图形环境，允许您设计包括分段、活动执行、文件处理等在内的复杂流程。例如，您可以使用某个工作流从服务器下载文件、解压缩，然后将其记录导入 Adobe Campaign 数据库。

工作流还可能会涉及用户，为他们分配任务或让他们批准已执行的任务。这意味着，您可以向一个或多个用户分配任务，以处理内容或指定目标，并在发送消息之前批准验证。

工作流可以在不同的上下文中使用，例如：

* 定位以管理受众或发送消息。
* 进行数据管理 (ETL) 以处理数据。
* 将数据导入 Campaign 数据库。
* 数据库清理、恢复跟踪信息等技术流程。

>[!IMPORTANT]
>
> Adobe建议客户同时不要运行20个以上的活动工作流执行，并排定工作流执行的优先级，并将其分散开来。 有关更多信息，请参阅 [本页](../../automating/using/best-practices-workflows.md).

## 工作流活动 {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

您可以使用各种活动来帮助您设计工作流。

[定位活动](../../automating/using/about-targeting-activities.md) 允许您通过定义集并使用交集、并集或排除运算拆分或组合这些集来构建一个或多个目标。

使用 [执行活动](../../automating/using/about-execution-activities.md)，可协调您的工作流及其活动，同时 [渠道活动](../../automating/using/about-channel-activities.md) 允许您合并Campaign Standard通信渠道以创建跨渠道工作流。

最后， [数据管理活动](../../automating/using/about-data-management-activities.md) 允许您处理来自数据库的数据。

了解更多信息:

* [构建工作流](../../automating/using/building-a-workflow.md)
* [执行工作流](../../automating/using/about-workflow-execution.md)
* [工作流最佳实践](../../automating/using/best-practices-workflows.md)

## 筛选数据 {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

利用 **查询编辑器** 从数据库中过滤数据并构建群体，以更好地定位收件人。 查询编辑器可用于在Campaign Standard中执行多个操作：在工作流活动中创建查询类型受众、定义投放目标或群体。

查询编辑器随附 **预定义过滤器和规则** 以便快速、轻松地进行筛选。 但是，您也可以使用 **高级表达式编辑** 功能。 这允许您手动输入条件和使用函数，以便形成您自己的规则。

了解更多信息:

* [编辑查询](../../automating/using/editing-queries.md)
* [高级表达式编辑](../../automating/using/advanced-expression-editing.md)
* [函数列表](../../automating/using/list-of-functions.md)

## 导入/导出数据 {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard附带多个 **数据管理功能** 导入和导出数据。

[工作流数据管理活动](../../automating/using/about-data-management-activities.md) 允许您导入数据、对字段执行批量更新、接收或发送文件，或将未识别的数据链接到现有资源。

使用 [导入模板](../../automating/using/importing-data-with-import-templates.md)，通过简化的导入功能管理管理员定义的特定类型导入。

[导出日志](../../automating/using/exporting-logs.md) 允许您通过简单的工作流导出日志数据，从而可以在自己的报表或BI工具中分析营销活动的结果。

利用 [包](../../automating/using/managing-packages.md) 在不同的campaign实例之间交换资源，例如复制实例的配置，或将数据从服务器传输到另一个实例，包括自定义资源。

最后， [导出列表](../../automating/using/exporting-lists.md) 允许您从Campaign Standard导出任何列表，例如测试用户档案列表、隔离电子邮件地址列表等。

了解更多信息:

* [导入和导出数据](../../automating/using/about-data-import-and-export.md)
* [用例：导出/导入自定义资源](../../automating/using/exporting-importing-custom-resources.md)

## 其他资源

* [流程和数据管理教程视频](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/managing-processes-and-data/creating-a-workflow.html?lang=zh-Hans)
* [技术工作流](../../administration/using/technical-workflows.md)
* [Campaign Standard 数据模型快速入门](../../developing/using/get-started-data-model.md)
