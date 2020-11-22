---
solution: Campaign Standard
product: campaign
title: 体验数据模型概述
description: 体验数据模型(XDM)是一套标准的数据模式，可以在其中摄取数据以用于Adobe Experience Platform解决方案和产品。
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 7%

---


# 体验数据模型概述 {#experience-data-model-overview}

>[!IMPORTANT]
>
>Adobe Experience Platform数据连接器目前处于测试阶段，可能会在不通知的情况下频繁进行更新。 客户必须托管在Azure上（目前仅限北美的beta版），才能访问这些功能。 如果您想要访问，请联系Adobe客户服务中心。

体验数据模型(XDM)是一套标准的数据模式，可以在其中摄取数据以用于Adobe Experience Platform解决方案和产品。

XDM模式的创建和管理可通过专用API或XDM用户界面提供。

## XDM工作区 {#xdm-workspace}

XDM Workspace提供了视图、创建和扩展数据模式的能力。

要访问XDM用户界面，请打开Adobe Experience Platform。 导航到“数据模型”窗口以创建或扩展XDM模式。

请查阅完整的 [XDM工作区文档](https://docs.adobe.com/content/help/zh-Hans/experience-platform/xdm/api/getting-started.html)。

![](assets/aep_xdmworkspace.png)

## XDM API {#xdm-api}

您可以通过XDM模式API执行以下操作：

* 视图现有模式的列表
* 视图特定模式扩展现有模式
* 向扩展添加字段
* 创建和更新新模式
* 视图模式描述符
* 创建、更新和删除模式描述符

可在开发人员指南中找到处理API调用的所 [有详细信息](https://docs.adobe.com/content/help/zh-Hans/experience-platform/xdm/api/getting-started.html)。
