---
title: 关于 Audience Destinations 服务
description: 进一步了解受众目标服务。
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e1fa546313e8d543685ef30a072ae2d97c5bf236

---


# 关于 Audience Destinations 服务 {#about-audiences}

>[!IMPORTANT]
>
>受众目标服务目前处于测试阶段，可能会在不另行通知的情况下频繁更新。 客户必须托管在Azure上（目前仅针对北美）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀。

利用 [Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/landing/home.html) ，基于大型、复杂的数据集构建高度定向的受众，从而增强您的消费者体验。 Adobe Experience Platform整合了线上和线下来源（包括Adobe Analytics）的用户档案、行为和多实体数据，可帮助您构建360度全方位的客户视图，使您能够有效管理客户体验。

Adobe Campaign标准版随后将使用 **受众目标服务从Adobe Experience Platform中检索一组用户档案(称为** 受众 ****)，用于多步骤和／或跨渠道活动项目。

**受众****是通过第一次构建细分创建的**，细分本质上是一组基于Adobe Experience Platform客户用户档案中几乎任何变量(例如用户档案、事件、多实体数据)的规则，用于创建多维目标。 统一用户档案和分段服务的全局概念在以下专用文档中引用：

* [实时客户用户档案概述](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)
* [分段服务概述](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html)

创建区段后，您便可以将其激活为受众，以在Campaign Standard中激活工作流 [投放](../../automating/using/aep-targeting-audiences.md)。 此外，您还可以使用Adobe Experience Platform中的情境数据来个性 [化](../../automating/using/aep-personalizing-campaigns.md) ，并向活动添加动态内容。

此部分还提供操作说明 [视频](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html)。

这些部分中使用的术语：

* **用户档案**:用户档案是Experience Platform标准数据模型，用于定义消费者的属性。 用户档案也可以是与人和设备相关的事件数据和属性的聚合。

   示例：“无名氏是55岁的男性。”

* **细分**:一组规则，它使用属性和用户档案数据定义数据库中的事件子集。

   示例：“男性>50岁。”

* **受众**:一组符合区段规则的用户档案。

   示例：对应于数据库中50岁以上男性的用户档案列表。
