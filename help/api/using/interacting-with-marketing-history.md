---
title: 与营销历史互动
description: 了解如何与用户档案的营销历史进行交互
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 67282d21-b4ed-4af5-b751-848a6d705118
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 4%

---

# 与营销历史互动{#interacting-with-marketing-history}

通过&#x200B;**history**&#x200B;终结点，可与用户档案的营销历史记录进行交互。
这样，您就可以（例如）轻松检索用于发送给用户档案的投放的镜像页面。 为此请执行以下操作步骤：

1. 使用&#x200B;**history**&#x200B;端点和配置文件的主键执行GET。
1. 对返回的&#x200B;**events** href执行GET请求。
1. 它会返回包含指向&#x200B;**mirrorPage**&#x200B;节点中镜像页面的链接的配置文件的事件列表。

<br/>

***示例请求***

用GET请求检索用户档案的营销历史。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/"<PKEY>" \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

“events”节点会返回用于访问配置文件上事件的URL。

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

它会返回该配置文件的事件列表，其中包含到“mirrorPage”节点中镜像页面的链接。

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
