---
title: 营销活动活跃用户档案
description: 了解如何访问客户量度和活动用户档案
feature: Profiles
role: User
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: 0ae2501b5c3ecf6dc9562bb53b5354c52aff7323
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 6%

---

# 使用中的用户档案{#active-profiles}

您可以从以下位置访问活动用户档案的详细信息： **[!UICONTROL Customer metrics]** 报告。 此报表仅供Campaign功能管理员使用。 Adobe Campaign要访问此报表，请单击 [用户界面](../../start/using/interface-description.md#advanced-menu)，并浏览至 **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_customer_metrics.png)

此报告由以下人员每月生成 **[!UICONTROL Billing]** 技术工作流，并显示 **活动用户档案**. 在中了解有关技术工作流的更多信息 [此页面](../../administration/using/technical-workflows.md).

“用户档案”是代表最终客户、潜在客户或潜在客户的信息记录。 考虑用户档案 **活动** 如果在过去12个月内通过任何渠道投放了Campaign，则表明其已定位。

根据您的合同，您的每个Campaign实例都会配置特定数量的活动用户档案。 请参阅您的许可协议，了解已购买的活动用户档案数量。

![](assets/audience_active_profiles_list.png)



* 在投放准备期间（例如通过类型规则或隔离机制）排除的用户档案不会考虑在内。

* 事务性消息收件人计入活动用户档案。

* 被多个投放项目定位的用户档案只被计算一次。

* 此报告只提供信息，对账单没有直接影响。

在页面底部，列出定向维度以及每个维度的用户档案数。 事务性消息的接收者关联到 **匿名** 维度。

>[!NOTE]
>
>作为管理员用户，您还可以直接从控制面板监控实例中使用的活动用户档案数。 有关详细信息，请参见 [控制面板文档](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
>
