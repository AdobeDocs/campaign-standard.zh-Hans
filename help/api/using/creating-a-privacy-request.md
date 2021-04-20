---
solution: Campaign Standard
product: campaign
title: 创建隐私请求
description: 了解如何使用API创建隐私请求
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 7%

---


# 创建隐私请求 {#creating-a-privacy-request}

>[!CAUTION]
>
>[隐私核心服务](https://adobe.io/apis/cloudplatform/gdpr.html)集成是您应用于所有访问和删除请求的方法。 从19.4开始，已不建议使用活动 API和接口访问和删除请求。 有关已弃用和已删除Campaign Standard功能的详细信息，请参阅[此页](../../rn/using/deprecated-features.md)。

使用&#x200B;**POST**&#x200B;请求创建隐私请求。

在创建请求之前，您需要定义要使用的命名空间。 有关详细信息，请参阅[隐私管理文档](https://helpx.adobe.com/cn/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)。

负载必须包含以下参数：

* **name**:唯一的内部名称
* **命名空间**:在命名空间界面中配置的Campaign Standard名称
* **reconsiblitionValue**:对帐值，基于在命名空间中定义的合并关键项
* **label**:请求标签
* **类型**:请求类型。接受的值为“access”或“delete”。
* **条例**:规章类型。示例：“GDPR”、“CCPA”。 此参数为必需参数，可从Campaign Standard 19.4版开始使用。 如果您使用的是旧版本，则无需将其添加到有效负荷中。

<br/>

***示例请求***

此POST请求根据命名空间AMCDS2中定义的电子邮件合并关键项创建隐私请求：

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
