---
title: 必读
description: 使用API之前必须读取。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 9e2d1b59-55a5-4715-adfb-35191a9df536
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 0%

---

# 必读 {#must-read}

## 技术要求

* Adobe Campaign API必须仅用于服务器到服务器。
* 如果要实施的用例与Adobe Campaign API允许的比例相一致，请始终咨询您的Adobe技术联系人。
* 设置AdobeIO访问需要特定权限，如有任何问题，请联系Adobe支持。

## 权限和访问

* 默认情况下，Adobe Campaign API使用管理员上下文，因此组织单位和角色不适用。
* Adobe Campaign API将从角色上下文中排除。
* 如果要使用组织单位或角色配置API，请先与您的技术联系人联系以Adobe。

## 资源表示

所有API资源在URL扩展名为&#x200B;**JSON**&#x200B;或HTTP接受标头中均可用：

`GET /profileAndServices/<resourceName>.json`

>[!NOTE]
>
>如果URL中没有扩展名，则&#x200B;**json格式是content-type的默认格式**。

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

* 请勿尝试自行构建URL。 所有URL都由API返回。 但是，可以基于顶级资源名称构建URL。

* 说明示例的自动主键值(PKey)不适用于其他特定部署。 它们由Adobe Campaign API生成。

* 由Adobe Campaign生成的自动主键值绝不能存储到外部数据库或网站中。 您必须在数据库定义中生成特定的键字段，并在开发过程中使用它。

## 自定义键 {#custom-keys}

如果用户档案资源已使用自定义键字段进行扩展，则可以将此字段用作键，而不是Adobe Campaign生成的自动主键：

`GET /.../profileAndServicesExt/profile/<customKey>`

如果键值与原始键不同，或者您使用自己的业务键作为URI而不是由PATCH提供的URI，则无法使用Adobe操作修改自定义键。

仅对&#x200B;**顶级配置文件资源**&#x200B;使用自定义键。 URL由API返回，绝不应由您自己构建。

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

对返回的订阅URL执行GET请求。

```
-X GET <SUBSCRIPTION_URL> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它会返回用户档案的订阅列表。

```
"service": {
"PKey": "<PKEY>",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
"label": "Sport Newsletter",
"name": "SVC1",
"title": "Sport Newsletter (SVC1)"
}
```
