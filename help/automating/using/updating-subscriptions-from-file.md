---
title: 从文件更新多个订阅状态
description: 此用例展示了如何导入包含用户档案的文件，并将其订阅更新为文件中指定的多项服务。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: setOfService,workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 2e98561a-97fd-483a-a547-c4e6d33993dc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 77%

---

# 从文件更新多个订阅状态 {#updating-multiple-subscription-statuses-from-a-file}

此示例说明如何导入包含用户档案的文件，并将其订阅更新为文件中指定的多项服务。导入文件后，需要执行协调，以便将导入的数据标识为带服务链接的用户档案。为确保文件不包含任何重复项，将对数据执行重复数据删除活动。

其工作流如下所示：

![](assets/subscription_activity_example1.png)

* A [加载文件](../../automating/using/load-file.md) 活动加载用户档案文件并定义导入列的结构。

  在本例中，加载的文件采用 .csv 格式并包含以下数据：

  ```
  lastname;firstname;email;birthdate;service;operation
  jackman;megan;megan.jackman@testmail.com;07/08/1975;SVC2;sub
  phillips;edward;phillips@testmail.com;09/03/1986;SVC3;unsub
  weaver;justin;justin_w@testmail.com;11/15/1990;SVC3;sub
  martin;babeth;babeth_martin@testmail.net;11/25/1964;SVC3;unsub
  reese;richard;rreese@testmail.com;02/08/1987;SVC3;sub
  cage;nathalie;cage.nathalie227@testmail.com;07/03/1989;SVC3;sub
  xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992;SVC4;sub
  grimes;daryl;daryl_890@testmail.com;12/06/1979;SVC3;unsub
  tycoon;tyreese;tyreese_t@testmail.net;10/08/1971;SVC2;sub
  ```

  ![](assets/subscription_example_load_file.png)

  如您所见，文件中的操作为“订阅”或“退订”。系统需要 **Boolean** 或 **Integer** 值以识别要执行的操作：“0”代表退订，“1”代表订阅。为满足此要求，将在“operation”列的详情中执行重映射值的操作。

  ![](assets/subscription_example_remapping.png)

  如果文件已使用“0”和“1”来标识操作，则无需重映射这些值。在 **[!UICONTROL Column definition]** 选项卡中确保仅将该列作为 **Boolean** 或 **Integer** 进行处理。

* A [调解](../../automating/using/reconciliation.md) 活动标识来自文件的数据，使其归属至Adobe Campaign数据库的用户档案维度。 通过 **[!UICONTROL Identification]** 选项卡，将文件的 **email** 字段与用户档案资源的 **email** 字段匹配。

  ![](assets/subscription_activity_example3.png)

  在 **[!UICONTROL Relations]** 选项卡中，使用服务资源创建一个链接，以识别文件的 **service** 字段。在本例中，这些值与服务资源的 **name** 字段匹配。

  ![](assets/subscription_example_service_relation.png)

* A [删除重复项](../../automating/using/deduplication.md) 基于 **电子邮件** 临时资源的字段（由协调产生）标识重复项。 消除重复项很重要，因为如果存在重复项，则所有数据的服务订阅都将失败。

  ![](assets/subscription_activity_example5.png)

* A [订阅服务](../../automating/using/subscription-services.md) 活动标识要更新的服务来自过渡，通过在中创建的链接 **[!UICONTROL Reconciliation]** 活动。

  将 **[!UICONTROL Operation type]** 标识为来自文件的 **operation** 字段。此处只能选择 Boolean 或 Integer 字段。如果列表中未显示包含要执行操作的文件列，请确保已根据本例前文所述，在 **[!UICONTROL Load file]** 活动中正确设置了列格式。

  ![](assets/subscription_activity_example_from_file.png)
