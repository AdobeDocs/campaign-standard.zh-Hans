---
title: 从导入的文件中消除重复数据
description: 此示例说明如何在将数据加载到数据库之前从导入的文件中删除重复数据。
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
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---


# 从导入的文件中消除重复数据 {#deduplicating-the-data-from-an-imported-file}

此示例说明如何在将数据加载到数据库之前从导入的文件中删除重复数据。 此过程可提高数据库中加载的数据的质量。

该工作流由以下几部分组成：

![](assets/deduplication_example2_workflow.png)

* 包含列表用户档案的文件使用“加载文件” [活动导入](../../automating/using/load-file.md) 。 在此示例中，导入的文件采用。csv格式，包含10个用户档案:

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

* 一 [个外部重复数据删除](../../automating/using/deduplication.md) 活动。 外部重复数据删除在导入文件后和将数据插入数据库之前直接执行。 因此，它应以活动 **[!UICONTROL Temporary resource]** 的数据为 **[!UICONTROL Load file]** 基础。

   在此示例中，我们希望对文件中包含的每个唯一电子邮件地址保留一个条目。 因此，重复标识在临时 **资源** 的电子邮件列上执行。 但是，两个电子邮件地址会在文件中显示两次。 因此，两行将被视为重复。

   ![](assets/deduplication_example2_dedup.png)

* 更新 [活动](../../automating/using/update-data.md) ，允许您将外部重复数据删除过程中保留的数据插入数据库。 只有在更新数据时，导入的数据才被标识为属于用户档案维。

   在此，我们希望 **[!UICONTROL Insert only]** 用户档案库中尚未存在的数据。 我们将使用文件的电子邮件列和用户档案维中的电子邮件字段作为 **合并关键项** ，来执行此操作。

   ![](assets/deduplication_example2_writer1.png)

   从选项卡中指定要插入数据的文件列与数据库字段之间的映 **[!UICONTROL Fields to update]** 射。

   ![](assets/deduplication_example2_writer2.png)

然后开始工作流。 然后，从外部重复数据删除进程保存的记录将添加到用户档案库中的记录。
