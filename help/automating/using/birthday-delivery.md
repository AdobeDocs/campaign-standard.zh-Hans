---
title: 生日投放
description: 本示例是生日工作流。每天向当天生日的用户档案发送一封电子邮件。
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 535ddbce-d8ba-4578-9e37-10604291c95d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 69%

---

# 生日投放 {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

本示例是生日工作流。每天向当天生日的用户档案发送一封电子邮件。

要构建工作流，请执行以下步骤：

* 的 [调度程序](../../automating/using/scheduler.md) 允许您在每天早上8点启动工作流。

   ![](assets/wkf_delivery_example_2.png)

* 的 [查询](../../automating/using/query.md) 活动允许您计算提供了电子邮件且生日在当天的用户档案。 使用查询编辑工具面板中提供的预定义过滤器，执行生日计算。

   ![](assets/wkf_delivery_example_3.png)

* 的 [电子邮件投放](../../automating/using/email-delivery.md) 重复。 按月聚合发送情况。因此，一个月内发送的所有电子邮件，都会被聚合到单独的一个视图中。因此，一年内要执行 365 次投放，但在 Adobe Campaign 界面中，已将它们重组为 12 个视图（也称&#x200B;**定期执行**）。历史记录和报告将按月提供而不是按每次发送提供。

   ![](assets/wkf_delivery_example_4.png)
