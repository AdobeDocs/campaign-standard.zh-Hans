---
title: 加载文件
description: “加载文件”活动允许您将数据导入一个结构化表单，以便在Adobe Campaign中使用此数据。
page-status-flag: never-activated
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9a4c2219d5f8b312deb476d852cf5db9cd19afcb
workflow-type: tm+mt
source-wordcount: '1364'
ht-degree: 0%

---


# 加载文件 {#load-file}

## 说明 {#description}

>[!CAUTION]
>
>使用此功能时，请记住SFTP存储、数据库存储和有效用户档案限制，这些限制均符合AdobeCampaign合同的规定。

![](assets/data_loading.png)

活动 **[!UICONTROL Load file]** 允许您以一种结构化形式导入数据，以在Adobe Campaign中使用此数据。 数据被临时导入，需要另一个活动将其完全集成到Adobe Campaign数据库中。

## 使用环境 {#context-of-use}

在配置活动时，定义数据的提取方式。 例如，要加载的文件可以是联系人的列表。

>[!CAUTION]
>
>只考虑&quot;平面&quot;结构文件，如。txt、.csv等文件。

您可以：

* 使用文件结构将其应用到其他文件的数据(使用活动恢 **[!UICONTROL Transfer file]** 复),
* 使用文件中的结构和数据将其导入Adobe Campaign。

**相关主题：**

* [用例： 使用外部数据更新数据库](../../automating/using/update-database-file.md)
* [用例： 根据自动文件下载更新数据](../../automating/using/update-data-automatic-download.md)
* [用例： 发送包含丰富字段的电子邮件](../../automating/using/sending-email-enriched-fields.md)
* [用例： 协调文件受众与数据库](../../automating/using/reconcile-file-audience-with-database.md)

## Configuration {#configuration}

活动配置涉及两个步骤。 首先，您需要通过上传示例文件来定义预期的文件结构。 完成此操作后，您可以指定要导入其数据的文件的来源。

>[!NOTE]
>
>示例文件的活动用于配置该数据，但不导入。 我们建议使用包含少量数据的示例文件。

1. 将活动拖放 **[!UICONTROL Load file]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。
1. 上传示例文件，该示例文件将允许您在导入最终文件时定义预期结构。

   ![](assets/wkf_file_loading.png)

   上传数据文件后，活动中会显示两个新选项卡： **[!UICONTROL File structure]** 和 **[!UICONTROL Column definition]**。

1. 转到选 **[!UICONTROL File structure]** 项卡以视图从示例文件自动检测到的结构。

   如果错误检测到文件结构，您有几个选项可以纠正任何可能的错误：

   * 您可以通过选择选项来选择使用另一个文件的 **[!UICONTROL Detect structure from a new file]** 结构。
   * 您可以修改默认检测参数，使其适应您的文件。 该 **[!UICONTROL File type]** 字段允许您指定要导入的文件是否由具有固定长度的列组成。 在这种情况下，您还必须在选项卡中为每列指定最大字符 **[!UICONTROL Column definition]** 数。

      正确从文件恢复数据所需的所有检测选项都重新分组在中 **[!UICONTROL File format]**。 您可以修改它们，然后考虑这些新设置，重新检测活动中加载的最后一个文件的结构。 为此，请使用按 **[!UICONTROL Apply configuration]** 钮。 例如，可指定不同的列分隔符。

      >[!NOTE]
      >
      >此操作将考虑活动中加载的最后一个文件。 如果检测到的文件很大，预览将仅显示前30行。

      ![](assets/wkf_file_loading3.png)

      在部 **[!UICONTROL File format]** 分中，选 **[!UICONTROL Check columns from file against column definitions]** 项允许您验证要上传的文件的列是否与列定义相对应。

      如果列数和／或列名与列定义不匹配，则在执行工作流时将显示错误消息。 如果未激活该选项，则日志文件中将显示警告。

      ![](assets/wkf_file_loading_check.png)

