---
title: 关于 Audience Destinations 服务
description: 了解有关Audience Destinations服务的更多信息。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 34235749-d056-4d4c-9939-7dc52f980a76
hide: true
hidefromtoc: true
source-git-commit: 376f00576ca1d0dfb536b29dbf25d88f7c93b9a8
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 2%

---

# 关于 Audience Destinations 服务 {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations服务现已弃用。 已弃用的功能仍然可用，但不会进一步增强或支持这些功能。 在此页面[&#128279;](../../rn/using/deprecated-features.md)中了解更多

利用[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html)基于大型复杂数据集构建具有高度针对性的受众，从而增强您的消费者体验。 Adobe Experience Platform可整合在线和离线来源(包括Adobe Analytics)中的用户档案、行为和多实体数据，以帮助您构建客户的360度视图，使您能够有效地管理客户体验。

然后，Adobe Campaign Standard将使用&#x200B;**Audience Destinations**&#x200B;服务从Adobe Experience Platform中检索名为&#x200B;**Audiences**&#x200B;的用户档案集合，以用于多步骤和/或跨渠道营销活动项目。

**受众**&#x200B;是通过首先构建&#x200B;**区段**&#x200B;创建的，这些区段实际上是一组规则，基于来自Adobe Experience Platform的客户配置文件中的几乎任何变量（例如，配置文件、事件、多实体数据）来创建多维目标。 有关实时客户配置文件和分段服务的全局概念可在以下专用文档中引用：

* [实时客户个人资料概述](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)
* [分段服务概述](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)

创建区段后，您可以将其激活为[Campaign Standard工作流](../../integrating/using/aep-targeting-audiences.md)中投放的受众。 此外，您还可以使用来自Adobe Experience Platform的上下文数据对[进行个性化](../../integrating/using/aep-personalizing-campaigns.md)并将动态内容添加到营销活动。

![](assets/do-not-localize/how-to-video.png)操作方法视频也可在[此部分](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html)中找到。

以下部分中使用的术语：

* **配置文件**：配置文件是用于定义使用者属性的Experience Platform标准数据模型。 配置文件也可以是与人员或设备相关的事件数据和属性的汇总。

  例如：“John Doe是一名55岁的男性。”

* **区段**：使用属性和事件数据从数据库中定义用户档案子集的一组规则。

  例如：“男性> 50岁。”

* **受众**：符合区段规则的配置文件集合。

  示例：与数据库中50岁以上所有男性对应的用户档案列表。
