---
solution: Campaign Standard
product: campaign
title: 流程和数据管理入门
description: 利用工作流实现流程自动化、管理数据和受众、发送消息等。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: 工作流
role: 数据架构师
level: 初学者
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 13%

---


# 流程和数据管理入门 {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">工作流活动</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">用例</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">筛选数据</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">导入/导出数据</a></p></td></tr>
</table>

Adobe Campaign优惠一个全面的图形环境，它允许您设计包括细分、活动执行、文件处理等在内的复杂流程。 例如，您可以使用工作流从服务器下载文件，解压缩文件，然后将其记录导入Adobe Campaign数据库。

工作流还可能会涉及用户，方法是为他们分配任务或让他们批准执行的任务。 这意味着，您可以向一个或多个用户分配任务，以处理内容或指定目标，并在发送消息之前批准验证。

工作流可以用于不同的上下文，例如：

* 定位以管理受众或发送消息。
* 数据管理(ETL)来操作数据。
* 将数据导入活动数据库。
* 诸如数据库清理、恢复跟踪信息等技术过程。

## 工作流活动{#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

各种活动可以帮助您设计工作流。

[定位](../../automating/using/about-targeting-activities.md) 活动允许您通过定义集并使用交叉、合并或排除操作拆分或组合这些集来构建一个或多个目标。

使用[执行活动](../../automating/using/about-execution-activities.md)协调工作流及其活动，而使用[渠道活动](../../automating/using/about-channel-activities.md)可以合并Campaign Standard通信渠道来创建跨渠道工作流。

最后，[数据管理活动](../../automating/using/about-data-management-activities.md)允许您操作数据库中的数据。

阅读更多:

* [构建工作流](../../automating/using/building-a-workflow.md)
* [执行工作流](../../automating/using/about-workflow-execution.md)
* [工作流最佳实践](../../automating/using/best-practices-workflows.md)

## 筛选数据{#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

利用&#x200B;**查询编辑器**&#x200B;从数据库中过滤数据并构建数据群以更好地目标收件人。 查询编辑器可用于在Campaign Standard中执行多个操作：创建查询类型受众，在工作流活动中定义投放目标或群体。

查询编辑器附带有&#x200B;**预定义过滤器和规则**，以便快速、轻松地进行筛选。 但是，您也可以使用&#x200B;**高级表达式编辑**&#x200B;功能。 这允许您手动输入条件并使用函数，以便形成您自己的规则。

阅读更多:

* [编辑查询](../../automating/using/editing-queries.md)
* [高级表达式编辑](../../automating/using/advanced-expression-editing.md)
* [函数列表](../../automating/using/list-of-functions.md)

## 导入/导出数据{#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard附带几个&#x200B;**数据管理功能**&#x200B;以导入和导出数据。

[工作流数据管理](../../automating/using/about-data-management-activities.md) 活动允许您导入数据、对字段执行大量更新、接收或发送文件，或将未识别的数据链接到现有资源。

对于[导入模板](../../automating/using/importing-data-with-import-templates.md)，通过简化的导入功能管理管理员定义的某些类型的导入。

[导](../../automating/using/exporting-logs.md) 出日志可让您通过简单的工作流程导出日志活动，从而使您能够在自己的报告或BI工具中分析营销的结果。

利用[Packages](../../automating/using/managing-packages.md)在不同活动实例之间交换资源，例如，复制实例的配置或将数据从服务器传输到包括自定义资源在内的其他实例。

最后，[导出列表](../../automating/using/exporting-lists.md)允许您从Campaign Standard导出任何列表，例如，测试用户档案的列表、隔离电子邮件地址的列表等。

阅读更多:

* [导入和导出数据](../../automating/using/about-data-import-and-export.md)
* [使用案例：导出/导入自定义资源](../../automating/using/exporting-importing-custom-resources.md)

## 其他资源

* [流程和数据管理教程视频](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/getting-started/create-workflow.html)
* [技术工作流](../../administration/using/technical-workflows.md)
* [Campaign Standard 数据模型快速入门](../../developing/using/get-started-data-model.md)
