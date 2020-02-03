---
title: 与营销历史互动
description: 了解如何与档案的营销历史互动。
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
source-git-commit: e60ec7790da46d234b66baf4c3db23815056b9fb

---


# 与营销历史互动 {#interacting-with-marketing-history}

历史 **记录端点** ，可让您与个人资料的营销历史记录进行交互。
例如，这样，您就可以轻松检索发送到配置文件的分发的镜像页面。 为此请执行以下操作步骤：

1. 使用历史端点 **和配置** 文件的主键执行GET。
1. 对返回的事件 **href执行** GET请求。
1. 它返回配置文件的事件列表，其中包含指向mirrorPage节点中镜像页面 **的链接** 。

<br/>

***示例请求&#x200B;***

通过GET请求检索个人资料的营销历史记录。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/"<PKEY>" \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

“事件”节点返回URL，通过该URL可访问配置文件中的事件。

```
{
  "PKey": "<PKEY>",
  "firstName": "John",
  "lastName":"Doe",
  "birthDate": "1980-10-24",
  "events": {
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/",
    "metadata": "subHisto"
    },
}
```

对返回的事件href执行GET请求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它返回配置文件的事件列表，其中包含指向“mirrorPage”节点中镜像页面的链接。

```
    {
      "PKey": "<PKEY>",
      "category": "email",
      "date": "2018-05-17 08:44:49.366Z",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/<PKEY>",
      "label": "Send via email",
      "mirrorPage": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/<PKEY>/mirrorPage/"
      },
      "type": "outbound"
    }
```
