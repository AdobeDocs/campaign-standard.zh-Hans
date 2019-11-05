---
title: 定位数据
description: 了解定位和选择所需数据的不同方式。
page-status-flag: 从未激活
uuid: 0645d6e5-6a7e-4917-874a-7e7725f06abd
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 工作流——一般操作
discoiquuid: 382ea74e-1662-4c64-96d7-676040586913
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 定位数据{#targeting-data}

## 选择数据 {#selecting-data}

您可以使用以下活动选择数据：

* 该活 **[!UICONTROL Query]** 动允许您从Adobe Campaign数据库中过滤和提取大量元素。 请参阅 [查询](../../automating/using/query.md) 部分。
* 该活 **[!UICONTROL Incremental query]** 动允许您从Adobe Campaign数据库中过滤和提取大量元素。 每次执行此活动时，都会排除先前执行的结果。 这允许您仅针对新元素。请参阅。 [增量查询](../../automating/using/incremental-query.md) 。
* 该活 **[!UICONTROL Read audience]** 动允许您检索现有受众，并通过应用其他筛选条件来优化它。请参阅阅读 [受众部分](../../automating/using/read-audience.md) 。

## 细分数据 {#segmenting-data}

Adobe Campaign允许您处理入站数据集。 因此，您可以组合多个人群，排除其中的一部分，或仅保持数据与多个目标的公用性。

* 该活 **[!UICONTROL Union]** 动允许您将多个活动的结果重新分组到单个目标中。 请参阅 [联合](../../automating/using/union.md) 。
* 活动 **[!UICONTROL Intersection]** 允许您仅保留活动中不同入站人群通用的元素。 请参阅“ [交叉](../../automating/using/intersection.md) ”部分。
* 该活 **[!UICONTROL Exclusion]** 动允许您根据特定标准从一个人群中排除元素。 请参阅“ [排除](../../automating/using/exclusion.md) ”部分。
* 通过 **[!UICONTROL Segmentation]** 活动，您可以根据工作流中先前放置的活动计算的人口来创建一个或多个区段。 在活动结束时，可以在一个过渡或不同的过渡中处理这些过渡。 请参阅 [分段](../../automating/using/segmentation.md) 。

## 丰富数据 {#enriching-data}

可以丰富、聚集和操作所识别和收集的数据以优化目标构造。 您可以通过包括未在数据集市中建模的数据来简化和优化定位流程。

通过 **[!UICONTROL Additional data]** 和活动的选 **[!UICONTROL Query]** 项卡 **[!UICONTROL Incremental query]** ，您可以丰富查询所针对的数据，并将这些数据传输到以下工作流活动中，以便在其中使用。 特别是，您可以添加：

* 简单数据
* 聚合
* 集合

**相关主题**

* [用例：创建每周一次的电子邮件发送](../../automating/using/workflow-weekly-offer.md)
* [用例：创建按位置分段的交付](../../automating/using/workflow-segmentation-location.md)
* [用例：使用补充创建交付](../../automating/using/workflow-created-query-with-complement.md)
* [用例：重定向工作流向非打开者发送新分发](../../automating/using/workflow-cross-channel-retargeting.md)
