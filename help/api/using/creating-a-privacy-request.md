---
title: 创建隐私请求
description: 了解如何使用API创建隐私请求
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 06ad2e13-922b-4f35-8726-007427125c63
source-git-commit: 4b0c4fb13cc11c06e2487e531ca96574e49b6beb
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 4%

---

# 创建隐私请求 {#creating-a-privacy-request}

>[!CAUTION]
>
>此 [隐私核心服务](https://developer.adobe.com/experience-platform-apis/references/privacy-service) “集成”是您应当用于所有访问和删除请求的方法。 <!--Starting 19.4, the use of the Campaign API and interface for access and delete requests is deprecated. For more on Campaign Standard deprecated and removed features, refer to [this page](../../rn/using/deprecated-features.md).-->

隐私请求是使用 **POST** 请求。

在创建请求之前，您需要定义将使用的命名空间。 有关更多信息，请参见 [隐私管理文档](../../start/using/privacy-requests.md).

有效负载必须包含以下参数：

* **name**：唯一的内部名称
* **命名空间**：在Campaign Standard界面中配置的命名空间名称
* **reconciliationValue**：基于命名空间中定义的协调键值的协调值
* **标签**：请求标签
* **type**：请求类型。 接受的值为“access”或“delete”。
* **法规**：法规类型。 示例：“GDPR”、“CCPA”。 此参数是必需的，从Campaign Standard19.4版本开始可用。 如果您使用的是旧版本，则无需将其添加到有效负载中。

<br/>

***示例请求***

此POST请求根据命名空间AMCDS2中定义的电子邮件对帐密钥创建一个隐私请求：

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'

{
"name":"PT11832",
"namespaceName": "AMCDS2",
"reconciliationValue": "customers@adobe.com",
"regulation": "gdpr",
"label":"Delete customers",
"type":"delete"
}
```

对POST请求的响应。

```
{
    "PKey": "<PKEY>",
    "audit": "",
    "created": "2018-03-21 10:41:58.570Z",
    "desc": "",
    "gdprRequestData": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/head/privacyTool/<PKEY>/gdprRequestData/"
    },
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>",
    "label": "Delete customers",
    "lastModified": "2018-03-21 10:41:58.570Z",
    "name": "PT11832",
    "namespace": {
        "PKey": "<PKEY>",
        "title": "Doc (AMCDS2)"
    },
    "namespaceName": "AMCDS2",
    "reconciliationValue": "customers@adobe.com",
    "regulation": "gdpr",
    "retryCount": 0,
    "status": "new",
    "title": "Delete customers (PT11832)",
    "type": "delete"
}
```
