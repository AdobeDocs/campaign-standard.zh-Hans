---
solution: Campaign Standard
product: campaign
title: 更新用户档案的组织单位
description: 了解如何使用API更新用户档案的组织单位。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: 数据工程师
level: 富有经验
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 11%

---


# 更新用户档案的组织单位 {#managing-organizational-units}

1. 对&#x200B;**orgUnitBase**&#x200B;资源执行GET请求以检索组织单元PKey
1. 对用户档案PKey执行PATCH请求，并在有效负荷中使用所需的组织单位PKey。

<br/>

***示例请求***

检索组织单位的列表。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它返回所有组织单位。 检索要向其分配用户档案的单元的PKey。

```
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "",
  "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
  "label": "Brand 4",
  "lastModified": "2019-04-03 07:34:56.579Z",
  "name": "brand4",
  "parentTitle": "All (all)",
  "title": "Brand 4 (brand1)"
},
```

对用户档案执行PATCH请求，有效负荷中所需组织单位的PKey。

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "orgUnit":{
-d    "PKey":"<PKEY>"
-d  }
-d }
```

<!-- + réponse -->
