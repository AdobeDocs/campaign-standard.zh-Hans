---
title: 必读
description: 使用API前必须读取。
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
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# 必读 {#must-read}

## 技术要求

* Adobe Campaign API只能用于服务器到服务器。
* 如果要实施的用例与Adobe Campaign API允许的规模一致，请始终与Adobe技术联系人联系。
* 设置Adobe IO访问需要特定权限，如有任何问题，请与Adobe支持联系。

## 资源表示

所有API资源在 **JSON中都可用** ,URL扩展名为JSON，或在HTTP接受头中：

`GET /profileAndServices/<resourceName>.json`

>[!NOTE]
>
>在URL中没有扩展名， **json格式是content** -type的默认格式。

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

* 请勿尝试自己构建URL。 所有URL都由API返回。 但是，可以基于顶级资源名称构建URL。

* 说明示例的自动主键(PKey)值不适用于其他特定部署。 它们由Adobe Campaign API生成。

* Adobe Campaign生成的自动主键值绝不能存储在外部数据库或网站中。 您必须在数据库定义中生成特定键字段，并在开发过程中使用它。

## 自定义键 {#custom-keys}

如果配置文件资源已扩展自定义密钥字段，则可以将此字段用作密钥，而不是Adobe Campaign生成的自动主密钥：

`GET /.../profileAndServicesExt/profile/<customKey>`

如果键值与源键不同，或者您使用自己的业务键作为URI而不是Adobe提供的业务键，则无法使用PATCH操作修改自定义键。

仅对顶级配置文 **件资源使用自定义密钥** 。 URL由API返回，绝不应由自己构建。

<br/>

***示例请求***

要使用自定义键检索配置文件的订阅，请对自定义键执行GET操作。

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

它返回配置文件的订阅列表。

```
"service": {
"PKey": "<PKEY>",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
"label": "Sport Newsletter",
"name": "SVC1",
"title": "Sport Newsletter (SVC1)"
}
```
