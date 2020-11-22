---
solution: Campaign Standard
product: campaign
title: 在投放之前标识重复项
description: 下方展示了一个重复数据删除示例，利用该用例可在发送电子邮件之前排除重复的目标。这意味着您可以避免向同一用户档案发送多次通信。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 78%

---


# 在投放之前标识重复项 {#identifying-duplicates-before-a-delivery}

下方展示了一个重复数据删除示例，利用该用例可在发送电子邮件之前排除重复的目标。这意味着您可以避免向同一用户档案发送多次通信。

该工作流由以下步骤组成：

![](assets/deduplication_example_workflow.png)

* A [Query](../../automating/using/query.md) which allows you to define the target of the email. 在本例中，该工作流用于定向客户端数据库中存在超过一年的 18 到 25 岁的所有用户档案。

   ![](assets/deduplication_example_query.png)

* A [Deduplication](../../automating/using/deduplication.md) activity, which allows you to identify the duplicates that come from the preceding query. 在本例中，只为每个重复项保存一个记录。使用电子邮件地址识别重复项。这意味着，只对定向中显示的每个电子邮件地址，发送一次电子邮件投放。

   选择的重复数据删除方法为 **[!UICONTROL Non-empty value]**。这样，就可确保在出现重复项时，优先保留提供了&#x200B;**名字**&#x200B;的记录。如果在电子邮件内容的个性化字段中使用了名字，这样可使其更加合乎逻辑。

   此外，还增加了额外的过渡，以保留重复项并将列它们列在表中。

   ![](assets/deduplication_example_dedup.png)

* An [Email delivery](../../automating/using/email-delivery.md) placed after the main outbound transition of the deduplication.
* A [Save audience](../../automating/using/save-audience.md) activity placed after the additional transition of the deduplication to save the duplicates in a **Duplicates** audience. 此受众可重复利用，以直接从每个电子邮件投放中将其排除。
