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
source-wordcount: '354'
ht-degree: 2%

---

# 关于 Audience Destinations 服务 {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations服务现已弃用。 已弃用的功能仍然可用，但不会进一步增强或支持这些功能。 了解详情 [本页内容](../../rn/using/deprecated-features.md)

利用以下资源增强您的消费者体验 [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html) 以基于大型复杂数据集构建具有高度针对性的受众。 Adobe Experience Platform可整合在线和离线来源(包括Adobe Analytics)中的用户档案、行为和多实体数据，以帮助您构建客户的360度视图，使您能够有效地管理客户体验。

Adobe Campaign Standard随后将使用 **受众目标** 用于检索配置文件集合的服务，称为 **受众**，从Adobe Experience Platform获取多步骤和/或跨渠道营销活动项目。

**受众** 由第一个生成创建 **区段**，这些规则基本上是一组规则，基于客户个人资料中的几乎任何变量（例如，个人资料、事件、多实体数据），来自Adobe Experience Platform以创建多维目标。 有关实时客户配置文件和分段服务的全局概念可在以下专用文档中引用：

* [Real-time Customer Profile概述](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)
* [分段服务概述](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)

创建区段后，您可以将其激活为中的投放受众 [Campaign Standard工作流](../../integrating/using/aep-targeting-audiences.md). 此外，您还可以将来自Adobe Experience Platform的上下文数据用于 [个性化](../../integrating/using/aep-personalizing-campaigns.md) 并将动态内容添加到营销活动。

![](assets/do-not-localize/how-to-video.png) 中还提供了操作方法视频 [本节](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

以下部分中使用的术语：

* **个人资料**：配置文件是用于定义使用者属性的Experience Platform标准数据模型。 配置文件也可以是与人员或设备相关的事件数据和属性的汇总。

  例如：“John Doe是一名55岁的男性。”

* **区段**：一组规则，使用属性和事件数据定义来自数据库的用户档案子集。

  例如：“男性> 50岁。”

* **受众**：符合区段规则的用户档案集合。

  示例：与数据库中50岁以上所有男性对应的用户档案列表。
