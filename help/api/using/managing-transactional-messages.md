---
solution: Campaign Standard
product: campaign
title: 管理事务型消息
description: 了解如何使用API管理事务性消息。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 1%

---


# 管理事务型消息 {#managing-transactional-messages}

## 关于事务型消息传递

创建事件后，您必须将触发此事件的操作集成到您的网站中。

>[!NOTE]
>
>创建和发布事件在[活动文档](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html)中。

例如，您希望当您的客户之一在购买购物车中的产品之前离开您的网站时，触发“购物车废弃”事件。 为此，您的Web开发人员必须使用REST事务性消息API。

1. 开发者根据POST方法发送请求，其触发事务事件](#sending-a-transactional-event)的[发送。
1. 对POST请求的响应包含主密钥，该密钥允许开发人员通过GET请求发送一个或多个请求。 这样，他能够获得[事件状态](#transactional-event-status)。

## 发送事务事件{#sending-a-transactional-event}

事务事件通过具有以下URL结构的POST请求发送：

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;organization>**:您的个人组织ID。请参阅[此章节](../../api/using/must-read.md) 。

* **&lt;transactionalapi>**:事务性消息API endPoints。

   事务性消息API端点的名称取决于您的实例配置。 它对应于值“mc”后跟您的个人组织ID。 让我们举一个Geometrixx公司的示例，其中“geometrixx”作为其组织ID。 在这种情况下，POST请求如下：

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   (请注意，事务性消息API端点在API预览期间也可见)

* **&lt;eventid>**:要发送的事件类型。此ID是在创建事件定义时生成的。 请参阅[活动文档](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html)。

### POST请求标题

请求必须包含“Content-Type:application/json”标题。

必须添加字符集，例如&#x200B;**utf-8**。 请注意，此值取决于您使用的REST应用程序。

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### POST请求主体

事件数据包含在JSONPOST主体中。 事件结构取决于其定义。 资源定义屏幕中的API预览按钮提供请求示例。 请参阅[活动文档](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html)。

可以将以下可选参数添加到事件内容以管理链接到事件的事务性消息的发送：

* **expiration** （可选）:在此日期之后，将取消事务事件的发送。
* **scheduled** （可选）:从此日期开始，将处理事务事件并发送事务性消息。

>[!NOTE]
>
>“expiration”和“scheduled”参数的值采用ISO 8601格式。 ISO 8601指定使用大写字母“T”分隔日期和时间。 但是，可以从输入或输出中删除它，以获得更好的可读性。

### 对POST请求的响应

POST响应返回创建时的事务事件状态。 要检索其当前状态(事件数据、事件状态……)，请在GET请求中使用POST响应返回的主键：

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***示例请求***

POST请求发送事件。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/mcAdobe/EVTcartAbandonment \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79'

{
  "email":"test@example.com",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "ctx":
  {
    "cartAmount": "$ 125",
    "lastProduct": "Leather motorbike jacket",
    "firstName": "Jack"
  }
}
```

响应POST请求。

```
{
  "PKey":"<PKEY>",
  "ctx":
  {
    "cartAmount": "",
    "lastProduct": "",
    "firstName": ""
  }
  "email":"",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "href": "mcAdobe/EVTcartAbandonment/<PKEY>",
  "serverUrl":" https://myserver.com ",
  "status":"pending",
  "type":""
}
```

### 事务事件状态{#transactional-event-status}

在响应中，“状态”字段允许您了解事件是否已处理：

* **待定**:事件处于挂起状态-事件在刚触发该状态时启用该状态。
* **处理**:事件正在挂起投放-正在将其转换为消息并发送消息。
* **暂停**:事件进程正在暂停。它不再被处理，而是被保留在Adobe Campaign库的队列中。 有关详细信息，请参阅[活动文档](https://helpx.adobe.com/campaign/standard/channels/using/event-transactional-messages.html#unpublishing-a-transactional-message)。
* **已处理**:已处理事件并成功发送消息。
* **忽略**:事件被投放忽略，通常当地址处于隔离状态时。
* **deliveryFailed**:处理投放时发生事件错误。
* **routingFailed**:路由阶段失败——例如，当找不到指定的事件类型时，可能会发生这种情况。
* **tooOld**:事件在处理之前已过期——这可能由于各种原因而发生，例如，发送失败多次(这会导致事件不再为最新状态)，或者服务器在过载后无法再处理事件。
* **targetingFailed**:Campaign Standard未能扩充用于消息定位的链接。
