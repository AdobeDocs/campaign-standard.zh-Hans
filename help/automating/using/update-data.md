---
title: 更新数据
description: “更新数据”活动允许您对数据库中的字段执行成批更新。
page-status-flag: never-activated
uuid: 1dc55db5-affd-4688-b673-adfb8c1338b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 4db83c95-4b75-4a16-8dbf-bd8940431fa9
context-tags: writer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 1%

---


# 更新数据{#update-data}

## 说明 {#description}

![](assets/data_update.png)

该 **[!UICONTROL Update data]** 活动允许您对数据库中的字段执行成批更新。

## 使用环境 {#context-of-use}

在导 **入文件** 后，可以使用更新活动，以便将恢复的数据插入Adobe Campaign数据库。 通过几个选项，您可以个性化更新数据。

**相关主题：**

* [用例： 更新基于文件的数据](../../automating/using/update-database-file.md)
* [根据自动文件下载更新数据](../../automating/using/update-data-automatic-download.md)

## Configuration {#configuration}

1. 将活动拖放 **[!UICONTROL Update data]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。
1. 指定 **[!UICONTROL Operation type]** 要执行的内容：

   * **[!UICONTROL Insert or update]**: 插入数据或更新数据（如果数据库中已存在记录）。
   * **[!UICONTROL Insert only]**: 仅插入数据。 已存在的记录不会更新。 如果定义了对帐标准，则只会添加未对帐记录。

      如果导 **[!UICONTROL Generate an outbound transition for rejects]** 入的数据包含数据库中已存在的某些记录，请选中此框以避免出现任何可能的错误。

   * **[!UICONTROL Update]**: 只更新数据库中已存在的记录的数据。
   * **[!UICONTROL Delete]**: 删除数据。
   >[!NOTE]
   >
   >该 **[!UICONTROL Batch size]** 字段允许您为要上传的数据定义最大批大小。

1. 在选项卡 **[!UICONTROL Identification]** 中，指定如何标识数据库中的记录：

   * **[!UICONTROL Using the targeting dimension]**: 选择 **[!UICONTROL Dimension to update]** ，然后指定 **[!UICONTROL Keys for finding records]**。 有关详细信息，请参 [阅定位维度和资源](../../automating/using/query.md#targeting-dimensions-and-resources)。
   * 如果输入的数据与现有定位维度匹配，请选择 **[!UICONTROL Using one or more links]** 选项。 然后选择 **[!UICONTROL Dimension to update]**。
   如果所选操作类型需要更新，则必须使用合并关键项。

1. 在选 **[!UICONTROL Fields to update]** 项卡中，指定将应用更新的字段，并根据需要添加条件以执行此更新。 为此，请使用 **[!UICONTROL Taken into account if]** 列。 按列表顺序依次应用条件。 使用右侧的箭头更改更新的顺序。 您可以多次使用同一目标字段。

   您可以使用按钮自动链接 ![](assets/wkf_magic_wand-24px.png) 字段。 自动链接会检测名称相同的字段。

   在类型操 **[!UICONTROL Insert or update]** 作过程中，您可以单独选择要应用于每个字段的操作。 为此，请在列中选择所需的 **[!UICONTROL Operation]** 值。

   >[!NOTE]
   >
   >**管理更新** 运行更 **[!UICONTROL lastModified]**&#x200B;新数据 **[!UICONTROL modifiedBy]**&#x200B;活动时，将自动更新、 **[!UICONTROL created]****[!UICONTROL createdBy]** 和字段，除非在字段更新表中明确执行了它们的配置。 只对已检测到至少一个差的记录执行更新。 如果值相同，则不执行更新。

1. 如果需要，可以管理活动 [的过渡](../../automating/using/activity-properties.md) ，以访问出站人口的高级选项。

   如果已选择并 **[!UICONTROL Insert only]** 且导入的数据可能包含数据库中已存在的记录，请选中该框以 **[!UICONTROL Generate an outbound transition for the rejects]** 避免出现任何可能的错误。

1. 确认活动的配置并保存工作流。
