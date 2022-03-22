---
title: 使用API创建用户档案
description: 了解如何使用API创建用户档案。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 69e8d034-6bdd-4b82-bcd7-1ef4be0a59b3
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 0%

---

# 使用API创建用户档案 {#creating-profiles-api}

使用 **POST** 请求。

>[!CAUTION]
>
>如果要关联 <b>orgUnit</b> 在创建的用户档案中，您需要使用此字段扩展用户档案资源，并在发布扩展后，对 <b>ProfileAndServicesExt</b> 端点。
>
>有关用户档案的资源扩展的更多信息，请参阅 <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">Campaign文档</a>.

<br/>

***示例请求***

使用电子邮件“john.doe@mail.com”创建用户档案的示例POST请求。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

它会返回新创建的用户档案，其中包含“john.doe@mail.com”电子邮件地址。

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
