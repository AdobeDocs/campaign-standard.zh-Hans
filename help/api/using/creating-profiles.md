---
solution: Campaign Standard
product: campaign
title: 创建用户档案
description: 了解更多如何使用API创建用户档案。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: 数据工程师
level: 富有经验
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 4%

---


# 创建用户档案 {#creating-profiles}

创建用户档案是使用用户档案资源上的&#x200B;**POST**&#x200B;请求执行的。

>[!CAUTION]
>
>如果要将<b>orgUnit</b>关联到创建的用户档案，您需要将用户档案资源与此字段扩展，并在发布扩展后，对<b>ProfileAndServicesExt</b>端点执行POST请求。
>
>有关用户档案资源扩展的详细信息，请参阅<a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">活动文档</a>。

<br/>

***示例请求***

使用电子邮件“john.doe@mail.com”创建POST的示例用户档案请求。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

它将返回新创建的用户档案，并带有“john.doe@mail.com”电子邮件地址。

```
{
    "PKey": "<PKEY>",
    "firstName": "John",
    "lastName":"Doe",
    "birthDate": "1980-10-24",
    "email": "john.doe@mail.com",
    ...
}
```
