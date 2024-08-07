---
title: 使用外部数据更新数据库
description: 此用例展示了如何使用从文件取回的数据，向Adobe Campaign数据库添加或更新用户档案。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: writer,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 2df7fbed-b979-4706-bd56-83f712cc3070
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 11%

---

# 使用外部数据更新数据库 {#update-database-file}

以下示例显示了&#x200B;**[!UICONTROL Load file]**&#x200B;活动之后&#x200B;**[!UICONTROL Update data]**&#x200B;活动的配置。 此工作流的目的是使用从文件取回的数据，向Adobe Campaign数据库添加用户档案或更新用户档案。

在此示例中，使用的协调密钥是&#x200B;**电子邮件地址**。 加载到[加载文件](../../automating/using/load-file.md)活动中的文件是包含以下示例数据的&#x200B;**.txt**&#x200B;格式文件：

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
