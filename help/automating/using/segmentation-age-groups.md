---
title: 根据年龄组进行细分
description: 本页根据用户档案库的年龄组显示数据库的细分。 该工作流旨在为每个年龄组发送特定电子邮件。
page-status-flag: never-activated
uuid: 77796f18-cad5-4e7a-9d7b-4ed0dd8943bf
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 0ccd9d02-772e-406b-874a-5381dd0c8709
context-tags: segmentation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%

---


# 根据年龄组进行细分 {#segmentation-age-groups}

以下示例显示了根据用户档案组对数据库数据进行细分。

该工作流旨在为每个年龄组发送特定电子邮件。 考虑到此工作流是测试活动的一部分，每个用户档案段最多只能包含100个随机选择的受众，以便同时使用受限且具有代表性的。

![](assets/wkf_segment_example_4.png)

工作流由以下元素组成：

* 用 [于指定](../../automating/using/segmentation.md) 工作流执行日期的调度程序活动。
* 查询 [](../../automating/using/query.md) ,活动已输入生日和电子邮件地址的目标用户档案。
* 用于 [创建](../../automating/using/segmentation.md) 3个细分区段的细分活动，它分为不同的出站过渡: 18-25岁，26-32岁，用户档案32岁以上。 段根据以下参数进行定义：

   ![](assets/wkf_segment_example_3.png)

   * 用于定义区段年龄组的年龄过滤器

      ![](assets/wkf_segment_new_segment.png)

   * 链 **[!UICONTROL Random sampling]** 接到限制为100的类 **[!UICONTROL Maximum size]** 型限制

      ![](assets/wkf_segment_example_1.png)

* 每个 [区段的电子邮件投放](../../automating/using/email-delivery.md) 活动。
