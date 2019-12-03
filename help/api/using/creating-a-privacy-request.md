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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# 创建隐私请求 {#creating-a-privacy-request}

>[!CAUTION]
>
>隐私 [核心服务集成](https://adobe.io/apis/cloudplatform/gdpr.html) ，是您应用于所有访问和删除请求的方法。 从19.4开始，不再使用Campaign API和界面访问和删除请求。 有关Campaign standard已弃用和已删除功能的详细信息，请参 [阅此页](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)。

隐私请求是使用 **POST请求创建** 的。

在创建请求之前，您需要定义要使用的命名空间。 有关详细信息，请参阅隐私 [管理文档](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)。

有效负荷必须包含以下参数：

* **name**:唯一的内部名称
* **namespace**:在Campaign standard界面中配置的命名空间名称
* **reconsiblitionValue**:基于命名空间中定义的对帐密钥的对帐值
* **label**:请求标签
* **类型**:请求类型。 接受的值为“access”或“delete”。
* **法规**:调节类型。 示例：“GDPR”、“CCPA”。 此参数是必需的，从Campaign Standard 19.4版本开始可用。 如果您使用的是较旧的版本，则无需将其添加到有效负荷中。

<br/>

***示例请求***

此POST请求基于在命名空间AMCDS2中定义的电子邮件对帐密钥创建隐私请求：

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

对POST请求的答复。

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
