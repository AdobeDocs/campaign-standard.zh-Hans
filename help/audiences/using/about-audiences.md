---
title: 关于受众
description: 了解如何从查询、列表或文件构建受众，以及如何从 Adobe Experience Cloud 导入受众。
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
translation-type: ht
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb
workflow-type: ht
source-wordcount: '249'
ht-degree: 100%

---


# 关于受众{#about-audiences}

受众是一种基于规则和属性的用户档案列表。

Adobe Campaign 允许您使用查询手动创建受众，或使用专用工作流自动创建受众。您也可以使用 Adobe Experience Cloud 中的共享受众。所有受众会重组为一个列表，该列表可通过 Adobe Campaign 主页上的 **[!UICONTROL Audiences]** 卡或 **[!UICONTROL Audiences]** 链接访问。

![](assets/audience_1.png)

您可以在 Adobe Campaign 中处理不同的受众类型。受众的类型对应于其创建方式：

* **[!UICONTROL Query]**：表示受众是基于 Adobe Campaign 受众列表数据库的数据[查询](../../automating/using/editing-queries.md#about-query-editor)创建的。每次复用时都会重新计算由查询定义的受众。。
* **[!UICONTROL List]**：表示受众是固定的用户档案列表。这些列表在[工作流](../../automating/using/get-started-workflows.md)中创建，在工作流中保存受众时，数据维度是已知的。例如，定向活动（尤其是 **[!UICONTROL Query]**）后或对从文件导入的数据进行协调后。
* **[!UICONTROL File]**：表示受众是直接从[文件导入](../../automating/using/load-file.md)工作流创建的，且保存受众时数据维度未知。
* **[!UICONTROL Experience Cloud]**：表示受众是从 Adobe Experience Cloud 导入的。仅当配置了受众共享功能时，此选项才可用。有关更多信息，请参阅[从 Adobe Experience Cloud 导入受众](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience)。

![](assets/audience_type_selection.png)
