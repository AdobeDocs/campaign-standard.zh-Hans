---
title: 用文件中包含的用户档案丰富数据
description: 此示例说明如何使用文件中包含的购买数据丰富用户档案数据。
page-status-flag: never-activated
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: enrichment,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 0%

---


# 用文件中包含的用户档案丰富数据 {#enriching-profile-data-with-data-contained-in-a-file}

此示例说明如何使用文件中包含的购买数据来丰富用户档案数据。在此我们考虑购买数据存储在第三方系统中。 每个用户档案都可以在文件中存储多个购买。 该工作流的最终目标是向至少购买了两件物品的目标用户档案发送电子邮件，感谢他们的忠诚度。

工作流的配置如下：

![](assets/enrichment_example_workflow.png)

* 查询 [活动](../../automating/using/query.md) ，用于目标将接收消息的用户档案。
* 加 [载购买](../../automating/using/load-file.md) 活动的加载文件。 例如：

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   对于此示例文件，我们将使用电子邮件地址将数据与数据库用户档案进行协调。 您还可以启用唯一ID，如本 [文档所述](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)。

* 一个 [扩充](../../automating/using/enrichment.md) 活动，它在从文件加载的事务数据与在中选择的用户档案之间创建链接 **[!UICONTROL Query]**。 链接在活动的 **[!UICONTROL Advanced relations]** 选项卡中定义。 链接基于来自过渡的 **[!UICONTROL Load file]** 活动。 它使用用户档案资源的“email”字段和导入文件的“customer”列作为协调标准。

   ![](assets/enrichment_example_workflow2.png)

   创建链接后，将添加两 **[!UICONTROL Additional data]** 组：

   * 与每个用户档案的最后两个事务处理相对应的两行的集合。 对于此集合，产品名称、交易日期和产品价格将作为附加数据添加。 对数据应用降序排序。 要创建集合，请从选项卡 **[!UICONTROL Additional data]** 中：

      选择之前在活动的选项卡 **[!UICONTROL Advanced relations]** 中定义的链接。

      ![](assets/enrichment_example_workflow3.png)

      选 **[!UICONTROL Collection]** 中并指定要检索的行数（本例中为2）。 在此屏幕中，您可以自 **[!UICONTROL Alias]** 定义集 **[!UICONTROL Label]** 合和集合。 引用此集合时，这些值将在工作流的以下活动中可见。

      ![](assets/enrichment_example_workflow4.png)

      要 **[!UICONTROL Data]** 保留集合，请选择将在最终投放中使用的列。

      ![](assets/enrichment_example_workflow6.png)

      对事务日期应用降序排序，以确保检索最新事务。

      ![](assets/enrichment_example_workflow7.png)

   * 聚合计数每个用户档案的事务处理总数。 此聚合稍后将用于筛选至少记录了两个事务的用户档案。 要创建聚合，请从选项卡 **[!UICONTROL Additional data]** 中：

      选择之前在活动的选项卡 **[!UICONTROL Advanced relations]** 中定义的链接。

      ![](assets/enrichment_example_workflow3.png)

      Select **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      要保 **[!UICONTROL Data]** 留，请定义“全部 **计数** ”聚合。 如果需要，请指定自定义别名，以便在以下活动中更快地找到它。

      ![](assets/enrichment_example_workflow9.png)

* 只 [有一个段](../../automating/using/segmentation.md) 的分段活动，它检索至少记录了两个事务的初始目标的用户档案。 仅包含一个事务的用户档案将被排除。 为此，分段的查询是根据之前定义的聚合进行的。

   ![](assets/enrichment_example_workflow5.png)

* 电 [子邮件投放](../../automating/using/email-delivery.md) 活动，它使用中定义的其他数据 **[!UICONTROL Enrichment]** 动态检索用户档案最后两次购买。 添加个性化字段时，可在“ **附加数据”(TargetData)节** 点中找到附加数据。

   ![](assets/enrichment_example_workflow10.png)

**相关主题：**

* [利用外部数据丰富客户用户档案](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)
