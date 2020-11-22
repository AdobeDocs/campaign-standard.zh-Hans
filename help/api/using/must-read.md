---
solution: Campaign Standard
product: campaign
title: 必读
description: 使用API之前必须读取。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 0%

---


# Must-Read {#must-read}

## 技术要求

* Adobe CampaignAPI必须仅用于服务器到服务器。
* 如果要实施的用例与AdobeAPI允许的比例一致，请始终与Adobe Campaign技术联系人联系。
* 设置AdobeIO访问需要特定权限，如有任何问题，请与Adobe支持联系。

## 资源表示

所有API资源在JSON **中都可** 用（带有URL扩展），或在HTTP接受标头中可用：

`GET /profileAndServices/<resourceName>.json`

>[!NOTE]
>
>如果URL中没有扩展名， **则json格式是content** -type的默认格式。

<br/>

***请求示例***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile.json \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

## 主键和URL

* 不要尝试自己构建URL。 所有URL都由API返回。 但是，可以基于顶级资源名称构建URL。

* 说明示例的自动主键(PKey)值不适用于其他特定部署。 它们由Adobe CampaignAPI生成。

* 由Adobe Campaign生成的自动主键值永远不能存储到外部数据库或网站中。 您必须在数据库定义中生成特定的关键字字段并在开发过程中使用它。

## 自定义键 {#custom-keys}

如果用户档案资源已使用自定义密钥字段进行扩展，则可以将此字段用作密钥，而不是Adobe Campaign生成的自动主密钥：

`GET /.../profileAndServicesExt/profile/<customKey>`

如果密钥值与PATCH密钥不同，或者您使用自己的业务密钥作为URI而不是Adobe提供的业务密钥，则无法使用来源操作修改自定义密钥。

仅对顶级用户档案 **资源使用自定义密钥** 。 URL由API返回，不应由您自己构建。

<br/>

***示例请求***

要使用自定义键检索用户档案的订阅，请对自定义键执行GET操作。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<customKey> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

对返回的GETURL执行订阅请求。

```
-X GET <SUBSCRIPTION_URL> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它返回列表订阅的用户档案。

```
"service": {
"PKey": "<PKEY>",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
"label": "Sport Newsletter",
"name": "SVC1",
"title": "Sport Newsletter (SVC1)"
}
```
