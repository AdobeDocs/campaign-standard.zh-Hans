---
title: 使用关系进行数据协调
description: 下方的示例演示了使用文件中的购买数据更新数据库的工作流。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 7d0e3f17-ef04-4890-b63b-6957fc6cd648
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 86%

---

# 使用关系进行数据协调 {#reconciliation-relations}

下方的示例演示了使用文件中的购买数据更新数据库的工作流。购买数据包含来自其他维度的数据引用元素，例如客户电子邮件和产品代码。

>[!NOTE]
>
>默认情况下，本示例中使用的&#x200B;**交易**&#x200B;和&#x200B;**产品**&#x200B;资源并不存在于 Adobe Campaign 数据库中。因此，它们是使用[自定义资源](../../developing/using/data-model-concepts.md)功能预先创建的。与导入文件中的电子邮件地址以及产品对应的用户档案，已预先加载到数据库中。

工作流由以下活动组成：

![](assets/reconciliation_example1.png)

* A [加载文件](../../automating/using/load-file.md) 活动，用于加载并检测导入文件的数据。 导入的文件包含以下数据：

   * 交易日期
   * 客户电子邮件地址
   * 所购买产品的代码

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

* A [协调](../../automating/using/reconciliation.md) 活动，将购买数据与数据库用户档案和产品绑定。 因此，有必要定义文件数据与用户档案表以及产品表之间的关系。此配置在活动的 **[!UICONTROL Relations]** 选项卡中执行：

   * 与&#x200B;**用户档案**&#x200B;的关系：文件的 **client** 列链接到&#x200B;**用户档案**&#x200B;维度的 **email** 字段。
   * 与&#x200B;**产品**&#x200B;的关系：文件的 **product** 列链接到&#x200B;**用户档案**&#x200B;维度的 **productCode** 字段。

   将向集客数据添加列，以引用链接维度的外键。

   ![](assets/reconciliation_example3.png)

* An [更新数据](../../automating/using/update-data.md) activity允许您定义要使用导入的数据进行更新的数据库字段。 由于数据已在上一活动中被识别为归属&#x200B;**交易**&#x200B;维度，因此您可以在此使用 **[!UICONTROL Directly using the targeting dimension]** 标识选项。

   通过使用“自动检测要更新字段”的选项，将之前活动中配置的链接（到用户档案和产品）添加到 **[!UICONTROL Fields to update]** 的列表。您还必须确保将与交易日期对应的字段正确添加到此列表。

   ![](assets/reconciliation_example5.png)

   ![](assets/reconciliation_example4.png)
