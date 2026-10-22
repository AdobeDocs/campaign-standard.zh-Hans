---
title: 根据年龄组进行细分
description: 本页介绍如何根据年龄组对数据库用户档案进行分段。 该工作流旨在为每个年龄组发送特定的电子邮件。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: dab7ef86-4776-48f4-be9a-37de316e0dd9
TQID: 'https://experienceleague.adobe.com/LkH1qmElMwEn6JGmUaWj7Qpv7arSvLAZixbfJYTi2NQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 58%
---
# 根据年龄组进行细分 {#segmentation-age-groups}

以下示例显示了根据年龄组对数据库用户档案进行分段的情况。

该工作流旨在为每个年龄组发送特定的电子邮件。 考虑到此工作流是测试营销策划的一部分，每个区段最多只能包含 100 个随机选择的轮廓，以便使用受限且具有代表性的受众。

![](assets/wkf_segment_example_4.png)

工作流由以下元素组成：

* 用于指定工作流执行日期的[调度程序活动](../../automating/using/segmentation.md)。
* [查询](../../automating/using/query.md)活动，用于定向已输入生日和电子邮件地址的用户档案。
* 用于创建3个区段的[分段](../../automating/using/segmentation.md)活动，这些区段将划分不同的叫客过渡：18-25岁、26-32岁以及32岁以上的用户档案。 区段根据以下参数进行定义：

  ![](assets/wkf_segment_example_3.png)

  * 用于定义区段年龄组的年龄过滤器

    ![](assets/wkf_segment_new_segment.png)

  * 链接到 **[!UICONTROL Maximum size]** 限制为 100 的 **[!UICONTROL Random sampling]** 类型限制

    ![](assets/wkf_segment_example_1.png)

* 每个区段的[电子邮件投放](../../automating/using/email-delivery.md)活动。
