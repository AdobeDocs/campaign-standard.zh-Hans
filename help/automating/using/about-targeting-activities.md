---
title: 关于定位活动
description: 您可以從熒幕左側存取目標定位活動。
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
ht-degree: 48%

---

# 关于定位活动{#about-targeting-activities}

从屏幕左侧的面板，展开 **[!UICONTROL Targeting]** 部分。

這些活動特定於定位、操控人口資料和篩選活動。 它們可讓您藉由定義集合，並使用交集、聯集或排除作業來分割或組合這些集合，以建立一或多個目標。

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

**[!UICONTROL Targeting]** 活動可讓您定義 **區段代碼** 適用於其對外轉變。 然后，您可以根据这些区段代码创建报告，以衡量营销活动的效果。有关更多信息，请参阅[此章节](../../reporting/using/creating-a-report-workflow-segment.md)。

## 選取資料 {#selecting-data}

您可以使用下列活動選取資料：

* 利用 **[!UICONTROL Query]** 活动，可筛选和提取 Adobe Campaign 数据库中的元素群体。請參閱 [查詢](../../automating/using/query.md) 區段。
* 利用 **[!UICONTROL Incremental query]** 活动，可筛选和提取 Adobe Campaign 数据库中的元素群体。每次执行此活动时，都会排除先前执行得出的结果。這可讓您僅鎖定新元素。請參閱。 [增量查詢](../../automating/using/incremental-query.md) 區段。
* 此 **[!UICONTROL Read audience]** 活動可讓您擷取現有對象，並套用其他篩選條件來調整對象。請參閱 [讀取對象](../../automating/using/read-audience.md) 區段。

## 將資料分段 {#segmenting-data}

Adobe Campaign可讓您處理傳入資料的集合。 因此，您可以合併多個母體、排除部分母體，或僅保留多個目標通用的資料。

* 利用 **[!UICONTROL Union]** 活动，可将多个活动的结果重组为单个目标。請參閱 [聯集](../../automating/using/union.md) 區段。
* 利用 **[!UICONTROL Intersection]** 活动，可仅在活动中保留不同集客群体的共有元素。請參閱 [交集](../../automating/using/intersection.md) 區段。
* 利用 **[!UICONTROL Exclusion]** 活动，可根据特定条件从一个群体中排除某些元素。請參閱 [排除](../../automating/using/exclusion.md) 區段。
* 利用 **[!UICONTROL Segmentation]** 活动，可根据由之前放在工作流中的活动计算出的客户群体，创建一个或多个区段。在活动结束时，可以在单一过渡或多个不同过渡中处理这些区段。請參閱 [細分](../../automating/using/segmentation.md) 區段。

## 丰富数据 {#enriching-data}

已識別和收集的資料可以擴充、彙總和操作，以最佳化目標建構。 您可以透過包含未在資料超市中模型化的資料，來簡化和最佳化鎖定過程。

此 **[!UICONTROL Additional data]** 的標籤 **[!UICONTROL Query]** 和 **[!UICONTROL Incremental query]** 活動可讓您擴充查詢所定位的資料，並將此資料傳輸至下列工作流程活動，以便在其中使用。 其中，您可以添加：

* 简单数据
* 聚合
* 集合

**相关主题：**

* [使用案例：使用其他資料個人化電子郵件](../../automating/using/personalizing-email-with-additional-data.md)
