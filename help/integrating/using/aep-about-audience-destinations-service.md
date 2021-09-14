---
title: 关于 Audience Destinations 服务
description: 了解有关受众目标服务的更多信息。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 34235749-d056-4d4c-9939-7dc52f980a76
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 2%

---

# 关于 Audience Destinations 服务 {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations服务目前处于测试阶段，可能会频繁更新，恕不另行通知。 需要在Azure上托管客户（目前仅适用于北美地区的测试版）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀团队。

利用[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html)根据大型复杂数据集构建高度定位的受众，从而增强您的消费者体验。 Adobe Experience Platform整合了包括Adobe Analytics在内的在线和离线来源的配置文件、行为和多实体数据，以帮助您构建客户的360度视图，从而使您能够有效管理客户体验。

然后，Adobe Campaign Standard将使用&#x200B;**Audience Destinations**&#x200B;服务从Adobe Experience Platform中检索多步和/或跨渠道营销活动项目的一组用户档案，称为&#x200B;**Audiences**。

**** 受众是通过首先构建 **区段来创建的**，区段本质上是一组基于Adobe Experience Platform客户配置文件中几乎任何变量（例如，配置文件、事件、多实体数据）的规则，用于创建多维目标。以下专用文档中引用了有关实时客户资料和分段服务的全局概念：

* [实时客户资料概述](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)
* [Segmentation Service概述](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)

创建区段后，您可以将其作为[Campaign Standard工作流](../../integrating/using/aep-targeting-audiences.md)中投放的受众激活。 此外，您还可以使用Adobe Experience Platform中的上下文数据来[personalize](../../integrating/using/aep-personalizing-campaigns.md)，并将动态内容添加到营销活动。

![](assets/do-not-localize/how-to-video.png) 此部分还提供操作方法 [视频](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html)。

以下部分使用的术语：

* **用户档案**:用户档案是用于定义用户属性的Experience Platform标准数据模型。用户档案也可以是与人员或设备相关的事件数据和属性的汇总。

   示例：“无名氏是一名55岁的男性。”

* **区段**:一组规则，通过属性和事件数据定义数据库中用户档案的子集。

   示例：“男性> 50岁。”

* **受众**:符合区段规则的用户档案集合。

   示例：数据库中所有年龄在50岁以上的男性对应的用户档案列表。
