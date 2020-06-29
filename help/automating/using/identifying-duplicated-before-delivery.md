---
title: 在重复之前识别投放
description: 以下示例说明了一个外部重复数据删除，它允许您在发送电子邮件之前排除目标的重复。 这意味着您避免向同一用户档案发送多次通信。
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---


# 在重复之前识别投放 {#identifying-duplicates-before-a-delivery}

以下示例说明了一个外部重复数据删除，它允许您在发送电子邮件之前排除目标的重复。 这意味着您避免向同一用户档案发送多次通信。

该工作流由以下几部分组成：

![](assets/deduplication_example_workflow.png)

* 一 [种查询](../../automating/using/query.md) ，允许您定义电子邮件的目标。 此处，该工作流目标了客户端用户档案库中已存在超过一年的18到25岁的所有。

   ![](assets/deduplication_example_query.png)

* 一 [个外部重复数据删除](../../automating/using/deduplication.md) 活动，它允许您识别来自前一个查询的重复。 在此示例中，每个重复只保存一个记录。 重复使用电子邮件地址进行标识。 这意味着，对于要在定位中显示的每个电子邮件地址，只能发送一次电子邮件投放。

   选择的外部重复数据删除方 **[!UICONTROL Non-empty value]**&#x200B;法。 这样，您就可以确保在保存的重复记录中，优先于提供名 **字** 的记录。 如果在电子邮件内容的个性化字段中使用名，这将使其更加连贯。

   此外，还增加了额外的过渡，以保留重复并能够列表它们。

   ![](assets/deduplication_example_dedup.png)

* 放 [在投放](../../automating/using/email-delivery.md) 主出站过渡之后的电子邮件外部重复数据删除。
* 保存 [受众](../../automating/using/save-audience.md) 活动，放在外部重复数据删除的附加过渡之后，将重复保存在 **重复受众** 。 可以重复使用此受众，以直接从每个电子邮件投放中排除其成员。
