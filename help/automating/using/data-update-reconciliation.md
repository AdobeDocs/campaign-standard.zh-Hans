---
title: 使用协调进行数据更新
description: 以下示例演示了一个工作流，它直接从包含新客户端的导入文件创建受众用户档案。
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
source-git-commit: 175709a41607bb9d64da7fac77dd749fa84f7360
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---


# 使用协调进行数据更新 {#data-update-reconciliation}

以下示例演示了一个工作流，它直接从包含新客户端的导入文件创建受众用户档案。 它由以下活动组成：

![](assets/identification_example2.png)

* 加 [载文件活动](../../automating/using/load-file.md) ，它加载并检测要导入的文件的数据。 导入的文件包含以下数据：

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

* 一个 [对帐活动](../../automating/using/reconciliation.md) ，它将加载文件的每个列链接到一个用户档案维列。 无法识别的文件记录（缺少数据、数据类型不兼容等） 将被忽略，以保持最终受众数据的完整性。

   ![](assets/identification_example1.png)

* 保 [存受众](../../automating/using/save-audience.md) 活动，它保存用户档案的受众。

   ![](assets/identification_example3.png)
