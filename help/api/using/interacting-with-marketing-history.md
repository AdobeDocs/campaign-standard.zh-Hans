---
solution: Campaign Standard
product: campaign
title: 与营销历史互动
description: 了解如何与用户档案营销历史互动。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 10%

---


# 与营销历史互动 {#interacting-with-marketing-history}

通过&#x200B;**history**端点，您可以与用户档案的营销历史交互。
例如，这样，您就可以轻松检索发送给镜像页面的投放的用户档案。 为此请执行以下操作步骤：

1. 使用&#x200B;**history**&#x200B;端点和GET的主键执行用户档案。
1. 对返回的&#x200B;**GET** href执行事件请求。
1. 它返回用户档案的列表，该事件具有到&#x200B;**mirrorPage**&#x200B;节点中镜像页面的链接。

<br/>

***示例请求***

使用用户档案请求检索营销历史。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/"<PKEY>" \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

“事件”节点返回URL，用于访问用户档案上的事件。

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

对返回的GEThref执行事件请求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它返回用户档案的列表符事件，该具有指向“mirrorPage”节点中镜像页面符的链接。

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
