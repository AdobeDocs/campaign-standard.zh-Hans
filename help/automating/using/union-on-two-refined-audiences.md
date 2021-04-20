---
solution: Campaign Standard
product: campaign
title: 两个已优化受众的联合
description: 此用例显示了两个读取受众活动的合并。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 57%

---


# 两个已优化受众的联合 {#example--union-on-two-refined-audiences}

此示例中定义的工作流展示了两个 **[!UICONTROL Read audience]** 活动的并集。此工作流程的目标，是向 18 至 30 岁的金牌或银牌会员发送电子邮件。系统中已创建特定受众以跟踪金牌和银牌会员。

工作流的设计如下所示：

![](assets/readaudience_activity_example1.png)

* 第一个[读取受众](../../automating/using/read-audience.md)活动，它检索黄金成员受众，并通过仅选择18到30岁之间的用户档案来优化它。
* 其次是 **[!UICONTROL Read audience]** 活动，用于检索银牌会员受众，并通过仅选择 18 到 30 岁之间的用户档案对其进行优化。
* [合并](../../automating/using/union.md)活动，将来自&#x200B;**[!UICONTROL Read audiences]**&#x200B;活动的群体合并为一个最终群体。
* [电子邮件投放](../../automating/using/email-delivery.md)活动，用于将电子邮件发送给来自&#x200B;**[!UICONTROL Union]**&#x200B;活动的用户。
