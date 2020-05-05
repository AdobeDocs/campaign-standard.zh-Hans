---
title: 关于受众
description: 了解如何从查询、列表或文件构建受众，以及如何从Adobe Experience Cloud导入它们。
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# 关于受众{#about-audiences}

受众是基于规则和属性的用户档案的列表。

Adobe Campaign允许您使用查询手动创建受众，或自动使用专用工作流。 您还可以使用Adobe Experience Cloud中的共享受众。 所有受众都重新分组为一个列表，可通过Adobe Campaign **[!UICONTROL Audiences]** 主页上的卡或链接访 **[!UICONTROL Audiences]** 问该。

![](assets/audience_1.png)

您可以在Adobe Campaign中处理不同的受众类型。 受众的类型与其创建方式相对应：

* **[!UICONTROL Query]**: 指示受众是从库 [中的](../../automating/using/editing-queries.md#about-query-editor) 查询创建的，该Adobe Campaign是从受众列表创建的。 由受众定义的查询在每次进一步使用时重新计算。
* **[!UICONTROL List]**: 表示受众是固定的用户档案列表。 这些列表在工作流 [中创建](../../automating/using/get-started-workflows.md)，在该工作流中保存受众时，数据维是已知的。 例如，定位活动(尤其是 **[!UICONTROL Query]** )后或对从文件导入的数据进行协调后。
* **[!UICONTROL File]**: 指示受众是直接从文件导入工 [作流创建](../../automating/using/load-file.md) 的，并且保存受众时数据维未知。
* **[!UICONTROL Experience Cloud]**: 表示受众是从Adobe Experience Cloud导入的。 仅当配置了受众共享功能时，此选项才可用。 有关详细信息，请 [参阅从Adobe Experience Cloud导入受众](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience)。

![](assets/audience_type_selection.png)
