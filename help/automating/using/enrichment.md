---
title: 扩充
description: 丰富化活动是一项高级活动，允许您定义要在工作流中处理的其他数据。
page-status-flag: 从未激活
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 定位活动
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: 富集，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 扩充{#enrichment}

## 说明 {#description}

![](assets/enrichment.png)

活 **[!UICONTROL Enrichment]** 动是一个高级活动，允许您定义要在工作流中处理的其他数据。

## 使用环境 {#context-of-use}

活动 **[!UICONTROL Enrichment]** 通常在定位活动之后或导入文件之后以及允许使用目标数据的活动之前使用。

此活动包含比活动更高级的丰富化 **[!UICONTROL Query]** 功能。 某些简单的富集案例可以直接在查询活动 [中执行](../../automating/using/query.md#enriching-data)。

通过活 **[!UICONTROL Enrichment]** 动，您可以利用入站过渡并配置活动以使用其他数据完成输出过渡。 它允许合并来自多个集的数据，或创建指向临时资源的链接。

## 配置 {#configuration}

配置活 **[!UICONTROL Enrichment]** 动：

1. 将活动拖放 **[!UICONTROL Enrichment]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。
1. 如果活动有多个入站过渡，请选择该过渡 **[!UICONTROL Primary set]**。 此活动中配置的其他数据将添加到出站过渡中的此主集。

   如果主集已包含其他数据，您可以选择保留或删除这些数据。 如果取消选 **[!UICONTROL Keep all additional data from the main set]** 中此选项，则只有在出站过渡中 **[!UICONTROL Enrichment]** 配置的其他数据会保留。

1. 如果有多个入站过渡，请在活动的选项卡中定义主集与其他入站数据 **[!UICONTROL Advanced Relations]** 之间的关系。 您可以使用按钮添加多个关 **[!UICONTROL Add element]** 系。

   定义新关系时，选择要链接到主集合的入站数据集。 然后定义关系类型。 根据入站数据和您的数据模型，可以使用几种类型的关系：

   * **[!UICONTROL 1 cardinality simple link]**:输入数据的每个记录与来自主集合的一个和仅一个记录相关联。 来自主集合的每个记录在链接数据中具有一个关联记录。
   * **[!UICONTROL N cardinality collection link]**:0、1或1个以上(N)记录可以与主集合的1个记录相关联。
   * **[!UICONTROL 0 or 1 cardinality simple link]**:来自主集合的记录可以与来自链接数据的0或1个记录相关联，但不能与多个记录相关联。
   定义完 **[!UICONTROL Cardinality]** 成后，请定义 **[!UICONTROL Reconciliation criteria]**。 对 **[!UICONTROL Source expression]** 帐条件可以是目标资源中的字段、表达式 [](../../automating/using/advanced-expression-editing.md) ，也可以是引号之间指定的值。

   定义一 **[!UICONTROL Label]** 个和 **[!UICONTROL ID]** 一个在以后的工作流中易于识别的。

   >[!NOTE]
   >
   >您只能定义主集合与连接到活动的其他入站过渡之间的关 **[!UICONTROL Enrichment]** 系。 对于旨在定义与数据库资源的关系的简单案例，请使用“ [协调](../../automating/using/reconciliation.md) ”活动。

1. 从活动的选项卡中 **[!UICONTROL Additional data]** 定义其他数据。 您可以定义与主集的定位维相关的其他数据（简单字段、聚合和集合），也可以根据在活动的选项卡中创建的 **[!UICONTROL Advanced relations]** 链接来定 **[!UICONTROL Enrichment]** 义。

   请参阅丰 [富数据部分](../../automating/using/query.md#enriching-data) 。

1. 确认活动的配置并保存工作流。

数据现在可用于在之后连接的活动中 **[!UICONTROL Enrichment]**。 例如，您可以在电子邮件内容中的个 **[!UICONTROL Additional data (targetData)]** 性化字段浏览器的链接下找到它。

## 示例：用文件中包含的数据丰富档案数据 {#example--enriching-profile-data-with-data-contained-in-a-file}

此示例说明如何使用文件中包含的购买数据来丰富配置文件数据。 我们认为购买数据存储在第三方系统中。 每个配置文件都可以在文件中存储多个购买。 该工作流的最终目标是向至少购买了两件物品的目标配置文件发送电子邮件，感谢他们的忠诚度。

工作流的配置如下：

![](assets/enrichment_example_workflow.png)

* 以 **[!UICONTROL Query]** 接收消息的配置文件为目标的活动。
* 加 **[!UICONTROL Load file]** 载购买数据的活动。 例如：

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   对于此示例文件，我们将使用电子邮件地址将数据与数据库配置文件进行协调。 您还可以启用本文档中所述的 [唯一ID](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)。

* 在从 **[!UICONTROL Enrichment]** 文件加载的事务数据和在中选择的配置文件之间创建链接的活动 **[!UICONTROL Query]**。 链接在活动的选 **[!UICONTROL Advanced relations]** 项卡中定义。 该链接基于来自活动的过渡 **[!UICONTROL Load file]** 效果。 它使用配置文件资源的“电子邮件”字段和导入文件的“客户”列作为对帐标准。

   ![](assets/enrichment_example_workflow2.png)

   创建链接后，将添加两 **[!UICONTROL Additional data]** 组：

   * 与每个配置文件的最后两个事务处理相对应的两行的集合。 对于此集合，产品名称、交易日期和产品价格将作为附加数据添加。 对数据应用降序排序。 要创建集合，请从选项卡 **[!UICONTROL Additional data]** 中：

      选择之前在活动的选项卡 **[!UICONTROL Advanced relations]** 中定义的链接。

      ![](assets/enrichment_example_workflow3.png)

      选 **[!UICONTROL Collection]** 中并指定要检索的行数（本例中为2）。 在此屏幕中，您可以自定 **[!UICONTROL Alias]** 义集合 **[!UICONTROL Label]** 和集合。 这些值在引用此集合时将显示在工作流的以下活动中。

      ![](assets/enrichment_example_workflow4.png)

      要保 **[!UICONTROL Data]** 留集合，请选择将在最终交付中使用的列。

      ![](assets/enrichment_example_workflow6.png)

      对事务日期应用降序排序，以确保检索最新事务。

      ![](assets/enrichment_example_workflow7.png)

   * 每个配置文件的事务处理总数的汇总计数。 此汇总将稍后用于筛选至少记录了两个事务的配置文件。 要创建聚合，请从选项卡 **[!UICONTROL Additional data]** 中：

      选择之前在活动的选项卡 **[!UICONTROL Advanced relations]** 中定义的链接。

      ![](assets/enrichment_example_workflow3.png)

      Select **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      要保 **[!UICONTROL Data]** 留，请定义“全部 **计数** ”聚合。 如果需要，请指定自定义别名以在以下活动中更快地查找它。

      ![](assets/enrichment_example_workflow9.png)

* 只 **[!UICONTROL Segmentation]** 有一个区段的活动，它检索至少记录了两个事务的初始目标的配置文件。 仅包含一个事务的配置文件将被排除。 为此，分段的查询是在之前定义的聚合上进行的。

   ![](assets/enrichment_example_workflow5.png)

* 使用 **[!UICONTROL Email delivery]** 中定义的其他数据动态检索配置 **[!UICONTROL Enrichment]** 文件最后两次购买的活动。 添加个性化字段时，可在“附 **加数据”(TargetData)节点中找到其他数据** 。

   ![](assets/enrichment_example_workflow10.png)

**相关主题：**

* [利用外部数据丰富客户档案](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)

