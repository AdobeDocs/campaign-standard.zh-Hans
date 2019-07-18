---
title: Contract
seo-title: Contract
description: Contract
seo-description: 通过“帐帐”活动，您可以将未识别的数据链接到现有资源。
page-status-flag: 从未激活
uuid: 7884db8c-1717-4724-be15-3b0 b32 cc071
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 数据管理活动
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: 调解，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Reconciliation{#reconciliation}

## Description {#description}

![](assets/reconciliation.png)

**[!UICONTROL Reconciliation]** 活动允许您将未识别的数据链接到现有资源。

## Context of use {#context-of-use}

**[!UICONTROL Reconciliation]** 该活动主要用于数据管理目的，并暗示两种不同的用例：

* Adding relations: a **[!UICONTROL Links]** tab allows you to add links between the inbound data and several other Adobe Campaign database dimensions.

   例如，包含购买数据的文件可能还包含用于标识购买的产品以及购买者的信息。Two additional dimensions (besides that of **Purchases**) are therefore concerned by the file data: the **Products** and **Profiles** dimensions. Relations then need to be created between these and the **Purchases** dimension (refer to the following example).

   定义关系时，将列添加到入站数据，以引用链接维度的外键。

   >[!NOTE]
   >
   >此操作表示链接维度的数据已在数据库中。例如，如果您导入了一个显示购买了哪个产品的产品，在什么时间、哪个时间、哪个客户端等，以及数据库中必须已经存在该客户端。

* Data identification: an **[!UICONTROL Identification]** tab allows you to simply link inbound data to columns of an existing dimension in the Adobe Campaign database. 活动完成后，数据被识别为属于定义的维度。

   例如，您可以执行保存受众、数据库更新等操作。

For example, the **[!UICONTROL Reconciliation]** activity can be placed after a load data activity with the aim of importing non-standard data into the database.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Reconciliation]** activity into your workflow, following a transition containing a population whose targeting dimension does not directly come from Adobe Campaign. For more on this, referr to [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. If you would like to define links between the inbound data and other database dimensions, go to the **[!UICONTROL Links]** tab.

   根据需要添加任意数量的关系。对于每个关系，首先选择链接的维度，然后在链接详细信息中指定相应的字段。

1. If you would like to simply identify the inbound data, go to the **[!UICONTROL Identification]** tab and check the **[!UICONTROL Identify the document from the working data]** box.

   选择要将入站数据协调到的定位维度。

   添加排序条件，将入站过渡记录链接到选定定位维度记录。如果指定了多个条件，则必须对它们进行验证，以便链接所有数据之间的链接。

   Choose the **[!UICONTROL Processing unidentified source lines]** mode:

   * **[!UICONTROL Ignore them]**：仅可识别的数据保留在活动的出站过渡中。
   * **[!UICONTROL Keep in the outbound population]**：入站过渡中的所有数据都保留在活动的出站过渡中。

1. 确认活动的配置并保存工作流。

## Example 1: Relation definition {#example-1--relation-definition}

以下示例演示了一个工作流，它使用文件中的购买数据更新数据库。购买数据包含来自其他维度的数据引用元素，例如客户电子邮件和产品代码。

>[!NOTE]
>
>The **Transactions** and **Products** resources used in this example do not exist in the Adobe Campaign database by default. They were therefore created beforehand using the [Custom resources](../../developing/using/data-model-concepts.md) function. 与导入文件中的电子邮件地址以及产品相对应的配置文件预先加载到数据库中。

该工作流由以下活动组成：

![](assets/reconciliation_example1.png)

* A **[!UICONTROL Load file]** activity, which loads and detects the data of the file to import. 导入的文件包含以下数据：

   * 事务日期
   * 客户端电子邮件地址
   * 购买的产品代码
   ```
   date;client;product
   2015-05-19 09:00:00;mail1@email.com;ZZ1
   2015-05-19 09:01:00;mail2@email.com;ZZ2
   2015-05-19 09:01:01;mail3@email.com;ZZ2
   2015-05-19 09:01:02;mail4@email.com;ZZ2
   2015-05-19 09:02:00;mail5@email.com;ZZ3
   2015-05-19 09:03:00;mail6@email.com;ZZ4
   2015-05-19 09:04:00;mail7@email.com;ZZ5
   2015-05-19 09:05:00;mail8@email.com;ZZ7
   2015-05-19 09:06:00;mail9@email.com;ZZ6
   ```

* **[!UICONTROL Reconciliation]** 将购买数据绑定到数据库配置文件以及产品的活动。因此，必须定义文件数据与配置文件表以及产品表之间的关系。This configuration is carried out in the activity's **[!UICONTROL Relations]** tab:

   * **与配置文件的关系**：该文件 **的客户** 端列链接到配置文件维度的 **电子邮件****** 字段。
   * **与产品的关系**：该文件 **的产品** 列链接到配置文件维度的 **productCode****** 字段。
   列添加到入站数据中，以便引用链接尺寸的外键。

   ![](assets/reconciliation_example3.png)

* **[!UICONTROL Update data]** 活动允许您定义要使用导入的数据更新的数据库字段。As the data was already identified as belonging to the **Transactions** dimension in the previous activity, here you can use the **[!UICONTROL Directly using the targeting dimension]** identification option.

   By using the option that automatically detects fields to update, the links configured in the previous activity (to profiles and products) are added to the list of **[!UICONTROL Fields to update]**. 您还必须确保与事务日期对应的字段正确添加到此列表。

   ![](assets/reconciliation_example5.png)

   ![](assets/reconciliation_example4.png)

## Example 2: Identification {#example-2--identification}

以下示例演示了一个工作流，它直接从包含新客户端的导入文件创建一个配置文件受众。它由以下活动组成：

![](assets/identification_example2.png)

* A **[!UICONTROL Load file]** activity, which loads and detects the data of the file to import. 导入的文件包含以下数据：

   ```
   lastname;firstname;email;dateofbirth
   jackman;megan;megan.jackman@testmail.com;07/08/1975
   phillips;edward;phillips@testmail.com;09/03/1986
   weaver;justin;justin_w@testmail.com;11/15/1990
   martin;babeth;babeth_martin@testmail.net;11/25/1964
   reese;richard;rreese@testmail.com;02/08/1987
   cage;nathalie;cage.nathalie227@testmail.com;07/03/1989
   xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992
   grimes;daryl;daryl_890@testmail.com;12/06/1979
   tycoon;tyreese;tyreese_t@testmail.net;10/08/1971
   ```

* **[!UICONTROL Reconciliation]** 活动，该活动将加载文件的每一列链接到配置文件维度列。无法识别的文件记录(缺少数据、不兼容数据类型等)忽略最终受众数据的完整性。

   ![](assets/identification_example1.png)

* **[!UICONTROL Save audience]** 可保存档案受众的活动。

   ![](assets/identification_example3.png)

