---
title: 加载文件
description: “加载文件”活动允许您将数据导入一个结构化表单，以在Adobe Campaign中使用此数据。
page-status-flag: 从未激活
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 数据管理活动
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 加载文件{#load-file}

## 说明 {#description}

![](assets/data_loading.png)

该活 **[!UICONTROL Load file]** 动允许您将数据导入一个结构化表单，以在Adobe Campaign中使用此数据。 数据将临时导入，并且必须执行其他活动才能将其完全集成到Adobe Campaign数据库中。

## 使用环境 {#context-of-use}

在配置活动时，将定义提取数据的方式。 例如，要加载的文件可以是联系人列表。

>[!CAUTION]
>
>只考虑“平面”结构文件，例如。txt、.csv等文件。

您可以：

* 使用文件结构将其应用于其他文件的数据(使用活动恢复 **[!UICONTROL Transfer file]** 的)，或
* 使用文件中的结构和数据将其导入Adobe Campaign。

## 配置 {#configuration}

活动配置涉及两个步骤。 首先，您需要通过上传示例文件来定义期望的文件结构。 完成此操作后，您可以指定要导入其数据的文件的源。

>[!NOTE]
>
>示例文件的数据用于配置活动，但不会导入。 我们建议使用包含少量数据的示例文件。

1. 将活动拖放 **[!UICONTROL Load file]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。
1. 上传示例文件，该示例文件将允许您在导入最终文件时定义期望的结构。

   ![](assets/wkf_file_loading.png)

   上传数据文件后，活动中会显示两个新选项卡： **[!UICONTROL File structure]** 和 **[!UICONTROL Column definition]**。

1. 转到选项卡 **[!UICONTROL File structure]** 以查看从示例文件自动检测到的结构。

   如果错误地检测到文件结构，您有几个选项可以纠正任何可能的错误：

   * 通过选择选项，可以选择使用其他文件的结 **[!UICONTROL Detect structure from a new file]** 构。
   * 您可以修改默认检测参数，使其适应您的文件。 该 **[!UICONTROL File type]** 字段允许您指定要导入的文件是否由具有固定长度的列组成。 在这种情况下，您还必须在选项卡中指定每列的最大字符 **[!UICONTROL Column definition]** 数。

      正确从文件恢复数据所需的所有检测选项都重新分组在中 **[!UICONTROL File format]**。 您可以修改它们，然后考虑到这些新设置，重新检测活动中加载的最后一个文件的结构。 为此，请使用按 **[!UICONTROL Apply configuration]** 钮。 例如，可指定其他列分隔符。

      >[!NOTE]
      >
      >此操作会考虑到在活动中加载的最后一个文件。 如果检测到的文件很大，数据预览将仅显示前30行。

      ![](assets/wkf_file_loading3.png)

      在部 **[!UICONTROL File format]** 分中，选 **[!UICONTROL Check columns from file against column definitions]** 项允许您验证要上传的文件的列是否与列定义相对应。

      如果列数和／或名称与列定义不匹配，则执行工作流时将显示一条错误消息。 如果未激活该选项，则日志文件中将显示警告。

      ![](assets/wkf_file_loading_check.png)

1. 转到选项卡 **[!UICONTROL Column definition]** 以检查每列的数据格式，并根据需要调整参数。

   该选 **[!UICONTROL Column definition]** 项卡允许您精确指定每列的数据结构，以便导入不包含任何错误的数据（例如，使用空值管理），并使其与Adobe Campaign数据库中已存在的类型相匹配，以便将来执行操作。

   例如，您可以更改列的标签，选择其类型（字符串、整数、日期等） 甚至指定错误处理。

   有关详细信息，请参阅列 [格式部分](#column-format) 。

   ![](assets/wkf_file_loading4.png)

1. 在选项卡 **[!UICONTROL Execution]** 中，指定是否要处理文件以加载数据：

   * 来自工作流中的入站过渡。
   * 是在上一步中上传的。
   * 是要从本地计算机上传的新文件。 如果 **[!UICONTROL Upload a new file from local machine]** 上传工作流中已定义第一个文件，则会显示此选项。 这允许您上传另一个文件，以便在当前文件不符合您的需要时进行处理。

      ![](assets/wkf_file_loading1.png)

1. 如果要从中加载数据的文件已压缩到GZIP文件(.gz)中，请在字段中 **[!UICONTROL Decompression]** 选择相应的 **[!UICONTROL Add a pre-processing step]** 选项。 这允许您在加载数据之前解压缩文件。 仅当文件来自活动的入站过渡时，此选项才可用。
1. 通过 **[!UICONTROL Keep the rejects in a file]** 此选项，您可以下载包含导入过程中发生的错误的文件，并将后处理阶段应用到该文件。 激活此选项后，出站过渡将重命名为“拒绝”。

   >[!NOTE]
   >
   >通过 **[!UICONTROL Add date and time to the file name]** 此选项，可以向包含拒绝项的文件的名称添加时间戳。

   ![](assets/wkf_file_loading_keeprejects.png)

1. 确认活动的配置并保存工作流。

如果执行工作流后活动发生任何错误，请参阅日志以获取有关文件中不正确的值的更多详细信息。 For more on workflows logs, refer to [this section](../../automating/using/executing-a-workflow.md#monitoring)

## 列格式 {#column-format}

加载示例文件时，将自动检测列格式以及每种数据类型的默认参数。 您可以修改这些默认参数，以指定要应用于数据的特定进程，尤其是当存在错误或空值时。

为此，请从 **[!UICONTROL Edit properties]** 要定义其格式的列的快速操作中进行选择。 将打开列格式详细信息窗口。

![](assets/wkf_file_loading4.png)

然后，您可以修改每列的格式。

列格式允许您定义每列的值处理：

* **[!UICONTROL Ignore column]**:在数据加载过程中不处理此列。
* **[!UICONTROL Data type]**:指定每列所需的数据类型。
* **[!UICONTROL Format and separators]**，属 **性**:指定文本的属性、时间、日期和数值格式以及列上下文指定的分隔符。

   * **[!UICONTROL Maximum number of characters]**:指定字符串类型列的最大字符数。

      加载由具有固定长度的列组成的文件时，必须填写此字段。

   * **[!UICONTROL Letter case management]**:定义是否需要对文本数据应用字符大小写 **过程** 。
   * **[!UICONTROL White space management]**:指定是否需要在Text数据的字符串中忽略某些 **空格** 。
   * **[!UICONTROL Time format]**, **[!UICONTROL Date format]**:指定日期、时间 **和日期****** 、 **日期和时间数据的格式** 。
   * **[!UICONTROL Format]**:允许您为整数和浮动数数据定义数 **值****的格式** 。
   * **[!UICONTROL Separator]**:为 **Date**、 **Time**、 **Date time和time定义列上下文数据指定的分隔符（数字值的千位分隔符或小数分隔符，日期和时间的分隔符）、** DateTime、Date Time ******** 、IntegerTinger、TherFloating number定义了上下文数据。

* **[!UICONTROL Remapping of values]**:此字段仅在列详细信息配置中可用。 它允许您在导入某些值时对其进行转换。 例如，您可以将“three”转换为“3”。
* **[!UICONTROL Error processing]**:定义遇到错误时的行为。

   * **[!UICONTROL Ignore the value]**:将忽略该值。 工作流执行日志中会生成警告。
   * **[!UICONTROL Reject the line]**:不处理整行。
   * **[!UICONTROL Use a default value]**:将导致错误的值替换为在字段中定义的默认 **[!UICONTROL Default value]** 值。
   * **[!UICONTROL Use a default value in case the value is not remapped]**:将导致错误的值替换为默认值（在字段中定义）, **[!UICONTROL Default value]** 除非为错误值定义了映射(请参阅上 **[!UICONTROL Remapping of values]** 面的选项)。
   * **[!UICONTROL Reject the line when there is no remapping value]**:除非为错误值定义了映射，否则不会处理整行(请参阅上 **[!UICONTROL Remapping of values]** 面的选项)。
   >[!NOTE]
   >
   >**[!UICONTROL Error processing]** 有关导入文件中的值的错误。 例如，遇到错误的数据类型（“4”,“整数”列全是字母）、包含多于授权的最大数字的字符串、具有错误分隔符的日期等。 但是，此选项不涉及由空值管理生成的错误。

* **[!UICONTROL Default value]**:根据所选的错误处理指定默认值。
* **[!UICONTROL Empty value management]**:指定在数据加载期间如何管理空值。

   * **[!UICONTROL Generate an error for numerical fields]**:仅为数字字段生成错误，否则插入NULL值。
   * **[!UICONTROL Insert NULL in the corresponding field]**:授权空值。 因此插入值NULL。
   * **[!UICONTROL Generate an error]**:如果值为空，则生成错误。

## 示例1:更新数据库 {#example-1-update-the-database}

加载文件活动主要从传输文件活动中构造数据以便将其集成到现有数据中。

以下示例显示通过传输文件活动自动下载的加载文件活动的结果，后跟更新数据活动。 此工作流旨在使用新配置文件丰富Adobe Campaign数据库，或使用从导入的文件中恢复的数据更新现有配置文件。

![](assets/load_file_workflow_ex1.png)

1. 将活动拖放 **[!UICONTROL Transfer file]** 到您的工作流中并以某种方式对其进行配置，以便恢复您需要的文件。
1. 将活动拖放到 **[!UICONTROL Load file]** 您的工作流中，并将其放在活动之 **[!UICONTROL Transfer file]** 后。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。
1. 在选 **[!UICONTROL File to load]** 项卡的部 **[!UICONTROL Execution]** 分中，选中 **[!UICONTROL Use the file specified in the inbound transition]** 选项。

   ![](assets/wkf_file_loading8.png)

1. 按照之前指定的方式配置活动。
1. 将活动拖放到 **[!UICONTROL Update data]** 您的工作流中，并将其放在活动之 **[!UICONTROL Load file]** 后，然后进行配置。 请参阅 [更新数据](../../automating/using/update-data.md)。

工作流启动后，将提取上传文件中的数据，然后用于丰富Adobe Campaign数据库。

## 示例2:发送包含丰富字段的电子邮件 {#example-2-email-with-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

加载文件活动还允许在同一工作流程中从外部文件发送包含附加数据的电子邮件。

以下示例演示如何使用从外部文件检索到的其他数据通过加载文件活动发送电子邮件。 在此示例中，外部文件包含一个配置文件列表及其关联的帐号。 您希望导入此数据以向每个配置文件发送电子邮件，并提供其帐号。

![](assets/load_file_workflow_ex2.png)

1. 将活动拖放到 **[!UICONTROL Query]** 您的工作流中，然后打开它以定义主目标。

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. 拖放活动以 **[!UICONTROL Load file]** 将一些数据分配到配置文件。 在此示例中，加载一个文件，其中包含与数据库的某些配置文件相对应的帐号。

   ![](assets/load_file_activity.png)

1. 将活动拖放到您 **[!UICONTROL Enrichment]** 的工作流中，并将加载文件和查询活动链接到该工作流。

1. 在富集 **[!UICONTROL Advanced relations]** 活动的选项卡中，选择并定 **[!UICONTROL 0 or 1 cardinality simple link]** 义要用于调节的字段。 这里，我们使用姓氏将数据与数据库配置文件协调起来。

   ![](assets/load_file_enrichment_relation.png)

1. 在选 **[!UICONTROL Additional data]** 项卡中，选择要在电子邮件中使用的元素。 在此选择帐户号（从您通过加载文件活动检索到的文件中的列）。

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   有关此方面的详细信息，请参 [阅丰富](../../automating/using/enrichment.md) 一节。

1. 将活动拖放到 **[!UICONTROL Segmentation]** 您的工作流中，然后打开它以细化主目标。

   ![](assets/load_file_segmentation.png)

   有关此方面的详细信息，请参阅 [分段](../../automating/using/segmentation.md) 。

1. 将活动拖放到 **[!UICONTROL Email delivery]** 您的工作流中并打开它。

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. 添加个性化字段，然后从节点中选择丰富化活动（此处为帐户号）中定义的其他 **[!UICONTROL Additional data (targetData)]** 数据。 这使得能够动态检索电子邮件内容中每个配置文件的帐号。

   ![](assets/load_file_perso_field.png)

1. 保存电子邮件并启动工作流。

电子邮件会发送到目标。 每个配置文件都会收到电子邮件，其中包含相应的帐号。

![](assets/load_file_email.png)
