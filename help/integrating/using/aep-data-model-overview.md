---
solution: Campaign Standard
product: campaign
title: 体验数据模型概述
description: Experience Data Model(XDM)是一组标准的数据架构，可以将数据引入其中，以与Adobe Experience Platform解决方案和产品一起使用。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM集成
role: Data Architect
level: Experienced
exl-id: cc1aa669-30cd-4ea4-9fab-4d1b6c373744
source-git-commit: 92365fe416fced72e7ad5818da0dbed5d8f52f15
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 0%

---

# 体验数据模型概述{#experience-data-model-overview}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前处于测试阶段，可能会频繁更新，恕不另行通知。 需要在Azure上托管客户（目前仅适用于北美地区的测试版）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀团队。

Experience Data Model(XDM)是一组标准的数据架构，可以将数据引入其中，以与Adobe Experience Platform解决方案和产品一起使用。

通过专用API或XDM用户界面，可以创建和管理XDM模式。

## XDM工作区{#xdm-workspace}

XDM工作区提供了查看、创建和扩展数据架构的功能。

要访问XDM用户界面，请打开Adobe Experience Platform。 导航到数据模型窗口以创建或扩展XDM架构。

请参阅完整的[XDM工作区文档](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html)。

![](assets/aep_xdmworkspace.png)

## XDM API {#xdm-api}

您可以通过XDM架构API执行以下操作：

* 查看现有架构的列表
* 查看特定架构扩展现有架构
* 向扩展添加字段
* 创建和更新新架构
* 查看架构描述符
* 创建、更新和删除架构描述符

[开发人员指南](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html)中提供了处理API调用的所有详细信息。
