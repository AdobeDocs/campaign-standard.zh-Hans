---
solution: Campaign Standard
product: campaign
title: Campaign活动用户档案
description: 了解如何访问客户量度和活动用户档案
feature: 用户档案
role: Business Practitioner
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: f66a4e35e1f42a3d7630556d020ce76adfea5891
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 7%

---

# 使用中的用户档案{#active-profiles}

Campaign功能管理员可以从&#x200B;**[!UICONTROL Administration > Customer metrics]**&#x200B;访问&#x200B;**[!UICONTROL Customer metrics]**&#x200B;报表。

![](assets/audience_customer_metrics.png)

此报告由&#x200B;**[!UICONTROL Billing]**&#x200B;技术工作流每月生成，并显示&#x200B;**活动用户档案**&#x200B;的数量。

“用户档案”是代表最终客户、潜在客户或潜在客户的信息记录。 如果用户档案在过去12个月内通过任何渠道被Campaign投放定向，则会将其视为&#x200B;**active**。

根据您的合同，您的每个Campaign实例都配置了特定数量的活动用户档案。 有关已购买的活动用户档案的数量，请参阅您的许可协议。

![](assets/audience_active_profiles_list.png)



* 在投放准备期间被排除的用户档案（例如，按分类规则或隔离机制）将不被考虑在内。

* 事务型消息的收件人会被计入活动用户档案。

* 被多个投放项目定位的用户档案只被计算一次。

* 此报表仅提供信息，对账单没有直接影响。

在页面底部，会列出定向维度，以及每个维度的用户档案数。 事务型消息的收件人与&#x200B;**Anonymous**&#x200B;维度相关联。

>[!NOTE]
>
>作为管理员用户，您还可以直接从控制面板监控实例上使用的活动配置文件数量。 有关更多信息，请参阅[控制面板文档](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html)。

