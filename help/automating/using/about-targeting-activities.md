---
title: 关于定位活动
description: 可以从屏幕的左侧访问定向活动。
audience: automating
content-type: reference
topic-tags: targeting-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 1cd471e3-5332-4119-b342-2c3c8503fdd1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 35%

---

# 关于定位活动{#about-targeting-activities}

从屏幕左侧的面板，展开 **[!UICONTROL Targeting]** 部分。

这些活动专门用于定位、处理人口数据和过滤活动。 它们允许您通过定义集并使用交集、并集或排除操作拆分或组合这些集来构建一个或多个目标。

![](assets/wkf_targeting_activities.png)

**[!UICONTROL Targeting]** 部分提供了以下活动：

* [查询](../../automating/using/query.md)
* [增量查询](../../automating/using/incremental-query.md)
* [并集](../../automating/using/union.md)
* [交集](../../automating/using/intersection.md)
* [排除](../../automating/using/exclusion.md)
* [分段](../../automating/using/segmentation.md)
* [读取受众](../../automating/using/read-audience.md)
* [保存受众](../../automating/using/save-audience.md)
* [重复数据删除](../../automating/using/deduplication.md)
* [扩充](../../automating/using/enrichment.md)

**[!UICONTROL Targeting]**&#x200B;活动允许您为其叫客过渡定义&#x200B;**区段代码**。 然后，您可以根据这些区段代码创建报告，以衡量营销活动的效果。有关更多信息，请参阅[此章节](../../reporting/using/creating-a-report-workflow-segment.md)。

## 选择数据 {#selecting-data}

您可以使用以下活动选择数据：

* 利用 **[!UICONTROL Query]** 活动，可筛选和提取 Adobe Campaign 数据库中的元素群体。请参阅[查询](../../automating/using/query.md)节。
* 利用 **[!UICONTROL Incremental query]** 活动，可筛选和提取 Adobe Campaign 数据库中的元素群体。每次执行此活动时，都会排除先前执行得出的结果。这允许您仅定向新元素。请参见。 [增量查询](../../automating/using/incremental-query.md)节。
* **[!UICONTROL Read audience]**&#x200B;活动允许您检索现有受众，并通过应用附加筛选条件来优化现有受众。请参阅[读取受众](../../automating/using/read-audience.md)部分。

## 分段数据 {#segmenting-data}

通过Adobe Campaign，可处理入站数据上的集。 因此，您可以合并多个群体，排除部分群体或仅保留多个目标的共有数据。

* 利用&#x200B;**[!UICONTROL Union]**&#x200B;活动，可将多个活动的结果重组为单个目标。 请参阅[并集](../../automating/using/union.md)部分。
* 利用&#x200B;**[!UICONTROL Intersection]**&#x200B;活动，可仅在活动中保留不同集客群体的共有元素。 请参阅[交集](../../automating/using/intersection.md)部分。
* 利用&#x200B;**[!UICONTROL Exclusion]**&#x200B;活动，可根据特定条件从一个群体中排除某些元素。 请参阅[排除项](../../automating/using/exclusion.md)部分。
* 利用 **[!UICONTROL Segmentation]** 活动，可根据由之前放在工作流中的活动计算出的客户群体，创建一个或多个区段。在活动结束时，可以在单个过渡或不同过渡中处理这些区段。 请参阅[分段](../../automating/using/segmentation.md)部分。

## 丰富数据 {#enriching-data}

识别出的和收集的数据可以被扩充、聚合和操作以优化目标构建。 您可以通过包括未在数据集市中建模的数据来简化和优化定位流程。

利用&#x200B;**[!UICONTROL Query]**&#x200B;和&#x200B;**[!UICONTROL Incremental query]**&#x200B;活动的&#x200B;**[!UICONTROL Additional data]**&#x200B;选项卡，可扩充查询所定向的数据，并将此数据传输到以下工作流活动，以便在其中使用。 其中，您可以添加：

* 简单数据
* 聚合
* 集合

**相关主题：**

* [用例：使用附加数据个性化电子邮件](../../automating/using/personalizing-email-with-additional-data.md)
