---
solution: Campaign Standard
product: campaign
title: 根据年龄组进行细分
description: 本页根据用户档案库的年龄组显示数据库的细分。 该工作流旨在为每个年龄组发送特定的电子邮件。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 66%

---


# 根据年龄组进行细分 {#segmentation-age-groups}

下方示例展示了如何根据年龄组对数据库用户档案进行分段。

该工作流旨在为每个年龄组发送特定的电子邮件。考虑到此工作流是测试营销策划的一部分，每个区段最多只能包含 100 个随机选择的用户档案，以便使用受限且具有代表性的受众。

![](assets/wkf_segment_example_4.png)

工作流由以下元素组成：

* A [Scheduler activity](../../automating/using/segmentation.md) to specify the workflow&#39;s execution date.
* A [Query](../../automating/using/query.md) activity to target profiles of people whose birthday and email address have been entered.
* A [Segmentation](../../automating/using/segmentation.md) activity to create 3 segments divided into different outbound transitions: 18-25-year old, 26-32-year old and profiles that are over 32 years old. 区段根据以下参数进行定义：

   ![](assets/wkf_segment_example_3.png)

   * 用于定义区段年龄组的年龄过滤器

      ![](assets/wkf_segment_new_segment.png)

   * 链接到 **[!UICONTROL Maximum size]** 限制为 100 的 **[!UICONTROL Random sampling]** 类型限制

      ![](assets/wkf_segment_example_1.png)

* 每个 [区段的电子邮件投放](../../automating/using/email-delivery.md) 活动。
