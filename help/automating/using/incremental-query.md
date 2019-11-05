---
title: 增量查询
description: 增量查询活动允许您从Adobe Campaign数据库中过滤和提取元素总量。
page-status-flag: 从未激活
uuid: 73b42422-e815-43ef-84c0-97c4433cc98
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 定位活动
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: 增量，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 增量查询{#incremental-query}

## 说明 {#description}

![](assets/incremental.png)

该活 **[!UICONTROL Incremental query]** 动允许您从Adobe Campaign数据库中过滤和提取大量元素。 每次执行此活动时，都会排除先前执行的结果。 这允许您仅将新元素作为目标。

您可以通过 **[!UICONTROL Additional data]** 专用选项卡为目标人群定义。 此数据存储在其他列中，并且只能用于进行中的工作流。

活动使用查询编辑器工具。 此工具在专用部分中 [有详细介绍](../../automating/using/editing-queries.md#about-query-editor)。

## 使用环境 {#context-of-use}

必须 **[!UICONTROL Incremental query]** 将一个链接到一个， **[!UICONTROL Scheduler]** 以定义工作流的执行频率，进而定义查询。

此选 **[!UICONTROL Processed data]** 项卡特定于此活动，允许您根据需要查看以前执行的活动的任何结果。

活动 **[!UICONTROL Incremental query]** 可用于各种类型的使用：

* 将个人细分以定义消息、受众等的目标
* 导出数据.

## 配置 {#configuration}

1. 将活动拖放 **[!UICONTROL Incremental query]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。
1. 如果要对配置文件资源以外的资源运行查询，请转到活动的选项卡，然 **[!UICONTROL Properties]** 后选择 **[!UICONTROL Resource]** 和 **[!UICONTROL Targeting dimension]**。

   该选 **[!UICONTROL Resource]****[!UICONTROL Targeting dimension]**&#x200B;项允许您调整调色板中显示的过滤器，而与所选资源相关的上下文过滤器与您要获取的人群类型（已识别的配置文件、交付、链接到所选资源的数据等）相对应。

1. 在选项卡 **[!UICONTROL Target]** 中，通过定义和组合规则来运行查询。
1. 在选项 **[!UICONTROL Processed data]** 卡中，选择要用于工作流的下一个执行的增量模式：

   * **[!UICONTROL Use the exclusion of the results of previous executions]**:每个新执行的先前执行的结果被排除。
   * **[!UICONTROL Use a date field]**:下一个执行只考虑选定日期字段大于或等于活动上次执行日期的结果 **[!UICONTROL Incremental query]** 。 您可以选择与在选项卡中选择的资源相关的任何日期 **[!UICONTROL Properties]** 字段。 此模式在查询大资源（如日志数据）时具有更好的性能。

      在工作流的第一次执行之后，您可以在此选项卡中看到用于下一次执行的最后一个执行日期。 每次执行工作流时，系统都会自动更新它。 您仍然可以手动输入新值来覆盖此值，以便它符合您的需求。
   >[!NOTE]
   >
   >该模 **[!UICONTROL Use a date field]** 式根据所选的日期字段允许更大的灵活性。 例如，如果选定字段与修改日期相对应，则日期字段模式将允许您检索最近更新的数据，而另一个模式将仅排除在上一执行中已定位的录制内容，即使这些录制内容自上次执行工作流后已被修改也是如此。

   ![](assets/incremental_query_usedatefield.png)

1. 您可以通过 **[!UICONTROL Additional data]** 专用选项卡为目标人群定义。 此数据存储在其他列中，并且只能用于进行中的工作流。 特别是，您可以从链接到查询的定位维的Adobe Campaign数据库表中添加数据。 请参阅丰 [富数据部分](../../automating/using/query.md#enriching-data) 。
1. 确认活动的配置并保存工作流。

## 丰富数据 {#enriching-data}

与查询一样，您也可以从中丰富数据 **[!UICONTROL Incremental query]**。 请参阅丰 [富数据部分](../../automating/using/query.md#enriching-data) 。

## 示例：对服务订阅者的增量查询 {#example--incremental-query-on-subscribers-to-a-service}

以下示例显示了一个活动的配置，该活动会过滤订阅 **[!UICONTROL Incremental query]** Running Newsletter **** service的Adobe Campaign数据库中的配置文件，以向他们发送一封包含促销代码的欢迎电子邮件。

工作流由以下元素组成：

![](assets/incremental_query_example1.png)

* 一 **[!UICONTROL Scheduler]** 个活动，每周一清晨6点执行工作流。

   ![](assets/incremental_query_example2.png)

* 在第 **[!UICONTROL Incremental query]** 一次执行期间针对当前所有订阅者的活动，在以下执行期间仅针对该周的新订阅者。

   ![](assets/incremental_query_example3.png)

* 活 **[!UICONTROL Email delivery]** 动。 该工作流每周执行一次，但您可以汇总发送的电子邮件和每月的结果，例如，在整个月（而不仅仅是一周）的时间段内生成报告。

   为此，请选择在此处创建一个 **[!UICONTROL Recurring email]** 重新分组电子邮件和结果的页面 **[!UICONTROL By month]**。

   定义电子邮件的内容并插入欢迎促销代码。

   有关详细信息，请参阅电子邮件 [分发](../../automating/using/email-delivery.md)[和定义电子邮件内容](../../designing/using/personalization.md) 。

然后开始执行工作流。 每周新订阅者都会收到包含促销代码的欢迎电子邮件。

## 示例：交付日志中的增量查询 {#example--incremental-query-on-delivery-logs}

您可以使用活 **[!UICONTROL Incremental query]** 动定期导出文件中的新日志。 例如，如果要在外部报告或BI工具中使用日志数据，则此选项会很有用。

导出日志部分提供了完整 [的示例](../../automating/using/exporting-logs.md) 。
