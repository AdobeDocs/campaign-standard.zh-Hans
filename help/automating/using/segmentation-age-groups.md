---
solution: Campaign Standard
product: campaign
title: 根据年龄组进行细分
description: 本页根据数据库用户档案的年龄组显示数据库数据的分段。 该工作流旨在为每个年龄组发送特定的电子邮件。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
feature: 工作流
role: 数据架构师
level: 中间
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 65%

---


# 根据年龄组进行细分 {#segmentation-age-groups}

下方示例展示了如何根据年龄组对数据库用户档案进行分段。

该工作流旨在为每个年龄组发送特定的电子邮件。考虑到此工作流是测试营销策划的一部分，每个区段最多只能包含 100 个随机选择的用户档案，以便使用受限且具有代表性的受众。

![](assets/wkf_segment_example_4.png)

工作流由以下元素组成：

* 用于指定工作流执行日期的[调度程序活动](../../automating/using/segmentation.md)。
* [查询](../../automating/using/query.md)活动，以目标已输入其生日和电子邮件地址的人的用户档案。
* A [分段](../../automating/using/segmentation.md)活动，用于创建3个分为不同出站过渡的区段：18-25岁，26-32岁，用户档案32岁以上。 区段根据以下参数进行定义：

   ![](assets/wkf_segment_example_3.png)

   * 用于定义区段年龄组的年龄过滤器

      ![](assets/wkf_segment_new_segment.png)

   * 链接到 **[!UICONTROL Maximum size]** 限制为 100 的 **[!UICONTROL Random sampling]** 类型限制

      ![](assets/wkf_segment_example_1.png)

* 每段[电子邮件投放](../../automating/using/email-delivery.md)活动。
