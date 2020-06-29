---
title: 合并两家精炼受众
description: 此用例显示两个读取受众活动的合并。
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 0%

---


# 合并两家精炼受众 {#example--union-on-two-refined-audiences}

此示例中定义的工作流显示两个合并的 **[!UICONTROL Read audience]** 活动。 此工作流程的目标是向年满18至30周岁的金牌或银牌会员发送电子邮件。 系统中已创建特定受众以跟踪金银会员。

该工作流的设计如下：

![](assets/readaudience_activity_example1.png)

* 第一个 [读取受众](../../automating/using/read-audience.md) 活动，它检索黄金成员受众，并通过仅选择18到30年的用户档案来优化它。
* 第二个活动 **[!UICONTROL Read audience]** ，检索银会员受众，并通过仅选择18到30岁之间的用户档案来优化它。
* 一种 [合并](../../automating/using/union.md) 活动，将来自两个活动的 **[!UICONTROL Read audiences]** 人群合并成最终的人群。
* 电 [子邮件投放](../../automating/using/email-delivery.md) 活动，用于向来自活动的人群发送电子邮件 **[!UICONTROL Union]** 。
