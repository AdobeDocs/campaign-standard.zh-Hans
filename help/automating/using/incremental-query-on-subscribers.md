---
title: 关于服务订阅者的增量查询
description: 以下示例演示如何配置增量查询活动以筛选服务的订阅者。
page-status-flag: never-activated
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: incremental,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 关于服务订阅者的增量查询 {#example--incremental-query-on-subscribers-to-a-service}

以下示例显示了 **[!UICONTROL Incremental query]** 活动的配置，该活动用于筛选 Adobe Campaign 数据库中订阅了 **Running Newsletter** 服务的用户档案，以向他们发送包含促销代码的欢迎电子邮件。

工作流由以下元素组成：

![](assets/incremental_query_example1.png)

* A [Scheduler](../../automating/using/scheduler.md) activity, to execute the workflow every Monday at 6 am.

   ![](assets/incremental_query_example2.png)

* An [Incremental query](../../automating/using/incremental-query.md) activity, which targets all of the current subscribers during the first execution, then only the new subscribers of that week during the following executions.

   ![](assets/incremental_query_example3.png)

* 电子 [邮件投放](../../automating/using/email-delivery.md) 活动。 该工作流每周执行一次，但您可以聚合每月发送的电子邮件和结果以生成报告，例如，生成针对整个月（而不仅仅是一周）时间段的报表。

   要实现此目的，请选择在此处创建一个 **[!UICONTROL Recurring email]**，以 **[!UICONTROL By month]** 重组电子邮件和结果。

   定义电子邮件的内容并插入欢迎促销代码。有关此内容的详细信息，请参 [阅定义电子邮件内](../../designing/using/personalization.md) 容部分。

然后，启动工作流执行。新订阅者每周都将收到包含促销代码的欢迎电子邮件。
