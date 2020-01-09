---
title: 管理交易消息
description: 了解如何使用API管理事务性消息。
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
source-git-commit: 45334e2d64c31ee22f11030e19f313b3c1b49936

---


# 管理交易消息 {#managing-transactional-messages}

## 关于交易消息传递

创建活动后，您必须将此事件的触发集成到您的网站中。

>[!NOTE]
>
>创建和发布活动将在此部分 [中显示](../../administration/using/configuring-transactional-messaging.md)。

例如，您希望当您的客户之一在购买购物车中的产品之前离开您的网站时，会触发“购物车放弃”事件。 为此，您的Web开发人员必须使用REST Transactional Messages API。

1. 开发者根据POST方法发送请求，该方法触发 [事务事件的发送](#sending-a-transactional-event)。
1. 对POST请求的响应包含主密钥，该密钥允许开发人员通过GET请求发送一个或多个请求。 这样，他就能获得活动 [状态](#transactional-event-status)。

## 发送交易事件 {#sending-a-transactional-event}

事务性事件通过具有以下URL结构的POST请求发送：

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;组织>**:您的个人组织ID。 Refer to [this section](../../api/using/must-read.md).

* **&lt;transactionalAPI>**:transactional Messages API endPoints。

   Transactional Messages API端点的名称取决于您的实例配置。 它对应于值“mc”后跟您的个人组织ID。 让我们举一个Geometrixx公司的示例，其组织ID为“geometrixx”。 在这种情况下，邮递要求如下：

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   （请注意，在API预览期间，事务消息API端点也可见）

* **&lt;eventID>**:要发送的事件类型。 此ID是在创建事件定义时生成的。 请参阅 [Campaign文档](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html)。

### POST请求标题

该请求必须包含“内容类型：application/json”头。

必须添加字符集，例如 **utf-8**。 请注意，此值取决于您使用的REST应用程序。

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### POST请求主体

事件数据包含在JSON POST主体中。 事件结构取决于其定义。 资源定义屏幕中的API预览按钮提供了请求示例。 请参阅 [Campaign文档](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html)。

可以将以下可选参数添加到事件内容以管理链接到该事件的事务消息的发送：

* **expiration** （可选）:在此日期之后，将取消事务事件的发送。
* **scheduled** （可选）:从此日期开始，将处理事务事件并发送事务消息。

>[!NOTE]
>
>“expiration”和“scheduled”参数的值遵循ISO 8601格式。 ISO 8601指定使用大写字母“T”分隔日期和时间。 但是，可以从输入或输出中删除它，以便获得更好的可读性。

### 对POST请求的答复

POST响应返回创建时的事务事件状态。 要检索其当前状态（事件数据、事件状态……），请在GET请求中使用POST响应返回的主键：

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***示例请求&#x200B;***

发送活动的POST请求。

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

对POST请求的答复。

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

### 交易事件状态 {#transactional-event-status}

在响应中，“状态”字段允许您了解事件是否已处理：

* **待定**:该事件处于待处理状态——该事件在刚触发该事件时开始处于此状态。
* **处理**:该事件正在等待传送——该事件将转换为消息并发送消息。
* **暂停**:正在暂停事件进程。 它不再被处理，而是保留在Adobe Campaign数据库的队列中。 有关详细信息，请参阅 [Campaign文档](https://helpx.adobe.com/campaign/standard/channels/using/event-transactional-messages.html#unpublishing-a-transactional-message)。
* **已处理**:已处理该事件并成功发送消息。
* **忽略**:交付会忽略该事件，通常在地址隔离时。
* **deliveryFailed**:处理事件时发生传送错误。
* **routingFailed**:路由阶段失败——例如，当找不到指定的事件类型时，可能会发生这种情况。
* **tooOld**:该事件在其处理之前已过期——这可能由于各种原因而发生，例如，当发送失败多次（这会导致事件不再是最新的）或当服务器过载后无法再处理事件时。
* **targetingFailed**:Campaign standard未能丰富用于消息定位的链接。
