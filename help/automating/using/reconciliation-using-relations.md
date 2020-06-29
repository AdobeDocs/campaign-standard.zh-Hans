---
title: 使用关系进行数据协调
description: 以下示例演示了一个使用文件中的购买数据更新数据库的工作流。
page-status-flag: never-activated
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---


# 使用关系进行数据协调 {#reconciliation-relations}

以下示例演示了一个使用文件中的购买数据更新数据库的工作流。 采购数据包含引用其他维度元素的数据，如客户电子邮件和产品代码。

>[!NOTE]
>
>默 **认情** 况下 **，此示例中** 使用的Transactions和Products资源在Adobe Campaign库中不存在。 因此，它们是使用“自定义资源” [功能预先创](../../developing/using/data-model-concepts.md) 建的。 与导入文件中的电子邮件地址以及产品对应的用户档案会预先加载到数据库中。

工作流由以下活动组成：

![](assets/reconciliation_example1.png)

* 加 [载文件活动](../../automating/using/load-file.md) ，它加载并检测要导入的文件的数据。 导入的文件包含以下数据：

   * 交易日期
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

* 一种 [协调活动](../../automating/using/reconciliation.md) ，用于将购买数据绑定到数据库用户档案和产品。 因此，有必要定义文件数据与用户档案表以及产品表之间的关系。 此配置在活动的选项卡中执 **[!UICONTROL Relations]** 行：

   * 与用户档案的 **关系**: 文件的 **client** 列链接到 **“用户档案”** 维的 **email** 字段。
   * 与产品的 **关系**: 文件的 **product** column链接到 **用户档案维** 的product **Code** 字段。
   列将添加到入站数据中以引用链接维的外键。

   ![](assets/reconciliation_example3.png)

* “更 [新数据](../../automating/using/update-data.md) ”活动允许您定义要使用导入的数据进行更新的数据库字段。 由于数据已在上一活动中被标识为 **属于** “事务”维，因此您可以在此使用 **[!UICONTROL Directly using the targeting dimension]** 标识选项。

   通过使用自动检测要更新的字段的选项，将之前活动中配置的链接(到用户档案和产品)添加到列表 **[!UICONTROL Fields to update]**。 您还必须确保与事务处理日期对应的字段正确添加到此列表。

   ![](assets/reconciliation_example5.png)

   ![](assets/reconciliation_example4.png)
