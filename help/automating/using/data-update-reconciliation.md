---
title: 使用协调进行数据更新
description: 下方的示例演示了直接从包含新客户的导入文件创建受众用户档案的工作流。
page-status-flag: never-activated
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliation,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 使用协调进行数据更新 {#data-update-reconciliation}

下方的示例演示了直接从包含新客户的导入文件创建受众用户档案的工作流。该工作流由以下活动组成：

![](assets/identification_example2.png)

* A [Load file](../../automating/using/load-file.md) activity, which loads and detects tshe data of the file to import. 导入的文件包含以下数据：

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

* A [Reconciliation](../../automating/using/reconciliation.md) activity, which links each column of the loaded file to a profile dimension column. 无法识别的文件记录（缺少数据、数据类型不兼容等）将被忽略，以保持最终受众数据的完整性。

   ![](assets/identification_example1.png)

* A [Save audience](../../automating/using/save-audience.md) activity, which saves the audience of profiles.

   ![](assets/identification_example3.png)
