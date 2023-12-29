---
title: 使用与定向维度不同的资源
description: 了解如何使用与定向维度不同的资源。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 5805bdfa-fb33-4a46-ba1e-7a10b067349b
source-git-commit: 9c14fc3de60d8e0304f8a7ebd46e7be34d2e0499
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 76%

---

# 使用与定向维度不同的资源 {#using-resources-different-from-targeting-dimensions}

此用例展示如何使用与定向维度不同的资源，例如在远程表格中查找特定记录。

有关定向维度和资源的更多信息，请参阅 [本节](../../automating/using/query.md#targeting-dimensions-and-resources)

**示例 1：确定被带“Welcome back !”标签的投放所定向的用户档案**。

* 在本例中，我们想定向用户档案。我们将定向维度设置为 **[!UICONTROL Profiles (profile)]**。
* 我们要根据投放标签筛选选定的用户档案。因此，我们将资源设置为 **[!UICONTROL Delivery logs]**。这样，我们直接在投放日志表中进行筛选，这将提供更好的性能。

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**示例 2：确定未被带“Welcome back !””标签的投放所定向的用户档案**

在上一个示例中，我们使用的资源与定向维度不同。仅当要查找远程表格（示例中的投放日志）中&#x200B;**存在**&#x200B;的记录时，才能执行此操作。

如果我们要查找远程表格中&#x200B;**不存在**&#x200B;的记录（例如，未被特定投放所定向的用户档案），则必须使用相同的资源和定向维度，因为远程表格（投放日志）中不存在该记录。

* 在本例中，我们想定向用户档案。我们将定向维度设置为 **[!UICONTROL Profiles (profile)]**。
* 我们要根据投放标签筛选选定的用户档案。无法直接对投放日志进行筛选，因为我们正在查找投放日志表格中不存在的记录。因此，我们将资源设置为 **[!UICONTROL Profile (profile)]**，并基于用户档案表构建查询。

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
