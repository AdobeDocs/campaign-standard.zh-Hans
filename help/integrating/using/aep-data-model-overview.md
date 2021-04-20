---
solution: Campaign Standard
product: campaign
title: 体验数据模型概述
description: 体验模式模型(XDM)是一套标准的数据模型，可以在其中摄取数据以用于Adobe Experience Platform解决方案和产品。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 7%

---


# 体验数据模型概述{#experience-data-model-overview}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前处于测试阶段，可能会在不通知的情况下频繁进行更新。 客户需要托管在Azure上（目前仅针对北美）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀团队。

体验模式模型(XDM)是一套标准的数据模型，可以在其中摄取数据以用于Adobe Experience Platform解决方案和产品。

XDM模式的创建和管理可通过专用API或XDM用户界面提供。

## XDM工作区{#xdm-workspace}

XDM Workspace提供了视图、创建和扩展数据模式的功能。

要访问XDM用户界面，请打开Adobe Experience Platform。 导航到“数据模型”窗口以创建或扩展XDM模式。

请查阅完整的[XDM工作区文档](https://docs.adobe.com/content/help/zh-Hans/experience-platform/xdm/api/getting-started.html)。

![](assets/aep_xdmworkspace.png)

## XDM API {#xdm-api}

您可以通过XDM模式API执行以下操作：

* 视图现有模式的列表
* 视图特定模式扩展现有模式
* 向扩展添加字段
* 创建和更新新模式
* 视图模式描述符
* 创建、更新和删除模式描述符

[《开发人员指南》](https://docs.adobe.com/content/help/en/experience-platform/xdm/api/getting-started.html)中提供了用于操作API调用的所有详细信息。
