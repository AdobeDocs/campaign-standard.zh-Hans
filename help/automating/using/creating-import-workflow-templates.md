---
title: 创建用于导入数据的工作流模板
description: 了解如何创建工作流模板以导入数据。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Experienced
exl-id: 5974a52c-8721-4575-b452-2982d6497235
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1172'
ht-degree: 1%

---

# 创建用于导入数据的工作流模板 {#import-workflow-template}

如果需要定期导入具有相同结构的文件，则使用导入模板是一种最佳实践。

此示例说明如何预先设置一个可重复使用的工作流，用于导入来自Adobe Campaign数据库中CRM的用户档案。

1. 从创建新工作流模板 **[!UICONTROL Resources > Templates > Workflow templates]**.
1. 添加以下活动：

   * **[!UICONTROL Load file]**：定义包含导入数据的文件的预期结构。

     >[!NOTE]
     >
     >您只能从单个文件导入数据。 如果工作流有多个 **[!UICONTROL Load file]** 活动，则每次都将使用相同的文件。

   * **[!UICONTROL Reconciliation]**：使用数据库数据协调导入的数据。
   * **[!UICONTROL Segmentation]**：创建过滤器以根据是否可以协调记录而采用不同方式处理记录。
   * **[!UICONTROL Deduplication]**：在将数据插入数据库之前，请删除传入文件中的重复数据。
   * **[!UICONTROL Update data]**：使用导入的用户档案更新数据库。

   ![](assets/import_template_example0.png)

1. 配置 **[!UICONTROL Load file]** 活动：

   * 通过上传样例文件来定义预期的结构。 样例文件应仅包含几行，但应包含导入所需的所有列。 检查并编辑文件格式，确保正确设置了每列的类型：文本、日期、整数等。 例如：

     ```
     lastname;firstname;birthdate;email;crmID
     Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
     ```

   * 在 **[!UICONTROL File to load]** 部分，选择 **[!UICONTROL Upload a new file from the local machine]** 并将字段留空。 每次从此模板创建新工作流时，只要该文件与定义的结构相对应，您就可以在此处指定所需的文件。

     您可以使用任何选项，但必须相应地修改模板。 例如，如果您选择 **[!UICONTROL Use the file specified in the inbound transition]**，您可以添加 **[!UICONTROL Transfer file]** 之前的活动，以检索要从FTP/SFTP服务器导入的文件。

     如果您希望用户能够下载包含导入期间发生错误的文件，请检查 **[!UICONTROL Keep the rejects in a file]** 选项并指定 **[!UICONTROL File name]**.

     ![](assets/import_template_example1.png)

