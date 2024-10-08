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
source-git-commit: 69621657e1d367043200f741d93972664e6eb8fb
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 27%

---

# 流程和数据管理入门 {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">工作流活动</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">用例</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">筛选数据</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">导入/导出数据</a></p></td></tr>
</table>

Adobe Campaign 提供了一个全面的图形环境，允许您设计包括分段、活动执行、文件处理等在内的复杂流程。例如，您可以使用某个工作流从服务器下载文件、解压缩，然后将其记录导入 Adobe Campaign 数据库。

工作流可以在不同的上下文中使用，例如：

* 定位以管理受众或发送消息。
* 进行数据管理 (ETL) 以处理数据。
* 将数据导入 Campaign 数据库。
* 数据库清理、恢复跟踪信息等技术流程。

>[!IMPORTANT]
>
> Adobe建议客户不要同时运行20个以上的活动工作流执行，并优先考虑工作流执行并将其分散到不同的时间段。 有关详细信息，请参阅[此页面](../../automating/using/best-practices-workflows.md)中提供的最佳实践。

## 工作流活动 {#workflow-activities}

提供了各种活动来帮助您设计工作流。

[定位活动](../../automating/using/about-targeting-activities.md)允许您通过定义集并使用交集、并集或排除操作拆分或组合这些集来构建一个或多个目标。

通过[执行活动](../../automating/using/about-execution-activities.md)，协调工作流及其活动，而[渠道活动](../../automating/using/about-channel-activities.md)允许您合并Campaign Standard通信渠道以创建跨渠道工作流。

最后，[数据管理活动](../../automating/using/about-data-management-activities.md)允许您处理数据库中的数据。

了解更多：

* [构建工作流](../../automating/using/building-a-workflow.md)
* [执行工作流](../../automating/using/about-workflow-execution.md)
* [工作流最佳实践](../../automating/using/best-practices-workflows.md)

## 筛选数据 {#filter-data}

利用&#x200B;**查询编辑器**&#x200B;筛选数据库中的数据，并构建群体以更好地定位收件人。 查询编辑器可用于在Campaign Standard中执行多个操作：创建查询类型受众、定义投放目标或工作流活动中的群体。

查询编辑器附带&#x200B;**预定义过滤器和规则**，以便快速轻松地过滤。 但是，您还可以使用&#x200B;**高级表达式编辑**&#x200B;功能。 这允许您手动输入条件并使用函数，以形成自己的规则。

了解更多：

* [编辑查询](../../automating/using/editing-queries.md)
* [高级表达式编辑](../../automating/using/advanced-expression-editing.md)
* [函数列表](../../automating/using/list-of-functions.md)

## 导入/导出数据 {#import-export-data}

Campaign Standard具有多个&#x200B;**数据管理功能**&#x200B;以导入和导出数据。

[工作流数据管理活动](../../automating/using/about-data-management-activities.md)允许您导入数据、对字段执行批量更新、接收或发送文件，或将未识别的数据链接到现有资源。

使用[导入模板](../../automating/using/importing-data-with-import-templates.md)，通过简化的导入功能管理管理员定义的特定类型的导入。

[导出日志](../../automating/using/exporting-logs.md)允许您通过简单的工作流程导出日志数据，从而允许您在自己的报告或BI工具中分析营销活动的结果。

利用[包](../../automating/using/managing-packages.md)在不同营销活动实例之间交换资源，例如，复制实例的配置，或者将数据从服务器传输到另一个服务器，包括自定义资源。

最后，[导出列表](../../automating/using/exporting-lists.md)允许您从Campaign Standard导出任何列表，例如测试用户档案列表、隔离电子邮件地址列表等。

了解更多：

* [导入和导出数据](../../automating/using/about-data-import-and-export.md)
* [用例：导出/导入自定义资源](../../automating/using/exporting-importing-custom-resources.md)

## 其他资源

* [流程和数据管理教程视频](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/managing-processes-and-data/creating-a-workflow.html?lang=zh-Hans)
* [技术工作流](../../administration/using/technical-workflows.md)
* [Campaign Standard 数据模型快速入门](../../developing/using/get-started-data-model.md)
