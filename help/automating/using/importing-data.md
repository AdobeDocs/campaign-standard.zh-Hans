---
title: 导入数据
description: 了解如何使用工作流导入数据。
page-status-flag: never-activated
uuid: d909d26a-cf50-46af-ae09-f0fd7258ca27
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769f489b16
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e22a2fcfd36adc1d4c9b62b1fd336e553c69b5af
workflow-type: tm+mt
source-wordcount: '1961'
ht-degree: 0%

---


# 导入数据{#importing-data}

## 收集数据 {#collecting-data}

您可以从文件收集数据以处理它和／或将它导入Adobe Campaign库。

* 活动 **[!UICONTROL Load file]** 允许您以一种结构化形式导入数据，以在Adobe Campaign中使用此数据。 数据被临时导入，需要另一个活动将其完全集成到Adobe Campaign数据库中。

   有关如何使用此活动的详细信息，请参 [阅本节](../../automating/using/load-file.md)。

* 活动 **[!UICONTROL Transfer file]** 允许您接收或发送文件、测试是否存在文件或以Adobe Campaign列表文件。
在需要从外部源检索 **[!UICONTROL Load file]** 文件时，可以在文件之前使用此活动。

   有关如何使用此活动的详细信息，请参 [阅本节](../../automating/using/transfer-file.md)。

## 导入最佳实践 {#import-best-practices}

谨慎并遵循下面详述的几个简单规则将有助于确保数据库内数据的一致性，避免在数据库更新或数据导出过程中出现常见错误。

### 使用导入模板 {#using-import-templates}

大多数导入工作流应包含以下活动: **[!UICONTROL Load file]**、 **[!UICONTROL Reconciliation]**、 **[!UICONTROL Segmentation]**、 **[!UICONTROL Deduplication]**、 **[!UICONTROL Update data]**。

使用导入模板可以非常方便地准备类似的导入并确保数据库中的数据一致性。

在许多项目中，导入是无 **[!UICONTROL Deduplication]** 活动构建的，因为项目中使用的文件没有重复。 重复有时会从导入其他文件时显示。 因此，重复数据消除很困难。 因此，外部重复数据删除步骤是所有进口工作流的良好预防措施。

切勿假定传入数据是一致、正确的，或由IT部门或Adobe Campaign主管负责处理。 在项目过程中，请牢记数据清理。 在导入数据时，消除重复、协调和维护一致性。

