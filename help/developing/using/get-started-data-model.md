---
solution: Campaign Standard
product: campaign
title: Campaign Standard 数据模型快速入门
description: 使用自定义字段和资源来丰富 Campaign Standard 数据模型，并扩展 REST API 以利用扩展的字段。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
translation-type: tm+mt
source-git-commit: 2729852365a2e74d2a603d95f75285fe54313e71
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 30%

---


# Campaign Standard 数据模型快速入门 {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">数据模型</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">自定义资源</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">使用API</a></p></td></tr>
</table>

使用您自己的字段和资源扩展 Campaign Standard 数据模型，并在单一视图中监控所有数据模型更改。

## 数据模型 {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

活动使用的数据是通过在&#x200B;**预定义数据模型**&#x200B;中定义的不同资源来定义的。 数据模型显示一组与营销相关的资源的现成SQL结构：投放、受众、登陆页、用户档案等 每个资源都附带相关过滤器，允许您在各个资源之间导航。

**诊断**&#x200B;菜单允许您列表由Campaign Standard生成的技术对象：数据模式、网页、过滤器等，允许您监视数据模型及对其进行的任何更改。

阅读更多:

* [数据模型概念](../../developing/using/data-model-concepts.md)
* [数据模型最佳实践](../../developing/using/data-model-best-practices.md)
* [数据模型描述](../../developing/using/datamodel-introduction.md)
* [监视数据模型的变化](../../developing/using/monitoring-data-model-changes.md)

## 自定义资源 {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Campaign Standard允许您&#x200B;**丰富预定义的数据模型**&#x200B;以创建您自己的资源（例如添加“购买”或“产品”表），或使用新字段扩展现有资源。 您还可以配置活动屏幕，以优化通过已创建的新资源和字段进行的导航。

此外，您还可以&#x200B;**扩展Campaign Standard REST API**&#x200B;以便在自定义资源用户档案的API扩展字段中公开。 例如，这允许您使用从计费系统生成的促销代码更新客户的用户档案。

阅读更多:

* [添加或扩展资源](../../developing/using/key-steps-to-add-a-resource.md)
* [扩展API](../../developing/using/about-extending-the-api.md)
* [用例：使用新字段扩展用户档案资源](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [用例：将订阅扩展到应用程序资源](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## 使用API {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

借助Campaign Standard API，为Adobe Campaign Standard创建集成，并通过将活动与您使用的技术面板接口来构建您自己的生态系统。 [Campaign Standard REST API 入门](../../api/using/get-started-apis.md)

## 其他资源

* [关于 Adobe Experience Platform Data Connector](../../developing/using/aep-about-data-connector.md)
* [导出/导入自定义资源](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
