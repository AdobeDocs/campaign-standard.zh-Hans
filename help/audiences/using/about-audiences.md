---
title: 关于受众
description: 了解如何从查询、列表或文件构建受众，以及如何从Adobe Experience cloud导入受众。
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
source-git-commit: 1059b840d9a2d0c89a6cbd1808b645862747a76c

---


# 关于受众{#about-audiences}

受众是基于规则和属性的档案列表。

Adobe Campaign允许您使用查询或自动使用专用工作流手动创建受众。 您还可以使用Adobe Experience cloud中的共享受众。 所有受众将重新分组到一个列表中，该列表可通过Adobe Campaign主页 **[!UICONTROL Audiences]**上的卡片或链接访问该**[!UICONTROL Audiences]** 列表。

![](assets/audience_1.png)

您可以在Adobe Campaign中处理不同的受众类型。 受众类型与创建受众的方式相对应：

* **[!UICONTROL Query]**:指示受众是从受众列表[中](../../automating/using/editing-queries.md#about-query-editor)，从Adobe Campaign数据库查询数据创建的。 由查询定义的受众在每次进一步使用时都被重新计算。
* **[!UICONTROL List]**:表示受众是配置文件的固定列表。 这些列表是在保存受众时已[知数据维度的工作流](../../automating/using/discovering-workflows.md)中创建的。 例如，在定位活动(尤其是**[!UICONTROL Query]** )之后或从文件导入的数据对帐之后。
* **[!UICONTROL File]**:指示受众是直接从文件导入工作[流创建的](../../automating/using/load-file.md)，并且保存受众时数据维度未知。
* **[!UICONTROL Experience Cloud]**:表示受众是从Adobe Experience cloud导入的。 仅当已配置受众共享功能时，此选项才可用。 有关详细信息，请[参阅从Adobe Experience cloud导入受众](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience)。

![](assets/audience_type_selection.png)
