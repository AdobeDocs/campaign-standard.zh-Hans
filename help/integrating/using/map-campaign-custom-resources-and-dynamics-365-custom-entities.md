---
title: 映射 Campaign 自定义资源和 Dynamics 365 自定义实体
description: 了解如何在Adobe Campaign Standard与Microsoft Dynamics 365集成的背景下映射资源和实体。
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 映射活动资源和Dynamics 365实体

了解如何在Adobe Campaign Standard与Microsoft Dynamics 365之间的集成环境中映射自定义资源和自定义实体。

>[!CAUTION]
>
>此功能并非作为产品的一部分现成可用。实施需要咨询 Adobe。请联系您的 Adobe 代表以了解更多信息。

## 先决条件

Microsoft [Dynamics 365-Adobe Campaign Standard集成支持自定义实体](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md) ，使Dynamics 365中的自定义实体能够同步到活动中的相应自定义资源。

自定义资源中的新数据可用于多种用途，包括细分和个性化。

集成支持链接表和非链接表。 链接最多支持三个级别（即级别1->级别2->级别3）。

>[!CAUTION]
>
>如果任何活动自定义资源记录包含个人信息，则应用特定建议。 在本节 [中了解更多](../../integrating/using/notices-and-recommendations-for-acs-and-ms-dynamics.md#privacy-linked-resources)。

## 声明

配置自定义实体数据流时，务必注意以下事项：

* 创建和修改活动自定义资源是敏感操作，必须由专家用户执行。
* 对于自定义实体数据流，必须在Dynamics 365中为同步的自定义实体启用更改跟踪。
* 如果在Dynamics 365中，父记录和链接的子记录在接近同一时间创建，则由于集成的并行处理，新的子记录在其父记录之前被写入活动的可能性很小。

* 如果父记录和子记录使用1基数简 **单链接选项在活动端链接** ，则子记录将保持隐藏且无法访问（通过UI或API），直到父记录到达活动。

* (假定活动 **中有1个基数简单链接** )如果在Dynamics 365中更新或删除子记录，并且该更改在父记录以活动显示之前写入活动（不可能，但可能是远程），则更新或删除将不在活动中处理，并且将引发错误。 在更新的情况下，需要在Dynamics 365中再次更新相关记录，以同步更新的记录。 在删除的情况下，相关记录需要在活动端单独处理，因为Dynamics 365中不再有要删除或更新的记录。

* 如果您遇到这样的情况，即您认为自己有隐藏的子记录并且无法访问这些记录，则可以将基数链接类型临时更改为0或 **1基数简单链接** ，以访问这些记录。

本节提供活动自定义资源的更全 [面概述](../../developing/using/key-steps-to-add-a-resource.md)。
