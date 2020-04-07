---
title: 分段和定位
description: “了解活动中的用户档案、定位和受众创建：构建受众、导入联系人与Experience Cloud解决方案共享受众，并避免营销疲劳。”
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
source-git-commit: 3b40a9bba79d04f1635b7522cfc99f9e7566c3c0

---


# 分段和定位{#segmentation-and-targeting}

## 用户档案 {#profiles}

使用Adobe Campaign的灵活数据模型来丰富客户用户档案数据并添加新的属性或表。 然后，使用这些客户用户档案更准确地细分、个性化和报告。

Adobe Campaign用户档案表示存储在数据库中的所有联系人。 每个用户档案对应于数据库中的一个条目，该条目包含该用户档案被定向、限定和单独跟踪的必要信息。 这意味着用户档案可以是：客户、潜在客户、订阅新闻稿的个人、收件人、用户或任何其他面额，具体取决于组织。

客户用户档案功能将所有客户数据整合到一个位置：

![](assets/mkt_hist_view.png)

Adobe Campaign提出了各种用户档案获取机制：通过登陆页 [、手动或自动导入机](../../channels/using/getting-started-with-landing-pages.md)制在线收集数据 [，在Adobe Campaign界面中直接输入](../../automating/using/about-data-import-and-export.md)，通过活动API进行批量 [](../../audiences/using/creating-profiles.md)[](../../api/using/about-campaign-standard-apis.md)创建。

**相关主题：**

* 在“用户档案”部分了解不同类型的 [用户档案](../../audiences/using/about-profiles.md) 。
* 访问本节中 **您组织中** 的活动 [用户档案](../../audiences/using/active-profiles.md)的数量。
* 了解如何使用工作流定位功能自定义数据、处理复杂的数据管理任务，如计算、聚合、消除重复和 [合并](../../automating/using/about-targeting-activities.md)

## Audiences {#audiences}

Adobe Campaign集成了高级分析和定位功能，使您能够提供相关、有效的信息并有效吸引客户。 借助工作流和查询编辑，您可以构建由不同活动定向的受众，具体取决于您对其的信息、活动、语言、偏好或营销历史。 这允许您筛选订阅用户档案，或根据不限数量的条件创建目标受众。

受众信息将在 [本页中显示](../../audiences/using/about-audiences.md) ，并在“ [受众](../../audiences/using/creating-audiences.md) ”部分中详细介绍。

**相关主题：**

* 了解如何通过发送多语言推送通知或多语言电子邮件触及 [多个地区的](../../channels/using/creating-a-multilingual-push-notification.md) 多语 [言受众](../../channels/using/creating-a-multilingual-email.md)
* 了解如何创 [建查询](../../audiences/using/creating-audiences.md#creating-query-audiences) ，以构建受众
* 了解如何在工 [作流中创建列表受众](../../audiences/using/creating-audiences.md#creating-list-audiences) 。
* 了解如何 [从工作流中的文件导入受众](../../audiences/using/creating-audiences.md#creating-file-audiences) ,
* 了解如何使 [用Experience Cloud解决方](../../audiences/using/creating-audiences.md#creating-experience-cloud-audiences) 案共享受众

## 一般数据保护规定 {#general-data-protection-regulation}

GDPR 是欧盟最新制定的一项隐私法规，用于协调和顺应时代更新数据保护需求。GDPR 适用于所持有数据的数据主体位于欧盟的 Adobe Campaign 客户。除了Adobe Campaign中已有的隐私权（包括同意管理、数据保留设置和用户角色）外，我们还将作为数据处理者的角色利用这一机会加入其他功能，以帮助您为某些GDPR请求做好数据管理者的准备。

请参阅本指 [南](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) ，进一步了解Adobe Campaign提供的工具和功能，帮助您符合GDPR标准。

## 疲劳管理 {#fatigue-management}

疲劳规则允许营销人员设置全局交叉渠道业务规则，该规则将自动从活动中排除过度请求的用户档案。

要实施疲劳规则，您需要为每个用户档案定义最大消息数，并选择将应用该规则的期间。 在投放准备过程中，用户档案会根据已发送给投放的消息数量从协议中排除（如果适用）。

**相关主题：**

* 了解如何通 [过一组样本](../../sending/using/fatigue-rules.md#examples) ，设计疲劳规则
* 了解如何创建 [类型规则](../../sending/using/about-typology-rules.md)
* 使用 [过滤器规则](../../sending/using/filtering-rules.md) ，优化消息的受众
