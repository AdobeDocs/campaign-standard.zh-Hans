---
title: 关于服务订阅者的增量查询
description: 以下範例說明如何設定增量查詢活動，以篩選服務的訂閱者。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: c80ed1f6-ad8a-4448-a6df-b9881327228a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 67%

---

# 关于服务订阅者的增量查询 {#example--incremental-query-on-subscribers-to-a-service}

以下示例显示了 **[!UICONTROL Incremental query]** 活动的配置，该活动用于筛选 Adobe Campaign 数据库中订阅了 **Running Newsletter** 服务的用户档案，以向他们发送包含促销代码的欢迎电子邮件。

工作流由以下元素组成：

![](assets/incremental_query_example1.png)

* A [排程器](../../automating/using/scheduler.md) 活動，每週一早上6點執行工作流程。

   ![](assets/incremental_query_example2.png)

* 一個 [增量查詢](../../automating/using/incremental-query.md) 活動，在第一次執行期間鎖定所有目前訂閱者，然後在下列執行期間只鎖定該周的新訂閱者。

   ![](assets/incremental_query_example3.png)

* 一個 [電子郵件傳遞](../../automating/using/email-delivery.md) 活動。 该工作流每周执行一次，但您可以聚合每月发送的电子邮件和结果以生成报告，例如，生成针对整个月（而不仅仅是一周）时间段的报表。

   要实现此目的，请选择在此处创建一个 **[!UICONTROL Recurring email]**，以 **[!UICONTROL By month]** 重组电子邮件和结果。

   定义电子邮件的内容并插入欢迎促销代码。有關詳細資訊，請參閱 [定義電子郵件內容](../../designing/using/personalization.md) 區段。

然后，启动工作流执行。新订阅者每周都将收到包含促销代码的欢迎电子邮件。
