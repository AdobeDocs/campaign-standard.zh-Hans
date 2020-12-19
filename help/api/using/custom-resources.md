---
solution: Campaign Standard
product: campaign
title: 自定义资源
description: 进一步了解使用API进行自定义资源管理/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 5%

---


# 自定义资源 {#custom-resources}

Adobe Campaign附带一个预定义的数据模型，在该模型中，数据通过不同的资源进行定义。 您可以通过扩展资源来添加您自己的自定义字段或自定义表（如购买表或产品表）来丰富提供的数据模型。

可通过使用&#x200B;**/profileAndServicesExt**&#x200B;端点的API和自定义资源名称访问自定义资源。

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>对于非现成资源，请始终在资源名称前使用<b>&quot;cus&quot;</b>前缀。

只要自定义资源已链接到用户档案表，您就可以使用这些资源执行任何操作。 例如，让我们考虑以下表结构：

![替换文本](assets/cusresources.png)

在这种情况下，只要&#x200B;**事务**、**TransactionDetails**&#x200B;和&#x200B;**产品**&#x200B;表链接到&#x200B;**用户档案**&#x200B;表，所有资源都可用。

<br/>

***示例请求***

访问扩展profileAndServicesExt资源的示例GET请求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

它返回所有链接的自定义资源的列表。 然后，您可以使用资源URL执行本文档中描述的任何API任务。

```
{
"apiName": "resourceType",
"cusProduct": {
        "content": ...,
        "data": "/profileAndServicesExt/cusProduct/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusProduct/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
"cusTransaction": {
        "content": ...,
        "data": "/profileAndServicesExt/cusTransaction/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusTransaction/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
    ...
}
```

有关数据模型扩展的详细信息，请参阅活动文档：

* [数据模型概念](../../developing/using/data-model-concepts.md)
* [扩展API](../../developing/using/about-extending-the-api.md)
* [定义与其他资源的链接](https://helpx.adobe.com/campaign/standard/developing/using/configuring-the-resource-s-data-structure.html#defining-links-with-other-resources)
