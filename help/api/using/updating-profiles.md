---
title: 更新用户档案
description: 了解更多如何使用API更新用户档案
feature: API
role: Data Engineer
level: Experienced
exl-id: fa3796ee-a00c-4d70-bf3d-e8d2099f1116
source-git-commit: 64f24fb692754973331b4fb2f7b95e9a6f31cd0d
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 2%

---

# 使用API更新用户档案{#updating-profiles-api}

使用 **PATCH** 请求。

`https://mc.adobe.io/<ORGANIZATION>/campaign/<apiName>/<resourceName>/<PKEY>`

1. 第一步是 **检索用户档案**.

1. 在第二个请求中，执行 **PATCH请求** 包含有效负载中已完成信息的用户档案。

1. 要检查PATCH请求是否更新了用户档案，我们可以执行最终GET请求。

<br/>

***示例请求***

用于检索用户档案的GET请求示例。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

响应请求。

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "Amy",
            "lastName":"Dakota",
            "birthDate": "1980-10-24",
            ...
        }
    ]
}
```

PATCH请求更新“phone”属性。

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-d '{"phone":"3301020304"}'
```

它会返回PKEY和URL以检索更新的用户档案。

```
{
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/@2v1dr3ZKJveMDhAdh0MPnh9hNQQ93qb7AW6BNVVKknjwXvTZRBAgUqz1SNcB4ZndgjqOofx3BwBZYBftlmObISoM3rs"
}
```
