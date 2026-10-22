---
title: 生日投放
description: 本示例是生日工作流。 每天向当天生日的用户档案发送一封电子邮件。
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 535ddbce-d8ba-4578-9e37-10604291c95d
TQID: 'https://experienceleague.adobe.com/LXiYfz5VXaY7j0pOHWUCGJzp5F4bCsSCmFzEqsQG18E'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 52%
---
# 生日投放 {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

本示例是生日工作流。 每天向当天生日的用户档案发送一封电子邮件。

要构建工作流，请执行以下步骤：

* [调度程序](../../automating/using/scheduler.md)允许您在每天早上8点启动工作流。

  ![](assets/wkf_delivery_example_2.png)

* 利用[查询](../../automating/using/query.md)活动，可算出提供了电子邮件、且生日在当天的用户档案。 使用查询编辑工具面板中提供的预定义过滤器，执行生日计算。

  ![](assets/wkf_delivery_example_3.png)

* [电子邮件投放](../../automating/using/email-delivery.md)是定期进行的。 按月聚合发送情况。 因此，一个月内发送的所有电子邮件，都会被聚合到单独的一个视图中。 因此，一年内要执行 365 次投放，但在 Adobe Campaign 界面中，已将它们重组为 12 个视图（也称&#x200B;**定期执行**）。 历史记录和报告将按月提供而不是按每次发送提供。

  ![](assets/wkf_delivery_example_4.png)
