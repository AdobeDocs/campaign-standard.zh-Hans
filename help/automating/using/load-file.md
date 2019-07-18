---
title: 加载文件
seo-title: 加载文件
description: 加载文件
seo-description: 加载文件活动允许您在一个结构化表单中导入数据，以便在Adobe Campaign中使用此数据。
page-status-flag: 从未激活
uuid: 69af12cc-6f82-4977-9f53-aa7 bc26 f5 d7 e
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 数据管理活动
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: FileImport，main
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Load file{#load-file}

## Description {#description}

![](assets/data_loading.png)

**[!UICONTROL Load file]** 活动允许您在一个结构化表单中导入数据，以便在Adobe Campaign中使用此数据。数据将临时导入，而必须另外一个活动才能将其集成到Adobe Campaign数据库中。

## Context of use {#context-of-use}

将在配置活动时定义数据的提取方式。例如，要加载的文件可能是联系人列表。

>[!CAUTION]
>
>只考虑“平面”结构文件，例如.txt、. csv等文件。

您可以：

* Use the file structure to apply it to another file's data (recovered using the **[!UICONTROL Transfer file]** activity) or,
* 使用文件中的结构和数据将其导入Adobe Campaign。

## Configuration {#configuration}

活动配置涉及两个步骤。首先，您需要通过上传示例文件来定义预期的文件结构。完成此操作后，您可以指定要导入数据的文件源。

>[!NOTE]
>
>示例文件的数据用于配置活动，但未被导入。我们建议使用一个包含少量数据的示例文件。

1. Drag and drop a **[!UICONTROL Load file]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. 上传将允许您在导入最终文件时定义预期结构的示例文件。

   ![](assets/wkf_file_loading.png)

   Once the data file is uploaded, two new tabs appear in the activity: **[!UICONTROL File structure]** and **[!UICONTROL Column definition]**.

1. Go to the **[!UICONTROL File structure]** tab to view the structure that is automatically detected from the sample file.

   如果检测到文件结构错误，您可以使用若干选项纠正任何可能的错误：

   * You can choose to use the structure of another file by selecting the **[!UICONTROL Detect structure from a new file]** option.
   * 您可以修改默认检测参数以将其改编为文件。**[!UICONTROL File type]** 该字段允许您指定要导入的文件是否由固定长度的列组成。In that case, you must also specify the maximum number of characters for each column in the **[!UICONTROL Column definition]** tab.

      All of the detection options necessary to correctly recover the data from the file are regrouped in **[!UICONTROL File format]**. 然后，您可以通过考虑这些新设置来修改活动中加载的最后一个文件的结构。To do this, use the **[!UICONTROL Apply configuration]** button. 例如，您可以指定不同的列分隔符。

      >[!NOTE]
      >
      >此操作考虑在活动中加载的最后一个文件。如果检测到的文件较大，数据预览将仅显示前30行。

      ![](assets/wkf_file_loading3.png)

      **[!UICONTROL File format]** 在该部分中，可 **[!UICONTROL Check columns from file against column definitions]** 通过该选项验证上传的文件的列是否对应列定义。

      如果列数和/或列名称与列定义不匹配，则在执行工作流时将显示错误消息。如果未激活该选项，则会在日志文件中显示警告。

      ![](assets/wkf_file_loading_check.png)

1. Go to the **[!UICONTROL Column definition]** tab to check the data format for each column and adjust the parameters if necessary.

   **[!UICONTROL Column definition]** 此选项卡允许您精确指定每个列的数据结构，以导入不包含任何错误的数据(例如，使用null管理)并使它与Adobe Campaign数据库中已有的类型匹配以将来操作。

   例如，您可以更改列的标签，选择它的类型(字符串、整数、日期等)。甚至指定错误处理。

   For more information, refer to the [Column format](../../automating/using/load-file.md#column-format) section.

   ![](assets/wkf_file_loading4.png)

1. In the **[!UICONTROL Execution]** tab, specify whether the file is to be processed for loading data:

   * 来自工作流中的入站过渡。
   * 是您在上一步上传的。
   * 是要从本地机器上传的新文件。The **[!UICONTROL Upload a new file from local machine]** option appears if uploading a first file was already defined in the workflow. 这允许您上传要处理的其他文件，如果当前文件不符合您的需求。

      ![](assets/wkf_file_loading1.png)

1. If the file that you want to load the data from is compressed into a GZIP file (.gz), select the **[!UICONTROL Decompression]** option in the **[!UICONTROL Add a pre-processing step]** field. 这允许您在加载数据之前解压缩文件。仅当文件来自活动的入站过渡时，此选项才可用。
1. The **[!UICONTROL Keep the rejects in a file]** option enables you to download a file containing errors that occurred during the import, and to apply to it a post-processing stage.

   >[!NOTE]
   >
   >The **[!UICONTROL Add date and time to the file name]** option lets you add a timestamp the name of the file containing the rejects.

   ![](assets/wkf_file_loading_keeprejects.png)

1. 确认活动的配置并保存工作流。

## Column format {#column-format}

加载示例文件时，会自动检测每个数据类型的默认参数的列格式。您可以修改这些默认参数，以指定要应用于数据的特定进程，尤其是当出现错误或空值时。

To do this, select **[!UICONTROL Edit properties]** from the quick actions of the column whose format you would like to define. 此时将打开列格式详细信息窗口。

![](assets/wkf_file_loading4.png)

然后，您可以修改每个列的格式。

列格式允许您定义每个列的值处理：

* **[!UICONTROL Ignore column]**：在数据加载过程中未处理此列。
* **[!UICONTROL Data type]**：指定每个列所需的数据类型。
* **[!UICONTROL Format and separators]****属性**：指定文本的属性、时间、日期和数值格式以及列上下文指定的分隔符。

   * **[!UICONTROL Maximum number of characters]**：指定字符串类型列的最大字符数。

      加载由具有固定长度的列组成的文件时，必须填写此字段。

   * **[!UICONTROL Letter case management]**：定义是否需要对 **文本** 数据应用字符案例处理。
   * **[!UICONTROL White space management]**：指定是否需要在 **文本** 数据字符串中忽略某些空格。
   * **[!UICONTROL Time format]**&#x200B;指定 **日期[!UICONTROL Date format]、**&#x200B;时间&#x200B;**、**&#x200B;日期和时间&#x200B;**数据的格式。******
   * **[!UICONTROL Format]**：允许您定义 **整数** 和 **浮点数** 数据的数值格式。
   * **[!UICONTROL Separator]**：定义由列上下文指定的分隔符(数值分隔符或小数分隔分隔符，适用于日期和时间的分隔符) ****、 **时间**、 **日期和时间**、 **整数**&#x200B;和 **浮点数** 数据。

* **[!UICONTROL Remapping of values]**：此字段仅在列详细信息配置中可用。它允许您在导入某些值时转换这些值。例如，可以将“三个”转换为“3”。
* **[!UICONTROL Error processing]**：定义遇到错误时的行为。

   * **[!UICONTROL Ignore the value]**：将忽略该值。在工作流执行日志中会生成警告。
   * **[!UICONTROL Reject the line]**：整个行未处理。
   * **[!UICONTROL Use a default value]**：替换导致默认值(在 **[!UICONTROL Default value]** 字段中定义)的值。
   * **[!UICONTROL Use a default value in case the value is not remapped]**：替换导致在 **[!UICONTROL Default value]** 字段中定义的默认值的值，除非为错误的值定义了映射(请参阅上面的 **[!UICONTROL Remapping of values]** 选项)。
   * **[!UICONTROL Reject the line when there is no remapping value]**：除非为错误的值定义映射(请参阅上面的 **[!UICONTROL Remapping of values]** 选项)，否则不会处理整个行。
   >[!NOTE]
   >
   >**[!UICONTROL Error processing]** 担心导入文件中的值错误。例如，遇到的错误数据类型(“整数”列中的字母全部以字母形式显示)、字符串超过授权的最大字符数、具有错误分隔符的日期等。但是，此选项不涉及由空值管理生成的错误。

* **[!UICONTROL Default value]**：根据所选的错误处理指定默认值。
* **[!UICONTROL Empty value management]**：指定在数据加载过程中如何管理空值。

   * **[!UICONTROL Generate an error for numerical fields]**：仅为数字字段生成错误，否则插入NULL值。
   * **[!UICONTROL Insert NULL in the corresponding field]**：授权空值。因此插入值NULL。
   * **[!UICONTROL Generate an error]**：如果值为空，则生成错误。

## Example {#example}

负载文件活动主要是从传输文件活动中结构数据，以便将其集成到现有数据中。

以下示例显示了自动下载的文件活动通过传输文件活动的结果，后跟更新数据活动。此工作流旨在使用新配置文件丰富Adobe Campaign数据库，或使用从导入的文件检索的数据更新现有配置文件。

1. Drag and drop a **[!UICONTROL Transfer file]** activity into your workflow and configure it in a way so that it recovers the file you would like.
1. Drag and drop a **[!UICONTROL Load file]** activity into your workflow and place it after the **[!UICONTROL Transfer file]** activity.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. In the **[!UICONTROL File to load]** section of the **[!UICONTROL Execution]** tab, check the **[!UICONTROL Use the file specified in the inbound transition]** option.

   ![](assets/wkf_file_loading8.png)

1. 按照之前指定的方式配置活动。
1. Drag and drop an **[!UICONTROL Update data]** activity into your workflow and place it after the **[!UICONTROL Load file]** activity, then configure it. Refer to [Update data](../../automating/using/update-data.md).

工作流启动后，将提取上传文件中的数据，然后用于丰富Adobe Campaign数据库。
