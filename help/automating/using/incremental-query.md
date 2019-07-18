---
title: 增量查询
seo-title: 增量查询
description: 增量查询
seo-description: 增量式查询活动允许您从Adobe Campaign数据库过滤和提取大量元素。
page-status-flag: 从未激活
uuid: 73b42422-e815-43ef-84c-97c4433 cc98
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 定位活动
discoiquuid: 80961e73-42ec-463a-8496-cff69 fab0475
context-tags: incremental，main
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 15bba7a6f76cbd17b07f1243075da0832619278b

---


# Incremental query{#incremental-query}

## Description {#description}

![](assets/incremental.png)

**[!UICONTROL Incremental query]** 活动允许您过滤和提取Adobe Campaign数据库中的大量元素。每次执行此活动时，之前执行的结果将被排除。这允许您仅定位新元素。

You can define **[!UICONTROL Additional data]** for the targeted population via a dedicated tab. 此数据存储在其他列中，只能用于进行中的工作流。

活动使用查询编辑器工具。This tool is detailed in a [dedicated section](../../automating/using/editing-queries.md#about-query-editor).

## Context of use {#context-of-use}

An **[!UICONTROL Incremental query]** has to be linked to a **[!UICONTROL Scheduler]** in order to define the execution frequency of the workflow, and therefore the query.

**[!UICONTROL Processed data]** 此选项卡特定于此活动，允许您根据需要查看活动之前执行的任何结果。

**[!UICONTROL Incremental query]** 该活动可用于各种类型的用途：

* 将个人细分为定义消息、受众等目标。
* 导出数据。

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Incremental query]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. If you would like to run a query on a resource other than the profile resource, go to the activity's **[!UICONTROL Properties]** tab and select a **[!UICONTROL Resource]** and a **[!UICONTROL Targeting dimension]**.

   The **[!UICONTROL Resource]** allows you to refine the filters displayed in the palette whereas the **[!UICONTROL Targeting dimension]**, contextual with regard to the resource selected, corresponds to the type of population that you would like to obtain (identified profiles, deliveries, data linked to the selected resource, etc.).

1. **[!UICONTROL Target]** 在选项卡中，通过定义和合并规则来运行查询。
1. **[!UICONTROL Processed data]** 在选项卡中，选择要用于工作流执行的增量模式：

   * **[!UICONTROL Use the exclusion of the results of previous executions]**：之前执行每个新执行的结果将被排除。
   * **[!UICONTROL Use a date field]**：下一次执行只考虑所选日期字段大于或等于 **[!UICONTROL Incremental query]** 活动上一个执行日期的结果。You can select any date field pertaining to the resource selected in the **[!UICONTROL Properties]** tab. 查询大型资源(如日志数据)时，此模式具有更好的性能。

      在第一次执行工作流后，您可以在此选项卡中看到将用于下一次执行的最后一个执行日期。每次执行工作流时，都会自动更新它。您仍可以手动输入新值来覆盖此值，从而满足您的需求。
   >[!NOTE]
   >
   >**[!UICONTROL Use a date field]** 此模式可根据选择的日期字段允许更大的灵活性。例如，如果选定字段与修改日期相对应，则日期字段模式允许您检索最近更新过的数据，而另一模式只会排除先前执行中已定位的录制内容，即使自最后一次执行工作流以来也是如此。

   ![](assets/incremental_query_usedatefield.png)

1. You can define **[!UICONTROL Additional data]** for the targeted population via a dedicated tab. 此数据存储在其他列中，只能用于进行中的工作流。特别是，您可以从链接到查询定位维度的Adobe Campaign数据库表中添加数据。Consult the [Enriching data](../../automating/using/query.md#enriching-data) section.
1. 确认活动的配置并保存工作流。

## Enriching data {#enriching-data}

Just as for a query, you can enrich the data from an **[!UICONTROL Incremental query]**. Consult the [Enriching data](../../automating/using/query.md#enriching-data) section.

## Example: incremental query on subscribers to a service {#example--incremental-query-on-subscribers-to-a-service}

The following example shows the configuration of an **[!UICONTROL Incremental query]** activity which filters the profiles in the Adobe Campaign database that are subscribed to the **Running Newsletter** service, to send them a welcome email containing a promo code.

该工作流由以下元素组成：

![](assets/incremental_query_example1.png)

* **[!UICONTROL Scheduler]** A activity，to execenecute the workflow very every at am.

   ![](assets/incremental_query_example2.png)

* **[!UICONTROL Incremental query]** 活动，该活动面向在第一次执行期间所有当前订户，然后仅针对在执行以下执行期间的那一周的新订户。

   ![](assets/incremental_query_example3.png)

* **[!UICONTROL Email delivery]** 活动。该工作流每周执行一次，但您可以汇总发送的电子邮件和每月的结果，例如，在整个月内生成报告，而不是仅在一周内生成报告。

   To do this, choose to create a **[!UICONTROL Recurring email]** here regrouping the emails and the results **[!UICONTROL By month]**.

   定义电子邮件的内容并插入欢迎促销代码。

   For more on this, refer to the [Email delivery](../../automating/using/email-delivery.md) and [Defining email content](../../designing/using/about-personalization.md) sections.

然后启动工作流执行。每周新订户将收到包含促销代码的欢迎电子邮件。

## Example: incremental query on delivery logs {#example--incremental-query-on-delivery-logs}

You can use an **[!UICONTROL Incremental query]** activity to regularly export new logs in files. 如果您希望在外部报表或BI工具中使用日志数据，则该选项卡可能很有用。

[导出日志](../../automating/using/exporting-logs.md) 部分提供了一个完整的示例。
