---
title: 导入数据
seo-title: 导入数据
description: 导入数据
seo-description: 了解如何使用工作流导入数据。
page-status-flag: 从未激活
uuid: d909d26a-cf50-46af-ae09-f0 fd7258 ca27
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 工作流常规操作
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769 f489 b16
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 6748e59aaeafce9dc6e77dc0664a9024a53c3e35

---


# Importing data{#importing-data}

## Collecting data {#collecting-data}

您可以从文件收集数据以处理数据和/或在Adobe Campaign数据库中导入数据。

* **[!UICONTROL Load file]** 活动允许您在一个结构化表单中导入数据，以便在Adobe Campaign中使用此数据。数据将临时导入，而必须另外一个活动才能将其集成到Adobe Campaign数据库中。
* **[!UICONTROL Transfer file]** 活动允许您接收或发送文件，测试是否存在文件或在Adobe Campaign中列出文件。

   You can use this activity before a **[!UICONTROL Load file]** in case you need to retrieve the file from an external source.

## Import best practices {#import-best-practices}

谨防以下几个简单的规则，有助于确保数据库中的数据一致性以及避免在数据库更新或数据导出过程中出现常见错误。

### Using import templates {#using-import-templates}

Most import workflows should contain the following activities: **[!UICONTROL Load file]**, **[!UICONTROL Reconciliation]**, **[!UICONTROL Segmentation]**, **[!UICONTROL Deduplication]**, **[!UICONTROL Update data]**.

使用导入模板可以非常方便地准备类似导入并确保数据库中的数据一致性。

In many projects, imports are built without **[!UICONTROL Deduplication]** activity because the files used in the project do not have duplicates. 有时，重复使用不同的文件会出现重复情况。然后，重复复制很困难。因此，删除删除步骤在所有导入工作流程中都是很好的预防措施。

请勿在假定传入数据一致且正确的前提下，或由IT部门或Adobe Campaign主管负责处理。在项目过程中，请记住数据。在导入数据时取消复制、协调和维护一致性。

