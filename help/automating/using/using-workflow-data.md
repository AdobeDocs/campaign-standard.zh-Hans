---
title: 使用工作流数据
seo-title: 使用工作流数据
description: 使用工作流数据
seo-description: 了解不同的可能性，以使用您导入或定位的数据。
page-status-flag: 从未激活
uuid: dd66aeb-3a26-4214-b6 a0-242c2 b7 fbc49
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 工作流常规操作
discoiquuid: 90b250f1-f32 d-4256-83ea-4c0627628610
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Using workflow data{#using-workflow-data}

识别并准备数据后，可在以下上下文中使用该数据：

* **[!UICONTROL Update data]** 活动允许您对数据库中的字段执行大规模更新。
* **[!UICONTROL Save audience]** 该活动允许您更新现有受众，或从工作流中上游计算的人群中创建新受众。The audiences created or updated from this activity are **List** or **File** audiences. 此活动还允许您将配置文件作为Adobe Experience Cloud受众/区段导出。
* **[!UICONTROL Subscription Services]** 通过该活动，您可以将配置文件放置在大量资产中，并将其订阅服务或取消订阅服务。
* **[!UICONTROL Extract file]** 活动允许您以外部文件的形式从Adobe Campaign中导出数据。

定义配置文件目标后，您可以使用多个活动创建和发送提交内容：

* **[!UICONTROL Email delivery]** 活动允许您配置在工作流中发送电子邮件。This can be a **single send** email and sent just once, or it can be a **recurring** email.
* **[!UICONTROL SMS delivery]** 活动允许您配置在工作流中发送SMS。This can be a **single send** SMS and sent just once, or it can be a **recurring** SMS.
* **[!UICONTROL Mobile app delivery]** 活动允许您配置在工作流中发送推送通知。This can be a **single send** notification and sent just once, or it can be a **recurring** notification.

