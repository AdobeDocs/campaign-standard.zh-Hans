---
title: 使用数据库协调文件受众
description: 此示例展示了如何使用读取受众活动协调直接从文件导入创建的受众。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 6a59907d-850e-4d61-b1f7-8fc8b915580e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 87%

---

# 使用数据库协调文件受众 {#example--reconcile-a-file-audience-with-the-database}

此示例展示了如何使用 **[!UICONTROL Read audience]** 活动协调直接从文件导入创建的受众。

执行文件导入时，可以直接将其内容保存在受众中。此受众属于文件受众，其数据未链接到任何数据库资源。

导入工作流的设计如下所示：

![](assets/readaudience_activity_example3.png)

* [加载文件](../../automating/using/load-file.md)活动，上传包含从外部工具提取之用户档案数据的文件。

  例如：

  ```
  lastname;firstname;birthdate;email;crmID
  Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
  Mars;Daniel;17/11/1987;dannymars@example.com;123545
  Smith;Clara;08/02/1989;hayden.smith@example.com;124567
  Durance;Allison;15/12/1978;allison.durance@example.com;120987
  Lucassen;Jody;28/03/1988;jody.lucassen@example.com;127634
  Binder;Tom;19/01/1982;tombinder@example.com;128653
  Binder;Tommy;19/01/1915;tombinder@example.com;134576
  Connor;Jade;10/10/1979;connor.jade@example.com;132452
  Mack;Clarke;02/03/1985;clarke.mack@example.com;149876
  Ross;Timothy;04/07/1986;timross@example.com;157643
  ```

* [保存受众](../../automating/using/save-audience.md)活动，将传入数据另存为受众。由于尚未协调数据，因此该受众属于文件受众，且其数据尚未被标识为用户档案数据。

协调工作流的设计如下所示：

![](assets/readaudience_activity_example2.png)

* [读取受众](../../automating/using/read-audience.md)活动会上传在导入工作流中创建的文件受众。 其受众数据尚未与 Adobe Campaign 数据库协调。
* [协调](../../automating/using/reconciliation.md)活动，通过其 **[!UICONTROL Identification]** 选项卡将传入数据标识为用户档案。例如，使用 **email** 字段作为协调条件。
* [更新数据](../../automating/using/update-data.md)活动，使用传入数据插入并更新数据库的用户档案资源。由于数据已被标识为用户档案，因此您可以选择 **[!UICONTROL Directly using the targeting dimension]** 选项并在活动的 **[!UICONTROL Profiles]** 选项卡中选择 **[!UICONTROL Identification]**。然后，您只需在相应的选项卡中添加需要更新的字段列表即可。
