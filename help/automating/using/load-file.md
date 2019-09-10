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
source-git-commit: fc3c687328c5a460b442b8b2497965ccab3be50b

---


# 加载文件{#load-file}

## 描述 {#description}

![](assets/data_loading.png)

**[!UICONTROL Load file]** 活动允许您在一个结构化表单中导入数据，以便在Adobe Campaign中使用此数据。数据将临时导入，而必须另外一个活动才能将其集成到Adobe Campaign数据库中。

## 使用情境 {#context-of-use}

将在配置活动时定义数据的提取方式。例如，要加载的文件可能是联系人列表。

>[!CAUTION]
>
>只考虑“平面”结构文件，例如.txt、. csv等文件。

您可以：

* 使用文件结构将其应用于其他文件的数据(使用 **[!UICONTROL Transfer file]** 活动恢复)或
* 使用文件中的结构和数据将其导入Adobe Campaign。

## 配置 {#configuration}

活动配置涉及两个步骤。首先，您需要通过上传示例文件来定义预期的文件结构。完成此操作后，您可以指定要导入数据的文件源。

>[!NOTE]
>
>示例文件的数据用于配置活动，但未被导入。我们建议使用一个包含少量数据的示例文件。

1. 将 **[!UICONTROL Load file]** 活动拖放到工作流程中。
1. 选择活动，然后使用出现的快速操作中 ![](assets/edit_darkgrey-24px.png) 的按钮打开该活动。
1. 上传将允许您在导入最终文件时定义预期结构的示例文件。

   ![](assets/wkf_file_loading.png)

   上传数据文件后，活动中会出现两个新选项卡： **[!UICONTROL File structure]****[!UICONTROL Column definition]**&#x200B;和.

1. 转到 **[!UICONTROL File structure]** 选项卡以查看从示例文件自动检测到的结构。

   如果检测到文件结构错误，您可以使用若干选项纠正任何可能的错误：

   * 选择该 **[!UICONTROL Detect structure from a new file]** 选项可选择使用其他文件的结构。
   * 您可以修改默认检测参数以将其改编为文件。**[!UICONTROL File type]** 该字段允许您指定要导入的文件是否由固定长度的列组成。在这种情况下，您还必须指定 **[!UICONTROL Column definition]** 选项卡中每个列的最大字符数。

      正确恢复文件中的数据所需的所有检测选项都重新加载 **[!UICONTROL File format]**。然后，您可以通过考虑这些新设置来修改活动中加载的最后一个文件的结构。为此，请使用 **[!UICONTROL Apply configuration]** 按钮。例如，您可以指定不同的列分隔符。

      >[!NOTE]
      >
      >此操作考虑在活动中加载的最后一个文件。如果检测到的文件较大，数据预览将仅显示前30行。

      ![](assets/wkf_file_loading3.png)

      **[!UICONTROL File format]** 在该部分中，可 **[!UICONTROL Check columns from file against column definitions]** 通过该选项验证上传的文件的列是否对应列定义。

      如果列数和/或列名称与列定义不匹配，则在执行工作流时将显示错误消息。如果未激活该选项，则会在日志文件中显示警告。

      ![](assets/wkf_file_loading_check.png)

