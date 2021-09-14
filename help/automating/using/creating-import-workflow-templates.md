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

如果您需要定期导入具有相同结构的文件，则使用导入模板是最佳做法。

此示例说明如何预设可重复使用的工作流，以导入来自Adobe Campaign数据库中CRM的用户档案。

1. 从&#x200B;**[!UICONTROL Resources > Templates > Workflow templates]**&#x200B;创建新的工作流模板。
1. 添加以下活动：

   * **[!UICONTROL Load file]**:定义包含要导入数据的文件的预期结构。

      >[!NOTE]
      >
      >您只能从单个文件导入数据。 如果工作流具有多个&#x200B;**[!UICONTROL Load file]**&#x200B;活动，则每次将使用同一文件。

   * **[!UICONTROL Reconciliation]**:使用数据库数据协调导入的数据。
   * **[!UICONTROL Segmentation]**:创建过滤器以根据记录是否可以协调而以不同方式处理记录。
   * **[!UICONTROL Deduplication]**:在将数据插入数据库之前，从传入文件中删除重复数据。
   * **[!UICONTROL Update data]**:使用导入的用户档案更新数据库。

   ![](assets/import_template_example0.png)

1. 配置&#x200B;**[!UICONTROL Load file]**&#x200B;活动：

   * 通过上传样例文件定义预期结构。 样例文件应仅包含几行，但包含导入所需的所有列。 检查并编辑文件格式，以确保正确设置每列的类型：文本、日期、整数等 例如：

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * 在&#x200B;**[!UICONTROL File to load]**&#x200B;部分中，选择&#x200B;**[!UICONTROL Upload a new file from the local machine]**&#x200B;并将字段留空。 每次使用此模板创建新工作流时，您都可以在此处指定所需的文件，只要该文件与定义的结构相对应。

      您可以使用任何选项，但必须相应地修改模板。 例如，如果选择&#x200B;**[!UICONTROL Use the file specified in the inbound transition]**，则可以先添加&#x200B;**[!UICONTROL Transfer file]**&#x200B;活动，然后再从FTP/SFTP服务器中检索要导入的文件。

      如果希望用户能够下载导入期间发生错误的文件，请勾选&#x200B;**[!UICONTROL Keep the rejects in a file]**&#x200B;选项并指定&#x200B;**[!UICONTROL File name]**。

      ![](assets/import_template_example1.png)

1. 配置&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活动。 此上下文中此活动的目的是识别传入数据。

   * 在&#x200B;**[!UICONTROL Relations]**&#x200B;选项卡中，选择&#x200B;**[!UICONTROL Create element]**&#x200B;并定义导入数据与定向维度的收件人之间的链接（请参阅[定向维度和资源](../../automating/using/query.md#targeting-dimensions-and-resources)）。 在此示例中，使用&#x200B;**CRM ID**&#x200B;自定义字段创建连接条件。 使用您需要的字段或字段组合，只要它允许标识唯一记录。
   * 在&#x200B;**[!UICONTROL Identification]**&#x200B;选项卡中，取消选中&#x200B;**[!UICONTROL Identify the document from the working data]**&#x200B;选项。

   ![](assets/import_template_example2.png)

1. 配置&#x200B;**[!UICONTROL Segmentation]**&#x200B;活动，以在一个过渡中检索已协调的收件人，以及在第二个过渡中无法协调但拥有足够数据的收件人。

   随后可以使用包含已协调收件人的过渡来更新数据库。 如果文件中有一组最低信息，则具有未知收件人的过渡可用于在数据库中创建新收件人条目。

   在补码叫客过渡中选择无法协调且没有足够数据的收件人，这些收件人可以导出到单独的文件中，或者干脆忽略。

   * 在活动的&#x200B;**[!UICONTROL General]**&#x200B;选项卡中，将&#x200B;**[!UICONTROL Resource type]**&#x200B;设置为&#x200B;**[!UICONTROL Temporary resource]**，然后选择&#x200B;**[!UICONTROL Reconciliation]**&#x200B;作为目标集。
   * 在&#x200B;**[!UICONTROL Advanced options]**&#x200B;选项卡中，选中&#x200B;**[!UICONTROL Generate complement]**&#x200B;选项，以便能够查看数据库中是否无法插入任何记录。 如果需要，您随后可以对补充数据应用进一步处理：文件导出、列表更新等。
   * 在&#x200B;**[!UICONTROL Segments]**&#x200B;选项卡的第一个区段中，对集客群体添加筛选条件，以仅选择用户档案CRM ID不等于0的记录。 这样，在该子集中选择来自与来自数据库的用户档案协调的文件的数据。

      ![](assets/import_template_example3.png)

   * 添加第二个区段，以选择具有足够数据要插入数据库的未协调记录。 例如：电子邮件地址、名字和姓氏。 未协调的记录的CRM ID值等于0。

      ![](assets/import_template_example3_2.png)

   * 未在前两个子集中选择的所有记录都将在&#x200B;**[!UICONTROL Complement]**&#x200B;中选择。

