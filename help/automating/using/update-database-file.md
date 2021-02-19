---
solution: Campaign Standard
product: campaign
title: 使用外部数据更新数据库
description: 此用例说明如何使用从文件恢复的用户档案向Adobe Campaign数据库添加或更新数据。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: writer,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 33%

---


# 使用外部数据更新数据库 {#update-database-file}

以下示例显示了&#x200B;**[!UICONTROL Load file]**&#x200B;活动后&#x200B;**[!UICONTROL Update data]**&#x200B;活动的配置。 此工作流的目标，是使用从文件取回的数据，向 Adobe Campaign 数据库添加或用户档案。

在此示例中，使用的合并关键项是&#x200B;**电子邮件地址**。 在[加载文件](../../automating/using/load-file.md)活动中加载的文件是包含以下示例数据的&#x200B;**.txt**&#x200B;格式文件：

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

[更新数据](../../automating/using/update-data.md)活动的配置如下：

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)
