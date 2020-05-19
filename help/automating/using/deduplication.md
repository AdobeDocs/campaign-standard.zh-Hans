---
title: 重复数据删除
description: 外部重复数据删除活动允许您删除入站活动结果中的重复。
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 0%

---


# 重复数据删除{#deduplication}

## 说明 {#description}

![](assets/deduplication.png)

该 **[!UICONTROL Deduplication]** 活动允许您删除入站活动结果中的重复。

## 使用环境 {#context-of-use}

该活动 **[!UICONTROL Deduplication]** 通常在目标活动或导入文件之后以及允许使用目标数据的活动之前使用。

在外部重复数据删除期间，将单独处理入站过渡。 例如，如果用户档案“A”出现在查询1的结果中，也出现在查询2的结果中，则不会消除重复。

因此，建议外部重复数据删除仅具有一个入站过渡。 为此，您可以使用与定位需求(如合并活动、交叉点活动等)相对应的活动来组合不同的查询。 例如：

![](assets/dedup_bonnepratique.png)

## 配置 {#configuration}

要配置外部重复数据删除活动，必须输入标签、方法和外部重复数据删除条件，以及与结果相关的选项。

1. 将活动拖放 **[!UICONTROL Deduplication]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。

   ![](assets/deduplication_1.png)

1. 选择 **[!UICONTROL Resource type]** 要执行外部重复数据删除的位置：

   * **[!UICONTROL Database resource]** 如果对外部重复数据删除库中已存在的数据执行该数据。 根据 **[!UICONTROL Filtering dimension]** 要 **[!UICONTROL Targeting dimension]**&#x200B;消除重复的数据，选择和。 默认情况下，外部重复数据删除对用户档案 **执行**。
   * **[!UICONTROL Temporary resource]** 如果对工作流的临时外部重复数据删除执行该： 选择包 **[!UICONTROL Targeted set]** 含要重复数据消除的数据。 在导入文件后，或者(例如，使用段代码)对数据库中的数据进行了丰富后，可能会遇到此用例。

1. 选择 **[!UICONTROL Number of unique records to keep]**。 此字段的默认值为1。 值0允许您保留所有重复。

   例如，如果记录A和B被视为记录Y的重复，而记录C被视为记录Z的重复:

   * 如果字段的值为1: 只保留Y和Z记录。
   * 如果字段的值为0: 所有记录都保存了。
   * 如果字段的值为2: 记录C和Z被保留，并且A、B和Y的两个记录被保留，偶然地或取决于此后选择的外部重复数据删除方法。

1. 通过在提 **[!UICONTROL Duplicate identification]** 供的列表中添加条件来定义标准。 指定允许标识相同值的字段和／或表达式: 电子邮件地址、名字、姓氏等。 条件的顺序允许您指定要先处理的条件。
1. 在下拉列表中，选择要 **[!UICONTROL Deduplication method]** 使用的：

   * **[!UICONTROL Choose for me]**: 随机选择要从重复中保留的记录。
   * **[!UICONTROL Following a list of values]**: 允许您为一个或多个字段定义值优先级。 要定义值，请选择一个字段或创建表达式，然后将值添加到相应的表中。 要定义新字段，请单击 **[!UICONTROL Add]** 位于值列表上方的按钮。

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**: 这样，您就可以保留选定表达式的值不为空的记录作为优先级。

      ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**: 这样，您就可以保留输入的表达式值最小或最大的记录。

      ![](assets/deduplication_4.png)

1. 如果需要，可以管理活动 [的过渡](../../automating/using/activity-properties.md) ，以访问出站人口的高级选项。
1. 确认活动的配置并保存工作流。

## 示例1: 在重复之前识别投放 {#example-1--identifying-duplicates-before-a-delivery}

以下示例说明了一个外部重复数据删除，它允许您在发送电子邮件之前排除目标的重复。 这意味着您避免向同一用户档案发送多次通信。

该工作流由以下几部分组成：

![](assets/deduplication_example_workflow.png)

