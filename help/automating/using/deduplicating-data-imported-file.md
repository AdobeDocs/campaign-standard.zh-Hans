---
title: 从导入的文件中删除数据重复项
description: 此示例说明如何在将数据加载到数据库之前，从导入的文件中删除重复数据。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 631eb661-a696-4352-aa58-9097b391723e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 83%

---

# 从导入的文件中删除数据重复项 {#deduplicating-the-data-from-an-imported-file}

此示例展示了如何在将数据加载到数据库之前，删除导入文件中的数据重复项。此过程可提高数据库加载数据的质量。

该工作流由以下步骤组成：

![](assets/deduplication_example2_workflow.png)

* 使用[加载文件](../../automating/using/load-file.md)活动导入了包含用户档案列表的文件。 在本例中，导入的文件为 .csv 格式，且包含 10 个用户档案：

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

  此文件还可用作检测和定义列格式的样例文件。在 **[!UICONTROL Column definition]** 选项卡中，确保已正确配置导入文件的每个列。

  ![](assets/deduplication_example2_fileloading.png)

* [重复数据删除](../../automating/using/deduplication.md)活动。 在导入文件后及将数据插入数据库之前，直接执行重复数据删除。这样，即可使用来自 **[!UICONTROL Load file]** 的 **[!UICONTROL Temporary resource]** 数据，以其为基础执行重复数据删除。

  在本例中，我们希望对文件中包含的每个唯一电子邮件地址保留一个条目。因此，应对临时资源的 **email** 列执行重复项识别。现在，两个相同的电子邮件地址会在文件中显示两次。此时，这两行将被视为重复项。

  ![](assets/deduplication_example2_dedup.png)

* 通过[更新数据](../../automating/using/update-data.md)活动，可将重复数据删除流程中保留的数据插入数据库。 只有在更新数据时，导入的数据才会被标识为属于用户档案维度。

  在此，我们希望 **[!UICONTROL Insert only]** 数据库中不存在的数据。我们将使用文件的电子邮件列和&#x200B;**用户档案**&#x200B;维度中的 email 字段作为协调键，以执行此操作。

  ![](assets/deduplication_example2_writer1.png)

  从 **[!UICONTROL Fields to update]** 选项卡中指定要插入数据的文件列与数据库字段之间的映射。

  ![](assets/deduplication_example2_writer2.png)

然后，启动工作流。接下来，在重复数据删除流程保存的记录，将被添加到数据库中的用户档案。
