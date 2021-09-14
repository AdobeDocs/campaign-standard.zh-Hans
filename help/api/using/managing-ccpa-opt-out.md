---
title: 管理 CCPA 选择退出
description: 了解如何使用API管理CCPA选择退出
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: bfc52511-f66f-4948-a939-d0d77e8ef03c
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 4%

---

# 管理 CCPA 选择退出 {#managing-ccpa-optout}

可以使用&#x200B;**ccpaOptOut**&#x200B;配置文件属性和“true”或“false”值监控和管理配置文件的CCPA选择退出状态：

`"ccpaOptOut": <value>`

* **true**:禁止出售个人信息。
* **false**:授权销售个人信息。

>[!CAUTION]
>
>“CCPA选择退出”属性仅从19.4开始可用。对于19.3环境，您需要扩展Profiles资源并添加布尔字段。 此字段将添加到具有所选标签的API中。 我们建议您使用“选择退出CCPA”。
>
>有关更多信息，请参阅[管理隐私请求文档](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa)。

<br/>

***示例请求***

* 用于检索用户档案CCPA选择退出状态的示例GET请求。

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

* 标记CCPA选择退出用户档案的示例POST请求。

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

* 用于更新CCPA选择退出用户档案的示例PATCH请求。

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