* 用 **[!UICONTROL Query]** 于定义电子邮件的目标。 此处，该工作流目标了客户端用户档案库中已存在超过一年的18到25岁的所有。

   ![](assets/deduplication_example_query.png)

* 一 **[!UICONTROL Deduplication]** 个活动，它允许您识别来自前一个查询的重复。 在此示例中，每个重复只保存一个记录。 重复使用电子邮件地址进行标识。 这意味着，对于要在定位中显示的每个电子邮件地址，只能发送一次电子邮件投放。

   选择的外部重复数据删除方 **[!UICONTROL Non-empty value]**&#x200B;法。 这样，您就可以确保在保存的重复记录中，优先于提供名 **字** 的记录。 如果在电子邮件内容的个性化字段中使用名，这将使其更加连贯。

   此外，还增加了额外的过渡，以保留重复并能够列表它们。

   ![](assets/deduplication_example_dedup.png)

* 位 **[!UICONTROL Email delivery]** 于外部重复数据删除主出站过渡之后的位置。 电子邮件投放的配置详见“电子邮件 [投放](../../automating/using/email-delivery.md) ”部分。
* 放 **[!UICONTROL Save audience]** 在活动附加过渡之后以将重复保存在重复 **受众** 。 可以重复使用此受众，以直接从每个电子邮件投放中排除其成员。

## 示例2: 从导入的文件中消除重复数据 {#example-2--deduplicating-the-data-from-an-imported-file}

此示例说明如何在将数据加载到数据库之前从导入的文件中删除重复数据。 此过程可提高数据库中加载的数据的质量。

该工作流由以下几部分组成：

![](assets/deduplication_example2_workflow.png)

* 包含列表用户档案的文件将使用活动 **[!UICONTROL Load file]** 导入。 在此示例中，导入的文件采用。csv格式，包含10个用户档案:

   ```
   lastname;firstname;dateofbirth;email
   Smith;Hayden;23/05/1989;hayden.smith@example.com
   Mars;Daniel;17/11/1987;dannymars@example.com
   Smith;Clara;08/02/1989;hayden.smith@example.com
   Durance;Allison;15/12/1978;allison.durance@example.com
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com
   Binder;Tom;19/01/1982;tombinder@example.com
   Binder;Tommy;19/01/1915;tombinder@example.com
   Connor;Jade;10/10/1979;connor.jade@example.com
   Mack;Clarke;02/03/1985;clarke.mack@example.com
   Ross;Timothy;04/07/1986;timross@example.com
   ```

   此文件还可用作检测和定义列格式的示例文件。 在选项卡 **[!UICONTROL Column definition]** 中，确保已正确配置导入文件的每列。

   ![](assets/deduplication_example2_fileloading.png)

* 一个 **[!UICONTROL Deduplication]** 活动。 外部重复数据删除在导入文件后和将数据插入数据库之前直接执行。 因此，它应以活动 **[!UICONTROL Temporary resource]** 的数据为 **[!UICONTROL Load file]** 基础。

   在此示例中，我们希望对文件中包含的每个唯一电子邮件地址保留一个条目。 因此，重复标识在临时 **资源** 的电子邮件列上执行。 但是，两个电子邮件地址会在文件中显示两次。 因此，两行将被视为重复。

   ![](assets/deduplication_example2_dedup.png)

* 活动 **[!UICONTROL Update data]** 允许您将外部重复数据删除过程中保留的数据插入数据库。 只有在更新数据时，导入的数据才被标识为属于用户档案维。

   在此，我们希望 **[!UICONTROL Insert only]** 用户档案库中尚未存在的数据。 我们将使用文件的电子邮件列和用户档案维中的电子邮件字段作为 **合并关键项** ，来执行此操作。

   ![](assets/deduplication_example2_writer1.png)

   从选项卡中指定要插入数据的文件列与数据库字段之间的映 **[!UICONTROL Fields to update]** 射。

   ![](assets/deduplication_example2_writer2.png)

然后开始工作流。 然后，从外部重复数据删除进程保存的记录将添加到用户档案库中的记录。
