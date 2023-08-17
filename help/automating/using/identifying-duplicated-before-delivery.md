---
title: 在投放之前标识重复项
description: 下方展示了一个重复数据删除示例，利用该用例可在发送电子邮件之前排除重复的目标。这意味着您可以避免向同一用户档案发送多次通信。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: a09b101b-f76f-4377-9854-1fcffaad4f9a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 78%

---

# 在投放之前标识重复项 {#identifying-duplicates-before-a-delivery}

下方展示了一个重复数据删除示例，利用该用例可在发送电子邮件之前排除重复的目标。这意味着您可以避免向同一用户档案发送多次通信。

该工作流由以下步骤组成：

![](assets/deduplication_example_workflow.png)

* A [查询](../../automating/using/query.md) 用于定义电子邮件的目标。 在本例中，该工作流用于定向客户端数据库中存在超过一年的 18 到 25 岁的所有用户档案。

  ![](assets/deduplication_example_query.png)

* A [删除重复项](../../automating/using/deduplication.md) 活动，用于标识来自上一个查询的重复项。 在本例中，只为每个重复项保存一个记录。使用电子邮件地址识别重复项。这意味着，只对定向中显示的每个电子邮件地址，发送一次电子邮件投放。

  选择的重复数据删除方法为 **[!UICONTROL Non-empty value]**。这样，就可确保在出现重复项时，优先保留提供了&#x200B;**名字**&#x200B;的记录。如果在电子邮件内容的个性化字段中使用了名字，这样可使其更加合乎逻辑。

  此外，还增加了额外的过渡，以保留重复项并将列它们列在表中。

  ![](assets/deduplication_example_dedup.png)

* An [电子邮件投放](../../automating/using/email-delivery.md) 位于重复数据删除的主叫客过渡之后。
* A [保存受众](../../automating/using/save-audience.md) 将活动放置到重复数据删除的附加过渡之后，以将重复项保存在 **重复** 受众。 此受众可重复利用，以直接从每个电子邮件投放中将其排除。
