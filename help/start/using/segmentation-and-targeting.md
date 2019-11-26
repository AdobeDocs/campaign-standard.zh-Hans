---
title: 分段和定位
description: “了解Campaign中的档案、定位和受众创建：利用Experience cloud解决方案构建受众、导入联系人共享受众，并避免营销疲劳。”
page-status-flag: never-activated
uuid: 71f53808-0309-49f6-a4ee-3446eac9758a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: about-adobe-campaign
discoiquuid: d8c8a318-9433-4aec-b378-fd0beb50e9fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 13430243e8f2840ca85e557798168f6380a7b0fa

---


# 分段和定位{#segmentation-and-targeting}

## 配置文件 {#profiles}

使用Adobe Campaign的灵活数据模型丰富客户档案数据并添加新属性或表。 然后，使用这些客户档案进行更准确的细分、个性化和报告。

Adobe Campaign配置文件代表存储在数据库中的所有联系人。 每个配置文件都对应于数据库中的一个条目，该条目包含该配置文件被定向、限定和单独跟踪的必要信息。 这意味着配置文件可以是：客户、潜在客户、订阅新闻稿的个人、收件人、用户或任何其他面额，具体取决于组织。

客户档案功能将所有客户数据整合到一个位置：

![](assets/mkt_hist_view.png)

Adobe Campaign提出了各种档案获取机制：通过Adobe Campaign界面直接输入 [,](../../channels/using/getting-started-with-landing-pages.md)通过 [Campaign API批量创建Adobe Campaign界面，在线收集数据](../../automating/using/about-data-import-and-export.md)[](../../audiences/using/creating-profiles.md)[](../../api/using/about-campaign-standard-apis.md)，手动或自动导入机制。

**相关主题：**

* 在“配置文件”部分了解不同类型的 [配置](../../audiences/using/about-profiles.md) 。
* 在此部分中访 **问组织中的** “活动配置 [文件”数量](../../audiences/using/active-profiles.md)。
* 了解如何使用工作流定位功能自定义数据、处理复杂的数据管理任务，如计算、聚合、去重复和 [合并](../../automating/using/about-targeting-activities.md)

## Audiences {#audiences}

为了使您能够投递相关、有效的消息并有效吸引客户，Adobe Campaign集成了高级分析和定位功能。 借助工作流和查询编辑器，您可以根据您对不同营销活动的信息、活动、语言、偏好或营销历史，构建受众，这些受众将被您的不同营销活动定位。 例如，这允许您筛选订阅的配置文件，或根据不限数量的标准创建目标受众。

此页面中显示 [受众](../../audiences/using/about-audiences.md) ,“受众”部分 [详细介绍](../../audiences/using/creating-audiences.md) 。

**相关主题：**

* 了解如何通过发送多语言推送通知或多语言电子邮件触及 [多个地区的多](../../channels/using/creating-a-multilingual-push-notification.md) 语 [言受众](../../channels/using/creating-a-multilingual-email.md)
* 了解如何创 [建查询](../../audiences/using/creating-audiences.md#creating-query-audiences) ，以构建受众
* 了解如何在工 [作流中创建列](../../audiences/using/creating-audiences.md#creating-list-audiences) 表受众
* 了解如何 [从工作流中的文件导入](../../audiences/using/creating-audiences.md#creating-file-audiences) 受众
* 了解如何使 [用Experience cloud解决方](../../audiences/using/creating-audiences.md#creating-experience-cloud-audiences) 案共享受众

## 一般数据保护规定 {#general-data-protection-regulation}

GDPR 是欧盟最新制定的一项隐私法规，用于协调和顺应时代更新数据保护需求。GDPR 适用于所持有数据的数据主体位于欧盟的 Adobe Campaign 客户。除了Adobe Campaign中已有的隐私权（包括同意管理、数据保留设置和用户角色）外，我们还将作为数据处理者利用这一机会加入其他功能，以帮助您为某些GDPR请求做好数据管理者的准备。

请参阅本指 [南](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) ，进一步了解Adobe Campaign提供的工具和功能，帮助您符合GDPR标准。

## 疲劳管理 {#fatigue-management}

疲劳规则允许营销人员设置全局跨渠道业务规则，这些规则将自动从营销活动中排除过度请求的档案。

要实施疲劳规则，您需要为每个配置文件定义最大消息数，并选择将应用该规则的期间。 在交付准备过程中，配置文件会根据已发送给它们的消息数量从交付中排除（如果适用）。

**相关主题：**

* 了解如何通 [过一组样本](../../administration/using/fatigue-rules.md#examples) ，设计疲劳规则
* 了解如何创建类 [型规则](../../administration/using/about-typology-rules.md)
* 使用 [过滤规则](../../administration/using/filtering-rules.md) ，优化消息受众
