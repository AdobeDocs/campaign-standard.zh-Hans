---
title: 创建用户档案
description: 进一步了解如何使用API创建配置文件。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# 创建用户档案 {#creating-profiles}

创建配置文件时会对配置 **文件资源** 发出POST请求。

>[!CAUTION]
>
>如果要将 <b>orgUnit</b> 关联到创建的配置文件，您需要将配置文件资源扩展到此字段，并在发布扩展后，对 <b></b> ProfileAndServicesExt端点执行POST请求。
>
>有关配置文件的资源扩展的详细信息，请参阅 <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">Campaign文档</a>。

<br/>

***示例请求***

创建包含电子邮件“john.doe@mail.com”的个人资料的POST请求示例。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

它将返回新创建的配置文件，其中带有“john.doe@mail.com”电子邮件地址。

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
