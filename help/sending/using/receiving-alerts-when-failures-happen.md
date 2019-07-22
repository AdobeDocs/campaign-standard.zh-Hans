---
title: 在发生故障时接收通知
seo-title: 在发生故障时接收通知
description: 在发生故障时接收通知
seo-description: 了解如何使用警报管理系统。
page-status-flag: 从未激活
uuid: a3ab733a-e3 db-4adc-b930-cd4064 b6 dc1 c
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 发送
content-type: reference
topic-tags: 监视消息
discoiquuid: 0766bd57-c5 f1-4f56-ac84-e5 a04 d3819 ec
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 07c0b1b1ad6f9822e220e86f54dfa46475009132

---


# Receiving alerts when failures happen{#receiving-alerts-when-failures-happen}

## About delivery alerting {#about-delivery-alerting}

**交付通知** 功能是一种警报管理系统，它允许一组用户自动接收通知，其中包含执行其交付的信息。

发送的通知包含默认情况下基于以下条件的报告：

* 交付失败
* 交付失败的交付
* 传送错误的软弹跳率
* 交付错误的退回错误比率
* 提供待定状态的交付时间较长
* 吞吐量低的交付
* 进行中的交付

通知收件人可以监控Adobe Campaign处理的交付内容，并在执行问题时采取相应的措施。

这些提醒通知可根据通过Adobe Campaign界面中的仪表板定义的特定警报标准进行自定义。

>[!NOTE]
>
>通知通知仅通过电子邮件发送。

发送的通知包含：

* A **[!UICONTROL Summary]** displaying the number of deliveries meeting the criteria that you defined and the label/color that you chose for each criterion.
* A **[!UICONTROL Details]** section listing all of the delivery criteria defined for the corresponding dashboard and all of the deliveries for each criterion.

![](assets/delivery-alerting_notification.png)

## Delivery alerting dashboards {#delivery-alerting-dashboards}

### About delivery alerting dashboards {#about-delivery-alerting-dashboards}

要管理通知收件人、定义警报条件并访问警报历史记录，您需要使用仪表板。

