---
title: 使用协调进行数据更新
description: 下方的示例演示了直接从包含新客户的导入文件创建受众轮廓的工作流。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: cfca6202-791d-4baf-b5ed-677d2480cf06
TQID: 'https://experienceleague.adobe.com/cEXfESw1LZcrQVlLsgrlDB8J2aGz4zCoSUrIAshECo0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 49%
---
# 使用协调进行数据更新 {#data-update-reconciliation}

下方的示例演示了直接从包含新客户的导入文件创建受众轮廓的工作流。 该工作流由以下活动组成：

![](assets/identification_example2.png)

* [加载文件](../../automating/using/load-file.md)活动，用于加载并检测导入文件的数据。 导入的文件包含以下数据：

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

* [协调](../../automating/using/reconciliation.md)活动，用于将加载文件的每个列链接到用户档案维度列。 无法识别的文件记录（缺少数据、数据类型不兼容等） 将被忽略，以保持最终受众数据的完整性。

  ![](assets/identification_example1.png)

* [保存受众](../../automating/using/save-audience.md)活动，用于保存用户档案的受众。

  ![](assets/identification_example3.png)