为导入数据而设计的通用工作流模板的示例在示例中 [可用： “导入工作流模板](#example--import-workflow-template) ”部分。

>[!NOTE]
>
>您还可以使用 [导入模板](../../automating/using/importing-data-with-import-templates.md)。 它们是由管理员定义的工作流模板，一旦激活，管理员只会优惠指定包含要导入数据的文件的可能性。

**相关主题：**

* [加载文件活动](../../automating/using/load-file.md)
* [对帐活动](../../automating/using/reconciliation.md)
* [细分活动](../../automating/using/segmentation.md)
* [外部重复数据删除活动](../../automating/using/deduplication.md)
* [更新数据活动](../../automating/using/update-data.md)

### 使用平面文件格式 {#using-flat-file-formats}

导入的最有效格式是平面文件。 平面文件可以在数据库级别以批量模式导入。

例如：

* 分隔符： 制表符或分号
* 带标题的第一行
* 无字符串分隔符
* 日期格式： YYYY/MM/DD HH:mm:SS

要导入的文件示例：

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

### 使用压缩 {#using-compression}

尽可能使用压缩文件进行导入和导出。 默认支持GZIP。 您可以分别在导入文件时添加预处理，在提取数据时添加后处理，在工作流活动 **[!UICONTROL Load file]** 和工作流 **[!UICONTROL Extract file]** 中添加。

**相关主题：**

* [加载文件活动](../../automating/using/load-file.md)
* [提取文件活动](../../automating/using/extract-file.md)

### 在增量模式下导入 {#importing-in-delta-mode}

常规导入必须在增量模式下完成。 这意味着每次只向Adobe Campaign发送修改或新数据，而不是向整个表发送。

完全导入应仅用于初始加载。

### 维护一致性 {#maintaining-consistency}

要在Adobe Campaign库中保持数据一致性，请遵循以下原则：

* 如果导入的数据与Adobe Campaign中的引用表匹配，则应将其与工作流中的该表协调。 不匹配的记录应被拒绝。
* 确保导入的数据始终“ **标准化** ”（电子邮件、电话号码、直接邮件地址），并且此标准化是可靠的，并且多年内不会更改。 如果不是这样，某些重复可能会出现在Adobe Campaign库中，而由于不提供进行“模糊”匹配的工具，因此很难管理和删除这些数据。
* 事务数据应具有合并关键项并与现有数据协调，以避免创建重复。
* **按顺序导入相关文件**。 如果导入由多个相互依赖的文件组成，则工作流应确保以正确的顺序导入文件。 文件失败时，不导入其他文件。
* **在导入**&#x200B;数据时，消除重复、协调并维护一致性。

## 管理加密数据 {#managing-encrypted-data}

在某些情况下，您要导入活动服务器的数据可能需要加密，例如，如果它包含PII数据。

要能够导入或导出加密文件，您首先需要联系Adobe客户服务部，以便他们为您的实例提供所需的加密／解密命令。

为此，请提交一个请求，其中指明：

* 将 **在活动** 界面中显示的标签以使用该命令。 例如“加密文件”。
* 在 **实例** 上安装的命令。
例如，要使用PGP解密文件，该命令将为：

   ```
   <path-to_pgp_if-not_global_or_server/>pgp.exe --decrypt --input nl6/var/vp/import/filename.pgp --passphrase "your password" --recipient recipient @email.com --verbose --output nl6/var/vp/import/filename
   ```

一旦请求得到处理，加密／解密命令将在字段中 **[!UICONTROL Pre-processing stage]** 和活动 **[!UICONTROL Load file]** 中可用 **[!UICONTROL Extract file]** 。 您可以使用它们解密或加密要导入或导出的文件。

![](assets/preprocessing-encryption.png)

**相关主题：**

* [加载文件](../../automating/using/load-file.md)
* [提取文件](../../automating/using/extract-file.md)

## 创建用于导入数据的工作流模板 {#example--import-workflow-template}

如果需要定期导入结构相同的文件，使用导入模板是最佳做法。

此示例说明如何预先设置一个工作流，该工作流可用于导入来自用户档案库中CRM的Adobe Campaign。

1. 从创建新的工作流模板 **[!UICONTROL Resources > Templates > Workflow templates]**。
1. 添加以下活动:

   * **[!UICONTROL Load file]**: 定义包含要导入的数据的文件的预期结构。

      >[!NOTE]
      >
      >只能从单个文件导入数据。 如果工作流有多个 **[!UICONTROL Load file]** 活动，则每次都使用同一文件。

   * **[!UICONTROL Reconciliation]**: 协调导入的数据与数据库数据。
   * **[!UICONTROL Segmentation]**: 创建过滤器，根据记录是否可以对帐，以不同方式处理记录。
   * **[!UICONTROL Deduplication]**: 在将数据插入数据库之前，从传入文件中消除重复数据。
   * **[!UICONTROL Update data]**: 使用导入的用户档案更新数据库。
   ![](assets/import_template_example0.png)

1. 配置 **[!UICONTROL Load file]** 活动:

   * 通过上传示例文件来定义预期结构。 示例文件应仅包含几行，但包含导入所需的所有列。 检查并编辑文件格式，确保正确设置每列的类型： 文本、日期、整数等。 例如：

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * 在部分 **[!UICONTROL File to load]** 中，选 **[!UICONTROL Upload a new file from the local machine]** 择该字段并将其留空。 每次从此模板创建新工作流时，您都可以在此处指定所需的文件，只要该文件与定义的结构相对应。

      您可以使用任何选项，但必须相应地修改模板。 例如，如果您选择 **[!UICONTROL Use the file specified in the inbound transition]**&#x200B;了此选项，则 **[!UICONTROL Transfer file]** 可以在之前添加活动，以检索要从FTP/SFTP服务器导入的文件。

      如果希望用户能够下载包含导入过程中发生的错误的文件，请选中该 **[!UICONTROL Keep the rejects in a file]** 选项并指定 **[!UICONTROL File name]**。

      ![](assets/import_template_example1.png)

1. 配置 **[!UICONTROL Reconciliation]** 活动。 此活动的目的是识别传入数据。

   * 在选项 **[!UICONTROL Relations]** 卡中，选 **[!UICONTROL Create element]** 择并定义导入数据与收件人定位维度之间的链接(请参 [阅定位维度和资源](../../automating/using/query.md#targeting-dimensions-and-resources))。 在此示例中， **CRM ID自定** 义字段用于创建连接条件。 只要字段允许识别唯一记录，就可以使用所需字段或字段组合。
   * 在选项卡 **[!UICONTROL Identification]** 中，将选项保留 **[!UICONTROL Identify the document from the working data]** 为未选中状态。
   ![](assets/import_template_example2.png)

1. 配置活动 **[!UICONTROL Segmentation]** 以在一个过渡和收件人中检索已协调的收件人，这些无法协调，但在第二个过渡中具有足够的数据。

   然后，具有已协调过渡的收件人可以用于更新数据库。 如果文件中有最少一组信息可用，则具有未知过渡的收件人随后可用于在数据库中创建新收件人条目。

   在补充出站收件人中，将选择无法协调且没有足够数据的过渡，并可以在单独的文件中导出，或只是忽略。

   * 在活动 **[!UICONTROL General]** 的选项卡中，将设置 **[!UICONTROL Resource type]** 为 **[!UICONTROL Temporary resource]** 并选择作 **[!UICONTROL Reconciliation]** 为目标集。
   * 在选 **[!UICONTROL Advanced options]** 项卡中，选 **[!UICONTROL Generate complement]** 中该选项可查看是否无法在数据库中插入任何记录。 如果需要，您随后可以对补充数据应用进一步处理： 文件导出、列表更新等。
   * 在选项卡的第一个 **[!UICONTROL Segments]** 区段中，在入站人口中添加过滤条件，以仅选择用户档案的CRM ID不等于0的记录。 这样，在该子集中选择与来自用户档案库的数据协调的文件数据。

      ![](assets/import_template_example3.png)

   * 添加第二个段，该段选择具有足够数据要插入数据库的未协调记录。 例如： 电子邮件地址、名字和姓氏。 未对帐的记录的用户档案CRM ID值等于0。

      ![](assets/import_template_example3_2.png)

   * 在前两个子集中未选择的所有记录都在中选择 **[!UICONTROL Complement]**。

1. 配置位 **[!UICONTROL Update data]** 于之前配置的活动的第一个出站过渡 **[!UICONTROL Segmentation]** 之后的活动。

   * 选 **[!UICONTROL Update]** 择为 **[!UICONTROL Operation type]** ，因为入站过渡只包含数据库中已存在的收件人。
   * 在选 **[!UICONTROL Identification]** 项卡中， **[!UICONTROL Using reconciliation criteria]** 选择并定义在-用户档案和在 **[!UICONTROL Dimension to update]** 活动中创建的链接之间的键 **[!UICONTROL Reconciliation]** 。 在此示例中， **使用CRM** ID自定义字段。

      ![](assets/import_template_example6.png)

   * 在选 **[!UICONTROL Fields to update]** 项卡中，指示用户档案维中的字段，以使用文件中的相应列的值进行更新。 如果文件列的名称与收件人维字段的名称相同或几乎相同，则可以使用魔棒按钮自动匹配不同的字段。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >如果您计划向这些用户档案发送直邮，请确保包含邮政地址，因为此信息对于直邮提供者至关重要。 同时确保选中 **[!UICONTROL Address specified]** 用户档案信息中的框。 要从工作流更新此选项，只需向要更新的字段中添加元素，然后 **指定** 1 **[!UICONTROL Source]** 作为，然 `postalAddress/@addrDefined` 后选择字段 **[!UICONTROL Destination]**。 有关直邮和使用此选项的详细 **[!UICONTROL Address specified]** 信息，请参 [阅此文档](../../channels/using/about-direct-mail.md#recommendations)。

1. 配置位 **[!UICONTROL Deduplication]** 于包含未对帐活动的过渡之后的用户档案:

   * 在选 **[!UICONTROL Properties]** 项卡中，将 **[!UICONTROL Resource type]** 其设置为从工作流的活动 **[!UICONTROL Reconciliation]** 生成的临时资源。

      ![](assets/import_template_example4.png)

   * 在此示例中，电子邮件字段用于查找唯一用户档案。 您可以使用您确定已填写的任何字段，并且它是唯一组合的一部分。
   * 选择 **[!UICONTROL Deduplication method]**。 在这种情况下，应用程序自动决定在出现重复时保留哪些记录。
   ![](assets/import_template_example7.png)

1. 配置先 **[!UICONTROL Update data]** 前配置活动之 **[!UICONTROL Deduplication]** 后的活动。

   * 选 **[!UICONTROL Insert only]** 择为 **[!UICONTROL Operation type]** ，因为入站过渡只包含数据库中不存在的用户档案。
   * 在选 **[!UICONTROL Identification]** 项卡中， **[!UICONTROL Using reconciliation criteria]** 选择并定义在-用户档案和在 **[!UICONTROL Dimension to update]** 活动中创建的链接之间的键 **[!UICONTROL Reconciliation]** 。 在此示例中， **使用CRM** ID自定义字段。

      ![](assets/import_template_example6.png)

   * 在选 **[!UICONTROL Fields to update]** 项卡中，指示用户档案维中的字段，以使用文件中的相应列的值进行更新。 如果文件列的名称与收件人维字段的名称相同或几乎相同，则可以使用魔棒按钮自动匹配不同的字段。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >如果您计划向这些用户档案发送直邮，请确保包含邮政地址，因为此信息对于直邮提供者至关重要。 同时确保选中 **[!UICONTROL Address specified]** 用户档案信息中的框。 要从工作流更新此选项，只需向要更新的字段添加元素， **将** 1 **[!UICONTROL Source]** 指定为， **[然后将postalAddress/@addrDefined]** 字段选为 **[!UICONTROL Destination]**。 有关直邮和使用此选项的详细 **[!UICONTROL Address specified]** 信息，请参 [阅此文档](../../channels/using/about-direct-mail.md#recommendations)。

1. 在活动的第三个 **[!UICONTROL Segmentation]** 过渡之后，如 **[!UICONTROL Extract file]** 果要跟踪未插入 **[!UICONTROL Transfer file]** 的数据，请添加活动和活动。 配置这些活动以导出所需列，并在FTP或SFTP服务器上传输文件，从中可以检索文件。
1. 添加 **[!UICONTROL End]** 活动并保存工作流模板。

该模板现在可以使用，并且可用于每个新工作流。 然后，需要全部指定包含要在活动中导入的数据的文 **[!UICONTROL Load file]** 件。

![](assets/import_template_example9.png)
