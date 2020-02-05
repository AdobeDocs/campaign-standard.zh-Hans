---
title: 关于受众目标服务
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
source-git-commit: 2ef524d1d276abb1ff0a7149462452cafe8e5cd3

---


# 关于受众目标服务 {#about-audiences}

>[!IMPORTANT]
>
>受众目标服务目前处于测试阶段，可能会在不另行通知的情况下频繁进行更新。 客户必须托管在Azure上（目前仅针对北美）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀。

通过利用 [Adobe Experience Platform](https://www.adobe.io/apis/experienceplatform/home.html) (AEP)根据大型、复杂的数据集构建高度针对性的受众，增强您的消费者体验。 Adobe Experience platform整合了线上和线下来源（包括Adobe Analytics）的档案、行为和多实体数据，可帮助您构建360度全方位的客户视图，使您能够有效管理客户体验。

然后，Adobe Campaign Standard将使用 **Audience Destinations** （受众目标）服务从AEP中检索多步骤和／或跨渠道营销活动计划的一组档案(称为 **Audiences**)。

**受众** 是通过首先构建细分来创建的 ****，这些细分本质上是一组基于客户档案中来自AEP的几乎任何变量（例如，档案、事件、多实体数据）的规则，以创建多维目标。 统一配置文件和分段服务的全局概念在这些专 [用文档中引用](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation.html)。

创建区段后，您便可以将其激活为受众，以便在 [Campaign Standard工作流中进行分发](../../automating/using/aep-targeting-audiences.md)。 此外，您还可以使用Adobe Experience Platform中的情境数据来个性化 [营销](../../automating/using/aep-personalizing-campaigns.md) ，并将动态内容添加到营销活动中。

此部分还提供操作说明 [视频](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html)。

这些部分中使用的术语：

* **简介**:Profile是Experience platform标准数据模型，用于定义消费者的属性。 配置文件也可以是与个人和设备相关的事件数据和属性的集合。

   示例：“无名氏是55岁的男性。”

* **细分**:一组规则，它使用属性和事件数据定义数据库中配置文件的子集。

   示例：“男性>50岁。”

* **受众**:满足细分规则的配置文件集合。

   示例：数据库中所有年龄在50岁以上的男性的相应资料列表。
