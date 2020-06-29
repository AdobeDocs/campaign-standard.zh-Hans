---
title: 协调文件受众与数据库
description: 此示例说明如何使用读取受众活动协调直接从文件导入创建的受众。
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 0%

---


# 协调文件受众与数据库 {#example--reconcile-a-file-audience-with-the-database}

此示例说明如何使用活动 **[!UICONTROL Read audience]** 协调直接从文件导入创建的受众。

执行文件导入时，可以直接将其内容保存在受众中。 此受众是文件受众，其数据未链接到任何数据库资源。

导入工作流的设计如下：

![](assets/readaudience_activity_example3.png)

* 加载 [文件活动](../../automating/using/load-file.md) ，上传包含从外部工具提取的用户档案数据的文件。

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

* “保 [存受众](../../automating/using/save-audience.md) ”活动将传入数据另存为受众。 由于受众尚未协调，因此该受众是文件，其数据尚未被识别为用户档案数据。

协调工作流的设计如下：

![](assets/readaudience_activity_example2.png)

* 读取 [受众](../../automating/using/read-audience.md) 活动将上传在导入工作流中创建的文件受众。 受众数据尚未与Adobe Campaign数据库协调。
* 对帐 [活动](../../automating/using/reconciliation.md) 通过其选项卡将传入数据标识为 **[!UICONTROL Identification]** 用户档案。 例如，使用电子邮件 **字段** 作为对帐标准。
* “更 [新活动](../../automating/using/update-data.md) ”会插入用户档案资源并用传入数据更新数据库的资源。 由于用户档案已标识为活动，因此您可以选 **[!UICONTROL Directly using the targeting dimension]** 择选项并 **[!UICONTROL Profiles]** 在该 **[!UICONTROL Identification]** 的选项卡中选择。 然后，您只需根据选项卡添加需要更新的字段列表。
