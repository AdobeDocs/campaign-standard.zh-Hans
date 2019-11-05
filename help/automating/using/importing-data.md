---
title: 导入数据
description: 了解如何使用工作流导入数据。
page-status-flag: 从未激活
uuid: d909d26a-cf50-46af-ae09-f0fd7258ca27
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 工作流——一般操作
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769f489b16
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 导入数据{#importing-data}

## 收集数据 {#collecting-data}

您可以从文件中收集数据以处理它和／或将其导入Adobe Campaign数据库中。

* 该活 **[!UICONTROL Load file]** 动允许您将数据导入一个结构化表单，以在Adobe Campaign中使用此数据。 数据将临时导入，并且必须执行其他活动才能将其完全集成到Adobe Campaign数据库中。
* 该 **[!UICONTROL Transfer file]** 活动允许您接收或发送文件，测试是否存在文件，或列出Adobe Campaign中的文件。

   在需要从外部源检索文 **[!UICONTROL Load file]** 件时，您可以在之前使用此活动。

## 导入最佳实践 {#import-best-practices}

谨慎并遵循下面详述的几个简单规则，将有助于确保数据库内的数据一致性，并避免在数据库更新或数据导出过程中出现常见错误。

### 使用导入模板 {#using-import-templates}

大多数导入工作流应包含以下活动： **[!UICONTROL Load file]**, **[!UICONTROL Reconciliation]**, **[!UICONTROL Segmentation]**, **[!UICONTROL Deduplication]**, **[!UICONTROL Update data]**.

使用导入模板可以非常方便地准备类似的导入并确保数据库中的数据一致性。

在许多项目中，导入是无活 **[!UICONTROL Deduplication]** 动构建的，因为项目中使用的文件没有重复项。 有时，从导入不同的文件中会显示重复项。 因此，重复数据消除很困难。 因此，重复数据消除步骤是所有导入工作流程中的一个良好预防措施。

切勿假定传入的数据是一致和正确的，或由IT部门或Adobe Campaign主管负责处理。 在项目过程中，请牢记数据清理。 在导入数据时消除重复、协调和维护一致性。

为导入数据而设计的通用工作流模板的示例在示例中 [可用：“导入工作流模板](#example--import-workflow-template) ”部分。

>[!NOTE]
>
>您还可以使用导 [入模板](../../automating/using/importing-data-with-import-templates.md)。 它们是管理员定义的工作流模板，一旦激活，管理员只提供指定包含要导入的数据的文件的可能性。

### 使用平面文件格式 {#using-flat-file-formats}

导入的最有效格式是平面文件。 平面文件可以在数据库级别以批量模式导入。

例如：

* 分隔符：制表符或分号
* 第一行带有标题
* 无字符串分隔符
* 日期格式：YYYY/MM/DD HH:mm:SS

要导入的文件示例：

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

### 使用压缩 {#using-compression}

尽可能使用压缩文件进行导入和导出。 默认情况下，支持GZIP。 您可以分别在导入文件时添加预处理，在提取数据时添加后处理（在工作流活动中），或 **[!UICONTROL Load file]** 在提取 **[!UICONTROL Extract file]** 数据时添加后处理。

### 在增量模式下导入 {#importing-in-delta-mode}

常规导入必须在增量模式下完成。 这意味着每次只向Adobe Campaign发送修改的或新的数据，而不是发送整个表。

完全导入应仅用于初始加载。

### 保持一致性 {#maintaining-consistency}

要维护Adobe Campaign数据库中的数据一致性，请遵循以下原则：

* 如果导入的数据与Adobe Campaign中的引用表匹配，则应将其与工作流中的该表协调一致。 不匹配的记录应被拒绝。
* 确保导入的数据始终“ **标准化”** （电子邮件、电话号码、直邮地址），并且这种标准化是可靠的，并且不会在多年内发生变化。 如果不是这样，某些重复项可能会出现在数据库中，而Adobe Campaign不提供用于执行“模糊”匹配的工具，因此很难管理和删除它们。
* 交易数据应具有对帐密钥，并与现有数据对帐，以避免创建重复项。
* **按顺序导入相关文件**。 如果导入由多个相互依赖的文件组成，则工作流应确保以正确的顺序导入文件。 当文件失败时，不导入其他文件。
* **在导入数据时**，可以消除重复项、协调并保持一致性。

## 示例：导入工作流模板 {#example--import-workflow-template}

如果需要定期导入具有相同结构的文件，则使用导入模板是最佳做法。

此示例说明如何预先设置一个工作流，该工作流可用于导入来自Adobe Campaign数据库中CRM的配置文件。

1. 从创建新的工作流模板 **[!UICONTROL Resources > Templates > Workflow templates]**。
1. 添加以下活动：

   * **[!UICONTROL Load file]**:定义包含要导入的数据的文件的预期结构。

      >[!NOTE]
      >
      >只能从单个文件导入数据。 如果该工作流有多 **[!UICONTROL Load file]** 个活动，则每次都使用同一文件。

   * **[!UICONTROL Reconciliation]**:协调导入的数据与数据库数据。
   * **[!UICONTROL Segmentation]**:创建过滤器以根据记录是否可以协调而以不同方式处理记录。
   * **[!UICONTROL Deduplication]**:在将数据插入数据库之前，从传入文件中删除重复数据。
   * **[!UICONTROL Update data]**:使用导入的配置文件更新数据库。
   ![](assets/import_template_example0.png)

1. 配置活 **[!UICONTROL Load file]** 动：

   * 通过上传示例文件来定义期望的结构。 示例文件应仅包含几行，但包含导入所需的所有列。 检查并编辑文件格式，确保正确设置每列的类型：文本、日期、整数等。 例如：

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * 在部分 **[!UICONTROL File to load]** 中，选择 **[!UICONTROL Upload a new file from the local machine]** 字段并将其留空。 每次从此模板创建新工作流时，您都可以在此处指定所需的文件，只要该文件与定义的结构相对应。

      您可以使用任何选项，但必须相应地修改模板。 例如，如果您选择 **[!UICONTROL Use the file specified in the inbound transition]**&#x200B;了此选项，则可以在 **[!UICONTROL Transfer file]** 之前添加一个活动，以从FTP/SFTP服务器检索要导入的文件。

      如果希望用户能够下载包含导入过程中发生的错误的文件，请选中该选 **[!UICONTROL Keep the rejects in a file]** 项并指定 **[!UICONTROL File name]**。

      ![](assets/import_template_example1.png)

1. 配置活 **[!UICONTROL Reconciliation]** 动。 此活动在此上下文中的目的是识别传入的数据。

   * 在选项卡 **[!UICONTROL Relations]** 中，选择并 **[!UICONTROL Create element]** 定义导入的数据与收件人定位维之间的链接(请参阅定位维 [和资源](../../automating/using/query.md#targeting-dimensions-and-resources))。 在此示例中， **CRM ID** custom字段用于创建连接条件。 只要允许识别唯一记录，就使用所需字段或字段组合。
   * 在选项卡 **[!UICONTROL Identification]** 中，将选项保留为未选 **[!UICONTROL Identify the document from the working data]** 中状态。
   ![](assets/import_template_example2.png)

1. 配置活 **[!UICONTROL Segmentation]** 动，以在一个过渡中检索已协调的收件人和在第二个过渡中具有足够数据的无法协调的收件人。

   随后可以使用与已协调的接收方进行的过渡来更新数据库。 如果文件中有最少的一组信息可用，则具有未知收件人的过渡可用于在数据库中创建新收件人条目。

   在补充出站过渡中，将选择无法协调且没有足够数据的收件人，这些收件人可以导出到单独的文件中，或者只是忽略。

   * 在活动 **[!UICONTROL General]** 的选项卡中，将设置为 **[!UICONTROL Resource type]** 并 **[!UICONTROL Temporary resource]** 选择作为目 **[!UICONTROL Reconciliation]** 标集。
   * 在选 **[!UICONTROL Advanced options]** 项卡中，选 **[!UICONTROL Generate complement]** 中此选项可查看是否无法在数据库中插入任何记录。 如果需要，您随后可以对补充数据应用进一步处理：文件导出、列表更新等。
   * 在选项卡的第一段中， **[!UICONTROL Segments]** 在入站人口中添加一个过滤条件，以仅选择配置文件的CRM ID不等于0的记录。 这样，将在该子集中选择与数据库配置文件协调的文件中的数据。

      ![](assets/import_template_example3.png)

   * 添加第二个区段，以选择具有足够数据要插入到数据库中的未协调记录。 例如：电子邮件地址、名字和姓氏。 未协调的记录的CRM ID值等于0。

      ![](assets/import_template_example3_2.png)

   * 未在前两个子集中选择的所有记录在中被选择 **[!UICONTROL Complement]**。

1. 配置位 **[!UICONTROL Update data]** 于之前配置的活动的首次出站转 **[!UICONTROL Segmentation]** 换之后的活动。

   * 选择 **[!UICONTROL Update]** 为， **[!UICONTROL Operation type]** 因为入站过渡只包含数据库中已存在的收件人。
   * 在选项 **[!UICONTROL Identification]** 卡中，选 **[!UICONTROL Using reconciliation criteria]** 择并定义——在本例中 **[!UICONTROL Dimension to update]** 为配置文件——与在活动中创建的链接之间的键 **[!UICONTROL Reconciliation]** 值。 在此示例中，将 **使用CRM ID** custom字段。

      ![](assets/import_template_example6.png)

   * 在选项 **[!UICONTROL Fields to update]** 卡中，指示配置文件维中的字段，以使用文件中相应列的值进行更新。 如果文件列的名称与收件人维字段的名称相同或几乎相同，则可以使用魔棒按钮自动匹配不同的字段。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >如果您计划向这些配置文件发送直邮，请确保包含邮政地址，因为此信息对直邮提供商至关重要。 另外，请确保已选 **[!UICONTROL Address specified]** 中配置文件信息中的框。 要从工作流更新此选项，只需向要更新的字段添加一个元素，将 **1** 指定为，然 **[!UICONTROL Source]** 后选择 **PostalAddress/@addrDefined** field as **[!UICONTROL Destination]**。 有关直邮和使用选项的更多信 **[!UICONTROL Address specified]** 息，请参阅 [本文档](../../channels/using/about-direct-mail.md#recommendations)。

1. 配置转 **[!UICONTROL Deduplication]** 换后包含未协调配置文件的活动：

   * 在选 **[!UICONTROL Properties]** 项卡中，将设置 **[!UICONTROL Resource type]** 为从工作流的活动生成 **[!UICONTROL Reconciliation]** 的临时资源。

      ![](assets/import_template_example4.png)

   * 在此示例中，电子邮件字段用于查找唯一的配置文件。 您可以使用您确定已填写的任何字段，并且它是唯一组合的一部分。
   * 选择 **[!UICONTROL Deduplication method]**。 在这种情况下，应用程序会自动决定在出现重复时保留哪些记录。
   ![](assets/import_template_example7.png)

1. 配置先 **[!UICONTROL Update data]** 前配置的活动之 **[!UICONTROL Deduplication]** 后的活动。

   * 选择 **[!UICONTROL Insert only]** 为， **[!UICONTROL Operation type]** 因为入站过渡只包含数据库中不存在的配置文件。
   * 在选项 **[!UICONTROL Identification]** 卡中，选 **[!UICONTROL Using reconciliation criteria]** 择并定义——在本例中 **[!UICONTROL Dimension to update]** 为配置文件——与在活动中创建的链接之间的键 **[!UICONTROL Reconciliation]** 值。 在此示例中，将 **使用CRM ID** custom字段。

      ![](assets/import_template_example6.png)

   * 在选项 **[!UICONTROL Fields to update]** 卡中，指示配置文件维中的字段，以使用文件中相应列的值进行更新。 如果文件列的名称与收件人维字段的名称相同或几乎相同，则可以使用魔棒按钮自动匹配不同的字段。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >如果您计划向这些配置文件发送直邮，请确保包含邮政地址，因为此信息对直邮提供商至关重要。 另外，请确保已选 **[!UICONTROL Address specified]** 中配置文件信息中的框。 要从工作流更新此选项，只需向要更新的字段添加一个元素，将 **1** 指定为，然 **[!UICONTROL Source]** 后选择 **[PostalAddress/@addrDefined]** field as **[!UICONTROL Destination]**。 有关直邮和使用选项的更多信 **[!UICONTROL Address specified]** 息，请参阅 [本文档](../../channels/using/about-direct-mail.md#recommendations)。

1. 在活动的第三次转 **[!UICONTROL Segmentation]** 换后，如果要跟踪未插入到数 **[!UICONTROL Extract file]****[!UICONTROL Transfer file]** 据库的数据，请添加活动和活动。 配置这些活动以导出所需的列，并在FTP或SFTP服务器上传输文件，从中可以检索文件。
1. 添加活 **[!UICONTROL End]** 动并保存工作流模板。

该模板现在可以使用，并且可用于每个新工作流。 然后，需要全部指定包含要在活动中导入的数据的文 **[!UICONTROL Load file]** 件。

![](assets/import_template_example9.png)

