---
title: 创建服务
description: 了解如何使用API创建服务
feature: API
role: Data Engineer
level: Experienced
exl-id: 91bbce9e-a618-4be2-840b-c7d021271f4e
source-git-commit: 64f24fb692754973331b4fb2f7b95e9a6f31cd0d
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 4%

---

# 使用API创建服务{#creating-a-service-api}

通过 **POST** 请求。

如果要使用特定属性创建服务，请将其添加到有效负载中。 否则，将使用默认服务创建新服务。

<br/>

***示例请求***

用于创建具有特定属性的服务的示例POST请求。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label": "My newsletter",
-d "messageType": "email",
-d "name": "email_newsletter",
-d "start": "2019-10-06"
-d }
```

它会返回具有更新属性的新创建服务。

```
{
    "PKey": "<PKEY>",
    "builtIn": false,
    "created": "2019-09-26 12:00:37.005Z",
    "href": "https://mc.adobe.io/<ORGANIZATION>/profileAndServices/service/@NLscZuVHxdVu9rPftvrMWFfR1zRIxQGswSOmGLrK09JTF_iWhB0JCUHEndA_vvy__k9mzOYa5NVkcWDcrK8qGh0wygahX9kRcD44kiWWSEceShn3",
    "label": "My newsletter",
    ...
}
```
