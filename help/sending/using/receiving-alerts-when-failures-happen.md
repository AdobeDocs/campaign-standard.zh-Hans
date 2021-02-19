---
solution: Campaign Standard
product: campaign
title: 在失败时接收提醒
description: 了解如何使用警报管理系统。
audience: sending
content-type: reference
topic-tags: monitoring-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '2031'
ht-degree: 2%

---


# 在失败时接收提醒{#receiving-alerts-when-failures-happen}

## 关于投放警报{#about-delivery-alerting}

**投放警报**&#x200B;功能是警报管理系统，它使一组用户能够自动接收包含关于其投放执行的信息的通知。

默认情况下，发送的通知包含基于以下条件的报告：

* 失败的投放
* 投放准备失败
* 软跳出错误率不佳的投放
* 硬跳出错误率不佳的投放
* 状态比通常长的投放
* 投放吞吐量低
* 投放正在进行

警报的收件人可以监视Adobe Campaign正在处理的投放，并在其执行中出现问题时采取适当的操作。

根据通过Adobe Campaign界面中的仪表板定义的特定警报标准，可以自定义这些警报通知。

>[!NOTE]
>
>警报通知仅通过电子邮件发送。

发送的通知包含：

* 一个&#x200B;**[!UICONTROL Summary]**，显示符合您定义的条件的投放数以及您为每个条件选择的标签/颜色。
* **[!UICONTROL Details]**&#x200B;部分列出为相应仪表板定义的所有投放条件以及每个标准的所有投放。

![](assets/delivery-alerting_notification.png)

## 投放警报仪表板{#delivery-alerting-dashboards}

### 关于投放警报仪表板{#about-delivery-alerting-dashboards}

要管理通知的收件人，请定义警报标准并访问警报历史记录，您需要使用仪表板。

>[!NOTE]
>
>要访问和配置仪表板和警报标准，您必须具有管理权限或显示在&#x200B;**投放监督者**&#x200B;安全组中。 标准用户无法访问Adobe Campaign界面中的仪表板。 他们只能接收警报通知。 有关Adobe Campaign中用户和安全性的详细信息，请参阅[用户类型](../../administration/using/users-management.md)和[关于安全组](../../administration/using/managing-groups-and-users.md#about-security-groups)。

从Adobe Campaign界面，您可以：

