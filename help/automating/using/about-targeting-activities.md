---
solution: Campaign Standard
product: campaign
title: 关于定位活动
description: 定位活动可从屏幕左侧访问。
audience: automating
content-type: reference
topic-tags: targeting-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 48%

---


# 关于定位活动{#about-targeting-activities}

从屏幕左侧的面板，展开 **[!UICONTROL Targeting]** 部分。

这些活动特定于定位、操作人口数据和筛选活动。 它们允许您通过定义集并使用交叉、合并或排除操作拆分或组合这些集来构建一个或多个目标。

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

**[!UICONTROL Targeting]** 活动允许您为 **其出站** 过渡定义段代码。 然后，您可以根据这些区段代码创建报告，以衡量营销活动的效果。有关更多信息，请参阅[此章节](../../reporting/using/creating-a-report-workflow-segment.md)。

## 选择数据 {#selecting-data}

您可以使用以下活动选择数据：

* 利用 **[!UICONTROL Query]** 活动，可筛选和提取 Adobe Campaign 数据库中的元素群体。请参阅 [查询](../../automating/using/query.md) 部分。
* 利用 **[!UICONTROL Incremental query]** 活动，可筛选和提取 Adobe Campaign 数据库中的元素群体。每次执行此活动时，都会排除先前执行得出的结果。这允许您仅目标新元素。请参阅。 [增量查询](../../automating/using/incremental-query.md) 。
* The **[!UICONTROL Read audience]** activity allows you to retrieve an existing audience and to refine it by applying additional filtering conditions.See the [Read audience](../../automating/using/read-audience.md) section.

## 细分数据 {#segmenting-data}

Adobe Campaign允许您处理入站数据集。 因此，您可以合并多个人群，排除其中的一部分，或仅保持数据与多个目标通用。

* 利用 **[!UICONTROL Union]** 活动，可将多个活动的结果重组为单个目标。请参阅 [合并](../../automating/using/union.md) 部分。
* 利用 **[!UICONTROL Intersection]** 活动，可仅在活动中保留不同集客群体的共有元素。请参阅 [交叉](../../automating/using/intersection.md) 部分。
* 利用 **[!UICONTROL Exclusion]** 活动，可根据特定条件从一个群体中排除某些元素。请参阅 [排除](../../automating/using/exclusion.md) 部分。
* 利用 **[!UICONTROL Segmentation]** 活动，可根据由之前放在工作流中的活动计算出的客户群体，创建一个或多个区段。在活动结束时，可以在单一过渡或多个不同过渡中处理这些区段。请参阅 [分段](../../automating/using/segmentation.md) 。

## 扩充数据{#enriching-data}

可以丰富、聚集和操纵所识别和收集的数据以优化目标构造。 您可以通过在数据集市中包含未建模的数据来简化和优化定位流程。

The **[!UICONTROL Additional data]** tab of the **[!UICONTROL Query]** and **[!UICONTROL Incremental query]** activities allows you to enrich the data targeted by the query and transfer this data to the following workflow activities, where it can be utilized. 其中，您可以添加：

* 简单数据
* 聚合
* 集合

**相关主题：**

* [用例：个性化包含其他数据的电子邮件](../../automating/using/personalizing-email-with-additional-data.md)
