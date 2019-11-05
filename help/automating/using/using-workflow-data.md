---
title: 使用工作流数据
description: 了解使用导入或目标数据的不同可能性。
page-status-flag: 从未激活
uuid: 3dd6aeb-3a26-4214-b6a0-242c2b7fbc49
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 工作流——一般操作
discoiquuid: 90b250f1-f32d-4256-83ea-4c0627628610
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 使用工作流数据{#using-workflow-data}

在识别和准备数据后，它便可以在以下上下文中使用：

* 活动 **[!UICONTROL Update data]** 允许您对数据库中的字段执行成批更新。
* 该活 **[!UICONTROL Save audience]** 动允许您更新现有受众或从工作流中上游计算的人群创建新受众。 通过此活动创建或更新的受众是 **List** 或 **File受众** 。 此活动还允许您将配置文件导出为Adobe Experience cloud受众／区段。
* 该活 **[!UICONTROL Subscription Services]** 动允许您批量获取配置文件，并将其订阅到服务或取消订阅服务。
* 该活 **[!UICONTROL Extract file]** 动允许您以外部文件的形式从Adobe Campaign导出数据。

在定义配置文件目标后，您可以使用多个活动创建和发送提交：

* 该活 **[!UICONTROL Email delivery]** 动允许您配置在工作流中发送电子邮件。 这可以是单 **个发送电子邮件** ，只发送一次，也可以是循环 **电子邮件** 。
* 该 **[!UICONTROL SMS delivery]** 活动允许您配置在工作流中发送SMS。 这可以是单 **发SMS** ，只发送一次，也可以是重复 **的** SMS。
* 该活 **[!UICONTROL Mobile app delivery]** 动允许您配置在工作流中发送推送通知。 这可以是单 **个发送通知** ，只发送一次，也可以是循环通 **知** 。

