---
title: 创建隐私请求
description: 了解如何使用API创建隐私请求
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 8%

---


# 创建隐私请求 {#creating-a-privacy-request}

>[!CAUTION]
>
>隐私 [核心服务集成](https://adobe.io/apis/cloudplatform/gdpr.html) ，是您应用于所有访问和删除请求的方法。 从19.4开始，已弃用活动API和接口访问和删除请求。 有关Campaign Standard已弃用和已删除功能的详细信息，请 [参阅此页](https://helpx.adobe.com/cn/campaign/kb/acs-deprecated-and-removed-features.html)。

隐私请求是使用POST请 **求创** 建的。

在创建请求之前，您需要定义要使用的命名空间。 有关此内容的详细信息，请参 [阅隐私管理文档](https://helpx.adobe.com/cn/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)。

有效负荷必须包含以下参数：

* **name**:唯一的内部名称
* **命名空间**:命名空间接口中配置的Campaign Standard名称
* **anjolicationValue**:对帐值，此对帐值基于在合并关键项中定义的命名空间
* **标签**:请求标签
* **类型**:请求类型。 接受的值为“access”或“delete”。
* **法规**:调节类型。 示例：“GDPR”、“CCPA”。 此参数为必需参数，从Campaign Standard19.4版开始可用。 如果您使用的是旧版本，则无需将其添加到有效负荷中。

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
