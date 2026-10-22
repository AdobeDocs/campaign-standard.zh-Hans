---
title: 使用与定向维度不同的资源
description: 了解如何使用与定向维度不同的资源。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 5805bdfa-fb33-4a46-ba1e-7a10b067349b
TQID: 'https://experienceleague.adobe.com/tGVP20eQpo7EuB1xluX2AQHHMZ-IM-q6JmgFGp6Iwk4'
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
source-wordcount: '295'
ht-degree: 76%
---
# 使用与定向维度不同的资源 {#using-resources-different-from-targeting-dimensions}

此用例展示如何使用与定向维度不同的资源，例如在远程表格中查找特定记录。

有关定向维度和资源的详细信息，请参阅[此部分](../../automating/using/query.md#targeting-dimensions-and-resources)

**示例 1：确定被带“Welcome back !”标签的投放所定向的轮廓**。

* 在本例中，我们想定向轮廓。 我们将定向维度设置为 **[!UICONTROL Profiles (profile)]**。
* 我们要根据投放标签筛选选定的轮廓。 因此，我们将资源设置为 **[!UICONTROL Delivery logs]**。 这样，我们直接在投放日志表中进行筛选，这将提供更好的性能。

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**示例 2：确定未被带“Welcome back !””标签的投放所定向的轮廓**

在上一个示例中，我们使用的资源与定向维度不同。 仅当要查找远程表格（示例中的投放日志）中&#x200B;**存在**&#x200B;的记录时，才能执行此操作。

如果我们要查找远程表格中&#x200B;**不存在**&#x200B;的记录（例如，未被特定投放所定向的轮廓），则必须使用相同的资源和定向维度，因为远程表格（投放日志）中不存在该记录。

* 在本例中，我们想定向轮廓。 我们将定向维度设置为 **[!UICONTROL Profiles (profile)]**。
* 我们要根据投放标签筛选选定的轮廓。 无法直接对投放日志进行筛选，因为我们正在查找投放日志表格中不存在的记录。 因此，我们将资源设置为 **[!UICONTROL Profile (profile)]**，并基于轮廓表构建查询。

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
