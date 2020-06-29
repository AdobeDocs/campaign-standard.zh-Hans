---
title: 扩充
description: 扩充活动是一种高级活动，允许您定义要在工作流中处理的其他数据。
page-status-flag: never-activated
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: enrichment,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---


# 扩充{#enrichment}

## 说明 {#description}

![](assets/enrichment.png)

该活动 **[!UICONTROL Enrichment]** 是一个高级活动，允许您定义要在工作流中处理的其他数据。

## 使用环境 {#context-of-use}

该活动 **[!UICONTROL Enrichment]** 通常在目标活动或导入文件之后以及允许使用目标数据的活动之前使用。

此活动包含比活动更高级的扩充 **[!UICONTROL Query]** 函数。 在扩充活动中可以直接执行一些简单 [的查询](../../automating/using/query.md#enriching-data)。

通过该 **[!UICONTROL Enrichment]** 活动，您可以利用入站过渡并配置活动以使用其他数据完成输出过渡。 它允许合并来自多个集的数据，或创建指向临时资源的链接。

**相关主题**

* [用例： 用文件中包含的用户档案丰富数据](../../automating/using/enriching-profile-data-file.md)。
* [用例： 发送包含丰富字段的电子邮件](../../automating/using/sending-email-enriched-fields.md)

## Configuration {#configuration}

配置 **[!UICONTROL Enrichment]** 活动:

1. 将活动拖放 **[!UICONTROL Enrichment]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。
1. 如果活动有多个入站过渡，请选择 **[!UICONTROL Primary set]**。 此活动中配置的其他数据将添加到出站过渡中的此主数据集。

   如果主集已包含其他数据，则可以选择保留或删除这些数据。 如果取消选 **[!UICONTROL Keep all additional data from the main set]** 中此选项，则只有在中配置的其 **[!UICONTROL Enrichment]** 他数据保留在出站过渡中。

1. 如果有多个入站过渡，则在活动的选项卡中定义主集与其他入站数据 **[!UICONTROL Advanced Relations]** 之间的关系。 您可以使用按钮添加多个 **[!UICONTROL Add element]** 关系。

   定义新关系时，选择要链接到主集的入站数据集。 然后定义关系类型。 根据入站数据和您的数据模型，可以使用几种类型的关系：

   * **[!UICONTROL 1 cardinality simple link]**: 输入数据的每个记录与主集合中的一个和仅一个记录相关联。 来自主集合的每个记录在链接数据中有一个关联记录。
   * **[!UICONTROL N cardinality collection link]**: 链接数据中的0、1个或多个(N)记录可以关联到主集的1个记录。
   * **[!UICONTROL 0 or 1 cardinality simple link]**: 来自主集的记录可以与来自链接数据的0或1个记录关联，但不能与多个记录关联。
   定义 **[!UICONTROL Cardinality]** 后，定义 **[!UICONTROL Reconciliation criteria]**。 对 **[!UICONTROL Source expression]** 帐标准可以是目标资源中的字段、 [表达式](../../automating/using/advanced-expression-editing.md) ，也可以直接是引号之间指定的值。

   定义一 **[!UICONTROL Label]** 个和 **[!UICONTROL ID]** 一个在以后的工作流中易于识别的。

   >[!NOTE]
   >
   >您只能定义主集与连接到该过渡的其他入站活动之间的 **[!UICONTROL Enrichment]** 关系。 对于旨在定义与数据库资源的关系的简单案例，请使用 [协调](../../automating/using/reconciliation.md) 活动。

1. 从活动的选项卡 **[!UICONTROL Additional data]** 中定义其他数据。 您可以定义与主集的定位维度相关的其他数据(简单字段、聚合和集合)，也可以根据在活动的选项卡中创建 **[!UICONTROL Advanced relations]** 的链接来定 **[!UICONTROL Enrichment]** 义。

   请参阅 [丰富数据](../../automating/using/query.md#enriching-data) 部分。

1. 确认活动的配置并保存工作流。

数据现在可用于在连接后连接的活动 **[!UICONTROL Enrichment]**。 例如，您可以在电子邮件内容中 **[!UICONTROL Additional data (targetData)]** 的个性化字段资源管理器链接下找到它。
