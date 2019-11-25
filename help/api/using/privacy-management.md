---
title: 隐私管理
description: 进一步了解使用API进行隐私管理
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
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# 隐私管理 {#privacy-management}

Campaign Standard API提供允许自动处理与隐私法规（如GDPR和CCPA）相关的请求的功能。

您可以执行的操作如下：

* 创建新的隐私请求，
* 监控隐私请求，
* 检索隐私数据文件，
* 管理配置文件的CCPA退出状态。

隐私API端点是 **/privacy/privacyTool**。 PrivacyTool资源说明和关联的筛选器在资源元数据中可用。 请参阅 [元数据机制](../../api/using/metadata-mechanism.md)。

CCPA退出是使用ccpaOptOut配置文件属 **性管理的** 。

有关Adobe Campaign standard和隐私合规性的更多信息，请参阅专 [用文档](https://helpx.adobe.com/campaign/kb/acs-privacy.html)。

## 创建隐私请求 {#creating-a-privacy-request}

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

## 监视隐私请求

您可以使用 **GET请求监视有关已创建隐私请求的信** 息。

状态列表说明可在隐私管理文 [档中找到](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)。

<br/>

***示例请求***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>'
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'
```

对GET请求的响应。

```
{
            "PKey": "<PKEY>",
            "audit": "",
            "created": "2018-03-09 12:28:37.319Z",
            "desc": "",
            "gdprRequestData": {
                "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>/gdprRequestData/"
            },
            "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>",
            "label": "Delete customer profile",
            "lastModified": "2018-03-09 12:39:21.232Z",
            "name": "GDPR6",
            "namespace": {
                "PKey": "<PKEY>",
                "title": "Email (defaultNamespace1)"
            },
            "namespaceName": "defaultNamespace1",
            "reconciliationValue": "customers@adobe.com",
            "regulation": "gdpr",
            "retryCount": 0,
            "status": "errorDataNotFound",
            "title": "Delete customer profile (GDPR6)",
            "type": "delete"
        }
```

## 检索隐私数据文件

>[!CAUTION]
>
>隐私 [核心服务集成](https://adobe.io/apis/cloudplatform/gdpr.html) ，是您应用于所有访问和删除请求的方法。 从19.4开始，不再使用Campaign API和界面访问和删除请求。 有关Campaign standard已弃用和已删除功能的详细信息，请参 [阅此页](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)。

要检索包含与对帐值关联的所有信息的文件，请按照以下三个步骤操作：

1. 执行 **POST** request to create a new request with attribute **type="access"**，请参阅 [Creating a new privacy request](#creating-a-privacy-request)。

1. 执行 **GET** request以检索有关该请求的信息。

1. 通过对返回的 **privacyRequestData** URL执行 **** POST请求（在有效负荷中包含隐私请求内部名称）来检索数据文件。 例如：{"name":"PT17"}。

<br/>

***示例请求***

使用type="access"属性创建隐私请求。

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
"type":"access"
}
```

<!-- + réponse -->

执行GET请求以检索有关该请求的信息。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'
```

它返回具有关联URL的privacyRequestData属性。

```
{
    ...
    "name": "PR2",
    "namespace": ...,
    "namespaceName": "defaultNamespace1",
    "privacyRequestData": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>/privacyRequestData/"
    },
    "reconciliationValue": "johndoe@mail.com",
    "regulation": "gdpr",
    "retryCount": 0,
    "status": "complete",
    "title": "EPR (PR2)",
    "type": "access"
    ...
},
```

对privacyRequestData URL执行POST请求，有效负荷中包含请求内部名称。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>/privacyRequestData \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'
-d '{"name": "PR1"}'
```

它返回文件内容。

```
"{data:<gdprRequestData _cs=\" ()\" id=\"8565163\" reconciliationValue=\"'customer@adobe.com'\">\n  <table name=\"nms:recipient\">\n    <rowId='8569152'\n\t\tlastName='customer'\n\t\tfirstName='customer'\n\t\tgender='1'\n\t\temail='customer@adobe.com'\n\t\tcreatedBy-id='8565162'\n\t\tmodifiedBy-id='8565162'\n\t\tlastModified='2018-03-15 13:54:28.708Z'\n\t\tcreated='2018-03-15 13:54:28.708Z'\n\t\tthumbnail='/nl/img/thumbnails/defaultProfil.png'\n\t\temailFormat='2'</row>\n  </table>\n  <table name=\"nms:broadLogRcp\">\n    <row>deliveryLabel='Send via email'\n\t\tdeliveryType='0'\n\t\tcontactDate='2018-03-15 13:58:31.667Z'\n\t\tid='8003'\n\t\taddress='customer@adobe.com'\n\t\tstatus='1'\n\t\tmsg-id='1194'\n\t\teventDate='2018-03-15 13:58:34.726Z'\n\t\tlastModified='2018-03-15 13:59:02.008Z'\n\t\tvariant='default'\n\t\tdelivery-id='8569153'\n\t\tpublicId='1'\n\t\tprofile-id='8569152'</row>\n  </table>\n  <table name=\"nms:trackingLogRcp\">\n    <row>deliveryLabel='Send via email'\n\t\tdeliveryType='0'\n\t\tcontactDate='2018-03-15 13:58:31.667Z'\n\t\turlLabel='Open'\n\t\turlSource=''\n\t\tuserAgent='-1178080215'\n\t\ttrackedDevice='pc'\n\t\tid='5000'\n\t\tlogDate='2018-03-15 14:00:51.650Z'\n\t\tsourceType='html'\n\t\tuserAgent='-1178080215'\n\t\turl-id='1'\n\t\tdelivery-id='8569153'\n\t\tbroadLog-id='8003'\n\t\trecipient-id='8569152'</row>\n    <row>deliveryLabel='Send via email'\n\t\tdeliveryType='0'\n\t\tcontactDate='2018-03-15 13:58:31.667Z'\n\t\turlLabel='Open'\n\t\turlSource=''\n\t\tuserAgent='0'\n\t\ttrackedDevice=''\n\t\tid='6000'\n\t\tlogDate='2018-03-15 16:00:41.110Z'\n\t\tsourceType='html'\n\t\turl-id='1'\n\t\tdelivery-id='8569153'\n\t\tbroadLog-id='8003'\n\t\trecipient-id='8569152'</row>\n  </table>\n</gdprRequestData>}"
```

## 管理CCPA退出

可以使用 **** ccpaOptOut配置文件属性和“true”或“false”值监视和管理配置文件的CCPA退出状态：

`"ccpaOptOut": <value>`

* **true**: 禁止销售个人信息。
* **false**:授权销售个人信息。

>[!CAUTION]
>
>“CCPA退出”属性仅从19.4开始可用。对于19.3环境，您需要扩展配置文件资源并添加一个布尔字段。 此字段将添加到API中，并带有所选标签。 我们建议您使用“CCPA退出”。
>
>有关详细信息，请参阅隐私 [管理文档](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa)。

<br/>

***示例请求***

* 检索配置文件CCPA退出状态的示例GET请求。

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

* 标记CCPA退出配置文件的POST请求示例。

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
