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
source-git-commit: be7ab90583e9c6472fd2c86082e832432d0a32b9
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 4%

---


# 关于 Audience Destinations 服务 {#about-audiences}

>[!IMPORTANT]
>
>受众目标服务目前处于测试阶段，可能会在不通知的情况下频繁进行更新。 客户必须托管在Azure上（目前仅限北美的beta版），才能访问这些功能。 如果您想要访问，请联系Adobe客户服务。

通过利用Adobe Experience Platform以基于大型、复 [杂的数据集](https://docs.adobe.com/content/help/en/experience-platform/landing/home.html) 构建高度定向的受众，增强您的消费者体验。 该Adobe Experience Platform整合了线上和线下来源(包括AdobeAnalytics)的用户档案、行为和多实体数据，帮助您构建360度全方位的视图，使您能够有效管理客户体验。

Adobe Campaign Standard随后将使 **用受众目标** ，从多步和／或跨渠道活动的Adobe Experience Platform中检索一组称为 ****&#x200B;受众的用户档案。

**受众** 是通过第 **一次构建段来创建的**，这些段实质上是基于客户用户档案中从Adobe Experience Platform到创建多维目标的几乎任何变量(例如用户档案、事件、多实体数据)的一组规则。 实时客户用户档案和细分服务的全局概念在以下专用文档中引用：

* [实时客户用户档案概述](https://docs.adobe.com/content/help/zh-Hans/experience-platform/profile/home.html)
* [分段服务概述](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html)

创建区段后，您便可以将其激活为受众，以在Campaign Standard [工作流中投放](../../automating/using/aep-targeting-audiences.md)。 此外，您还可以使用Adobe Experience Platform中的情境数据来 [个性化](../../automating/using/aep-personalizing-campaigns.md) ，并向活动添加动态内容。

此部分还提供操作方法 [视频](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html)。

这些部分使用的术语：

* **用户档案**: 用户档案是一种Experience Platform标准数据模型，用于定义消费者的属性。 用户档案也可以是事件数据和与个人或设备相关的属性的聚合。

   示例： “John Doe是一名55岁的男性。”

* **细分**: 一组规则，它们使用属性和用户档案数据来定义数据库中的事件子集。

   示例： “男性> 50岁。”

* **受众**: 一组符合细分规则的用户档案。

   示例： 列表数据库中所有年龄在50岁以上的男性对应的用户档案。