1. 转到选 **[!UICONTROL Column definition]** 项卡，检查每列的数据格式，并根据需要调整参数。

   该 **[!UICONTROL Column definition]** 选项卡允许您精确指定每列的Adobe Campaign结构，以便导入不包含任何错误的数据（例如，使用空值管理），并使其与数据库中已存在的类型匹配，以便将来进行操作。

   例如，您可以更改列的标签，选择其类型（字符串、整数、日期等） 甚至指定错误处理。

   有关详细信息，请参阅列 [格式部分](#column-format) 。

   ![](assets/wkf_file_loading4.png)

1. 在选项卡 **[!UICONTROL Execution]** 中，指定是否要处理文件以加载数据：

   * 来自工作流中的入站过渡。
   * 是在上一步中上传的。
   * 是要从本地计算机上传的新文件。 如果 **[!UICONTROL Upload a new file from local machine]** 上传工作流中已定义第一个文件，则会显示该选项。 这允许您上传另一个文件，如果当前文件不适合您的需要，则可以对其进行处理。

      ![](assets/wkf_file_loading1.png)

1. 如果要从中加载数据的文件已压缩为GZIP文件(.gz)，请在字 **[!UICONTROL Decompression]** 段中选择 **[!UICONTROL Add a pre-processing step]** 选项。 这允许您在加载数据之前解压缩文件。 仅当文件来自活动的入站过渡时，此选项才可用。

   该字 **[!UICONTROL Add a pre-processing step]** 段还允许您在将文件导入数据库之前对其进行解密。 有关如何处理加密文件的详细信息，请参 [阅本节](../../automating/using/managing-encrypted-data.md)

1. 该 **[!UICONTROL Keep the rejects in a file]** 选项允许您下载包含导入过程中发生的错误的文件，并将其应用到后处理阶段。 激活该选项后，出站过渡将重命名为“拒绝”。

   >[!NOTE]
   >
   >通过 **[!UICONTROL Add date and time to the file name]** 此选项，可以在包含拒绝项的文件名称中添加时间戳。

   ![](assets/wkf_file_loading_keeprejects.png)

1. 确认活动的配置并保存工作流。

如果执行工作流后活动出现任何错误，请参阅日志以获取有关文件中不正确的值的更多详细信息。 For more on workflows logs, refer to [this section](../../automating/using/monitoring-workflow-execution.md).

## 列格式 {#column-format}

加载示例文件时，将自动检测列格式以及每种数据类型的默认参数。 您可以修改这些默认参数，以指定要应用于数据的特定进程，尤其是当存在错误或空值时。

为此，请 **[!UICONTROL Edit properties]** 从要定义其格式的列的快速操作中进行选择。 将打开列格式详细信息窗口。

![](assets/wkf_file_loading4.png)

然后，您可以修改每列的格式。

列格式允许您定义每列的值处理：

* **[!UICONTROL Ignore column]**: 在数据加载过程中不处理此列。
* **[!UICONTROL Data type]**: 指定每列所需的数据类型。
* **[!UICONTROL Format and separators]**，属 **性**: 指定文本的属性、时间、日期和数值格式以及列上下文指定的分隔符。

   * **[!UICONTROL Maximum number of characters]**: 指定字符串类型列的最大字符数。

      加载由具有固定长度的列组成的文件时，必须填写此字段。

   * **[!UICONTROL Letter case management]**: 定义是否需要对文本数据应用字符大小写 **过程** 。
   * **[!UICONTROL White space management]**: 指定Text数据的字符串中是否需要忽略某些 **空** 格。
   * **[!UICONTROL Time format]**, **[!UICONTROL Date format]**: 指定日期、时 **间**、日 **期****** 和时间数据的格式。
   * **[!UICONTROL Format]**: 允许您定义整数和浮动数数 **据****的数值格式** 。
   * **[!UICONTROL Separator]**: 定义由列上下文指定的分隔符（数值的千位分隔符或小数分隔符，日期和时间的分隔符） **为日期**、时间 ****、 **日期和时间**、整 ******** 数、和数据。

* **[!UICONTROL Remapping of values]**: 此字段仅在列详细信息配置中可用。 它允许您在导入某些值时转换它们。 例如，您可以将“three”转换为“3”。
* **[!UICONTROL Error processing]**: 定义遇到错误时的行为。

   * **[!UICONTROL Ignore the value]**: 将忽略该值。 工作流执行日志中会生成警告。
   * **[!UICONTROL Reject the line]**: 不处理整行。
   * **[!UICONTROL Use a default value]**: 将导致错误的值替换为在字段中定义的默认值 **[!UICONTROL Default value]** 。
   * **[!UICONTROL Use a default value in case the value is not remapped]**: 将导致错误的值替换为默认值(在字段中定 **[!UICONTROL Default value]** 义)，除非为错误值定义了映射(请参阅 **[!UICONTROL Remapping of values]** 上面的选项)。
   * **[!UICONTROL Reject the line when there is no remapping value]**: 除非为错误值定义了映射，否则不会处理整行(请参 **[!UICONTROL Remapping of values]** 阅上面的选项)。

   >[!NOTE]
   >
   >**[!UICONTROL Error processing]** 有关导入文件中值的错误。 例如，遇到错误的数据类型（“4”,“整数”列全部用字母表示）、包含多于授权最大数字的字符串、具有错误分隔符的日期等。 但是，此选项不涉及由空值管理生成的错误。

* **[!UICONTROL Default value]**: 根据所选的错误处理指定默认值。
* **[!UICONTROL Empty value management]**: 指定如何在数据加载期间管理空值。

   * **[!UICONTROL Generate an error for numerical fields]**: 仅为数字字段生成错误，否则插入NULL值。
   * **[!UICONTROL Insert NULL in the corresponding field]**: 授权空值。 因此插入值NULL。
   * **[!UICONTROL Generate an error]**: 如果值为空，则生成错误。
