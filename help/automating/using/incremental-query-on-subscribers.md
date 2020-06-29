---
title: 增量查询服务的订户
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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 0%

---


# 增量查询服务的订户 {#example--incremental-query-on-subscribers-to-a-service}

以下示例显示了活动的配 **[!UICONTROL Incremental query]** 置，该Adobe Campaign过滤器库中订阅了运行Newsletter服务的 **用户档案** ，以向他们发送包含促销代码的欢迎电子邮件。

工作流由以下元素组成：

![](assets/incremental_query_example1.png)

* 一 [个调度程序](../../automating/using/scheduler.md) 活动，每周一早6点执行该工作流。

   ![](assets/incremental_query_example2.png)

* 一 [个增量查询](../../automating/using/incremental-query.md) 活动，在第一次执行时目标所有当前订阅者，然后在以下执行时仅该周的新订阅者。

   ![](assets/incremental_query_example3.png)

* 电子 [邮件投放](../../automating/using/email-delivery.md) 活动。 该工作流每周执行一次，但您可以聚合每月发送的电子邮件和结果，例如，在整个月（而不仅仅是一周）的时间段内生成报表。

   为此，请选择在此处创建一 **[!UICONTROL Recurring email]** 个重新分组电子邮件和结果 **[!UICONTROL By month]**。

   定义电子邮件的内容并插入欢迎促销代码。 有关此内容的详细信息，请参 [阅定义电子邮件内](../../designing/using/personalization.md) 容部分。

然后开始工作流执行。 每周，新订阅者将收到包含促销代码的欢迎电子邮件。
