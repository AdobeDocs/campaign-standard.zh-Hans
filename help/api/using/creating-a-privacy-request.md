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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 22%

---

# 创建隐私请求 {#creating-a-privacy-request}

>[!CAUTION]
>
>[隐私核心服务](https://adobe.io/apis/cloudplatform/gdpr.html)集成是您应用于所有访问和删除请求的方法。 从 19.4 版开始，将 Campaign API 和接口用于访问和删除请求的方法已被弃用。有关 Campaign Standard 的已弃用和已删除功能的详细信息，请参阅[此页面](../../rn/using/deprecated-features.md)。

使用&#x200B;**POST**&#x200B;请求创建隐私请求。

在创建请求之前，您需要定义将使用的命名空间。 有关更多信息，请参阅[隐私管理文档](https://helpx.adobe.com/cn/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)。

有效负载必须包含以下参数：

* **名称**:唯一的内部名称
* **命名空间**:在Campaign Standard界面中配置的命名空间名称
* **reconciliationValue**:基于命名空间中定义的协调键值的协调值
* **标签**:请求标签
* **类型**:请求类型。接受的值为“access”或“delete”。
* **法规**:调节类型。示例：“GDPR”、“CCPA”。 此参数是强制性的，从Campaign Standard19.4版本开始提供。 如果您使用的是较旧的内部版本，则无需将其添加到有效负载中。

<br/>

***示例请求***

此POST请求基于命名空间AMCDS2中定义的电子邮件对帐密钥创建隐私请求：

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

响应POST请求。

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
