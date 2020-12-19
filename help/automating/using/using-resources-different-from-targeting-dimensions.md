---
solution: Campaign Standard
product: campaign
title: 使用与定向维度不同的资源
description: 了解如何使用与定位维度不同的资源。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 81%

---


# 使用与定向维度不同的资源{#using-resources-different-from-targeting-dimensions}

此用例说明如何使用与定位维度不同的资源，例如，在远程表中查找特定记录。

有关定位维度和资源的详细信息，请参阅[此部分](../../automating/using/query.md#targeting-dimensions-and-resources)

**示例 1：确定被带“Welcome back !”标签的投放所定向的用户档案**。

* 在本例中，我们想定向用户档案。我们将定向维度设置为 **[!UICONTROL Profiles (profile)]**。
* 我们要根据投放标签筛选选定的用户档案。因此，我们将资源设置为 **[!UICONTROL Delivery logs]**。这样，我们可直接在投放日志表格中进行筛选，从而提高效率。

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**示例 2：确定未被带“Welcome back !””标签的投放所定向的用户档案**

在上一个示例中，我们使用的资源与定向维度不同。仅当要查找远程表格（示例中的投放日志）中&#x200B;**存在**&#x200B;的记录时，才能执行此操作。

如果我们要查找远程表格中&#x200B;**不存在**&#x200B;的记录（例如，未被特定投放所定向的用户档案），则必须使用相同的资源和定向维度，因为远程表格（投放日志）中不存在该记录。

* 在本例中，我们想定向用户档案。我们将定向维度设置为 **[!UICONTROL Profiles (profile)]**。
* 我们要根据投放标签筛选选定的用户档案。无法直接对投放日志进行筛选，因为我们正在查找投放日志表格中不存在的记录。因此，我们将资源设置为 **[!UICONTROL Profile (profile)]**，并基于用户档案表构建查询。

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
