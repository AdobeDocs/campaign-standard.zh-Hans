---
title: 使用中的用户档案
description: 您可以访问有关客户指标的专门报告，并在活动库中直观显示活动用户档案。
page-status-flag: never-activated
uuid: ee8ac493-c297-49ca-aed4-3976d8a685a4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: e029213f-0b65-41b1-8adf-34fa813b0c70
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4575c1152f1a33ff18b2200151346cc6e56b45fa
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 19%

---


# 使用中的用户档案{#active-profiles}

Adobe Campaign提供一个报告，其中显示活动用户档案的数量。 此报告仅提供信息，对计费没有直接影响。 只有管理员才能访问此报告，位于 **[!UICONTROL Administration > Customer metrics]**&#x200B;下。

![](assets/audience_active_profiles1.png)

技术 **[!UICONTROL Billing]** 工作流每月生成一份报告，其中包含过去12个月滚动期间目标的活动用户档案数。

在投放准备期间（类型规则，隔离）被排除在外的用户档案不包含在內。被多个投放项目定位的用户档案只被计算一次。在报表底部，您将找到每个定位维度的活动用户档案列表。

![](assets/audience_active_profiles2.png)

如果您托管在AWS上，并使用构建10368中的Campaign Standard，您还可以直接从控制面板监视实例上使用的活动用户档案数。 有关此问题的详细信息，请参 [阅控制面板文档](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html)。
