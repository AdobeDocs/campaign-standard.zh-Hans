---
title: 从文件更新多个订阅状态
description: 此用例说明如何导入包含用户档案的文件，并将其订阅更新为文件中指定的多个服务。
page-status-flag: never-activated
uuid: 56637024-15ab-4145-9c48-3fbd27ab8af8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 74a6df0e-fd85-4404-a42c-9a7406512717
context-tags: setOfService,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 0%

---


# 从文件更新多个订阅状态 {#updating-multiple-subscription-statuses-from-a-file}

此示例说明如何导入包含用户档案的文件，并将其订阅更新为文件中指定的多个服务。 导入文件后，需要执行协调，以便将导入的数据标识为具有指向服务的链接的用户档案。 为确保文件不包含任何重复，将对数据执行外部重复数据删除活动。

工作流如下所示：

![](assets/subscription_activity_example1.png)

* “加 [载文件](../../automating/using/load-file.md) ”活动加载用户档案文件并定义导入列的结构。

   在此示例中，加载的文件采用。csv格式并包含以下数据：

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

   如您所注意的，该操作在文件中指定为“sub”或“nims”。 系统需要一个 **布尔** 或整 **数值来** 识别要执行的操作： “0”取消订阅，“1”取消订阅。 为满足此要求，将在“操作”列的详细信息中执行值的重新映射。

   ![](assets/subscription_example_remapping.png)

   如果文件已使用“0”和“1”来标识操作，则无需重新映射这些值。 仅确保在选项卡中将列作为 **布尔****或整数** 进行 **[!UICONTROL Column definition]** 处理。

* 协调 [活动](../../automating/using/reconciliation.md) 将文件中的数据标识为属于Adobe Campaign库的用户档案维。 通过选 **[!UICONTROL Identification]** 项卡， **文件的电子邮件** 字段与用户档案资 **源的电** 子邮件字段匹配。

   ![](assets/subscription_activity_example3.png)

   在选 **[!UICONTROL Relations]** 项卡中，将使用服务资源创建一个链接，以允 **许** 识别文件的服务字段。 在此示例中，这些值与服务 **资源** 的名称字段匹配。

   ![](assets/subscription_example_service_relation.png)

* 基 [于临](../../automating/using/deduplication.md) 时资 **源** （由对帐产生）的电子邮件字段的外部重复数据删除标识重复。 消除重复很重要，因为在出现重复时，对服务的订阅将对所有数据失败。

   ![](assets/subscription_activity_example5.png)

* 订阅服务 [](../../automating/using/subscription-services.md) 活动通过在活动中创建的链接，将要更新的服务标识为来自过渡的 **[!UICONTROL Reconciliation]** 服务。

   该 **[!UICONTROL Operation type]** 文件标识为来自 **文件** 的操作字段。 此处只能选择布尔或整数字段。 如果列表中未显示包含要执行的操作的文件列，请确保已在活动中正确设置列格式，如本例前面所述。 **[!UICONTROL Load file]**

   ![](assets/subscription_activity_example_from_file.png)
