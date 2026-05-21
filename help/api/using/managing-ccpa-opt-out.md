---
title: 管理 CCPA 选择退出
description: 了解如何使用API管理CCPA选择退出
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: bfc52511-f66f-4948-a939-d0d77e8ef03c
TQID: https://experienceleague.adobe.com/XcgCy73XQYn-JyB0N41X3n30nGGo1tHVzmn-UQ1TOJQ
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 103
ht-degree: 7%

---

# 管理 CCPA 选择退出 {#managing-ccpa-optout}

可以使用&#x200B;**ccpaOptOut**&#x200B;配置文件属性和“true”或“false”值监视和管理配置文件的CCPA选择退出状态：

`"ccpaOptOut": <value>`

* **true**：禁止销售个人信息。
* **false**：授权个人信息销售。

<!--
The “CCPA Opt-Out” attribute is only available starting 19.4. For 19.3 environments, you need to extend the Profiles resource and add a boolean field. This field will be added to the API with the chosen label. We suggest you use “Opt-Out for CCPA”.
>
>For more on this, refer to the [Managing Privacy requests documentation](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa).
-->

<br/>

***示例请求***

* 用于检索用户档案的CCPA选择退出状态的示例GET请求。

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -H 'Content-Type: application/json;charset=utf-8'
  ```

  对GET请求的响应。

  ```
  {
  "PKey": "<PKEY>",
    "ccpaOptOut": false,
    "firstName": "John",
    "lastName": "Doe",
  ...
  }
  ```

* 用于为CCPA选择退出标记配置文件的示例POST请求。

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

  对GET请求的响应。

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

* 用于更新CCPA选择退出的配置文件的示例PATCH请求。

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

  对GET请求的响应。

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