1. 配置 **[!UICONTROL Reconciliation]** 活动。 在此上下文中，此活动的目的是标识传入数据。

   * 在 **[!UICONTROL Relations]** 选项卡，选择 **[!UICONTROL Create element]** 并定义导入数据与收件人定向维度之间的链接(请参阅 [定向维度和资源](../../automating/using/query.md#targeting-dimensions-and-resources))。 在此示例中， **CRM ID** 自定义字段用于创建连接条件。 只要允许标识唯一记录，就可以使用所需的字段或字段组合。
   * 在 **[!UICONTROL Identification]** 选项卡，离开 **[!UICONTROL Identify the document from the working data]** 选项未选中。

   ![](assets/import_template_example2.png)

1. 配置 **[!UICONTROL Segmentation]** 用于在某个过渡中检索已协调的收件人以及在第二个过渡中无法协调但具有足够数据的收件人的活动。

   然后，可以使用包含已协调收件人的过渡来更新数据库。 如果文件中具有最小信息集，则可以使用具有未知收件人的过渡在数据库中创建新收件人条目。

   无法协调且数据不足的收件人将在补充叫客过渡中选择，并可以在单独文件中导出或直接忽略。

   * 在 **[!UICONTROL General]** 选项卡中，设置 **[!UICONTROL Resource type]** 到 **[!UICONTROL Temporary resource]** 并选择 **[!UICONTROL Reconciliation]** 作为目标集。
   * 在 **[!UICONTROL Advanced options]** 选项卡，检查 **[!UICONTROL Generate complement]** 选项，用于查看数据库中是否不能插入任何记录。 如果需要，可以对补充数据执行进一步处理：文件导出、列表更新等。
   * 在 **[!UICONTROL Segments]** 选项卡，为集客群体添加筛选条件，以仅选择配置文件的CRM ID不等于0的记录。 这样，来自与来自数据库的用户档案协调的文件的数据便在该子集中被选择。

     ![](assets/import_template_example3.png)

   * 添加第二个区段，用于选择具有足够数据可插入数据库中的未协调记录。 例如：电子邮件地址、名字和姓氏。 未协调的记录其配置文件的CRM ID值等于0。

     ![](assets/import_template_example3_2.png)

   * 在前两个子集中未选择的所有记录都会在 **[!UICONTROL Complement]**.

1. 配置 **[!UICONTROL Update data]** 位于的第一个叫客过渡之后的活动 **[!UICONTROL Segmentation]** 之前配置的活动。

   * 选择 **[!UICONTROL Update]** 作为 **[!UICONTROL Operation type]** 由于集客过渡仅包含数据库中已存在的收件人。
   * 在 **[!UICONTROL Identification]** 选项卡，选择 **[!UICONTROL Using reconciliation criteria]** 并定义 **[!UICONTROL Dimension to update]**  — 在此例中是配置文件 — 以及在中创建的链接 **[!UICONTROL Reconciliation]** 活动。 在此示例中， **CRM ID** 自定义字段。

     ![](assets/import_template_example6.png)

   * 在 **[!UICONTROL Fields to update]** 选项卡，指示要用文件中对应列的值更新的用户档案维度中的字段。 如果文件列的名称与收件人维字段的名称相同或几乎相同，则可以使用魔棒按钮自动匹配不同的字段。

     ![](assets/import_template_example6_2.png)

     >[!NOTE]
     >
     >如果您计划向这些用户档案发送直邮，请确保包含邮政地址，因为此信息对直邮提供商至关重要。 同时确保 **[!UICONTROL Address specified]** 复选框。 要从工作流更新此选项，只需将元素添加到要更新的字段中，然后指定 **1** 作为 **[!UICONTROL Source]** 并选择 `postalAddress/@addrDefined` 字段为 **[!UICONTROL Destination]**. 有关直邮和使用的更多信息， **[!UICONTROL Address specified]** 选项，请参见 [本文档](../../channels/using/about-direct-mail.md#recommendations).

1. 配置 **[!UICONTROL Deduplication]** 位于包含未协调用户档案的过渡之后的活动：

   * 在 **[!UICONTROL Properties]** 选项卡，设置 **[!UICONTROL Resource type]** 临时资源从 **[!UICONTROL Reconciliation]** 工作流活动。

     ![](assets/import_template_example4.png)

   * 在本例中，电子邮件字段用于查找独特的用户档案。 您可以使用任何确信已填充的字段以及唯一组合的一部分。
   * 选择 **[!UICONTROL Deduplication method]**. 在这种情况下，应用程序会自动决定要保留哪些记录以防出现重复项。

   ![](assets/import_template_example7.png)

1. 配置 **[!UICONTROL Update data]** 位于活动之后 **[!UICONTROL Deduplication]** 之前配置的活动。

   * 选择 **[!UICONTROL Insert only]** 作为 **[!UICONTROL Operation type]** 因为集客过渡仅包含数据库中不存在的用户档案。
   * 在 **[!UICONTROL Identification]** 选项卡，选择 **[!UICONTROL Using reconciliation criteria]** 并定义 **[!UICONTROL Dimension to update]**  — 在此例中是配置文件 — 以及在中创建的链接 **[!UICONTROL Reconciliation]** 活动。 在此示例中， **CRM ID** 自定义字段。

     ![](assets/import_template_example6.png)

   * 在 **[!UICONTROL Fields to update]** 选项卡，指示要用文件中对应列的值更新的用户档案维度中的字段。 如果文件列的名称与收件人维字段的名称相同或几乎相同，则可以使用魔棒按钮自动匹配不同的字段。

     ![](assets/import_template_example6_2.png)

     >[!NOTE]
     >
     >如果您计划向这些用户档案发送直邮，请确保包含邮政地址，因为此信息对直邮提供商至关重要。 同时确保 **[!UICONTROL Address specified]** 复选框。 要从工作流更新此选项，只需将元素添加到要更新的字段中，然后指定 **1** 作为 **[!UICONTROL Source]** 并选择 **[邮政地址/@addrDefined]** 字段为 **[!UICONTROL Destination]**. 有关直邮和使用的更多信息， **[!UICONTROL Address specified]** 选项，请参见 [本文档](../../channels/using/about-direct-mail.md#recommendations).

1. 在第三个过渡之后 **[!UICONTROL Segmentation]** 活动，添加 **[!UICONTROL Extract file]** 活动和 **[!UICONTROL Transfer file]** 活动。 配置这些活动以导出所需的列，并在FTP或SFTP服务器上传输文件，以便检索。
1. 添加 **[!UICONTROL End]** 活动并保存工作流模板。

现在可以使用该模板，并且该模板可用于每个新工作流。 然后只需指定包含要在中导入的数据的文件 **[!UICONTROL Load file]** 活动。

![](assets/import_template_example9.png)