>[!NOTE]
>
>To access and configure the dashboards and the alerting criteria, you must have administration rights or appear in the **Delivery supervisors** security group. 标准用户无法访问Adobe Campaign界面中的仪表板。他们只能接收通知通知。For more on users and security in Adobe Campaign, see [Types of users](../../administration/using/users-management.md) and [About security groups](../../administration/using/managing-groups-and-users.md#about-security-groups).

在Adobe Campaign界面中，您可以：

* 创建和管理交付通知仪表板。See [Creating a delivery alerting dashboard](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-dashboard).
* 为每个仪表板定义和管理交付警报标准。例如，您可以根据交付失败的准备或交付，以低吞吐量生成提醒。See [About alerting criteria](../../sending/using/receiving-alerts-when-failures-happen.md#about-alerting-criteria).
* 修改每个功能板的条件参数。See [Criteria parameters](../../sending/using/receiving-alerts-when-failures-happen.md#criteria-parameters).
* 为每个控制板定义一组收件人。

   例如，您希望仅向用户通知失败交付的管理权限。但是，您希望营销用户收到软弹回错误的传送信息。因此，您需要创建两个不同的仪表板，并定义每个收件人组所需的条件。

* 访问每个功能板发送的所有警报的历史记录。

   选择仪表板时，默认情况下会显示此控制板的上次发送警报。所有发送的警报都会列在屏幕左侧。Click an item in the **[!UICONTROL History]** list to access the corresponding alerts.

![](assets/delivery-alerting_dashboard.png)

### Creating a delivery alerting dashboard {#creating-a-delivery-alerting-dashboard}

如果要根据特定条件向不同用户组发送通知，则需要使用多个控制面板。要创建新的仪表板，请执行以下操作：

1. Go to **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]**.
1. Select **[!UICONTROL Delivery alerting dashboards]** and click **[!UICONTROL Create]**.
1. Check the **[!UICONTROL Enabled]** box to activate the current dashboard.

   如果禁用此选项，则链接到此控制板的通知将不再发送。默认情况下禁用此选项。

   ![](assets/delivery-alerting_dashboard_general.png)

1. Select the group of recipients that you want to notify from the **[!UICONTROL Alert group]** drop-down list. To modify or create a group, see [Creating a security group and assigning users](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users).
1. From the **[!UICONTROL Delivery alerting criteria]** section, click **[!UICONTROL Create element]** to add criteria. See [About alerting criteria](../../sending/using/receiving-alerts-when-failures-happen.md#about-alerting-criteria).
1. Select the **[!UICONTROL Edit properties]** button. **[!UICONTROL Criteria parameters]** 在选项卡中，定义标准的应用方式。See [Criteria parameters](../../sending/using/receiving-alerts-when-failures-happen.md#criteria-parameters).
1. Click **[!UICONTROL Create]** to save the dashboard.

现在，每次分发均满足您在此控制面板中定义的标准，通知通知将发送给指定用户组。

## Delivery alerting criteria {#delivery-alerting-criteria}

### About alerting criteria {#about-alerting-criteria}

To access the delivery alerting criteria, go to **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]** and select **[!UICONTROL Delivery alerting criteria]**.

![](assets/delivery-alerting_criteria.png)

以下条件可用于交付通知仪表板：

* **[!UICONTROL Deliveries failed]**：在定义范围内计划的任何交付，并且状态错误。
* **[!UICONTROL Deliveries with preparation failed]**：在定义的范围内修改的任何交付都将失败，该范围(目标计算和内容生成)已失败。For more on this, see [Preparing the send](../../sending/using/preparing-the-send.md).
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**：在定义范围内计划的任何交付(至少包含状态) **[!UICONTROL In progress]**，软弹跳率比定义百分比更高。
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**：在定义范围内计划的任何交付(至少包含状态) **[!UICONTROL In progress]**，硬弹跳率大于定义的百分比。
* **[!UICONTROL Deliveries with long start pending]**：在定义范围内计划的任何交付， **[!UICONTROL Start pending]** 状态的长度均大于定义的持续时间， **[!UICONTROL Start pending]** 状态意味着系统尚未考虑消息。
* **[!UICONTROL Deliveries with low throughput]**：任何交付的开始时间都比定义的持续时间长，所定义的处理消息的百分比低于定义的值，并且吞吐量低于定义的值。
* **[!UICONTROL Deliveries in progress]**：在定义范围内计划的任何交付，包括 **[!UICONTROL In progress]** 状态。

>[!NOTE]
>
>适用于上述条件的所有参数都具有默认值。These values can be changed in the **[!UICONTROL Criteria parameters]** tab of the delivery alerting dashboards. See [Criteria parameters](../../sending/using/receiving-alerts-when-failures-happen.md#criteria-parameters).

You can select any item from the **[!UICONTROL Delivery alerting criteria]** list to access its details.

![](assets/delivery-alerting_criteria_definition.png)

对于每个标准，您可以定义以下设置：

* **[!UICONTROL Indicators to add in alerts]**&#x200B;这意味着将显示在与选定标准对应的发送 **[!UICONTROL Details]** 通知部分中的列。

   ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**&#x200B;这意味着标签摘要中将显示的标签和颜色。

   ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**：如果满足某一交付标准，在监控期内发送的每个通知中都会重复该项。否则，一个交付的警报标准将仅发出一天(在第一个出现时)警报。

   默认情况下，此选项在所有条件下设置为一次。

**相关主题：**

* [发送日志](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [提醒频率](../../sending/using/receiving-alerts-when-failures-happen.md#alerting-frequency)
* [营销活动图标和状态](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### Creating a delivery alerting criterion {#creating-a-delivery-alerting-criterion}

您可以创建新的交付警报标准以更好地满足您的需求。

For example, you can create a new criterion enabling to send a notification listing all deliveries with a **[!UICONTROL Finished]** status.

To do this, you first need to extend the **Delivery** resource and add a new filter allowing you to select only the deliveries with a **[!UICONTROL Finished]** status.

1. Go to **Adobe Campaign** &gt; **Administration** &gt; **Development** &gt; **Custom resources** and click **[!UICONTROL Create]**.
1. Select **[!UICONTROL Extend an existing resource]**, select the **[!UICONTROL Delivery]** resource from the drop-down list and click **[!UICONTROL Create]** to edit it.

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   For more on extending an existing resource, see [Define the resource](../../developing/using/creating-or-extending-the-resource.md).

1. **[!UICONTROL Delivery]** 在资源中，转到 **[!UICONTROL Filter definition]** 选项卡并单击 **[!UICONTROL Add an element]** 以创建过滤器。

   ![](assets/delivery-alerting_new-filter.png)

1. Edit the new filter definition: in the **[!UICONTROL Filter definition]** window, drag and drop the **[!UICONTROL Status]** item into the workspace and select **[!UICONTROL Finished]** as the filter condition.

   ![](assets/delivery-alerting_filter-status.png)

   For more on creating and editing custom filters, see [Define filters](../../developing/using/configuring-filter-definition.md).

1. 保存更改并发布资源。For more on this, see [Publishing a custom resource](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   将创建过滤器，现在可在新的交付通知标准中选择该过滤器。

1. Go to **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]**, select **[!UICONTROL Delivery alerting criteria]** and click **[!UICONTROL Create]**.
1. In the **[!UICONTROL Delivery filter applied by this criterion]** drop-down list, select the filter that you just created.

   ![](assets/delivery-alerting_cus-filter.png)

   您可以像默认条件一样定义标准的设置。See [About alerting criteria](../../sending/using/receiving-alerts-when-failures-happen.md#about-alerting-criteria).

创建后，这些标准可添加到配送通知仪表板以及其他条件。See [About delivery alerting dashboards](../../sending/using/receiving-alerts-when-failures-happen.md#about-delivery-alerting-dashboards).

![](assets/delivery-alerting_new-criterion.png)

**相关主题：**

[添加或扩展资源](../../developing/using/key-steps-to-add-a-resource.md)

## Delivery alerting parameters {#delivery-alerting-parameters}

### Criteria parameters {#criteria-parameters}

**[!UICONTROL Criteria parameters]**[在配送通知功能板](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-dashboard)的选项卡中，您可以定义应用于此控制板中所选标准的设置。

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**：例如，如果在此字段中输入100，则仅发送目标等于或大于100个收件人的传送通知。此参数适用于所有条件。
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**：当前时间前后的小时数。只会考虑在此时间范围内提供联系日期的交付。此参数适用于所有条件。默认情况下，此字段的值设置为24小时。

   For more information on the contact date, see [About the scheduling](../../sending/using/about-scheduling-messages.md).

* **[!UICONTROL Maximum ratio of soft bounce errors]**：将向所有提交发送通知，软弹跳比率大于指定值。默认情况下，此字段的值设置为0.05(5%)。

   For more on soft bounce errors, see [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) and [List of delivery failure types](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Maximum ratio of hard bounce errors]**：将向所有交付发送一个通知，其中硬弹跳率大于指定值。默认情况下，此字段的值设置为0.05(5%)。

   For more on hard bounce errors, see [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) and [List of delivery failure types](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**：向所有提交发送通知的 **[!UICONTROL Start pending]** 时间比该字段中指定的持续时间长， **[!UICONTROL Start pending]** 状态意味着系统尚未考虑消息。
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**：仅会考虑到在指定持续时间内开始(状态 **[!UICONTROL In progress]** )的分发 **[!UICONTROL Deliveries with low throughput]** ，以符合标准。
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**：仅会考虑到低于指定百分比的处理过的消息百分比的分发 **[!UICONTROL Deliveries with low throughput]** 。
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**：仅应考虑到低于指定值的分发才 **[!UICONTROL Deliveries with low throughput]** 会考虑标准。
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**：只考虑具有高于指定百分比的处理过的消息百分比的交付。

### Alerting frequency {#alerting-frequency}

**[!UICONTROL Frequency of delivery alerting]** 此选项允许定义两个警报会话之间的延迟。默认情况下，它设置为10分钟。

You can change this setting through the **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]** menu.

>[!NOTE]
>
>此选项适用于在Adobe Campaign中定义的所有仪表板。您不能为每个仪表板设置特定频率。

## Delivery alerting reasons {#delivery-alerting-reasons}

**交付通知** 功能会使所有相关Adobe Campaign用户都可通过电子邮件和仪表板自动获知投放执行状态。

现在，当您收到发送通知通知时，以下是有关您可以执行的操作的几点提示。

First of all, check the delivery's **Log** tab to view all information relating to the delivery and proofs. 红色和黄色图标允许您识别错误或警告。红色图标表示一个关键错误，该错误导致交付无法开始。

To view the history of every occurrence of a delivery, select the **[!UICONTROL Sending logs]** tab. 它包含已发送消息及其状态的列表。There you can check the delivery status for each recipient ( **[!UICONTROL Sent]**, **[!UICONTROL Pending]**, **[!UICONTROL Failed]**, etc.). For more on this, see [Sending logs](../../sending/using/monitoring-a-delivery.md#sending-logs).

以下是根据交付符合交付条件的条件接收通知通知的几个可能原因。

* **[!UICONTROL Deliveries failed]**：此标准将向您提供错误状态的所有交付内容。它可能是由于：

   * 交付服务器问题(MTA、消息传输代理)
   * Adobe Campaign交付服务器与接收服务器之间的连接超时
   * 可交付性问题
   * 错误的工作流程
   如果传送通过工作流触发，请检查该工作流是否已正确启动。For more on this, see [Executing a workflow](../../automating/using/executing-a-workflow.md). 否则，请与Adobe Campaign管理员联系以解决此问题。

* **[!UICONTROL Deliveries with preparation failed]**：在以下情况下，可以在交付准备过程中出错：

   * 分发缺少主题。
   * 个性化字段中有一个错误的语法。
   * 目标缺失。
   * 分发超出了大小限制。
   For more on this, see [Preparing the send](../../sending/using/preparing-the-send.md). 但是，在消息分析过程中，这些错误通常是拼写错误。See [Control rules](../../administration/using/control-rules.md).

* **[!UICONTROL Delivery with bad error ratio for soft bounces]** 警报的可能原因可能是：

   * 收件人的服务器关闭。
   * 收件人的邮箱已满。
   For more information, check the **[!UICONTROL Exclusion logs]** and **[!UICONTROL Exclusion causes]** tabs of the delivery logs. See [Exclusion logs](../../sending/using/monitoring-a-delivery.md#exclusion-logs).

   **[!UICONTROL Delivery with bad error ratio for hard bounces]** 警报的可能原因可能是：

   * 收件人已列入黑名单，这意味着他们不再希望联系他人。
   * 收件人的电子邮件地址不存在。
   * 收件人的域不存在。
   * 接收方的服务器阻止交付。
   为避免出现软弹跳错误，请遵循下面的最佳实践：

   * 构建过滤类型规则，以在交付分析过程中排除消息目标的一部分，如隔离收件人。See [Creating a filtering rule](../../administration/using/filtering-rules.md).
   * 定期更新您的客户数据库以保持良好的隔离管理流程。See [About quarantines](../../sending/using/understanding-quarantine-management.md#about-quarantines).
   * 一般而言，可尽可能提高交付能力。See the Adobe Campaign v7 [Managing deliverability](http://docs.campaign.adobe.com/doc/AC/getting_started/EN/deliverability.html) detailed guide and contact your Adobe Campaign administrator for assistance.



* **[!UICONTROL Deliveries with long start pending]**：通常情况下，这意味着MTA(消息传输代理)级别存在问题。执行过程正在等待某些资源的可用性。MTA可能尚未启动。

   **[!UICONTROL Deliveries with low throughput]**：同样，这是一个可交付性问题，表示MTA太慢。

   有关这些问题的更多信息，请与Adobe Campaign管理员联系。

**相关主题：**

* [了解交付失败](../../sending/using/understanding-delivery-failures.md)
* [了解隔离管理](../../sending/using/understanding-quarantine-management.md)
* [管理Campaign中的黑名单](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

