---
title: 定位数据
seo-title: 定位数据
description: 定位数据
seo-description: 了解不同的目标定位方法并选择所需的数据。
page-status-flag: 从未激活
uuid: 0645d6e5-6a7e-4917-874a-7e7725f06abd
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 工作流常规操作
discoiquuid: 382ea74e-1662-4c64-96d7-676040586913
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# 定位数据{#targeting-data}

## 选择数据 {#selecting-data}

您可以使用以下活动选择数据：

* **[!UICONTROL Query]** 活动允许您过滤和提取Adobe Campaign数据库中的大量元素。请参阅 [查询](../../automating/using/query.md) 部分。
* **[!UICONTROL Incremental query]** 活动允许您过滤和提取Adobe Campaign数据库中的大量元素。每次执行此活动时，之前执行的结果将被排除。这允许您仅定位新元素查看。[增量查询](../../automating/using/incremental-query.md) 部分。
* **[!UICONTROL Read audience]** 活动允许您检索现有受众并通过应用其他过滤条件来调整该受众。请参阅 [阅读受众](../../automating/using/read-audience.md) 部分。

## 分段数据 {#segmenting-data}

通过Adobe Campaign，您可以在入站数据上处理集。因此，您可以合并多个人群、排除部分内容或只将多个目标的数据保留在一起。

* **[!UICONTROL Union]** 活动允许您将多个活动的结果重新转化为单个目标。请参阅 [Union](../../automating/using/union.md) 部分。
* **[!UICONTROL Intersection]** 活动允许您仅保留活动中不同入站人群共有的元素。请参阅 [“相交](../../automating/using/intersection.md) ”部分。
* **[!UICONTROL Exclusion]** 活动允许您根据特定条件从一个人群排除元素。请参阅 [排除](../../automating/using/exclusion.md) 部分。
* 通过 **[!UICONTROL Segmentation]** 该活动，您可以从之前放置在工作流中的活动计算出的人口中创建一个或多个区段。在活动结束时，可以在一个过渡或不同的过渡中处理它们。请参阅 [分段](../../automating/using/segmentation.md) 部分。

## 丰富数据 {#enriching-data}

可以对所识别和收集的数据进行丰富、聚集和操作以优化目标构建。您可以通过包括数据集市中的数据，简化和优化定位流程。

**[!UICONTROL Additional data]** 通过这些 **[!UICONTROL Query]** 和 **[!UICONTROL Incremental query]** 活动选项卡，您可以丰富查询目标，并将此数据传输到以下工作流活动，以便在其中使用它。特别是，您可以添加：

* 简单数据
* 集合
* 集合

**相关主题**

* [使用案例：创建一次每周一次的电子邮件分发](../../automating/using/workflow-weekly-offer.md)
* [使用案例：在位置上创建分发分段](../../automating/using/workflow-segmentation-location.md)
* [使用案例：通过补充创建交付](../../automating/using/workflow-created-query-with-complement.md)
* [使用案例：重定向向非Opener发送新交付的工作流](../../automating/using/workflow-cross-channel-retargeting.md)
