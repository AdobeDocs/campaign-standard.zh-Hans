---
solution: Campaign Standard
product: campaign
title: 关于服务订阅者的增量查询
description: 以下示例演示如何配置增量查询活动以过滤服务的订阅者。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 66%

---


# 关于服务订阅者的增量查询 {#example--incremental-query-on-subscribers-to-a-service}

以下示例显示了 **[!UICONTROL Incremental query]** 活动的配置，该活动用于筛选 Adobe Campaign 数据库中订阅了 **Running Newsletter** 服务的用户档案，以向他们发送包含促销代码的欢迎电子邮件。

工作流由以下元素组成：

![](assets/incremental_query_example1.png)

* [调度程序](../../automating/using/scheduler.md)活动，每周一早6点执行工作流。

   ![](assets/incremental_query_example2.png)

* 一个[增量查询](../../automating/using/incremental-query.md)活动，它在第一次执行期间目标所有当前用户，然后在以下执行期间仅该周的新用户。

   ![](assets/incremental_query_example3.png)

* [电子邮件投放](../../automating/using/email-delivery.md)活动。 该工作流每周执行一次，但您可以聚合每月发送的电子邮件和结果以生成报告，例如，生成针对整个月（而不仅仅是一周）时间段的报表。

   要实现此目的，请选择在此处创建一个 **[!UICONTROL Recurring email]**，以 **[!UICONTROL By month]** 重组电子邮件和结果。

   定义电子邮件的内容并插入欢迎促销代码。有关详细信息，请参阅[定义电子邮件内容](../../designing/using/personalization.md)部分。

然后，启动工作流执行。新订阅者每周都将收到包含促销代码的欢迎电子邮件。
