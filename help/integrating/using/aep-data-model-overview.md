---
title: Experience数据模型概述
description: Experience Data Model (XDM)是一组标准数据架构，可能会将数据摄取到其中以用于Adobe Experience Platform解决方案和产品。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: cc1aa669-30cd-4ea4-9fab-4d1b6c373744
hide: true
hidefromtoc: true
source-git-commit: 110f3ccb5865e70c78e18485b4ff4ba7a648af3f
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 0%

---

# Experience数据模型概述 {#experience-data-model-overview}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前处于测试阶段，可能会频繁更新，恕不另行通知。 客户需要在Azure上托管（目前为仅北美测试版）才能访问这些功能。 如果您希望获得访问权限，请联系Adobe客户关怀团队。

Experience Data Model (XDM)是一组标准数据架构，可能会将数据摄取到其中以用于Adobe Experience Platform解决方案和产品。

XDM模式的创建和管理可通过专用的API或XDM用户界面进行。

## XDM工作区 {#xdm-workspace}

XDM工作区提供了查看、创建和扩展数据架构的功能。

要访问XDM用户界面，请打开Adobe Experience Platform。 导航到“数据模型”窗口以创建或扩展XDM架构。

请参阅完整版 [XDM工作区文档](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html).

![](assets/aep_xdmworkspace.png)

## XDM API {#xdm-api}

您可以通过XDM架构API执行以下操作：

* 查看现有架构的列表
* 查看特定架构扩展现有架构
* 将字段添加到扩展
* 创建和更新新架构
* 查看架构描述符
* 创建、更新和删除架构描述符

有关处理API调用的所有详细信息，请参阅 [开发人员指南](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html).
