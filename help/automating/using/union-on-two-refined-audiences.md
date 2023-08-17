---
title: 两个已优化受众的联合
description: 此用例展示了两个读取受众活动的并集。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 6261f800-11bd-4b02-a587-49ddb0da240f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 58%

---

# 两个已优化受众的联合 {#example--union-on-two-refined-audiences}

此示例中定义的工作流展示了两个 **[!UICONTROL Read audience]** 活动的并集。此工作流程的目标，是向 18 至 30 岁的金牌或银牌会员发送电子邮件。系统中已创建特定受众以跟踪金牌和银牌会员。

工作流的设计如下所示：

![](assets/readaudience_activity_example1.png)

* 第一个 [读取受众](../../automating/using/read-audience.md) 此活动用于检索金牌会员受众，并通过仅选择18到30岁之间的用户档案对其进行优化。
* 其次是 **[!UICONTROL Read audience]** 活动，用于检索银牌会员受众，并通过仅选择 18 到 30 岁之间的用户档案对其进行优化。
* A [并集](../../automating/using/union.md) 将来自两者的群体联合在一起的活动 **[!UICONTROL Read audiences]** 将活动归入一个最终群体。
* An [电子邮件投放](../../automating/using/email-delivery.md) 活动向来自的群体发送电子邮件 **[!UICONTROL Union]** 活动。
