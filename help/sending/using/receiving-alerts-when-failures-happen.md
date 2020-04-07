---
title: 在失败时接收提醒
description: 了解如何使用警报管理系统。
page-status-flag: never-activated
uuid: a3ab733a-e3db-4adc-b930-cd4064b6dc1c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: 0766bd57-c5f1-4f56-ac84-e5a04d3819ec
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 155ed7e50e207e4c4dc0569e5e96b24e712e4be8

---


# 在失败时接收提醒{#receiving-alerts-when-failures-happen}

## 关于投放警报 {#about-delivery-alerting}

投放 **警报功能** ，是使一组用户能够自动接收包含关于其投放执行的信息的通知的警报管理系统。

发送的通知默认包含基于以下条件的报告：

* 失败的投放
* 准备失败的投放
* 软弹跳错误率差的投放
* 硬弹跳错误率不佳的投放
* 状态为待定的投放比通常长
* 低吞吐量投放
* 投放进行中

警报的收件人可以监视Adobe Campaign正在处理的投放，并在执行过程中出现问题时采取相应的操作。

这些警报通知可以根据通过Adobe Campaign界面中的仪表板定义的特定警报标准进行自定义。

>[!NOTE]
>
>警报通知仅通过电子邮件发送。

发送的通知包含：

* 显 **[!UICONTROL Summary]** 示符合您定义的条件的投放数以及您为每个条件选择的标签／颜色。
* 一 **[!UICONTROL Details]** 节列出为相应仪表板定义的所有投放标准以及每个标准的所有投放。

![](assets/delivery-alerting_notification.png)

## 投放警报仪表板 {#delivery-alerting-dashboards}

### 关于投放警报仪表板 {#about-delivery-alerting-dashboards}

要管理通知的收件人，请定义警报标准并访问警报的历史记录，您需要使用仪表板。

