---
title: 细分和定位
seo-title: 细分和定位
description: 细分和定位
seo-description: “了解Campaign中的档案、定位和受众创建：构建受众，导入联系人使用Experience Cloud解决方案共享受众，避免营销疲劳”。
page-status-flag: 从未激活
uuid: 71f53808-0309-49f6-a4 ee-3446eac9758 a
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: about-adobe-campaign
discoiquuid: d8c8a318-9433-4aec-b378-fd0 beb50 e9 fb
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Segmentation and targeting{#segmentation-and-targeting}

## Profiles {#profiles}

使用Adobe Campaign的灵活数据模型丰富客户档案数据，并添加新属性或表格。然后，使用这些客户档案实现更准确的细分、个性化和报告。

Adobe Campaign配置文件代表存储在数据库中的所有联系人。每个配置文件对应数据库中的一个条目，该条目包含要定向、有资格和单独跟踪的配置文件的必要信息。这意味着配置文件可以是：客户端、潜在客户、个人订阅新闻稿、收件人、用户或根据组织的任何其他分配额。

客户档案功能将您的所有客户数据整合在一个位置：

![](assets/mkt_hist_view.png)

Adobe Campaign proposes various mechanisms for profile acquisition: collecting data online via [landing pages](../../channels/using/about-landing-pages.md), manual or [automated import mechanisms](../../automating/using/about-data-import-and-export.md), [direct input](../../audiences/using/creating-profiles.md) in the Adobe Campaign interface, bulk creation through [Campaign APIs](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).

**相关主题：**

* Learn about different types of profiles in the [Profiles](../../audiences/using/about-profiles.md) section.
* Access the number of **Active Profiles** in your organization in [this section](../../audiences/using/active-profiles.md).
* Learn how to customize your data, handle complex data management tasks, such as calculations, aggregates, de-dupes, and merges, using [workflow targeting capabilities](../../automating/using/about-targeting-activities.md)

## Audiences {#audiences}

为了使您能够提供相关且有效的消息，并有效地吸引客户，Adobe Campaign集成了高级分析和定位功能。由于工作流程和查询编辑器，您可以根据您的活动、活动、语言、偏好或营销历史信息，构建将由不同营销活动定位的受众。这允许您过滤订阅的配置文件，或以无限数量的标准创建目标受众。

Audiences are presented [in this page](../../audiences/using/about-audiences.md) and detailed in the [Audiences](../../audiences/using/creating-audiences.md) section.

**相关主题：**

* Learn how to reach multilingual audiences across multiple regions by sending [multilingual push notifications](../../channels/using/creating-a-multilingual-push-notification.md) or [multilingual emails](../../channels/using/creating-a-multilingual-email.md)
* Learn how to [create queries](../../audiences/using/creating-audiences.md#creating-query-audiences) to build audiences
* Learn how to [create list audiences](../../audiences/using/creating-audiences.md#creating-list-audiences) in a workflow
* Learn how to [import an audience from a file](../../audiences/using/creating-audiences.md#creating-file-audiences) in a workflow
* Learn how to [share audiences](../../audiences/using/creating-audiences.md#creating-experience-cloud-audiences) with Experience Cloud solutions

## General Data Protection Regulation {#general-data-protection-regulation}

GDPR是欧盟(欧盟)新的隐私法规，旨在协调数据保护要求并使其现代化。GDPR适用于持有在欧盟存放数据主体数据的Adobe Campaign客户。除了Adobe Campaign中已经提供的隐私权功能(包括同意管理、数据保留设置和用户角色)之外，我们还将利用我们作为数据处理者的机会作为数据处理者，以帮助您为特定GDPR请求的数据管理者做好准备。

Refer to this [guide](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) to learn more about the tools and functionalities that Adobe Campaign provides to help you become GDPR compliant.

## Fatigue management {#fatigue-management}

疲劳规则允许营销人员制定全局跨渠道业务规则，这些规则会自动将主动提供的档案排除在营销活动中。

要实施疲劳规则，您可以为每个配置文件定义最大消息数，并选择规则适用的期限。在交付准备过程中，将根据发送给他们的消息数量，将配置文件排除在交付中(如果适用)。

**相关主题：**

* Learn how to [design fatigue rules](../../administration/using/fatigue-rules.md#examples) through a set of samples
* Learn how to create [typology rules](../../administration/using/about-typology-rules.md)
* Use [filter rules](../../administration/using/filtering-rules.md) to refine the audience of your messages
