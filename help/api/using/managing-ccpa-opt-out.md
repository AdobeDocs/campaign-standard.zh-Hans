---
title: 管理 CCPA 选择退出
description: 了解如何使用API管理CCPA退出
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 9240686a36146b45de6dfd07fc50a71fab663001
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 4%

---


# 管理 CCPA 选择退出 {#managing-ccpa-optout}

用户档案的CCPA退出状态可以使用ccpaOptOut **用户档案属性和“true** ”或“false”值进行监视和管理：

`"ccpaOptOut": <value>`

* **true**: 禁止销售个人信息。
* **false**:授权销售个人信息。

>[!CAUTION]
>
>“CCPA退出”属性仅从19.4开始可用。对于19.3环境，您需要扩展用户档案资源并添加一个布尔字段。 此字段将添加到API中并带有所选标签。 我们建议您使用“CCPA退出”。
>
>有关此方面的详细信息，请参阅 [管理隐私请求文档](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa)。

<br/>

***示例请求***

* 检索GET的CCPA退出状态的示例用户档案请求。

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   ```

   响应GET请求。

   ```
   {
   "PKey": "<PKEY>",
     "ccpaOptOut": false,
     "firstName": "John",
     "lastName": "Doe",
   ...
   }
   ```

* 示例POST请求，用于标记CCPA选择退出的用户档案。

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/ \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   -i
   -d {
   -d  "firstName": "John",
   -d  "lastName": "Doe",
   -d  "email": "jdoe@mail.com",
   -d  "ccpaOptOut": true
   -d }'
   ```

   响应GET请求。

   ```
   {
       ...
       "email": "john.doe@mail.com",
       "firstName": "John",
       "lastName": "Doe",
       "ccpaOptOut": true,
       ...
   }
   ```

* PATCH请求示例，用于更新CCPA选择退出的用户档案。

   ```
   -X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   -i
   -d {
   -d  "ccpaOptOut": true
   -d }'
   ```

   响应GET请求。

   ```
   {
       ...
       "email": "john.doe@mail.com",
       "firstName": "John",
       "lastName": "Doe",
       "ccpaOptOut": true,
       ...
   }
   ```