>[!NOTE]
>
>要访问和配置仪表板和警报标准，您必须拥有管理权限或显示在投放监管者安 **全组中** 。 标准用户无法访问仪表板界面中的Adobe Campaign。 他们只能接收警报通知。 有关Adobe Campaign中用户和安全性的详细信息，请参 [阅用户类型](../../administration/using/users-management.md) 和 [关于安全组](../../administration/using/managing-groups-and-users.md#about-security-groups)。

从Adobe Campaign界面，您可以：

* 创建和管理投放警报仪表板。 请参 [阅创建投放警报仪表板](#creating-a-delivery-alerting-dashboard)。
* 定义和管理每个投放的仪表板警报标准。 例如，您可以根据准备失败的投放或仅低吞吐量的投放来构建警报。 请参 [阅关于警报标准](#about-alerting-criteria)。
* 修改每个仪表板的条件参数。 请参阅 [标准参数](#criteria-parameters)。
* 为每个收件人定义一组仪表板。

   例如，您希望仅向具有管理权限的用户通知失败的投放。 但是，您希望营销用户以软弹跳错误率接收有关投放的信息。 因此，您需要创建两个不同的仪表板，并为每组收件人定义所需的条件。

* 访问每个仪表板的所有已发送警报的历史记录。

   选择仪表板时，默认情况下会显示此仪表板的上次发送警报。 所有发送的警报都列在屏幕左侧。 单击列表中的某 **[!UICONTROL History]** 个项目以访问相应的警报。

![](assets/delivery-alerting_dashboard.png)

### 创建投放警报仪表板 {#creating-a-delivery-alerting-dashboard}

如果要根据特定条件向不同用户组发送通知，您需要使用多个仪表板。 要创建新仪表板，请执行以下操作：

1. 转到 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**。
1. 选择 **[!UICONTROL Delivery alerting dashboards]** 并单击 **[!UICONTROL Create]**。
1. 选中该 **[!UICONTROL Enabled]** 复选框以激活当前仪表板。

   如果禁用此选项，则不再发送链接到此仪表板的通知。 此选项默认处于禁用状态。

   ![](assets/delivery-alerting_dashboard_general.png)

1. 从下拉收件人中选择要通知的 **[!UICONTROL Alert group]** 列表组。 要修改或创建用户组，请参阅 [创建安全组和分配用户](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users)。
1. 在部分 **[!UICONTROL Delivery alerting criteria]** 中，单击以 **[!UICONTROL Create element]** 添加条件。 请参 [阅关于警报标准](#about-alerting-criteria)。
1. 选择按 **[!UICONTROL Edit properties]** 钮。 在选项卡 **[!UICONTROL Criteria parameters]** 中，定义如何应用条件。 请参阅 [标准参数](#criteria-parameters)。
1. 单 **[!UICONTROL Create]** 击以保存仪表板。

现在，每次投放符合您在本仪表板中定义的条件时，都会向指定的用户组发送警报通知。

## 投放警报标准 {#delivery-alerting-criteria}

### 关于警报标准 {#about-alerting-criteria}

要访问投放警报标准，请转到 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** >并 **[!UICONTROL Delivery alerting]** 选择 **[!UICONTROL Delivery alerting criteria]**。

![](assets/delivery-alerting_criteria.png)

以下标准可用于投放警报仪表板:

* **[!UICONTROL Deliveries failed]**:在定义的范围内计划的任何投放均具有错误的状态。
* **[!UICONTROL Deliveries with preparation failed]**:在定义范围内修改的任何投放，其准备步骤(目标计算和内容生成)已失败。 有关此问题的详细信息，请参 [阅准备发送](../../sending/using/preparing-the-send.md)。
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**:在已定义的范围内计划的任何投放，其状态至少 **[!UICONTROL In progress]**&#x200B;为，软弹回错误率大于已定义百分比。
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**:在已定义的范围内计划的任何投放，其状态至少 **[!UICONTROL In progress]**&#x200B;为，硬弹回错误率大于已定义的百分比。
* **[!UICONTROL Deliveries with long start pending]**:在定义的范围内计划的任何投放的 **[!UICONTROL Start pending]** 状态长于定义的持续时间，状态 **[!UICONTROL Start pending]** 意味着系统尚未考虑消息。
* **[!UICONTROL Deliveries with low throughput]**:任何投放的启动时间都长于定义的持续时间，并且小于定义的已处理消息百分比，吞吐量低于定义的值。
* **[!UICONTROL Deliveries in progress]**:在已定义的范围内计划的任何投放，其状 **[!UICONTROL In progress]** 态为。

>[!NOTE]
>
>应用于上述标准的所有参数都具有默认值。 这些值可以在投放警报仪表板 **[!UICONTROL Criteria parameters]** 的选项卡中更改。 请参阅 [标准参数](#criteria-parameters)。

您可以从列表中选择任何项目以 **[!UICONTROL Delivery alerting criteria]** 访问其详细信息。

![](assets/delivery-alerting_criteria_definition.png)

对于每个标准，您可以定义以下设置：

* **[!UICONTROL Indicators to add in alerts]**，表示将在通知的部分中显示与选定 **[!UICONTROL Details]** 标准对应的投放的列。

   ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**，表示将在通知摘要中投放标准旁边显示的标签和颜色。

   ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**:如果一个投放符合一个标准，则在监控期间内发送的每个通知中重复该标准。 否则，对于一个投放，每天（在第一次出现时）只会发送一个警报。

   默认情况下，此选项设置为所有条件的每天一次。

**相关主题：**

* [发送日志](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [警报频率](#alerting-frequency)
* [营销活动图标和状态](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### 创建投放警报标准 {#creating-a-delivery-alerting-criterion}

您可以创建新的投放警报标准以更好地满足您的需求。

例如，您可以创建新标准，以便发送列出所有具有状态的投放的通知 **[!UICONTROL Finished]** 。

为此，您首先需要扩展 **投放资源** ，并添加新的过滤器，以便只选择具有状态的投放 **[!UICONTROL Finished]** 。

1. 转到 **>** >管理 **** >开发 **>** Adobe Campaign **** >自定 **[!UICONTROL Create]**&#x200B;义资源。
1. 选 **[!UICONTROL Extend an existing resource]**&#x200B;择，从 **[!UICONTROL Delivery]** 下拉列表中选择资源，然后单击 **[!UICONTROL Create]** 以编辑它。

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   有关扩展现有资源的详细信息，请参 [阅定义资源](../../developing/using/creating-or-extending-the-resource.md)。

1. 在资 **[!UICONTROL Delivery]** 源中，转到选项卡并 **[!UICONTROL Filter definition]** 单击以 **[!UICONTROL Add an element]** 创建过滤器。

   ![](assets/delivery-alerting_new-filter.png)

1. 编辑新的过滤器定义：在窗 **[!UICONTROL Filter definition]** 口中，将项目拖放到工 **[!UICONTROL Status]** 作区中，然后选择 **[!UICONTROL Finished]** 作为筛选条件。

   ![](assets/delivery-alerting_filter-status.png)

   有关创建和编辑自定义过滤器的详细信息，请参阅 [定义过滤器](../../developing/using/configuring-filter-definition.md)。

1. 保存更改并发布资源。 有关此功能的详细信息，请参 [阅发布自定义资源](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

   该过滤器已创建，并且现在可以在新的投放警报标准中选择。

1. 转到 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**，选择并 **[!UICONTROL Delivery alerting criteria]** 单击 **[!UICONTROL Create]**。
1. 在下 **[!UICONTROL Delivery filter applied by this criterion]** 拉列表中，选择您刚刚创建的筛选器。

   ![](assets/delivery-alerting_cus-filter.png)

   您可以按与默认标准相同的方式定义标准的设置。 请参 [阅关于警报标准](#about-alerting-criteria)。

创建后，这些条件可以添加到投放警报仪表板以及其他条件。 请参阅 [关于投放警报仪表板](#about-delivery-alerting-dashboards)。

![](assets/delivery-alerting_new-criterion.png)

**相关主题：**

[添加或扩展资源](../../developing/using/key-steps-to-add-a-resource.md)

## 投放警报参数 {#delivery-alerting-parameters}

### 标准参数 {#criteria-parameters}

在投放 **[!UICONTROL Criteria parameters]** 警报仪表板的 [选项卡中](#creating-a-delivery-alerting-dashboard)，您可以定义适用于此仪表板中选定条件的设置。

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**:例如，如果在此字段中输入100，则仅对目标等于或大于100个收件人的投放发送通知。 此参数适用于所有条件。
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**:当前时间前后的小时数。 只考虑具有此时间范围内的联系日期的投放。 此参数适用于所有条件。 默认情况下，此字段的值设置为24小时。

   有关联系日期的详细信息，请参 [阅关于日程安排](../../sending/using/about-scheduling-messages.md)。

* **[!UICONTROL Maximum ratio of soft bounce errors]**:系统会为所有投放发送一个通知，其软弹出错误率大于指定值。 默认情况下，此字段的值设置为0.05(5%)。

   有关软弹回错误的详细信息，请参 [阅弹回邮件资格](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)[和投放故障类型列表](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)。

* **[!UICONTROL Maximum ratio of hard bounce errors]**:系统会为所有投放发送一条通知，其硬弹回错误率大于指定值。 默认情况下，此字段的值设置为0.05(5%)。

   有关硬弹回错误的详细信息，请参 [阅弹回邮件资格](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)[和投放故障类型列表](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)。

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**:系统会为所有投放发送一条通知，其状态的时间 **[!UICONTROL Start pending]** 长于此字段中指定的持续时间，该状态 **[!UICONTROL Start pending]** 意味着系统尚未考虑这些消息。
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**:该标准只考虑在超 **[!UICONTROL In progress]** 过指定持续时间时开始的投放（状态为） **[!UICONTROL Deliveries with low throughput]** 。
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**:只有处理消息百分比低于指定百分比的投放才会考虑该标 **[!UICONTROL Deliveries with low throughput]** 准。
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**:该标准只考虑吞吐量低于指定值的投放 **[!UICONTROL Deliveries with low throughput]** 。
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**:只有处理消息百分比高于指定百分比的投放才会被考虑在内。

### 警报频率 {#alerting-frequency}

该选 **[!UICONTROL Frequency of delivery alerting]** 项允许定义两个警报发送之间的延迟。 默认情况下，它设置为10分钟。

可以通过> **[!UICONTROL Administration]** >菜单更改 **[!UICONTROL Application settings]** 此 **[!UICONTROL Options]** 设置。

>[!NOTE]
>
>此选项适用于在Adobe Campaign中定义的所有仪表板。 不能为每个仪表板设置特定频率。

## 投放警报原因 {#delivery-alerting-reasons}

投放警 **报功能** ，可通过电子邮件和仪表板自动向您所有参与的Adobe Campaign用户通知投放执行状态。

现在，当您收到投放警报通知时，请提供一些提示，说明您可以做什么。

首先，检查投放的“ **日志** ”选项卡以视图与投放和验证相关的所有信息。 红色和黄色图标允许您识别错误或警告。 红色图标表示阻止启动投放的严重错误。

要视图每次出现投放的历史记录，请选择选 **[!UICONTROL Sending logs]** 项卡。 它包含已发送消息及其状态的列表。 您可以在此处检查每个投放( **[!UICONTROL Sent]**、 **[!UICONTROL Pending]**、 **[!UICONTROL Failed]**&#x200B;等)的收件人状态。 有关此内容的详细信息，请参 [阅发送日志](../../sending/using/monitoring-a-delivery.md#sending-logs)。

以下是根据符合投放标准接收警报通知的几个可能原因。

* **[!UICONTROL Deliveries failed]**:此标准会通知您所有状态错误的投放。 这可能是由于：

   * 投放服务器（MTA，消息传输代理）的问题
   * Adobe Campaign投放服务器和接收服务器之间的连接超时
   * 可交付性问题
   * 错误的工作流
   如果投放是使用工作流触发的，请检查该工作流是否正确启动。 有关此功能的详细信息，请参 [阅执行工作流](../../automating/using/executing-a-workflow.md)。 否则，请与Adobe Campaign管理员联系以解决此问题。

* **[!UICONTROL Deliveries with preparation failed]**:在以下情况下，投放准备过程中可能会出错：

   * 投放缺少一个主题。
   * 个性化字段中的语法错误。
   * 目标不见了。
   * 投放超出大小限制。
   有关此问题的详细信息，请参 [阅准备发送](../../sending/using/preparing-the-send.md)。 但是，这些错误通常会在消息分析过程中发现。 请参阅 [控制规则](../../sending/using/control-rules.md)。

* 发出警报的可 **[!UICONTROL Delivery with bad error ratio for soft bounces]** 能原因包括：

   * 收件人的服务器关闭。
   * 收件人的邮箱满了。
   有关详细信息，请查 **[!UICONTROL Exclusion logs]** 看投放日志 **[!UICONTROL Exclusion causes]** 的选项卡和选项卡。 请参阅 [排除日志](../../sending/using/monitoring-a-delivery.md#exclusion-logs)。

   发出警报的可 **[!UICONTROL Delivery with bad error ratio for hard bounces]** 能原因包括：

   * 收件人是已列入黑名单的，这意味着他们不再希望被联系。
   * 收件人的电子邮件地址不存在。
   * 收件人的域不存在。
   * 收件人服务器阻止投放。
   要避免软弹回和硬弹回错误，请遵循以下最佳实践：

   * 构建过滤类型规则以在投放分析期间排除消息目标的一部分，如隔离收件人。 请参 [阅创建筛选规则](../../sending/using/filtering-rules.md)。
   * 定期更新客户数据库以保持良好的隔离管理流程。 请参阅 [关于隔离](../../sending/using/understanding-quarantine-management.md#about-quarantines)。
   * 一般而言，尽可能提高可交付性。 请参阅Adobe Campaign [交付性详细文档](../../sending/using/about-deliverability.md) ，并与Adobe Campaign管理员联系以获得帮助。



* **[!UICONTROL Deliveries with long start pending]**:通常，这意味着在MTA（消息传输代理）级别存在问题。 执行过程正在等待某些资源的可用性。 MTA可能尚未启动。

   **[!UICONTROL Deliveries with low throughput]**:同样，这是一个可交付性问题，这意味着MTA太慢。

   有关这些问题的更多信息，请与Adobe Campaign管理员联系。

**相关主题：**

* [了解投放失败](../../sending/using/understanding-delivery-failures.md)
* [了解隔离管理](../../sending/using/understanding-quarantine-management.md)
* [管理活动中的黑名单](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

