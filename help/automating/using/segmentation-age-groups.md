---
title: 根据年龄组进行细分
description: 此頁面會根據年齡群組區分資料庫設定檔。 该工作流旨在为每个年龄组发送特定的电子邮件。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: dab7ef86-4776-48f4-be9a-37de316e0dd9
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 66%

---

# 根据年龄组进行细分 {#segmentation-age-groups}

下方示例展示了如何根据年龄组对数据库用户档案进行分段。

该工作流旨在为每个年龄组发送特定的电子邮件。考虑到此工作流是测试营销策划的一部分，每个区段最多只能包含 100 个随机选择的用户档案，以便使用受限且具有代表性的受众。

![](assets/wkf_segment_example_4.png)

工作流由以下元素组成：

* A [排程器活動](../../automating/using/segmentation.md) 以指定工作流程的執行日期。
* A [查詢](../../automating/using/query.md) 已輸入其生日及電子郵件地址之人們的目標設定檔的活動。
* A [細分](../../automating/using/segmentation.md) 建立分為不同出站轉變的3個區段的活動：18-25歲、26-32歲及超過32歲的設定檔。 区段根据以下参数进行定义：

   ![](assets/wkf_segment_example_3.png)

   * 用于定义区段年龄组的年龄过滤器

      ![](assets/wkf_segment_new_segment.png)

   * 链接到 **[!UICONTROL Maximum size]** 限制为 100 的 **[!UICONTROL Random sampling]** 类型限制

      ![](assets/wkf_segment_example_1.png)

* 一個 [電子郵件傳遞](../../automating/using/email-delivery.md) 每個區段的活動。
