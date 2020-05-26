---
title: 流程和数据管理入门
description: Adobe Campaign优惠一个全面的图形环境，它允许您设计流程并实现流程自动化。
page-status-flag: never-activated
uuid: 7c1e8cea-90d0-491f-ab8f-6cd69f8a6c3b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
discoiquuid: 40503917-7a53-4d99-96a4-57aa9e98ec87
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 5%

---


# 流程和数据管理入门 {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">工作流活动</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">用例</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">筛选数据</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">导入／导出数据</a></p></td></tr>
</table>

Adobe Campaign优惠是一个全面的图形环境，它允许您设计复杂的流程，包括细分、活动执行、文件处理、批准等。 例如，您可以使用工作流从服务器下载文件，解压它，然后将其记录导入Adobe Campaign库。

工作流还可能涉及用户，方法是为他们分配任务或让他们批准已执行的任务。 这意味着您可以向一个或多个用户分配任务，以处理内容或指定目标，并在发送消息之前批准验证。

工作流可以用于不同的上下文，例如：

* 定位以管理受众或发送消息。
* 数据管理(ETL)来操作数据。
* 将数据导入活动库。
* 诸如数据库清理、恢复跟踪信息等技术流程。

## 工作流活动 {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

提供各种活动，帮助您设计工作流。

[定位活动](../../automating/using/about-targeting-activities.md) 允许您通过定义集并使用交叉、合并或排除操作拆分或组合这些集来构建一个或多个目标。

借助 [执行活动](../../automating/using/about-execution-activities.md)，协调您的工作流及其活动，而 [渠道活动](../../automating/using/about-channel-activities.md) 则允许您组合Campaign Standard通信渠道来创建跨渠道工作流。

最后， [数据管理活动](../../automating/using/about-data-management-activities.md) 允许您处理数据库中的数据。

阅读更多：

* [构建工作流](../../automating/using/building-a-workflow.md)
* [执行工作流](../../automating/using/about-workflow-execution.md)
* [工作流最佳实践](../../automating/using/best-practices-workflows.md)

## 筛选数据 {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

利用查询 **编辑器** ，从数据库中过滤数据并建立目标群，从而更好地收件人。 查询编辑器可用于在Campaign Standard中执行多个操作： 创建查询类型受众，在工作流活动中定义投放目标或人口。

查询编辑器附带 **预定义过滤器和规则** ，可快速、轻松地进行筛选。 但是，您也可以使用 **高级表达式编辑** 功能。 这允许您手动输入条件和使用函数，以形成您自己的规则。

阅读更多：

* [编辑查询](../../automating/using/editing-queries.md)
* [高级表达式编辑](../../automating/using/advanced-expression-editing.md)
* [功能列表](../../automating/using/list-of-functions.md)

## 导入／导出数据 {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard具有多 **种数据管理功能** ，可导入和导出数据。

[工作流](../../automating/using/about-data-management-activities.md) 数据管理活动允许您导入数据、对字段执行大量更新、接收或发送文件，或将未识别的数据链接到现有资源。

借助 [导入模板](../../automating/using/importing-data-with-import-templates.md)，通过简化的导入功能管理管理员定义的特定类型的导入。

[导出日志](../../automating/using/exporting-logs.md) ，您可以通过一个简单的工作流程导出日志活动，从而在您自己的报告或BI工具中分析营销的结果。

利用 [包](../../automating/using/managing-packages.md) ，在不同活动实例之间交换资源，例如，复制实例的配置，或将数据从服务器传输到包括自定义资源在内的其他实例。

最后， [导出列表](../../automating/using/exporting-lists.md) 允许您从Campaign Standard导出任何列表，例如，测试用户档案的列表、隔离电子邮件地址的列表等。

阅读更多：

* [导入和导出数据](../../automating/using/about-data-import-and-export.md)
* [用例：导出/导入自定义资源](../../automating/using/exporting-importing-custom-resources.md)

## 其他资源

* [流程和数据管理教程视频](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/getting-started/create-workflow.html)
* [技术工作流](../../administration/using/technical-workflows.md)
* [Campaign Standard数据模型入门](../../developing/using/get-started-data-model.md)
