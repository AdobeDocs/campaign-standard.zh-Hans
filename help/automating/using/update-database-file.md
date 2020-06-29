---
title: 使用外部数据更新数据库
description: 此用例说明如何使用从文件恢复的用户档案向Adobe Campaign数据库添加或更新数据。
page-status-flag: never-activated
uuid: 1dc55db5-affd-4688-b673-adfb8c1338b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 4db83c95-4b75-4a16-8dbf-bd8940431fa9
context-tags: writer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 0%

---


# 使用外部数据更新数据库 {#update-database-file}

以下示例显示了活动 **[!UICONTROL Update data]** 在活动后的配 **[!UICONTROL Load file]** 置。 此工作流的目的是使用从文件恢复的用户档案向Adobe Campaign库添加或更新数据。

在此示例中，使用的合并关键项是电 **子邮件地址**。 加载文件活动中 [加载的文件](../../automating/using/load-file.md) ，是包含 **** 以下示例数据的。txt格式文件：

```
lastname;firstname;email;birthdate
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

更 [新活动](../../automating/using/update-data.md) ，如下所示：

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)
