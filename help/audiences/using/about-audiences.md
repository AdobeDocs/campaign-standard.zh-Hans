---
title: 关于受众
seo-title: 关于受众
description: 关于受众
seo-description: 了解如何从查询、列表或文件构建受众，以及如何从Adobe Experience Cloud中导入受众。
page-status-flag: 从未激活
uuid: b3996642-96ec-489e-b146-c8 c2 cb52 aa32
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 受众
content-type: reference
topic-tags: 管理受众
discoiquuid: 750ed8d-67a5-4180-bfec-2a8 e3098 c812
context-tags: 受众，向导；受众，概述；交付，受众，返回
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# About audiences{#about-audiences}

受众是基于规则和属性的档案列表。

Adobe Campaign允许您使用查询或使用专用工作流程自动创建受众。您还可以从Adobe Experience Cloud中使用共享受众。All of the audiences are regrouped into a list that can be accessed via the **[!UICONTROL Audiences]** card on the Adobe Campaign home page or from the **[!UICONTROL Audiences]** link.

![](assets/audience_1.png)

您可以在Adobe Campaign中处理不同的受众类型。受众的类型与创建该受众的方式对应：

* **[!UICONTROL Query]**：表示受众是从 [Adobe](../../automating/using/editing-queries.md#about-query-editor) Campaign数据库中的数据查询创建的，该查询来自受众列表。每次进一步使用查询定义的受众都会重新计算。
* **[!UICONTROL List]**：表示受众是一个固定的配置文件列表。These lists are created in a [workflow](../../automating/using/discovering-workflows.md), where the data dimension is known when saving the audience. For example, after targeting activities (especially **[!UICONTROL Query]** ) or after the reconciliation of data imported from a file.
* **[!UICONTROL File]**：表示受众是从 [文件导入](../../automating/using/load-file.md) 工作流直接创建的，并且在保存受众时数据维度未知。
* **[!UICONTROL Experience Cloud]**：表示受众从Adobe Experience Cloud导入。仅当配置了受众共享功能时，此选项才可用。For more information, see [Importing an audience from the Adobe Experience Cloud](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience).

![](assets/audience_type_selection.png)

