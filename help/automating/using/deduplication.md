---
title: 删除重复项
seo-title: 删除重复项
description: 删除重复项
seo-description: “取消复制”活动允许您删除入站活动结果中的重复项。
page-status-flag: 从未激活
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 定位活动
discoiquuid: e7a5e7e7-4680-46c7-98b8-0a47bb7bs8b8
context-tags: dublp，main
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Deduplication{#deduplication}

## Description {#description}

![](assets/deduplication.png)

**[!UICONTROL Deduplication]** 活动允许您删除入站活动结果中的重复项。

## Context of use {#context-of-use}

**[!UICONTROL Deduplication]** 活动通常用于定位活动或导入文件之后，在允许使用目标数据的活动之前。

在删除重复项期间，将单独处理入站过渡。例如，如果查询的结果中存在profile'A'，并且查询的结果也是如此，则不会重复删除它。

因此，建议删除重复项仅有一个入站过渡。为此，您可以使用符合定位需求(如联合活动、相交活动等)的活动合并不同的查询。例如：

![](assets/dedup_bonnepratique.png)

## Configuration {#configuration}

要配置取消删除活动，您必须输入标签、方法和删除条件条件以及与结果相关的选项。

1. Drag and drop a **[!UICONTROL Deduplication]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   ![](assets/deduplication_1.png)

1. Select the **[!UICONTROL Resource type]** on which the deduplication has to be carried out:

   * **[!UICONTROL Database resource]** 如果对数据库中已经存在的数据执行取消删除操作。Select the **[!UICONTROL Filtering dimension]** and the **[!UICONTROL Targeting dimension]**, depending on the data that you want to deduplicate. By default, deduplication is carried out on the **profiles**.
   * **[!UICONTROL Temporary resource]** 如果对工作流的临时数据执行取消删除操作：选择 **[!UICONTROL Targeted set]** 包含要重复的数据的数据。导入文件或数据库中的数据(例如，使用区段代码)时，可能会遇到此用例。

1. Select the **[!UICONTROL Number of unique records to keep]**. 此字段的默认值为1。值允许您保留所有副本。

   例如，如果记录A和B被视为记录Y的副本，而记录C被视为记录Z的副本：

   * 如果字段的值为1：只保留Y和Z记录。
   * 如果字段的值为0：保留所有记录。
   * 如果字段的值为2：保留C和Z记录，保留从A、B和Y记录的记录，按概率或根据以后选择的删除方法保留。

1. Define the **[!UICONTROL Duplicate identification]** criteria by adding conditions in the list provided. 指定相同值允许识别重复项的字段和/或表达式：电子邮件地址、名字、姓氏等。条件的顺序允许您指定要处理的第一个。
1. In the drop-down list, select the **[!UICONTROL Deduplication method]** to use:

   * **[!UICONTROL Choose for me]**：随机选择要保留的记录。
   * **[!UICONTROL Following a list of values]**：允许您为一个或多个字段定义值优先级。要定义这些值，请选择一个字段或创建一个表达式，然后将该值添加到相应的表中。To define a new field, click the **[!UICONTROL Add]** button located above the list of values.

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**：这样，您就可以保留所选表达式的值不是空的记录。

      ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**：这样，您就可以保留输入的表达式值是最小或最大的记录。

      ![](assets/deduplication_4.png)

1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.
1. 确认活动的配置并保存工作流。

## Example 1: Identifying duplicates before a delivery {#example-1--identifying-duplicates-before-a-delivery}

以下示例演示了一个取消删除，它允许您在发送电子邮件之前排除目标的重复项。这意味着您可以避免将通信多次发送到同一配置文件。

该工作流由以下组成部分构成：

![](assets/deduplication_example_workflow.png)

* A **[!UICONTROL Query]** which allows you to define the target of the email. 此处，该工作流面向在客户端数据库中已存在一年以上的所有配置文件(18到25个)。

   ![](assets/deduplication_example_query.png)

* **[!UICONTROL Deduplication]** 活动，允许您识别来自先前查询的副本。在此示例中，每个重复项只保存一个记录。重复项使用电子邮件地址进行标识。这意味着，电子邮件发送只能发送一次，以便在定位中显示每个电子邮件地址。

   The deduplication method selected is **[!UICONTROL Non-empty value]**. This allows you to ensure that amongst the records kept in case of duplicates, priority is given to those in which the **First name** has been provided. 如果在电子邮件内容的个性化字段中使用了名字，这将使其更加一致。

   此外，还添加了一个额外过渡以保留重复项并能够列出这些过渡。

   ![](assets/deduplication_example_dedup.png)

* **[!UICONTROL Email delivery]** 位于删除重复项的主出站过渡之后。The configuration for email deliveries is detailed in the [Email delivery](../../automating/using/email-delivery.md) section.
* A **[!UICONTROL Save audience]** activity placed after the additional transition of the deduplication to save the duplicates in a **Duplicates** audience. 可以重复使用此受众，直接从每个电子邮件分发中排除其成员。

## Example 2: Deduplicating the data from an imported file {#example-2--deduplicating-the-data-from-an-imported-file}

此示例显示如何从导入的文件中删除数据，然后将数据加载到数据库中。此过程提高了数据库中加载的数据的质量。

该工作流由以下组成部分构成：

![](assets/deduplication_example2_workflow.png)

* A file that contains a list of profiles is imported using a **[!UICONTROL Load file]** activity. 在此示例中，导入的文件采用. csv格式，并且包含10个配置文件：

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

   此文件还可用作示例文件，用于检测和定义列的格式。From the **[!UICONTROL Column definition]** tab, make sure that each column of the imported file is configured correctly.

   ![](assets/deduplication_example2_fileloading.png)

* **[!UICONTROL Deduplication]** 活动。在导入文件并将数据插入数据库之前，会直接执行删除重复项。It should therefore be based on the **[!UICONTROL Temporary resource]** from the **[!UICONTROL Load file]** activity.

   对于此示例，我们希望保留文件中包含的每个唯一电子邮件地址的单个条目。Duplicate identification is therefore carried out on the **email** column of the temporary resource. 但是，两个电子邮件地址在文件中显示两次。因此，两行将被视为重复内容。

   ![](assets/deduplication_example2_dedup.png)

* **[!UICONTROL Update data]** 活动允许您将数据从删除过程插入数据库。只有在更新数据后，导入的数据才会识别为配置文件维度。

   Here, we would like to **[!UICONTROL Insert only]** the profiles that do not already exist in the database. We are going to do this by using the file's email column and the email field from the **Profile** dimension as the reconciliation key.

   ![](assets/deduplication_example2_writer1.png)

   Specify the mappings between the file's columns from which you want to insert the data and the database fields from the **[!UICONTROL Fields to update]** tab.

   ![](assets/deduplication_example2_writer2.png)

然后启动工作流。从删除重复项过程保存的记录随后会添加到数据库中的配置文件中。
