---
solution: Campaign Standard
product: campaign
title: 两个已优化受众的联合
description: 此用例显示两个读取受众活动的合并。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 58%

---


# 两个已优化受众的联合 {#example--union-on-two-refined-audiences}

此示例中定义的工作流展示了两个 **[!UICONTROL Read audience]** 活动的并集。此工作流程的目标，是向 18 至 30 岁的金牌或银牌会员发送电子邮件。系统中已创建特定受众以跟踪金牌和银牌会员。

工作流的设计如下所示：

![](assets/readaudience_activity_example1.png)

* A first [Read audience](../../automating/using/read-audience.md) activity that retrieves the Gold members audience and refines it by selecting only profiles that are between 18 and 30 years old.
* 其次是 **[!UICONTROL Read audience]** 活动，用于检索银牌会员受众，并通过仅选择 18 到 30 岁之间的用户档案对其进行优化。
* A [Union](../../automating/using/union.md) activity that unites populations from both **[!UICONTROL Read audiences]** activities into one final population.
* An [Email delivery](../../automating/using/email-delivery.md) activity that sends the email to the population coming from the **[!UICONTROL Union]** activity.
