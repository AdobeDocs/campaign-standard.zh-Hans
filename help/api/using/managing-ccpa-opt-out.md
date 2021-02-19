---
solution: Campaign Standard
product: campaign
title: 管理 CCPA 选择退出
description: 了解如何使用API管理CCPA退出
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 4%

---


# 管理 CCPA 选择退出 {#managing-ccpa-optout}

可以使用&#x200B;**ccpaOptOut**&#x200B;用户档案属性和“true”或“false”值监视和管理用户档案的CCPA退出状态：

`"ccpaOptOut": <value>`

* **true**:禁止销售个人信息。
* **false**:授权销售个人信息。

>[!CAUTION]
>
>“CCPA退出”属性仅从19.4开始可用。对于19.3环境，您需要扩展用户档案资源并添加一个布尔字段。 此字段将添加到具有所选标签的API。 我们建议您使用“选择退出CCPA”。
>
>有关详细信息，请参阅[管理隐私请求文档](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa)。

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

* 标记CCPA选择退出用户档案的POST请求示例。

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

* 更新CCPA选择退出用户档案的PATCH请求示例。

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
