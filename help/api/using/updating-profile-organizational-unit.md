---
title: 更新个人资料的组织单位
description: 了解如何使用API更新个人资料的组织单位。
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


# 更新个人资料的组织单位 {#managing-organizational-units}

1. 对orgUnitBase资源执行GET **请求** ，以检索组织单元PKey
1. 对配置文件PKey执行PATCH请求，在有效负荷中包含所需的组织单元PKey。

<br/>

***示例请求***

检索组织单位列表。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它返回所有组织单位。 检索要将配置文件分配到的设备的PKey。

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

对配置文件执行PATCH请求，有效负荷中所需组织单元的PKey。

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
