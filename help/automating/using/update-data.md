---
title: 更新数据
description: 利用更新数据活动，可对数据库中的字段执行批量更新。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: writer,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d362563f-5ab3-4f7f-ae9f-a42b6f0bb2b9
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 97%

---

# 更新数据{#update-data}

## 说明 {#description}

![](assets/data_update.png)

利用 **[!UICONTROL Update data]** 活动，可对数据库中的字段执行批量更新。

## 使用环境 {#context-of-use}

在导入文件后，可以使用&#x200B;**更新数据**&#x200B;活动，以便将取回的数据插入 Adobe Campaign 数据库。您可以利用多个选项，以个性化方式更新数据。

**相关主题：**

* [用例：根据文件更新数据](../../automating/using/update-database-file.md)
* [根据自动文件下载更新数据](../../automating/using/update-data-automatic-download.md)

## 配置 {#configuration}

1. 将 **[!UICONTROL Update data]** 活动拖放到工作流中。
1. 选择活动，然后使用所显示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。
1. 指定执行的 **[!UICONTROL Operation type]**：

   * **[!UICONTROL Insert or update]**：插入数据或更新数据（如果数据库中已存在记录）。
   * **[!UICONTROL Insert only]**：仅插入数据。已存在的记录不会更新。如果定义了协调条件，则只会添加未协调的记录。

     如果导入的数据包含数据库中已存在的某些记录，请勾选 **[!UICONTROL Generate an outbound transition for rejects]** 方框以避免发生任何可能的错误。

   * **[!UICONTROL Update]**：只更新数据库中已存在之记录的数据。
   * **[!UICONTROL Delete]**：删除数据。

   >[!NOTE]
   >
   >利用 **[!UICONTROL Batch size]** 字段，可定义上传数据的批次大小上限。

1. 在 **[!UICONTROL Identification]** 选项卡中，指定如何识别数据库中的记录：

   * **[!UICONTROL Using the targeting dimension]**：选择 **[!UICONTROL Dimension to update]**，然后指定 **[!UICONTROL Keys for finding records]**。有关更多信息，请参阅[定向维度和资源](../../automating/using/query.md#targeting-dimensions-and-resources)。
   * 如果输入的数据与现有定向维度匹配，请选择 **[!UICONTROL Using one or more links]** 选项。然后选择 **[!UICONTROL Dimension to update]**。

   如果所选操作类型需要更新，则必须使用协调键。

1. 在 **[!UICONTROL Fields to update]** 选项卡中，指定要应用更新的字段，并根据需要添加条件以执行此更新。要实现此目的，请使用 **[!UICONTROL Taken into account if]** 列。按列表顺序依次应用条件。使用右侧的箭头可更改更新的顺序。您可以多次使用同一目标字段。

   您可以使用 ![](assets/wkf_magic_wand-24px.png) 按钮自动链接字段。自动链接会检测具有相同名称的字段。

   在 **[!UICONTROL Insert or update]** 类型操作期间，您可以单独选择要应用于每个字段的操作。要实现此目的，请在 **[!UICONTROL Operation]** 列中选择所需的值。

   >[!NOTE]
   >
   >**管理更新** 运行更新数据活动时，将自动更新&#x200B;**[!UICONTROL lastModified]**、**[!UICONTROL modifiedBy]**、**[!UICONTROL created]** 和 **[!UICONTROL createdBy]** 字段，除非在字段更新表中明确执行了其配置。只对检测到了至少一个差异的记录执行更新。如果值相同，则不执行更新。

1. 如果需要，可以管理活动的[过渡](../../automating/using/activity-properties.md)，以访问叫客群体的高级选项。

   如果已选择 **[!UICONTROL Insert only]** 并且导入的数据可能包含数据库中已存在的记录，请勾选 **[!UICONTROL Generate an outbound transition for the rejects]** 方框以避免发生任何可能的错误。

1. 确认活动的配置并保存工作流。
