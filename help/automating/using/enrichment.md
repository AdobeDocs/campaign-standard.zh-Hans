---
title: 扩充
description: 扩充活动是一种高级活动，利用该活动可定义要在工作流中处理的附加数据。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: enrichment,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: c8af67b0-6789-4b4e-9d01-e2dfa14f1e8f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 95%

---

# 扩充{#enrichment}

## 说明 {#description}

![](assets/enrichment.png)

**[!UICONTROL Enrichment]** 活动是一种高级活动，利用该活动可定义要在工作流中处理的附加数据。

## 使用环境 {#context-of-use}

**[!UICONTROL Enrichment]** 活动通常用在定向活动或导入文件之后、以及允许使用定向数据的活动之前。

此活动包含比 **[!UICONTROL Query]** 活动更高级的扩充功能。在[查询](../../automating/using/query.md#enriching-data)活动中可以直接执行一些简单的扩充用例。

通过 **[!UICONTROL Enrichment]** 活动，您可以应用集客过渡并配置活动以使用附加数据填写输出过渡。该活动允许合并来自多个集的数据，或创建指向临时资源的链接。

**相关主题**

* [用例：使用文件](../../automating/using/enriching-profile-data-file.md)中包含的数据扩充配置文件数据。
* [用例：发送包含扩充字段的电子邮件](../../automating/using/sending-email-enriched-fields.md)

## 配置 {#configuration}

要配置 **[!UICONTROL Enrichment]** 活动，请执行以下步骤：

1. 将 **[!UICONTROL Enrichment]** 活动拖放到工作流中。
1. 选择活动，然后使用所显示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。
1. 如果活动包含多个集客过渡，请选择 **[!UICONTROL Primary set]**。此活动中配置的附加数据，将添加到叫客过渡中的此主集。

   如果主集已包含附加数据，则可以选择保留或删除这些数据。如果取消勾选 **[!UICONTROL Keep all additional data from the main set]** 选项，则只有在 **[!UICONTROL Enrichment]** 中配置的附加数据会保留在叫客过渡中。

1. 如果有多个集客过渡，则在活动的 **[!UICONTROL Advanced Relations]** 选项卡中定义主集与其他集客数据之间的关系。您可以使用 **[!UICONTROL Add element]** 按钮添加多个关系。

   定义新关系时，请选择想要链接到主集的集客数据集。然后定义关系的类型。根据集客数据和您的数据模型，可以使用的关系类型如下所示：

   * **[!UICONTROL 1 cardinality simple link]**：传入数据的每个记录都只与主集中的一个记录相关联。来自主集的每个记录，在已链接的数据中都有一个关联的记录。
   * **[!UICONTROL N cardinality collection link]**：可将来自链接数据中的 0、1 个或多个 (N) 记录关联到主集的 1 个记录。
   * **[!UICONTROL 0 or 1 cardinality simple link]**：可将来自主集的记录与来自链接数据的 0 或 1 个记录关联，但不能与多个记录关联。

   定义 **[!UICONTROL Cardinality]** 后，定义 **[!UICONTROL Reconciliation criteria]**。协调条件的 **[!UICONTROL Source expression]** 可以是目标资源中的字段、[表达式](../../automating/using/advanced-expression-editing.md)，也可以直接使用带引号的值。

   定义便于将来在工作流中识别的 **[!UICONTROL Label]** 和 **[!UICONTROL ID]**。

   >[!NOTE]
   >
   >您只能定义主集与连接 **[!UICONTROL Enrichment]** 活动之集客过渡之间的关系。对于旨在定义与数据库资源的关系的简单案例，请使用[协调](../../automating/using/reconciliation.md)活动。

1. 从活动的 **[!UICONTROL Additional data]** 选项卡中定义附加数据。您可以定义与主集的定向维度相关的附加数据（简单字段、聚合和集合），也可以根据在 **[!UICONTROL Enrichment]** 活动的 **[!UICONTROL Advanced relations]** 选项卡中创建的链接来定义附加数据。

   请参阅[扩充数据](../../automating/using/query.md#enriching-data)一节。

1. 确认活动的配置并保存工作流。

进行 **[!UICONTROL Enrichment]** 后，现在即可将数据用在连接的活动中。例如，您可以在电子邮件内容中的个性化字段探索工具的 **[!UICONTROL Additional data (targetData)]** 链接下找到它。