1. 配置位于之前配置的&#x200B;**[!UICONTROL Segmentation]**&#x200B;活动首次叫客过渡之后的&#x200B;**[!UICONTROL Update data]**&#x200B;活动。

   * 选择&#x200B;**[!UICONTROL Update]**&#x200B;作为&#x200B;**[!UICONTROL Operation type]**，因为集客过渡仅包含数据库中已存在的收件人。
   * 在&#x200B;**[!UICONTROL Identification]**&#x200B;选项卡中，选择&#x200B;**[!UICONTROL Using reconciliation criteria]**&#x200B;并定义&#x200B;**[!UICONTROL Dimension to update]** — 本例中的配置文件 — 与在&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活动中创建的链接之间的键。 在此示例中，使用&#x200B;**CRM ID**&#x200B;自定义字段。

      ![](assets/import_template_example6.png)

   * 在&#x200B;**[!UICONTROL Fields to update]**&#x200B;选项卡中，指示Profiles维度中的字段，以使用文件中相应列的值进行更新。 如果文件列的名称与收件人维度字段的名称相同或几乎相同，则可以使用魔棒按钮自动匹配不同的字段。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >如果您计划向这些用户档案发送直邮，请确保包含邮政地址，因为此信息对直邮提供商至关重要。 另外，请确保选中用户档案信息中的&#x200B;**[!UICONTROL Address specified]**&#x200B;框。 要从工作流中更新此选项，只需在要更新的字段中添加一个元素，并将&#x200B;**1**&#x200B;指定为&#x200B;**[!UICONTROL Source]**，然后选择`postalAddress/@addrDefined`字段为&#x200B;**[!UICONTROL Destination]**。 有关直邮和使用&#x200B;**[!UICONTROL Address specified]**&#x200B;选项的更多信息，请参阅[本文档](../../channels/using/about-direct-mail.md#recommendations)。

1. 配置位于包含未协调用户档案的过渡之后的&#x200B;**[!UICONTROL Deduplication]**&#x200B;活动：

   * 在&#x200B;**[!UICONTROL Properties]**&#x200B;选项卡中，将&#x200B;**[!UICONTROL Resource type]**&#x200B;设置为从工作流的&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活动生成的临时资源。

      ![](assets/import_template_example4.png)

   * 在本例中，电子邮件字段用于查找唯一的用户档案。 您可以使用您确定已填写的任何字段以及唯一组合的一部分。
   * 选择&#x200B;**[!UICONTROL Deduplication method]**。 在这种情况下，应用程序会自动决定在出现重复时保留哪些记录。

   ![](assets/import_template_example7.png)

1. 配置位于之前配置的&#x200B;**[!UICONTROL Deduplication]**&#x200B;活动之后的&#x200B;**[!UICONTROL Update data]**&#x200B;活动。

   * 选择&#x200B;**[!UICONTROL Insert only]**&#x200B;作为&#x200B;**[!UICONTROL Operation type]**，因为集客过渡仅包含数据库中不存在的配置文件。
   * 在&#x200B;**[!UICONTROL Identification]**&#x200B;选项卡中，选择&#x200B;**[!UICONTROL Using reconciliation criteria]**&#x200B;并定义&#x200B;**[!UICONTROL Dimension to update]** — 本例中的配置文件 — 与在&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活动中创建的链接之间的键。 在此示例中，使用&#x200B;**CRM ID**&#x200B;自定义字段。

      ![](assets/import_template_example6.png)

   * 在&#x200B;**[!UICONTROL Fields to update]**&#x200B;选项卡中，指示Profiles维度中的字段，以使用文件中相应列的值进行更新。 如果文件列的名称与收件人维度字段的名称相同或几乎相同，则可以使用魔棒按钮自动匹配不同的字段。

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >如果您计划向这些用户档案发送直邮，请确保包含邮政地址，因为此信息对直邮提供商至关重要。 另外，请确保选中用户档案信息中的&#x200B;**[!UICONTROL Address specified]**&#x200B;框。 要从工作流中更新此选项，只需在要更新的字段中添加一个元素，并将&#x200B;**1**&#x200B;指定为&#x200B;**[!UICONTROL Source]**，然后将&#x200B;**[postalAddress/@addrDefined]**&#x200B;字段选为&#x200B;**[!UICONTROL Destination]**。 有关直邮和使用&#x200B;**[!UICONTROL Address specified]**&#x200B;选项的更多信息，请参阅[本文档](../../channels/using/about-direct-mail.md#recommendations)。

1. 在&#x200B;**[!UICONTROL Segmentation]**&#x200B;活动的第三个过渡之后，如果要跟踪未插入数据库的数据，请添加&#x200B;**[!UICONTROL Extract file]**&#x200B;活动和&#x200B;**[!UICONTROL Transfer file]**&#x200B;活动。 配置这些活动以导出所需的列，并在FTP或SFTP服务器上传输文件，您可以在其中检索该文件。
1. 添加&#x200B;**[!UICONTROL End]**&#x200B;活动并保存工作流模板。

模板现在可供使用，并可用于每个新工作流。 然后，需要指定包含要在&#x200B;**[!UICONTROL Load file]**&#x200B;活动中导入的数据的文件。

![](assets/import_template_example9.png)
