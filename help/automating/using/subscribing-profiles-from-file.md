---
title: 将用户档案从文件订阅到特定服务
description: 此用例说明如何导入包含用户档案的文件并将其订阅到现有服务。
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
source-wordcount: '238'
ht-degree: 0%

---


# 在导入文件后为特定服务订阅用户档案 {#subscribing-profiles-to-a-specific-service-after-importing-a-file}

此示例说明如何导入包含用户档案的文件并将其订阅到现有服务。 导入文件后，需要执行协调，以便将导入的数据标识为用户档案。 为确保文件不包含任何重复，将对数据执行外部重复数据删除活动。

工作流如下所示：

![](assets/subscription_activity_example1.png)

* “加 [载文件](../../automating/using/load-file.md) ”活动加载用户档案文件并定义导入列的结构。

   在此示例中，加载的文件采用。csv格式并包含以下数据：

   ```
   lastname;firstname;email;birthdate;subdate
   jackman;megan;megan.jackman@testmail.com;07/08/1975;10/08/2017
   phillips;edward;phillips@testmail.com;09/03/1986;10/08/2017
   weaver;justin;justin_w@testmail.com;11/15/1990;10/08/2017
   martin;babeth;babeth_martin@testmail.net;11/25/1964;10/08/2017
   reese;richard;rreese@testmail.com;02/08/1987;11/08/2017
   cage;nathalie;cage.nathalie227@testmail.com;07/03/1989;11/08/2017
   xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992;11/08/2017
   grimes;daryl;daryl_890@testmail.com;12/06/1979;12/08/2017
   tycoon;tyreese;tyreese_t@testmail.net;10/08/1971;12/08/2017
   ```

   ![](assets/subscription_activity_example2.png)

* 协调 [活动](../../automating/using/reconciliation.md) 将文件中的数据标识为属于Adobe Campaign库的用户档案维。 只配置 **[!UICONTROL Identification]** 了选项卡。 它根据用户档案的电子邮件地址来标识文件数据。

   ![](assets/subscription_activity_example3.png)

* 基 [于临](../../automating/using/deduplication.md) 时资 **源的** “电子邮件”字段的外部重复数据删除（由对帐产生）标识任何重复。 如果从文件导入的重复包含任何订阅，则对于所有数据，对服务的将失败。

   ![](assets/subscription_activity_example5.png)

* 订阅服务 [订阅](../../automating/using/subscription-services.md) 活动允许您选择用户档案必须订阅的服务、与订阅日期对应的字段以及订阅的来源。

   ![](assets/subscription_activity_example4.png)
