---
title: 元数据机制
description: 了解有关元数据机制的更多信息。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 58ec0999-b28a-4198-8d57-729b074c6a6d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 1%

---

# 元数据机制 {#metadata-mechanism}

您可以在GET请求中使用&#x200B;**resourceType**&#x200B;检索资源元数据：

`GET /profileAndServices/resourceType/<resourceName>`

响应会从资源返回主元数据（所有其他字段都是描述性或内部字段）：

* **Content**&#x200B;节点返回资源的字段。 对于&#x200B;**content**&#x200B;节点中的每个字段，我们可以找到以下字段：

   * &quot;apiName&quot;:API中使用的属性的名称。
   * &quot;type&quot;:这是高级类型定义（字符串、数字、链接、集合、枚举……）。
   * &quot;dataPolicy&quot;:字段的值必须遵循给定的策略规则。 例如，如果dataPolicy规则设置为“email”，则值必须是有效的电子邮件。 在PATCH或POST期间，dataPolicy可以检查值或修改要转换的值（例如，smartCase）。
   * &quot;category&quot;:在查询编辑器中提供字段的类别。
   * &quot;resType&quot;:这是技术类型。

      如果已完成“type”且其值为“link”或“collection”，则resTarget值即为链接所定向资源的名称。
如果“type”用值“enumeration”填写，则会添加“values”字段，并在**values**&#x200B;节点中详细描述每个枚举值。

* **Filters**&#x200B;节点会返回用于检索关联过滤器的URL。 有关过滤器的更多信息，请参阅[此部分](../../api/using/filtering.md)一节。

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

它会返回用户档案资源的完整描述。

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
