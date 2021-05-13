---
solution: Campaign Standard
product: campaign
title: 活动活动用户档案
description: 了解如何访问客户指标和活动用户档案
feature: 用户档案
role: Business Practitioner
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: d2fcf2ca22bb5fe3632280f922dfed0972f6eb09
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 5%

---

# 客户量度{#customer-metrics}

活动职能管理员可以从&#x200B;**[!UICONTROL Administration > Customer metrics]**&#x200B;访问&#x200B;**[!UICONTROL Customer metrics]**&#x200B;报告。

![](assets/audience_active_profiles1.png)

此报表显示：

* Experience CloudID
* IMS组织ID
* **活动用户档案**&#x200B;的数量
* 列表实例中可用的定位维度

此报表每月由&#x200B;**[!UICONTROL Billing]**&#x200B;技术工作流生成。

## 使用中的用户档案{#active-profiles}

根据您的合同，您的每个活动实例都会配置特定数量的活动用户档案。 请参阅您的许可协议，了解已购买的有效用户档案数量。

>[!NOTE]
>
>作为管理员用户，您还可以直接从控制面板监视实例上使用的活动用户档案数。 有关详细信息，请参阅[控制面板文档](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html)。


“用户档案”是表示最终客户、潜在客户或潜在客户的信息记录。 如果用户档案在过去12个月内通过任何渠道被活动投放锁定，则会将其视为&#x200B;**active**。 在准备投放时(例如，由类型规则或隔离机制)排除的用户档案不会被考虑在内。 被多个投放项目定位的用户档案只被计算一次。此报告只提供信息，对账单没有直接影响。

![](assets/audience_active_profiles2.png)

在报表底部，您将找到每个定位维度的活动用户档案列表。 它显示在过去12个月滚动期间内目标的活动用户档案数。

* **[!UICONTROL NmsRecipient]**&#x200B;源包含使用其Campaign Standard用户档案中的信息联系的所有用户档案。

* 客户&#x200B;**[!UICONTROL anonymous]**&#x200B;源显示仅使用特定信息（电子邮件地址、电话号码）而与其用户档案用户档案无关的目标活动数。
