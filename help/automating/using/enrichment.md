---
title: 丰富性
seo-title: 丰富性
description: 丰富性
seo-description: 丰富化活动是一种高级活动，允许您定义要在工作流程中处理的其他数据。
page-status-flag: 从未激活
uuid: 8c1693ef-1312-422c-b05 d-263555113f8 f
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 定位活动
discoiquuid: f67c1caf-3284-4c34-a5 b0-8654a95640 ae
context-tags: 丰富化，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Enrichment{#enrichment}

## Description {#description}

![](assets/enrichment.png)

**[!UICONTROL Enrichment]** 活动是一个高级活动，允许您定义工作流中要处理的其他数据。

## Context of use {#context-of-use}

**[!UICONTROL Enrichment]** 活动通常用于定位活动或导入文件之后，在允许使用目标数据的活动之前。

This activity contains more advanced enrichment functions than the **[!UICONTROL Query]** activity. Some simple cases of enrichment can be directly performed in the [Query activity](../../automating/using/query.md#enriching-data).

With the **[!UICONTROL Enrichment]** activity, you can leverage the inbound transition and configure the activity to complete the output transition with additional data. 它允许合并来自多个集合的数据，或创建指向临时资源的链接。

## Configuration {#configuration}

To configure an **[!UICONTROL Enrichment]** activity:

1. Drag and drop an **[!UICONTROL Enrichment]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. If the activity has several inbound transitions, select the **[!UICONTROL Primary set]**. 此活动中配置的其他数据将添加到出站过渡中的此主要设置。

   如果主集合已经包含其他数据，您可以选择保留它们或删除它们。If you uncheck the **[!UICONTROL Keep all additional data from the main set]** option, only the additional data configured in the **[!UICONTROL Enrichment]** are kept in the outbound transition.

1. If there are several inbound transitions, define relations between the primary set and the other inbound data in the **[!UICONTROL Advanced Relations]** tab of the activity. You can add several relations using the **[!UICONTROL Add element]** button.

   定义新关系时，请选择要链接到主集合的集数据集。然后定义关系类型。有几种类型的关系可用，具体取决于入站数据和您的数据模型：

   * **[!UICONTROL 1 cardinality simple link]**：传入数据的每个记录与一个记录相关联，并且只与主要集中的一个记录相关联。主集合中的每个记录都有关联的数据中的一个关联记录。
   * **[!UICONTROL N cardinality collection link]**：链接数据中的0、1或更多(N)记录可与主要设置的记录相关联。
   * **[!UICONTROL 0 or 1 cardinality simple link]**：主集合中的记录可以与链接数据中的0或记录关联，但不能与多个记录关联。
   Once the **[!UICONTROL Cardinality]** is defined, define a **[!UICONTROL Reconciliation criteria]**. The **[!UICONTROL Source expression]** of the reconciliation criteria can be a field from the target resource, an [expression](../../automating/using/advanced-expression-editing.md) or directly a value specified between quotes.

   Define a **[!UICONTROL Label]** and an **[!UICONTROL ID]** that will be easy to identify later in the workflow.

   >[!NOTE]
   >
   >You can only define relations between the primary set and the other inbound transitions connected to the **[!UICONTROL Enrichment]** activity. For simpler cases aiming at defining relations with database resources, use a [Reconciliation](../../automating/using/reconciliation.md) activity.

1. Define the additional data from the **[!UICONTROL Additional data]** tab of the activity. You can define additional data (simple fields, aggregates and collections) related to the targeting dimension of the primary set or based on the links created in the **[!UICONTROL Advanced relations]** tab of the **[!UICONTROL Enrichment]** activity.

   Consult the [Enriching data](../../automating/using/query.md#enriching-data) section.

1. 确认活动的配置并保存工作流。

The data is now available to use in the activities connected after the **[!UICONTROL Enrichment]**. For example, you can find it under the **[!UICONTROL Additional data (targetData)]** link of the personalization fields explorer in an email content.

## Example: Enriching profile data with data contained in a file {#example--enriching-profile-data-with-data-contained-in-a-file}

此示例显示如何使用文件中包含的购买数据来丰富配置文件数据。我们在此处考虑购买数据存储在第三方系统中。每个配置文件都可以存储在文件中的多个购买。工作流程的最后目标是向已购买至少两个项目的目标档案发送电子邮件，感谢他们忠诚度。

工作流的配置如下：

![](assets/enrichment_example_workflow.png)

* A **[!UICONTROL Query]** activity that targets the profiles who will receive the message.
* A **[!UICONTROL Load file]** activity that loads the purchase data. 例如：

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   通过此示例文件，我们将使用电子邮件地址将数据与数据库配置文件协调。You can also enable unique IDs as described in [this document](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).

* **[!UICONTROL Enrichment]** 创建从文件加载的事务数据和在中选择的配置文件之间的链接的活动 **[!UICONTROL Query]**。The link is defined in the **[!UICONTROL Advanced relations]** tab of the activity. The link is based on the transition coming from the **[!UICONTROL Load file]** activity. 它使用配置文件资源的“电子邮件”字段和导入文件的“客户”列作为排序标准。

   ![](assets/enrichment_example_workflow2.png)

   Once the link is created, two sets of **[!UICONTROL Additional data]** are added:

   * 与每个配置文件的最后两个事务对应的两行的集合。对于此集合，产品名称、事务日期和产品价格将添加为其他数据。对数据应用降序排序。To create the collection, from the **[!UICONTROL Additional data]** tab:

      Select the link previously defined in the **[!UICONTROL Advanced relations]** tab of the activity.

      ![](assets/enrichment_example_workflow3.png)

      Check **[!UICONTROL Collection]** and specify the number of lines to retrieve (2 in this example). In this screen, you can customize the **[!UICONTROL Alias]** and the **[!UICONTROL Label]** of the collection. 引用此集合时，这些值将在工作流的以下活动中可见。

      ![](assets/enrichment_example_workflow4.png)

      As **[!UICONTROL Data]** to keep for the collection, select the columns that will be used in the final delivery.

      ![](assets/enrichment_example_workflow6.png)

      对事务日期应用降序排序以确保检索最新事务。

      ![](assets/enrichment_example_workflow7.png)

   * 汇总每个配置文件的事务总数的汇总。以后将使用此汇总过滤至少录制了两个事务的配置文件。To create the aggregate, from the **[!UICONTROL Additional data]** tab:

      Select the link previously defined in the **[!UICONTROL Advanced relations]** tab of the activity.

      ![](assets/enrichment_example_workflow3.png)

      Select **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      As **[!UICONTROL Data]** to keep, define a **Count All** aggregate. 如果需要，请指定自定义别名以在以下活动中更快地找到它。

      ![](assets/enrichment_example_workflow9.png)

* **[!UICONTROL Segmentation]** 仅具有一个区段的活动，该区段检索至少已记录两个事务的初始目标的配置文件。仅包含一个事务的配置文件被排除。为此，对之前定义的聚合进行了查询查询。

   ![](assets/enrichment_example_workflow5.png)

* **[!UICONTROL Email delivery]** 使用中定义的附加数据动态检索 **[!UICONTROL Enrichment]** 配置文件所做的两次购买的活动。The additional data can be found in the **Additional data (TargetData)** node when adding a personalization field.

   ![](assets/enrichment_example_workflow10.png)