[示例中提供了为导入数据而设计的通用工作流模板示例：导入工作流模板](../../automating/using/importing-data.md#example--import-workflow-template) 部分。

>[!NOTE]
>
>You can also use [import templates](../../automating/using/importing-data-with-import-templates.md). 它们是由管理员定义的工作流模板，一旦激活后，只提供指定包含要导入的数据的文件的可能性。

### Using flat file formats {#using-flat-file-formats}

最有效的导入格式是平面文件。可在数据库级别以批量模式导入平面文件。

例如：

* 分隔符：选项卡或分号
* 具有标题的第一行
* 无字符串分隔符
* 日期格式：YYYY/MM/DD HH：mm：SS

要导入的文件示例：

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

### Using compression {#using-compression}

尽可能使用压缩文件进行导入和导出。默认情况下，支持GZIP。You can add pre-processing when importing files or post-processing when extracting data, respectively in the **[!UICONTROL Load file]** and **[!UICONTROL Extract file]** workflow activities.

### Importing in Delta mode {#importing-in-delta-mode}

常规导入必须在delta模式下完成。这意味着只会将修改后的或新的数据发送到Adobe Campaign，而不是每次都发送。

完全导入应仅用于初始加载。

### Maintaining consistency {#maintaining-consistency}

要保持Adobe Campaign数据库中的数据一致性，请遵循以下原则：

* 如果导入的数据与Adobe Campaign中的引用表匹配，则应在工作流中与该表协调。不匹配的记录应被拒绝。
* Ensure that the imported data is always **"normalized"** (email, phone number, direct mail address) and that this normalization is reliable and will not change over the years. 如果不是这种情况，可能会在数据库中出现一些重复的副本，因为Adobe Campaign没有提供“模糊”匹配的工具，因此很难管理和删除它们。
* 交易数据应具有一个核对密钥并与现有数据协调，以避免创建重复内容。
* **按顺序导入相关文件**。如果导入由多个相互依赖的文件组成，则该工作流应确保以正确的顺序导入文件。文件失败时，不会导入其他文件。
* **在导入数据时取消复制**、协调和维护一致性。

## Example: Import workflow template {#example--import-workflow-template}

如果需要定期导入具有相同结构的文件，则使用导入模板是最佳做法。

此示例展示了如何预设置可重用于从Adobe Campaign数据库中的CRM导入配置文件的工作流。

1. Create a new workflow template from **[!UICONTROL Resources > Templates > Workflow templates]**.
1. 添加以下活动：

   * **[!UICONTROL Load file]**：定义包含要导入数据的文件的预期结构。

      >[!NOTE]
      >
      >只能从单个文件导入数据。If the workflow has multiple **[!UICONTROL Load file]** activities, the same file will be used each time.

   * **[!UICONTROL Reconciliation]**：将导入的数据与数据库数据协调。
   * **[!UICONTROL Segmentation]**：创建过滤器以按不同的方式处理记录，具体取决于是否可以协调这些记录。
   * **[!UICONTROL Deduplication]**：在插入数据库中的数据之前，删除传入文件中的数据。
   * **[!UICONTROL Update data]**：使用导入的配置文件更新数据库。
   ![](assets/import_template_example0.png)

1. Configure the **[!UICONTROL Load file]** activity:

   * 通过上传示例文件定义预期结构。示例文件只能包含一些行，但必须包含导入所需的所有列。检查并编辑文件格式，确保正确设置每个列的类型：text、date、integer等。例如：

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * In the **[!UICONTROL File to load]** section, select **[!UICONTROL Upload a new file from the local machine]** and leave the field blank. 每次通过此模板创建新工作流时，您可以在此处指定所需的文件，只要其与定义的结构相对应。

      您可以使用任意选项，但必须相应地修改模板。For example, if you select **[!UICONTROL Use the file specified in the inbound transition]**, you can add a **[!UICONTROL Transfer file]** activity before to retrieve the file to import from a FTP/SFTP server.

      If you want users to be able to download a file containing errors that occurred during an import, check the **[!UICONTROL Keep the rejects in a file]** option and specify the **[!UICONTROL File name]**.

      ![](assets/import_template_example1.png)

1. Configure the **[!UICONTROL Reconciliation]** activity. 此上下文中的活动目的是识别传入的数据。

   * **[!UICONTROL Relations]** 在选项卡中，选择 **[!UICONTROL Create element]** 并定义导入数据与收件人定位维度之间的链接(请参阅 [定位维度和资源](../../automating/using/query.md#targeting-dimensions-and-resources))。In this example, the **CRM ID** custom field is used to create the join condition. 使用所需字段的字段或组合，以便识别唯一记录。
   * In the **[!UICONTROL Identification]** tab, leave the **[!UICONTROL Identify the document from the working data]** option unchecked.
   ![](assets/import_template_example2.png)

1. Configure the **[!UICONTROL Segmentation]** activity to retrieve reconciled recipients in one transition and recipients that could not be reconciled but who have enough data in a second transition.

   随后，可以使用已协调收件人的过渡来更新数据库。如果文件中有最少的信息集，则使用未知收件人的过渡随后可用于在数据库中创建新收件人条目。

   无法协调且没有足够数据的收件人在补充出站过渡中选择了充足的数据，并且可以在单独的文件中导出或只被忽略。

   * In the **[!UICONTROL General]** tab of the activity, set the **[!UICONTROL Resource type]** to **[!UICONTROL Temporary resource]** and select **[!UICONTROL Reconciliation]** as the targeted set.
   * In the **[!UICONTROL Advanced options]** tab, check the **[!UICONTROL Generate complement]** option to be able to see if any record cannot be inserted in the database. 您可以根据需要进一步处理补充数据：文件导出、列表更新等。
   * In the first segment of the **[!UICONTROL Segments]** tab, add a filtering condition on the inbound population to select only records for which the profile's CRM ID is not equal to 0. 这样，从数据库中与配置文件协调的数据就会在该子集中被选中。

      ![](assets/import_template_example3.png)

   * 添加一个第二个区段，它选择有足够数据要插入数据库的未和解记录。例如：电子邮件地址、名字和姓氏。未协调的记录的CRM ID值等于0。

      ![](assets/import_template_example3_2.png)

   * All records that are not selected in the first two subsets are selected in the **[!UICONTROL Complement]**.

1. Configure the **[!UICONTROL Update data]** activity located after the first outbound transition of the **[!UICONTROL Segmentation]** activity configured previously.

   * Select **[!UICONTROL Update]** as **[!UICONTROL Operation type]** since the inbound transition only contains recipients already present in the database.
   * **[!UICONTROL Identification]** 在选项卡中，在 **[!UICONTROL Using reconciliation criteria]** 该实例中的-以及 **[!UICONTROL Dimension to update]****[!UICONTROL Reconciliation]** 活动中创建的链接之间选择并定义一个密钥。In this example, the **CRM ID** custom field is used.

      ![](assets/import_template_example6.png)

   * **[!UICONTROL Fields to update]** 在选项卡中，指示配置文件维度中的字段，用相应列的值进行更新。如果文件列的名称与收件人维度字段的名称相同或几乎完全相同，则可以使用魔术棒按钮自动匹配不同的字段。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >如果您计划将邮寄直接邮寄到这些档案，请确保包含邮寄地址，因为此信息对于直接邮递提供商至关重要。Also make sure that the **[!UICONTROL Address specified]** box in your profiles' information is checked. To update this option from a workflow, simply add an element to the fields to update, and specify **1** as **[!UICONTROL Source]** and select the **postalAddress/@addrDefined** field as **[!UICONTROL Destination]**. For more on direct mail and the use of the **[!UICONTROL Address specified]** option, see [this document](../../channels/using/about-direct-mail.md#recommendations).

1. Configure the **[!UICONTROL Deduplication]** activity located after the transition containing unreconciled profiles:

   * **[!UICONTROL Properties]** 在选项卡中，将从 **[!UICONTROL Resource type]** 工作流 **[!UICONTROL Reconciliation]** 活动生成的临时资源设置为。

      ![](assets/import_template_example4.png)

   * 例如，电子邮件字段用于查找唯一配置文件。您可以使用确定的任何字段，并将其组成一个唯一组合。
   * Choose a **[!UICONTROL Deduplication method]**. 在这种情况下，应用程序会自动确定保留的记录以备副本。
   ![](assets/import_template_example7.png)

1. Configure the **[!UICONTROL Update data]** activity located after the **[!UICONTROL Deduplication]** activity configured previously.

   * Select **[!UICONTROL Insert only]** as **[!UICONTROL Operation type]** since the inbound transition only contains profiles not present in the database.
   * **[!UICONTROL Identification]** 在选项卡中，在 **[!UICONTROL Using reconciliation criteria]** 该实例中的-以及 **[!UICONTROL Dimension to update]****[!UICONTROL Reconciliation]** 活动中创建的链接之间选择并定义一个密钥。In this example, the **CRM ID** custom field is used.

      ![](assets/import_template_example6.png)

   * **[!UICONTROL Fields to update]** 在选项卡中，指示配置文件维度中的字段，用相应列的值进行更新。如果文件列的名称与收件人维度字段的名称相同或几乎完全相同，则可以使用魔术棒按钮自动匹配不同的字段。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >如果您计划将邮寄直接邮寄到这些档案，请确保包含邮寄地址，因为此信息对于直接邮递提供商至关重要。Also make sure that the **[!UICONTROL Address specified]** box in your profiles' information is checked. To update this option from a workflow, simply add an element to the fields to update, and specify **1** as **[!UICONTROL Source]** and select the **[postalAddress/@addrDefined]** field as **[!UICONTROL Destination]**. For more on direct mail and the use of the **[!UICONTROL Address specified]** option, see [this document](../../channels/using/about-direct-mail.md#recommendations).

1. **[!UICONTROL Segmentation]** 在活动的第三个过渡完成后，如果您要跟踪未插入数据库中的数据，则添加 **[!UICONTROL Extract file]** 活动和 **[!UICONTROL Transfer file]** 活动。配置这些活动以导出所需的列，并将文件传输到FTP或SFTP服务器上，您可以在该服务器上检索该文件。
1. Add an **[!UICONTROL End]** activity and save the workflow template.

现在可以使用该模板，并且可用于每个新工作流程。All is needed is then to specify the file containing the data to import in the **[!UICONTROL Load file]** activity.

![](assets/import_template_example9.png)

