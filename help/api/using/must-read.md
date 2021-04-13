---
solution: Campaign Standard
product: campaign
title: 必读
description: 使用API前必须读取。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 9e2d1b59-55a5-4715-adfb-35191a9df536
translation-type: tm+mt
source-git-commit: 01e4eb027b55815c3680b26691e61cbe5b63ee8c
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 0%

---

# 必读{#must-read}

## 技术要求

* Adobe CampaignAPI必须仅用于服务器到服务器。
* 如果要实施的用例与Adobe API允许的比例一致，请始终与您的Adobe Campaign技术联系人联系。
* 设置AdobeIO访问需要特定权限，如有任何问题，请与Adobe支持联系。

## 权限和访问

* 默认情况下，Adobe Campaign API使用管理员上下文，因此组织单位和角色不适用。
* Adobe CampaignAPI被排除在角色上下文之外。
* 如果要配置具有组织单位或角色的API，请首先与您的Adobe技术联系人联系。

## 资源表示

所有API资源均在具有URL扩展的&#x200B;**JSON**&#x200B;中或在HTTP接受标头中可用：

`GET /profileAndServices/<resourceName>.json`

>[!NOTE]
>
>如果URL中没有扩展名，则&#x200B;**json格式是content-type的默认格式。**

<br/>

***请求示例***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile.json \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

## 主要密钥和URL

* 不要尝试自己构建URL。 所有URL都由API返回。 但是，可以基于顶级资源名称构建URL。

* 说明示例的自动主键(PKey)值不适用于其他特定部署。 它们由Adobe Campaign API生成。

* 由Adobe Campaign生成的自动主键值绝不能存储在外部数据库或网站中。 您必须在数据库定义中生成特定的关键字段，并在开发过程中使用它。

## 自定义键{#custom-keys}

如果用户档案资源已使用自定义键字段进行扩展，则可以将此字段用作键，而不是Adobe Campaign生成的自动主键：

`GET /.../profileAndServicesExt/profile/<customKey>`

如果键值与PATCH键不同，或者您使用自己的业务键作为URI而不是Adobe提供的业务键，则无法使用来源操作修改自定义键。

仅对&#x200B;**顶级用户档案资源**&#x200B;使用自定义键。 URL由API返回，绝不应由您自己构建。

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

它返回用户档案的订阅列表。

```
"service": {
"PKey": "<PKEY>",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
"label": "Sport Newsletter",
"name": "SVC1",
"title": "Sport Newsletter (SVC1)"
}
```