* 创建和管理投放警报仪表板。 请参阅[创建投放警报仪表板](#creating-a-delivery-alerting-dashboard)。
* 定义和管理每个投放的仪表板警报标准。 例如，您可以根据准备失败的投放或仅吞吐量低的投放来构建警报。 请参阅[关于警报标准](#about-alerting-criteria)。
* 修改每个仪表板的条件参数。 请参阅[标准参数](#criteria-parameters)。
* 为每个收件人定义一组仪表板。

   例如，您希望仅通知具有失败投放管理权限的用户。 但是，您希望营销用户接收有关投放的信息，并且跳出错误率较低。 因此，您需要创建两个不同的仪表板，并为每组收件人定义所需的条件。

* 访问每个仪表板所有已发送警报的历史记录。

   选择仪表板时，默认情况下会显示此仪表板的上次发送警报。 所有发送的警报都列在屏幕左侧。 单击&#x200B;**[!UICONTROL History]**&#x200B;列表中的项以访问相应的警报。

![](assets/delivery-alerting_dashboard.png)

### 创建投放警报仪表板{#creating-a-delivery-alerting-dashboard}

如果要向不同用户组发送基于特定标准的通知，您需要使用多个仪表板。 要创建新仪表板:

1. 转到 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**。
1. 选择 **[!UICONTROL Delivery alerting dashboards]** 并单击 **[!UICONTROL Create]**。
1. 选中&#x200B;**[!UICONTROL Enabled]**&#x200B;框以激活当前仪表板。

   如果禁用此选项，则不再发送链接到此仪表板的通知。 此选项在默认情况下处于禁用状态。

   ![](assets/delivery-alerting_dashboard_general.png)

1. 从&#x200B;**[!UICONTROL Alert group]**&#x200B;下拉收件人中选择要通知的列表组。 要修改或创建组，请参阅[创建安全组和分配用户](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users)。
1. 在&#x200B;**[!UICONTROL Delivery alerting criteria]**&#x200B;部分，单击&#x200B;**[!UICONTROL Create element]**&#x200B;添加条件。 请参阅[关于警报标准](#about-alerting-criteria)。
1. 选择 **[!UICONTROL Edit properties]** 按钮。在&#x200B;**[!UICONTROL Criteria parameters]**&#x200B;选项卡中，定义如何应用条件。 请参阅[标准参数](#criteria-parameters)。
1. 单击&#x200B;**[!UICONTROL Create]**&#x200B;保存仪表板。

现在，每次投放满足您在此仪表板中定义的条件时，都会向指定的用户组发送警报通知。

## 投放警报标准{#delivery-alerting-criteria}

### 关于警报标准{#about-alerting-criteria}

要访问投放警报标准，请转至&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**&#x200B;并选择&#x200B;**[!UICONTROL Delivery alerting criteria]**。

![](assets/delivery-alerting_criteria.png)

以下标准可用于投放警报仪表板:

* **[!UICONTROL Deliveries failed]**:在定义的范围内计划的任何投放，状态都不正确。
* **[!UICONTROL Deliveries with preparation failed]**:在定义范围内修改的任何投放，其准备步骤(目标计算和内容生成)失败。有关此的详细信息，请参阅[准备send](../../sending/using/preparing-the-send.md)。
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**:在已定义范围内计划的任何投放，其状态至少 **[!UICONTROL In progress]**&#x200B;为软跳出错误率大于已定义百分比。
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**:在已定义范围内计划的任何投放，其状态至少 **[!UICONTROL In progress]**&#x200B;为硬跳出错误率大于已定义百分比。
* **[!UICONTROL Deliveries with long start pending]**:任何在定义范围内计划的投放, **[!UICONTROL Start pending]** 其状态长于定义的持 **[!UICONTROL Start pending]** 续时间，状态表示系统尚未考虑消息。
* **[!UICONTROL Deliveries with low throughput]**:任何投放启动时间长于定义的持续时间，且小于已处理消息的定义百分比，其吞吐量低于定义值。
* **[!UICONTROL Deliveries in progress]**:在已定义的范围内计划的任何投放，其状 **[!UICONTROL In progress]** 态为。

>[!NOTE]
>
>应用于上述条件的所有参数都具有默认值。 这些值可以在投放警报仪表板的&#x200B;**[!UICONTROL Criteria parameters]**&#x200B;选项卡中更改。 请参阅[标准参数](#criteria-parameters)。

您可以从&#x200B;**[!UICONTROL Delivery alerting criteria]**&#x200B;列表中选择任何项目以访问其详细信息。

![](assets/delivery-alerting_criteria_definition.png)

对于每个标准，您可以定义以下设置：

* **[!UICONTROL Indicators to add in alerts]**，表示将在通知的部分中显示与所 **[!UICONTROL Details]** 选标准对应的投放的列。

   ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**，表示通知摘要中投放标准旁边将显示的标签和颜色。

   ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**:如果一个投放符合某个标准，则在监控期间内发送的每个通知中重复该标准。否则，对于一个投放，每天（在第一次出现时）只会发送一个警报。

   默认情况下，此选项设置为所有条件的每天一次。

**相关主题：**

* [发送日志](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [警报频率](#alerting-frequency)
* [营销活动的图标和状态](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### 创建投放警报标准{#creating-a-delivery-alerting-criterion}

您可以创建新的投放警报标准以更好地满足您的需求。

例如，您可以创建新标准，以便发送列出所有&#x200B;**[!UICONTROL Finished]**&#x200B;状态投放的通知。

为此，您首先需要扩展&#x200B;**投放**&#x200B;资源并添加一个新筛选器，以便只选择状态为&#x200B;**[!UICONTROL Finished]**&#x200B;的投放。

1. 转到&#x200B;**Adobe Campaign** > **管理** > **开发** > **自定义资源**&#x200B;并单击&#x200B;**[!UICONTROL Create]**。
1. 选择&#x200B;**[!UICONTROL Extend an existing resource]**，从下拉列表中选择&#x200B;**[!UICONTROL Delivery]**&#x200B;资源，然后单击&#x200B;**[!UICONTROL Create]**&#x200B;进行编辑。

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   有关扩展现有资源的详细信息，请参阅[定义资源](../../developing/using/creating-or-extending-the-resource.md)。

1. 在&#x200B;**[!UICONTROL Delivery]**&#x200B;资源中，转到&#x200B;**[!UICONTROL Filter definition]**&#x200B;选项卡并单击&#x200B;**[!UICONTROL Add an element]**&#x200B;以创建筛选器。

   ![](assets/delivery-alerting_new-filter.png)

1. 编辑新筛选器定义：在&#x200B;**[!UICONTROL Filter definition]**&#x200B;窗口中，将&#x200B;**[!UICONTROL Status]**&#x200B;项拖放到工作区中，并选择&#x200B;**[!UICONTROL Finished]**&#x200B;作为过滤器条件。

   ![](assets/delivery-alerting_filter-status.png)

   有关创建和编辑自定义过滤器的详细信息，请参阅[定义过滤器](../../developing/using/configuring-filter-definition.md)。

1. 保存更改并发布资源。 有关详细信息，请参阅[发布自定义资源](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

   将创建该过滤器，现在可以在新的投放警报标准中选择该过滤器。

1. 转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**，选择&#x200B;**[!UICONTROL Delivery alerting criteria]**&#x200B;并单击&#x200B;**[!UICONTROL Create]**。
1. 在&#x200B;**[!UICONTROL Delivery filter applied by this criterion]**&#x200B;下拉列表中，选择刚刚创建的筛选器。

   ![](assets/delivery-alerting_cus-filter.png)

   您可以以与默认标准相同的方式定义标准的设置。 请参阅[关于警报标准](#about-alerting-criteria)。

创建后，可以将这些条件添加到投放警报仪表板以及其他条件。 请参阅[关于投放警报仪表板](#about-delivery-alerting-dashboards)。

![](assets/delivery-alerting_new-criterion.png)

**相关主题：**

[添加或扩展资源](../../developing/using/key-steps-to-add-a-resource.md)

## 投放警报参数{#delivery-alerting-parameters}

### 条件参数{#criteria-parameters}

在[投放警报仪表板](#creating-a-delivery-alerting-dashboard)的&#x200B;**[!UICONTROL Criteria parameters]**&#x200B;选项卡中，您可以定义适用于此仪表板中选定条件的设置。

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**:例如，如果在此字段中输入100，则只会为目标等于或大于100个收件人的投放发送通知。此参数适用于所有条件。
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**:当前时间前后的小时数。只考虑具有此时间范围内联系日期的投放。 此参数适用于所有条件。 默认情况下，此字段的值设置为24小时。

   有关联系日期的详细信息，请参阅[关于计划](../../sending/using/about-scheduling-messages.md)。

* **[!UICONTROL Maximum ratio of soft bounce errors]**:系统会为所有投放发送通知，其软跳出错误率大于指定值。默认情况下，此字段的值设置为0.05(5%)。

   有关软跳出错误的详细信息，请参阅[跳出邮件资格](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)和[投放故障类型列表](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)。

* **[!UICONTROL Maximum ratio of hard bounce errors]**:系统会为所有投放发送通知，其硬跳出错误率大于指定值。默认情况下，此字段的值设置为0.05(5%)。

   有关硬跳出错误的详细信息，请参阅[跳出邮件资格](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)和[投放故障类型列表](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)。

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**:系统会为状态长于此字段 **[!UICONTROL Start pending]** 中指定持续时间的所有投放发送 **[!UICONTROL Start pending]** 通知，状态表示系统尚未考虑消息。
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**:该标准只考虑 **[!UICONTROL In progress]** 超过指定持续时间的已启动投放(状态 **[!UICONTROL Deliveries with low throughput]** )。
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**:只有处理消息百分比低于指定百分比的投放才会考虑该 **[!UICONTROL Deliveries with low throughput]** 标准。
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**:只有吞吐量低于指定值的投放才会考虑该 **[!UICONTROL Deliveries with low throughput]** 标准。
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**:只考虑处理邮件百分比高于指定百分比的投放。

### 警报频率{#alerting-frequency}

**[!UICONTROL Frequency of delivery alerting]**&#x200B;选项允许定义两个警报发送之间的延迟。 默认情况下，设置为10分钟。

可以通过&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**&#x200B;菜单更改此设置。

>[!NOTE]
>
>此选项适用于在Adobe Campaign中定义的所有仪表板。 不能为每个仪表板设置特定频率。

## 投放警报原因{#delivery-alerting-reasons}

**投放警报**&#x200B;功能可通过电子邮件和仪表板自动向所有相关Adobe Campaign用户通知投放执行状态。

现在，当您收到投放警报通知时，以下是一些有关您可以做什么的提示。

首先，检查投放的&#x200B;**日志**&#x200B;选项卡，以视图与投放和验证相关的所有信息。 红色和黄色图标允许您识别错误或警告。 红色图标表示严重错误，该错误会阻止投放启动。

要视图每次出现投放的历史记录，请选择&#x200B;**[!UICONTROL Sending logs]**&#x200B;选项卡。 它包含已发送消息的列表及其状态。 您可以在此处检查每个收件人的投放状态（**[!UICONTROL Sent]**、**[!UICONTROL Pending]**、**[!UICONTROL Failed]**&#x200B;等）。 有关详细信息，请参阅[发送日志](../../sending/using/monitoring-a-delivery.md#sending-logs)。

以下是根据符合投放标准接收警报通知的几个可能原因。

* **[!UICONTROL Deliveries failed]**:此标准会通知所有状态错误的投放。这可能是由于：

   * 投放服务器（MTA、消息传输代理）出现问题
   * Adobe Campaign投放服务器与接收服务器之间的连接超时
   * 可交付性问题
   * 错误的工作流

   如果投放是通过工作流触发的，请检查该工作流是否正确启动。 有关详细信息，请参阅[执行工作流](../../automating/using/about-workflow-execution.md)。 否则，请联系您的Adobe Campaign管理员以解决此问题。

* **[!UICONTROL Deliveries with preparation failed]**:在以下情况下，投放准备过程中可能会出错：

   * 投放缺少一个主题。
   * 个性化字段中的语法错误。
   * 目标丢失。
   * 投放超过大小限制。

   有关此的详细信息，请参阅[准备send](../../sending/using/preparing-the-send.md)。 但是，在消息分析期间通常会发现这些错误。 请参阅[控制规则](../../sending/using/control-rules.md)。

* **[!UICONTROL Delivery with bad error ratio for soft bounces]**&#x200B;警报的可能原因可以是：

   * 收件人的服务器已关闭。
   * 收件人邮箱已满。

   有关详细信息，请检查投放日志的&#x200B;**[!UICONTROL Exclusion logs]**&#x200B;和&#x200B;**[!UICONTROL Exclusion causes]**&#x200B;选项卡。 请参阅[排除日志](../../sending/using/monitoring-a-delivery.md#exclusion-logs)。

   **[!UICONTROL Delivery with bad error ratio for hard bounces]**&#x200B;警报的可能原因可以是：

   * 收件人会添加到阻止列表中，这意味着不再希望与他们联系。
   * 收件人的电子邮件地址不存在。
   * 收件人的域不存在。
   * 收件人服务器正在阻止投放。

   要避免出现软跳出和硬跳出错误，请遵循以下最佳实践：

   * 构建过滤类型规则，以在投放分析期间排除消息目标的一部分，如隔离收件人。 请参阅[创建筛选规则](../../sending/using/filtering-rules.md)。
   * 定期更新客户隔离库，以保持良好的客户管理流程。 请参阅[关于隔离](../../sending/using/understanding-quarantine-management.md#about-quarantines)。
   * 一般而言，尽可能提高供应能力。 请参阅Adobe Campaign[Deliverability](../../sending/using/about-deliverability.md)详细文档，并与Adobe Campaign管理员联系以获得帮助。



* **[!UICONTROL Deliveries with long start pending]**:通常，这意味着在MTA（消息传输代理）级别存在问题。执行过程正在等待某些资源的可用性。 MTA可能尚未启动。

   **[!UICONTROL Deliveries with low throughput]**:同样，这是一个可交付性问题，意味着MTA太慢。

   有关这些问题的详细信息，请与您的Adobe Campaign管理员联系。

**相关主题：**

* [了解投放失败](../../sending/using/understanding-delivery-failures.md)
* [了解隔离管理](../../sending/using/understanding-quarantine-management.md)
* [关于 Campaign 中的选择启用和选择禁用](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

