---
title: 排序
description: 了解有关如何执行排序操作的更多信息
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 7db25b8d-a6f1-4151-bf37-c47e9991ae48
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 11%

---

# 排序

默认情况下，排序以升序方式提供。 要按降序排序，请将&#x200B;**%20desc**&#x200B;附加到&#x200B;**_order**&#x200B;参数的值。

要了解某个字段是否可以排序，请将“可排序”参数检查到资源元数据中。 如需详细信息，请参阅[此小节](../../api/using/metadata-mechanism.md)。

<br/>

***示例请求***

* 用于检索数据库中按字母顺序排序的电子邮件的示例GET请求。

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  对请求的响应。

  ```
  {
  "content": [
      "adam@email.com",
      "allison.durance@example.com",
      "amy.dakota@mail.com",
      "andrea.johnson@mail.com",
      ...
  ]
  ...
  }
  ```

* 用于以降序Alpha顺序检索数据库中的电子邮件的示例GET请求。

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email%20desc \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  对请求的响应。

  ```
  {
  "content": [
      "tombinder@example.com",
      "tombinder@example.com",
      "timross@example.com",
      "john.smith@example.com",
      ...
  ]
  }
  ```
