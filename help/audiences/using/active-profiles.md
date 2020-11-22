---
solution: Campaign Standard
product: campaign
title: 使用中的用户档案
description: 您可以访问有关客户指标的专门报告，并在活动库中直观显示活动用户档案。
audience: audiences
content-type: reference
topic-tags: managing-profiles
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 5%

---


# 使用中的用户档案{#active-profiles}

Adobe Campaign提供一个报告，其中显示活动用户档案的数量。 此报告仅提供信息，对计费没有直接影响。 只有管理员才能访问此报告，位于 **[!UICONTROL Administration > Customer metrics]**&#x200B;下。

![](assets/audience_active_profiles1.png)

>[!NOTE]
>
>如果您托管在AWS上，并使用构建10368中的Campaign Standard，您还可以直接从控制面板监视实例上使用的活动用户档案数。 For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
>
>请注意，活动用户档案量度仅对Marketing实例可 **用且相** 关。 它不适用于执行实例，也不适用于MID（中间采购）和RT（消息中心／实时消息）实例。


在投放准备过程中排除的用户档案(类型规则、隔离、对照组)不予考虑。 被多个投放项目定位的用户档案只被计算一次。在报表底部，您将找到每个定位维度的活动用户档案列表。

此报告每月由技术工作流 **[!UICONTROL Billing]** 生成。 它包含过去12个月滚动期间目标的活动用户档案数。

请注意，在投放准备过程中排除的用户档案(类型规则、隔离)不会被考虑在内。 此外，一个被几个用户档案所瞄准的投放只计一次。

![](assets/audience_active_profiles2.png)

在报表底部，您将找到开单工作流处理的有效用户档案的列表:

* 来 **[!UICONTROL NmsRecipient]** 源包括使用Campaign Standard用户档案中的信息联系的所有客户。

* 另一方面，仅使用特定信息（电子邮件地址、电话号码）而与活动用户档案无关的客户将归入来源 **[!UICONTROL anonymous]** 中。
