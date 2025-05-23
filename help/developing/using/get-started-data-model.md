---
title: Campaign Standard 数据模型快速入门
description: 使用自定义字段和资源来丰富 Campaign Standard 数据模型，并扩展 REST API 以利用扩展的字段。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Data Model
role: Developer
level: Intermediate
exl-id: a8d15053-c20f-4334-a732-3b36cb00794d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 21%

---

# Campaign Standard 数据模型快速入门 {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">数据模型</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">自定义资源</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">使用API</a></p></td></tr>
</table>

使用您自己的字段和资源扩展Campaign Standard数据模型，并在单一视图中监控所有数据模型更改。

## 数据模型 {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

Campaign使用的数据是通过&#x200B;**预定义的数据模型**&#x200B;中定义的不同资源定义的。 数据模型为一组与营销相关的资源（投放、受众、登陆页面、用户档案等）显示现成的SQL结构。 每个资源都附带关联的过滤器，允许您浏览这些资源。

**诊断**&#x200B;菜单允许您列出由Campaign Standard生成的技术对象：数据架构、网页、过滤器等，从而允许您监视数据模型及其所做的任何更改。

了解更多：

* [数据模型概念](../../developing/using/data-model-concepts.md)
* [数据模型最佳实践](../../developing/using/data-model-best-practices.md)
* [数据模型描述](../../developing/using/datamodel-introduction.md)
* [监视数据模型的变化](../../developing/using/monitoring-data-model-changes.md)

## 自定义资源 {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Campaign Standard允许您&#x200B;**扩充预定义的数据模型**&#x200B;以创建您自己的资源（例如，添加Purchase表或Product表），或使用新字段扩展现有资源。 您还可以配置Campaign屏幕，以优化已创建的新资源和字段中的导航。

此外，您可以&#x200B;**扩展Campaign StandardREST API**，以便在API扩展字段中公开自定义资源配置文件。 例如，这可让您使用从计费系统生成的促销代码更新客户的用户档案。

了解更多：

* [添加或扩展资源](../../developing/using/key-steps-to-add-a-resource.md)
* [扩展API](../../developing/using/about-extending-the-api.md)
* [用例：使用新字段扩展用户档案资源](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [用例：将订阅扩展到应用程序资源](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## 使用API {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

使用Campaign Standard API，通过将Campaign与您使用的技术面板连接，为Adobe Campaign Standard创建集成并构建您自己的生态系统。 [Campaign Standard REST API 入门](../../api/using/get-started-apis.md)

## 其他资源

* [导出/导入自定义资源](https://helpx.adobe.com/cn/campaign/kb/acs-get-started-with-cusres.html)
* [将数据从 Campaign 导出到 Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
