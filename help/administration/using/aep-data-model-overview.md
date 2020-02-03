---
title: 体验数据模型概述
description: Experience Data Model(XDM)是一套标准的数据架构，可以在其中摄取数据以与Adobe Experience Platform解决方案和产品一起使用。
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5f3bf4c2d0bba095182194ac28b3107eae2c54a6

---


# 体验数据模型概述 {#experience-data-model-overview}

>[!IMPORTANT]
>
>Campaign Standard Data服务目前处于测试阶段，可能会在不另行通知的情况下频繁进行更新。 客户必须托管在Azure上（目前仅针对北美）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀。

Experience Data Model(XDM)是一套标准的数据架构，可以在其中摄取数据以与Adobe Experience Platform解决方案和产品一起使用。

XDM架构的创建和管理可通过专用API或XDM用户界面使用。

## XDM工作区(#xdm-workspace)

XDM Workspace提供了查看、创建和扩展数据架构的功能。

要访问XDM用户界面，请打开Adobe Experience Platform。 导航到“数据模型”窗口以创建或扩展XDM架构。

请查阅完整 [的XDM Workspace文档](https://www.adobe.io/apis/experienceplatform/home/xdm/xdmservices.html#!api-specification/markdown/narrative/technical_overview/schema_registry/xdm_system/xdm_system_in_experience_platform.md)。

![](assets/aep_xdmworkspace.png)

## XDM API {#xdm-api}

您可以通过XDM架构API执行以下操作：

* 查看现有架构的列表
* 查看特定架构扩展现有架构
* 向扩展添加字段
* 创建和更新新架构
* 查看架构描述符
* 创建、更新和删除架构描述符

《开发人员指南》中提供了用于操作API调用的所 [有详细信息](https://www.adobe.io/apis/experienceplatform/home/xdm/xdmservices.html#!api-specification/markdown/narrative/technical_overview/schema_registry/schema_registry_developer_guide.md)。
