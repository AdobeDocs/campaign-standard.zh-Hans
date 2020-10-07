---
title: 创建用户档案
description: 进一步了解如何使用API创建用户档案。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 3%

---


# 创建用户档案 {#creating-profiles}

创建用户档案时会对 **用户档案** 资源发出POST请求。

>[!CAUTION]
>
>如果要将orgUnit与创 <b>建的用户档案关联</b> ，您需要将用户档案资源与此字段扩展，并在发布扩展后，对ProfileAndServicesExt端点执行 <b>POST请求</b> 。
>
>有关用户档案资源扩展的详细信息，请参阅 <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">活动文档</a>。

<br/>

***示例请求***

POST请求示例：使用电子邮件“john.doe@mail.com”创建用户档案。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

它返回新创建的用户档案，其电子邮件地址为“john.doe@mail.com”。

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
