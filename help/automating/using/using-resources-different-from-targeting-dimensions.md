---
title: 使用不同于定位维度的资源
description: 了解如何使用与定位维度不同的资源。
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f3a668860659e40645ce3e4aab879cae5ad90083
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---


# 使用不同于定位维度的资源 {#using-resources-different-from-targeting-dimensions}

此用例说明如何使用与定位维度不同的资源，例如，在远程表中查找特定记录。

有关定位维度和资源的详细信息，请参 [阅本节](../../automating/using/query.md#targeting-dimensions-and-resources)

**示例1: 用标签“欢迎回来！”标识投放所针对的用户档案**。

* 在这个例子中，我们想目标用户档案。 我们将定位维度设为 **[!UICONTROL Profiles (profile)]**。
* 我们要根据用户档案标签筛选选定的投放。 因此，我们将资源设为 **[!UICONTROL Delivery logs]**。 这样，我们直接在投放日志表中进行过滤，这将优惠更好的性能。

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**示例2: 标有“欢迎回来！”的标签，识别未被投放瞄准的用户档案**

在上一个示例中，我们使用的资源与定位维度不同。 仅当要查找远程表中存在的记录( **示例中的投放日志** )时，才能执行此操作。

如果我们要查找远程表中 **不存在** (例如，未被特定投放定位的用户档案)的记录，则必须使用相同的资源和定位维度，因为该记录将不在远程表中(投放日志)。

* 在这个例子中，我们想目标用户档案。 我们将定位维度设为 **[!UICONTROL Profiles (profile)]**。
* 我们要根据用户档案标签筛选选定的投放。 无法直接对投放日志进行筛选，因为我们正在查找投放日志表中不存在的记录。 因此，我们将在查询表 **[!UICONTROL Profile (profile)]** 上设置资源并构建用户档案。

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
