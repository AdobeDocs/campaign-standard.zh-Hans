---
title: 生日投放
description: 此示例是生日工作流。 每天都会向用户档案发送一封电子邮件，其生日就在当天。
page-status-flag: never-activated
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-8010260554bb
context-tags: delivery,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 0%

---


# 生日投放 {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

此示例是生日工作流。 每天都会向用户档案发送一封电子邮件，其生日就在当天。

要构建工作流，请按照以下步骤操作：

* 该 [调度程序](../../automating/using/scheduler.md) 允许您每天早8点开始工作流。

   ![](assets/wkf_delivery_example_2.png)

* 该 [查询](../../automating/using/query.md) 活动允许您计算每次执行工作流时，提供电子邮件的用户档案以及其生日是当天的。 生日计算是使用查询编辑工具调色板中提供的预定义过滤器进行的。

   ![](assets/wkf_delivery_example_3.png)

* 电子 [邮件投放](../../automating/using/email-delivery.md) ，将重复出现。 发送按月汇总。 因此，一个月内发送的所有电子邮件都会汇总为单个视图。 因此，在一年内，有365个投放被执行，但在Adobe Campaign界面中，它们被重新分 **组为12个视图**（也称重复执行）。 历史记录和报告详细信息每月均显示，而不是每次发送。

   ![](assets/wkf_delivery_example_4.png)
