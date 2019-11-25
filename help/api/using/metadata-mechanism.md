---
title: 元数据机制
description: 了解有关元数据机制的更多信息。
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


# 元数据机制 {#metadata-mechanism}

您可以使用GET请求中的 **resourceType** 检索资源元数据：

`GET /profileAndServices/resourceType/<resourceName>`

响应会从资源返回主元数据（所有其他字段都是描述性的或内部的）:

* “内 **容** ”节点返回资源的字段。 对于内容节点中的每 **个字段** ，我们可以找到以下字段：

   * “apiName”:API中使用的属性的名称。
   * “type”:这是高级类型定义（字符串、数字、链接、集合、枚举……）。
   * “dataPolicy”:字段的值必须遵循给定的策略规则。 例如，如果dataPolicy规则设置为“email”，则该值必须是有效的电子邮件。 在PATCH或POST期间，dataPolicy可以检查值或修改要转换的值（例如，smartCase）。
   * “类别”:在查询编辑器中提供字段的类别。
   * “resType”:这是技术类型。

      如果“type”是使用值“link”或“collection”完成的，则resTarget值是链接所针对的资源的名称。
如果“type”是用值“enumeration”完成的，则会添加一个“values”字段，并且每个枚举值都会在值节点中详 **细说** 明。

* “筛 **选器** ”节点返回URL以检索关联的筛选器。 For more on filters, refer to [this section](../../api/using/filtering.md) section.

<!-- créer une section au même niveau sur les liens -->
<!-- dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien -->
<!-- plus reparler du node Data -->

<br/>

***示例请求***

对资源执行GET请求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它返回配置文件资源的完整说明。

```
{
...
"content": {
  "email": {...},
    ...
    },
"data": "/profileAndServices/profile/",
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>"
    },
"help": "Identified profiles",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/metadata",
"label": "Profiles",
"mandatory": false,
"name": "profile",
"pkgStatus": "never",
"readOnly": false,
"schema": "nms:recipient",
"type": "item"
}
```
