---
title: 管理事务型消息
description: 了解如何使用API管理事务型消息。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 00d39438-a232-49f1-ae5e-1e98c73397e3
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 3%

---

# 管理事务型消息 {#managing-transactional-messages}

## 关于事务性消息传递

创建并发布事务型事件后，您需要将此事件的触发集成到您的网站中。

>[!NOTE]
>
>有关配置事件的信息，请参见[此部分](../../channels/using/configuring-transactional-event.md)。

例如，您希望每当您的一位客户在购买购物车中的产品之前离开您的网站时，都触发“购物车放弃”事件。 要实现此目的，您的Web开发人员必须使用REST事务型消息API。

1. 开发人员根据POST方法发送请求，该方法将触发事务事件](#sending-a-transactional-event)的[发送。
1. 对POST请求的响应包含主密钥，该密钥允许开发人员通过GET请求发送一个或多个请求。 这样，他便能够获得[事件状态](#transactional-event-status)。

## 发送事务型事件 {#sending-a-transactional-event}

事务性事件通过具有以下URL结构的POST请求发送：

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;organization>**:您的个人组织ID。请参阅[此小节](../../api/using/must-read.md)。

* **&lt;transactionalapi>**:事务型消息API endPoint。

   事务型消息API端点的名称取决于您的实例配置。 它对应于值“mc”后跟您的个人组织ID。 让我们以Geometrixx公司为例，将“geometrixx”作为其组织ID。 在这种情况下，POST请求如下：

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   （请注意，在API预览期间，事务型消息API端点也可见）

* **&lt;eventid>**:要发送的事件类型。此ID在创建事件配置时生成（请参阅[此部分](../../channels/using/configuring-transactional-event.md#creating-an-event)）。

### POST请求标头

请求必须包含“Content-Type:application/json”标头。

必须添加字符集，例如&#x200B;**utf-8**。 请注意，此值取决于您所使用的REST应用程序。

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### POST请求正文

事件数据包含在JSONPOST正文中。 事件结构取决于其定义。 资源定义屏幕中的API预览按钮提供了一个请求示例。 请参阅[此小节](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

可以将以下可选参数添加到事件内容中，以管理链接到事件的事务型消息的发送：

* **过期** （可选）：在此日期之后，将取消事务性事件的发送。
* **已计划** （可选）：从此日期开始，将处理事务型事件并发送事务型消息。

>[!NOTE]
>
>“到期”和“计划”参数的值遵循ISO 8601格式。 ISO 8601指定使用大写字母“T”来分隔日期和时间。 但是，可以从输入或输出中删除它，以便更好地阅读。

### 响应POST请求

POST响应会返回创建事务型事件时的事务型事件状态。 要检索其当前状态（事件数据、事件状态……），请在GET请求中使用POST响应返回的主键：

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***示例请求***

POST发送事件的请求。

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

### 事务性事件状态 {#transactional-event-status}

在响应中，“状态”字段允许您知道事件是否已处理：

* **待处理**:事件处于待处理状态 — 事件在刚触发时会启用此状态。
* **处理**:事件处于待投放状态 — 它将转换为消息并发送消息。
* **暂停**:事件进程正在暂停。系统将不再处理该数据，而是将其保留在Adobe Campaign数据库的队列中。 如需详细信息，请参阅[此部分](../../channels/using/publishing-transactional-message.md#suspending-a-transactional-message-publication)。
* **已处理**:已处理事件并成功发送消息。
* **忽略**:投放会忽略该事件，通常是在地址处于隔离状态时。
* **deliveryFailed**:处理事件时发生投放错误。
* **routingFailed**:路由阶段失败 — 例如，当找不到指定的事件类型时，可能会发生这种情况。
* **tooOld**:该事件在能够处理之前过期 — 这可能由于各种原因而发生，例如，发送失败多次（这会导致事件不再为最新状态）或服务器在过载后无法再处理事件。
* **targetingFailed**:Campaign Standard未能扩充用于消息定位的链接。