1. 转到 **[!UICONTROL Column definition]** 选项卡以检查每个列的数据格式，并根据需要调整参数。

   **[!UICONTROL Column definition]** 此选项卡允许您精确指定每个列的数据结构，以导入不包含任何错误的数据(例如，使用null管理)并使它与Adobe Campaign数据库中已有的类型匹配以将来操作。

   例如，您可以更改列的标签，选择它的类型(字符串、整数、日期等)。甚至指定错误处理。

   有关详细信息，请参阅 [列格式](../../automating/using/load-file.md#column-format) 部分。

   ![](assets/wkf_file_loading4.png)

1. 在 **[!UICONTROL Execution]** 选项卡中，指定是否要对文件进行处理以加载数据：

   * 来自工作流中的入站过渡。
   * 是您在上一步上传的。
   * 是要从本地机器上传的新文件。如果在工作流中已定义第一个文件，则显示该 **[!UICONTROL Upload a new file from local machine]** 选项。这允许您上传要处理的其他文件，如果当前文件不符合您的需求。

      ![](assets/wkf_file_loading1.png)

1. 如果您希望将数据加载到GZIP文件(.gz)中，请在字段中选择该 **[!UICONTROL Decompression]** 选项 **[!UICONTROL Add a pre-processing step]** 。这允许您在加载数据之前解压缩文件。仅当文件来自活动的入站过渡时，此选项才可用。
1. 该 **[!UICONTROL Keep the rejects in a file]** 选项允许您下载包含在导入过程中发生的错误并将其应用于后处理舞台的文件。

   >[!NOTE]
   >
   >通过 **[!UICONTROL Add date and time to the file name]** 该选项，您可以添加包含拒绝的文件名称的时间戳。

   ![](assets/wkf_file_loading_keeprejects.png)

1. 确认活动的配置并保存工作流。

## 列格式 {#column-format}

加载示例文件时，会自动检测每个数据类型的默认参数的列格式。您可以修改这些默认参数，以指定要应用于数据的特定进程，尤其是当出现错误或空值时。

为此，请选择 **[!UICONTROL Edit properties]** 要定义其格式的列的快速操作。此时将打开列格式详细信息窗口。

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

## 示例1：更新数据库 {#example-1-update-the-database}

负载文件活动主要是从传输文件活动中结构数据，以便将其集成到现有数据中。

以下示例显示了自动下载的文件活动通过传输文件活动的结果，后跟更新数据活动。此工作流旨在使用新配置文件丰富Adobe Campaign数据库，或使用从导入的文件检索的数据更新现有配置文件。

![](assets/load_file_workflow_ex1.png)

1. 将 **[!UICONTROL Transfer file]** 某个活动拖放到工作流中并以某种方式对其进行配置，以便它与您需要的文件重叠。
1. 将 **[!UICONTROL Load file]** 活动拖放到工作流中，然后将其放置在 **[!UICONTROL Transfer file]** 活动之后。
1. 选择活动，然后使用出现的快速操作中 ![](assets/edit_darkgrey-24px.png) 的按钮打开该活动。
1. 在选项卡 **[!UICONTROL File to load]** 的部分 **[!UICONTROL Execution]** ，选中 **[!UICONTROL Use the file specified in the inbound transition]** 选项。

   ![](assets/wkf_file_loading8.png)

1. 按照之前指定的方式配置活动。
1. 将 **[!UICONTROL Update data]** 活动拖放到工作流中并将其放置在 **[!UICONTROL Load file]** 活动之后，然后进行配置。请参阅 [更新数据](../../automating/using/update-data.md)。

工作流启动后，将提取上传文件中的数据，然后用于丰富Adobe Campaign数据库。

## 示例2：发送包含丰富字段的电子邮件 {#example-2-email-with-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](../../automating/using/load-file.md#example-2-email-with-enriched-fields)-->

加载文件活动还允许在同一工作流程中使用外部文件中的额外数据发送电子邮件。

以下示例显示了如何通过加载文件活动从外部文件检索从外部文件检索的其他数据。在此示例中，外部文件包含配置文件列表及其关联的帐户编号。您需要导入此数据，以向每个配置文件发送一封电子邮件，并使用其帐号。

![](assets/load_file_workflow_ex2.png)

1. 将 **[!UICONTROL Query]** 某个活动拖放到工作流中，然后打开它以定义主目标。

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. 拖放 **[!UICONTROL Load file]** 活动，为配置文件分配一些数据。在此示例中，加载一个文件，其中包含与数据库的某些配置文件对应的帐号。

   ![](assets/load_file_activity.png)

1. 将 **[!UICONTROL Enrichment]** 活动拖放到工作流中，并将文件和查询活动链接到该工作流。

1. 在丰富化活动 **[!UICONTROL Advanced relations]** 的选项卡中，选择 **[!UICONTROL 0 or 1 cardinality simple link]** 并定义要用于进行排序的字段。在这里，我们使用姓氏将数据与数据库配置文件协调。

   ![](assets/load_file_enrichment_relation.png)

1. 在 **[!UICONTROL Additional data]** 选项卡中，选择要在电子邮件中使用的元素。此处选择帐户编号(通过加载文件活动检索的文件中的列)。

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   有关此功能的详细信息，请参阅 [“丰富化](../../automating/using/enrichment.md) ”部分。

1. 将 **[!UICONTROL Segmentation]** 活动拖放到工作流中，打开它以优化主目标。

   ![](assets/load_file_segmentation.png)

   有关此问题的详细信息，请参阅 [分段](../../automating/using/segmentation.md) 部分。

1. 将 **[!UICONTROL Email delivery]** 活动拖放到工作流中并将其打开。

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. 添加个性化字段，并从 **[!UICONTROL Additional data (targetData)]** 节点中选择丰富活动(此帐户编号)中定义的其他数据。这允许动态检索电子邮件内容中每个配置文件的帐号。

   ![](assets/load_file_perso_field.png)

1. 保存电子邮件并启动工作流。

电子邮件将发送到目标。每个配置文件都会收到包含相应帐户编号的电子邮件。

![](assets/load_file_email.png)
