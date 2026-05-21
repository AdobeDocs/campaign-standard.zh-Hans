---
title: 关于定位活动
description: 可以从屏幕的左侧访问定向活动。
audience: automating
content-type: reference
topic-tags: targeting-activities
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 1cd471e3-5332-4119-b342-2c3c8503fdd1
TQID: https://experienceleague.adobe.com/PPDlvoeHKNpeLfYe4qYFq7mzQUb3oR7XkrMK-jQFpmY
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 437
ht-degree: 54%

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

**[!UICONTROL Targeting]**&#x200B;活动允许您为其叫客过渡定义&#x200B;**区段代码**。 然后，您可以根据这些区段代码创建报告，以衡量营销活动的效果。 如需详细信息，请参阅[此小节](../../reporting/using/creating-a-report-workflow-segment.md)。

## 选择数据 {#selecting-data}

您可以使用以下活动选择数据：

* 利用 **[!UICONTROL Query]** 活动，可筛选和提取 Adobe Campaign 数据库中的元素群体。 请参阅[查询](../../automating/using/query.md)节。
* 利用 **[!UICONTROL Incremental query]** 活动，可筛选和提取 Adobe Campaign 数据库中的元素群体。 每次执行此活动时，都会排除先前执行得出的结果。 这允许您仅定向新元素。请参见。 [增量查询](../../automating/using/incremental-query.md)节。
* 利用 **[!UICONTROL Read audience]** 活动，可检索现有受众，并通过应用附加筛选条件来优化现有受众。请参阅[读取受众](../../automating/using/read-audience.md)部分。

## 分段数据 {#segmenting-data}

通过Adobe Campaign，可处理入站数据上的集。 因此，您可以合并多个群体，排除部分群体或仅保留多个目标的共有数据。

* 利用 **[!UICONTROL Union]** 活动，可将多个活动的结果重组为单个目标。 请参阅[并集](../../automating/using/union.md)部分。
* 利用 **[!UICONTROL Intersection]** 活动，可仅在活动中保留不同集客群体的共有元素。 请参阅[交集](../../automating/using/intersection.md)部分。
* 利用 **[!UICONTROL Exclusion]** 活动，可根据特定条件从一个群体中排除某些元素。 请参阅[排除项](../../automating/using/exclusion.md)部分。
* 利用 **[!UICONTROL Segmentation]** 活动，可根据由之前放在工作流中的活动计算出的客户群体，创建一个或多个区段。 在活动结束时，可以在单一过渡或多个不同过渡中处理这些区段。 请参阅[分段](../../automating/using/segmentation.md)部分。

## 丰富数据 {#enriching-data}

识别出的和收集的数据可以被扩充、聚合和操作以优化目标构建。 您可以通过包括未在数据集市中建模的数据来简化和优化定位流程。

利用&#x200B;**[!UICONTROL Query]**&#x200B;和&#x200B;**[!UICONTROL Incremental query]**&#x200B;活动的&#x200B;**[!UICONTROL Additional data]**&#x200B;选项卡，可扩充查询所定向的数据，并将此数据传输到以下工作流活动，以便在其中使用。 其中，您可以添加：

* 简单数据
* 聚合
* 集合

**相关主题：**

* [用例：使用附加数据个性化电子邮件](../../automating/using/personalizing-email-with-additional-data.md)
