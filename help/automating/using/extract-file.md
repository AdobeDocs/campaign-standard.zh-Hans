---
title: 提取文件
description: “提取文件”活动允许您以外部文件的形式从Adobe Campaign中导出数据。
page-status-flag: never-activated
uuid: 631f0fbd-9e8d-4f77-a338-fcb7f4fc1774
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: a06509f9-4731-4187-b43d-3bfa361284d3
context-tags: fileExport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 15e5aebdd67e8f5ddee89506c0469a101d94d2e8
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 1%

---


# 提取文件{#extract-file}

## 说明 {#description}

![](assets/export.png)

活动 **[!UICONTROL Extract file]** 允许您以外部文件的形式从Adobe Campaign导出数据。

## 使用环境 {#context-of-use}

在配置活动时，定义数据的提取方式。

>[!CAUTION]
>
>活动 **[!UICONTROL Extract file]** 必须放在活动之后才能 **[!UICONTROL Query]** 使用。

**相关主题：**

* [用例： 在外部文件中导出用户档案](../../automating/using/exporting-profiles-in-file.md)

## Configuration {#configuration}

1. 将活动拖放 **[!UICONTROL Extract file]** 到工作流中。

   ![](assets/wkf_data_export1.png)

1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。
1. 输入输出文件 **的标签**。 文件的标签将自动完成，其创建日期和时间是唯一的。 例如： 收件人20150815_081532.txt文件，2015年8月15日08:15:32生成。

   >[!NOTE]
   >
   >可以使用此字段 **[!UICONTROL formatDate]** 中的函数指定文件名。

1. 如果需要，可以通过在字段中选择来压缩输 **[!UICONTROL Compression]** 出文 **[!UICONTROL Add a pre-processing step]** 件。 输出文件将压缩为GZIP文件(.gz)。

   该字 **[!UICONTROL Add a pre-processing step]** 段还允许您在解压文件之前对其进行加密。 有关如何处理加密文件的详细信息，请参 [阅本节](../../automating/using/managing-encrypted-data.md)

1. 单击或 ![](assets/add_darkgrey-24px.png) 按 **[!UICONTROL Add an element]** 钮以添加输出列。

   ![](assets/wkf_data_export2.png)

   将打开一个新窗口。

   ![](assets/wkf_data_export3.png)

1. 输入表达式。 为此，您可以选择现有表达式或使用编辑器创建新 **表达式**。
1. 确认您的表达式。

   表达式将添加到输出列。

1. 创建所需数量的列。 可以通过单击列的表达式和标签来编辑列。

   如果要导出用户档案并希望在外部工具中使用它们，请确保导出唯一标识符。 默认情况下，并非所有用户档案都具有唯一标识符，具体取决于它们添加到数据库的方式。 有关详细信息，请参 [阅为用户档案生成唯一ID](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources) 。

1. 单击选 **[!UICONTROL File structure]** 项卡，为要导出的文件配置输出、日期和编号格式。

   如果导 **[!UICONTROL Export labels instead of internal values of enumerations]** 出明细列表值，请选中此选项。 此选项允许检索易于理解的较短标签（而非ID）。

1. 在选项 **[!UICONTROL Properties]** 卡中，选择选 **[!UICONTROL Do not generate a file if the inbound transition is empty]** 项，以避免在入站过渡为空时在SFTP服务器上创建和上传空文件。
1. 确认活动的配置并保存工作流。
