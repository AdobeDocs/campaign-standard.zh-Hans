---
title: 关于定位活动
description: 定位活动可从屏幕左侧访问。
page-status-flag: never-activated
uuid: a6cbc431-1ae3-428e-b2c9-893454b32ae2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 5f7607a1-5f71-4d66-9688-3e5a1774f1b4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 5%

---


# 关于定位活动{#about-targeting-activities}

从调色板的屏幕左侧展开部 **[!UICONTROL Targeting]** 分。

这些活动特定于定位、操作人口数据和筛选活动。 它们允许您通过定义集并使用交叉、合并或排除操作拆分或组合这些集来构建一个或多个目标。

![](assets/wkf_targeting_activities.png)

该 **[!UICONTROL Targeting]** 部分提供以下活动:

* [查询](../../automating/using/query.md)
* [增量查询](../../automating/using/incremental-query.md)
* [合并](../../automating/using/union.md)
* [交叉](../../automating/using/intersection.md)
* [排除](../../automating/using/exclusion.md)
* [分段](../../automating/using/segmentation.md)
* [读取受众](../../automating/using/read-audience.md)
* [保存受众](../../automating/using/save-audience.md)
* [重复数据删除](../../automating/using/deduplication.md)
* [扩充](../../automating/using/enrichment.md)

**[!UICONTROL Targeting]** 活动允许您为 **其出站** 过渡定义段代码。 然后，您可以根据这些段代码创建报告，以衡量营销活动的效率。 如需详细信息，请参阅[此部分](../../reporting/using/creating-a-report-workflow-segment.md)。

## 选择数据 {#selecting-data}

您可以使用以下活动选择数据：

* 活动 **[!UICONTROL Query]** 允许您过滤和提取Adobe Campaign数据库中的元素集合。 请参阅 [查询](../../automating/using/query.md) 部分。
* 活动 **[!UICONTROL Incremental query]** 允许您过滤和提取Adobe Campaign数据库中的元素集合。 每次执行此活动时，都会排除先前执行的结果。 这允许您仅目标新元素。请参阅。 [增量查询](../../automating/using/incremental-query.md) 。
* 该 **[!UICONTROL Read audience]** 活动允许您检索现有受众，并通过应用其他过滤条件来优化它。请参阅 [读取受众](../../automating/using/read-audience.md) 部分。

## 细分数据 {#segmenting-data}

Adobe Campaign允许您处理入站数据集。 因此，您可以合并多个人群，排除其中的一部分，或仅保持数据与多个目标通用。

* 该 **[!UICONTROL Union]** 活动允许您将多个活动的结果重新分组为单个目标。 请参阅 [合并](../../automating/using/union.md) 部分。
* 活动 **[!UICONTROL Intersection]** 允许您仅保留活动中不同入站群体通用的元素。 请参阅 [交叉](../../automating/using/intersection.md) 部分。
* 该 **[!UICONTROL Exclusion]** 活动允许您根据特定标准从一个种群中排除元素。 请参阅 [排除](../../automating/using/exclusion.md) 部分。
* 通过 **[!UICONTROL Segmentation]** 活动，您可以根据活动在工作流中放置的先前计算的群体创建一个或多个区段。 在活动结束时，可以在一个过渡或不同过渡中处理这些数据。 请参阅 [分段](../../automating/using/segmentation.md) 。

## 丰富数据 {#enriching-data}

可以丰富、聚集和操纵所识别和收集的数据以优化目标构造。 您可以通过在数据集市中包含未建模的数据来简化和优化定位流程。

通 **[!UICONTROL Additional data]** 过活动 **[!UICONTROL Query]** 和的选 **[!UICONTROL Incremental query]** 项卡，您可以丰富查询所针对的数据，并将这些数据传输到以下工作流活动，以便在这些中加以利用。 特别是，您可以添加：

* 简单数据
* 聚合
* 集合

**相关主题**

* [用例： 创建每周一次的电子邮件投放](../../automating/using/workflow-weekly-offer.md)
* [用例： 在位置创建投放分段](../../automating/using/workflow-segmentation-location.md)
* [用例： 使用补充创建投放](../../automating/using/workflow-created-query-with-complement.md)
* [用例： 重定向工作流向非打开者发送新投放](../../automating/using/workflow-cross-channel-retargeting.md)
