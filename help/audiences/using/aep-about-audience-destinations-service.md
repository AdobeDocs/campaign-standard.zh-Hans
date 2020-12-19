---
solution: Campaign Standard
product: campaign
title: 关于 Audience Destinations 服务
description: 进一步了解受众目标服务。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
translation-type: tm+mt
source-git-commit: 2a92600df01fd3c78a2b35c8034a2ce347e5c1d8
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 7%

---


# 关于 Audience Destinations 服务 {#about-audiences}

>[!IMPORTANT]
>
>受众目标服务目前处于测试阶段，可能会在不通知的情况下频繁进行更新。 客户必须托管在Azure上（目前仅限北美的beta版），才能访问这些功能。 如果您想要访问，请联系Adobe客户服务中心。

利用[Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/landing/home.html)根据复杂的大数据集构建高度定向的受众，增强您的消费者体验。 Adobe Experience Platform整合了包括Adobe Analytics在内的线上和线下来源的用户档案、行为和多实体数据，帮助您构建360度全方位的客户视图，使您能够有效管理客户体验。

然后，Adobe Campaign Standard将使用&#x200B;**受众目标**&#x200B;服务从Adobe Experience Platform检索用户档案集合，称为&#x200B;**受众**，用于多步骤和／或跨渠道活动项目。

**受** 众是通过第 **一次构建细分来创建的**，这些细分实质上是一组基于Adobe Experience Platform客户用户档案内几乎任何变量(如用户档案、事件、多实体数据)的规则，以创建多维目标。实时客户用户档案和细分服务的全局概念在以下专用文档中引用：

* [实时客户用户档案概述](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)
* [分段服务概述](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html)

创建区段后，您便可以将其激活为[Campaign Standard工作流](../../automating/using/aep-targeting-audiences.md)中的投放的受众。 此外，您还可以使用Adobe Experience Platform的情境数据来[个性化](../../automating/using/aep-personalizing-campaigns.md)，并向活动添加动态内容。

![](assets/do-not-localize/how-to-video.png) 此部分还提供操作方法 [视频](https://docs.adobe.com/content/help/zh-Hans/campaign-standard-learn/tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.translate.html)。

这些部分使用的术语：

* **用户档案**:用户档案是一种Experience Platform标准数据模型，用于定义消费者的属性。用户档案也可以是事件数据和与个人或设备相关的属性的聚合。

   示例：“John Doe是一名55岁的男性。”

* **细分**:一组规则，它们使用属性和用户档案数据来定义数据库中的事件子集。

   示例：“男性> 50岁。”

* **受众**:一组符合细分规则的用户档案。

   示例：列表数据库中所有年龄在50岁以上的男性对应的用户档案。
