---
title: 与营销历史互动
description: 了解如何与用户档案的营销历史进行交互。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 67282d21-b4ed-4af5-b751-848a6d705118
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 10%

---

# 与营销历史互动 {#interacting-with-marketing-history}

的 **历史** 端点允许您与用户档案的营销历史记录进行交互。
这样，您就可以轻松检索已发送到用户档案的投放的镜像页面。 为此请执行以下操作步骤：

1. 使用执行GET **历史** 端点和用户档案的主密钥。
1. 对执行GET请求 **事件** 返回了href。
1. 它会返回配置文件的事件列表，其中包含指向 **mirrorPage** 节点。

<br/>

***示例请求***

使用GET请求检索用户档案的营销历史记录。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/"<PKEY>" \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

“events”节点会返回一个URL，通过该URL，您可以访问用户档案中的事件。

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

它会返回配置文件的事件列表，其中包含指向“mirrorPage”节点中镜像页面的链接。

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
