---
title: 在失败时接收提醒
description: 了解如何使用警报管理系统。
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Proofs
role: User
level: Beginner
exl-id: dc8bd1d3-e199-4901-9b1f-7b485879897d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '2038'
ht-degree: 2%

---

# 在失败时接收提醒{#receiving-alerts-when-failures-happen}

## 关于投放警报 {#about-delivery-alerting}

**投放警报**&#x200B;功能是一个警报管理系统，它允许一组用户自动接收包含其投放执行信息的通知。

默认情况下，发送的通知包含基于以下条件的报告：

* 投放失败
* 准备失败的投放
* 软退回错误率不高的投放
* 硬退回错误率不高的投放
* 具有待定状态的投放比平常更长
* 吞吐量较低的投放
* 投放进行中

警报的接收者可以监控Adobe Campaign正在处理的投放，并在执行过程中出现问题时采取适当措施。

根据通过Adobe Campaign界面中的仪表板定义的特定警报标准，可以自定义这些警报通知。

>[!NOTE]
>
>警报通知仅通过电子邮件发送。

发送的通知包含：

* 一个&#x200B;**[!UICONTROL Summary]**，用于显示符合您定义的条件的投放数量以及您为每个条件选择的标签/颜色。
* **[!UICONTROL Details]**&#x200B;部分列出了为相应仪表板定义的所有投放标准以及每个标准的所有投放。

![](assets/delivery-alerting_notification.png)

## 投放警报仪表板 {#delivery-alerting-dashboards}

### 关于投放警报仪表板 {#about-delivery-alerting-dashboards}

要管理通知的收件人、定义警报标准并访问警报历史记录，您需要使用功能板。

>[!NOTE]
>
>要访问和配置功能板和警报条件，您必须具有管理权限或出现在&#x200B;**投放主管**&#x200B;安全组中。 标准用户无法在Adobe Campaign界面中访问功能板。 他们只能接收警报通知。 有关Adobe Campaign中的用户和安全性的详细信息，请参阅[用户类型](../../administration/using/users-management.md)和[关于安全组](../../administration/using/managing-groups-and-users.md#about-security-groups)。

从Adobe Campaign界面中，您可以：

* 创建和管理投放警报仪表板。 请参阅[创建投放警报仪表板](#creating-a-delivery-alerting-dashboard)。
* 定义和管理每个仪表板的投放警报标准。 例如，您可以基于准备失败的投放或仅低吞吐量的投放构建警报。 请参阅[关于警报条件](#about-alerting-criteria)。
* 修改每个仪表板的标准参数。 请参阅[标准参数](#criteria-parameters)。
* 为每个仪表板定义一组收件人。

  例如，您只想通知具有管理权限的用户投放失败。 但是，您希望营销用户接收有关软退回错误率的投放信息。 因此，您需要创建两个不同的功能板，并定义希望用于每个收件人组的标准。

* 访问每个仪表板所有已发送警报的历史记录。

  选择仪表板时，默认情况下将显示该仪表板的最后一次发送警报。 屏幕左侧列出了所有已发送的警报。 单击&#x200B;**[!UICONTROL History]**&#x200B;列表中的项以访问相应的警报。

![](assets/delivery-alerting_dashboard.png)

### 创建投放警报仪表板 {#creating-a-delivery-alerting-dashboard}

如果要根据特定标准向不同的用户组发送通知，您需要使用多个功能板。 要创建新仪表板，请执行以下操作：

1. 转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**。
1. 选择 **[!UICONTROL Delivery alerting dashboards]** 并单击 **[!UICONTROL Create]**。
1. 选中&#x200B;**[!UICONTROL Enabled]**&#x200B;框以激活当前仪表板。

   如果禁用此选项，则不再发送链接到该功能板的通知。 默认禁用此选项。

   ![](assets/delivery-alerting_dashboard_general.png)

1. 从&#x200B;**[!UICONTROL Alert group]**&#x200B;下拉列表中选择要通知的收件人组。 要修改或创建组，请参阅[创建安全组并分配用户](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users)。
1. 在&#x200B;**[!UICONTROL Delivery alerting criteria]**&#x200B;部分中，单击&#x200B;**[!UICONTROL Create element]**&#x200B;以添加条件。 请参阅[关于警报条件](#about-alerting-criteria)。
1. 选择&#x200B;**[!UICONTROL Edit properties]**&#x200B;按钮。 在&#x200B;**[!UICONTROL Criteria parameters]**&#x200B;选项卡中，定义标准的应用方式。 请参阅[标准参数](#criteria-parameters)。
1. 单击&#x200B;**[!UICONTROL Create]**&#x200B;以保存仪表板。

现在，每次投放满足您在此功能板中定义的标准时，都会向指定的用户组发送警报通知。

## 投放警报条件 {#delivery-alerting-criteria}

### 关于警报标准 {#about-alerting-criteria}

要访问投放警报条件，请转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**&#x200B;并选择&#x200B;**[!UICONTROL Delivery alerting criteria]**。

![](assets/delivery-alerting_criteria.png)

可在投放警报功能板中使用以下标准：

* **[!UICONTROL Deliveries failed]**：在定义的范围内计划的任何投放，状态错误。
* **[!UICONTROL Deliveries with preparation failed]**：在定义的范围内修改的任何投放，其准备步骤（目标计算和内容生成）已失败。 有关此内容的详细信息，请参阅[准备发送](../../sending/using/preparing-the-send.md)。
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**：在定义的范围内计划的任何投放，状态至少为&#x200B;**[!UICONTROL In progress]**，软退回错误率大于定义的百分比。
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**：在定义的范围内计划的任何投放，状态至少为&#x200B;**[!UICONTROL In progress]**，硬退回错误率大于定义的百分比。
* **[!UICONTROL Deliveries with long start pending]**：在定义的范围内计划的任何投放，**[!UICONTROL Start pending]**&#x200B;状态超过定义的持续时间，**[!UICONTROL Start pending]**&#x200B;状态表示系统尚未考虑这些邮件。
* **[!UICONTROL Deliveries with low throughput]**：任何已开始的投放超过定义的持续时间，未达到定义的已处理消息百分比，吞吐量低于定义的值。
* **[!UICONTROL Deliveries in progress]**：在定义的范围内计划的任何投放，状态为&#x200B;**[!UICONTROL In progress]**。

>[!NOTE]
>
>应用于上述标准的所有参数都有默认值。 可以在投放警报仪表板的&#x200B;**[!UICONTROL Criteria parameters]**&#x200B;选项卡中更改这些值。 请参阅[标准参数](#criteria-parameters)。

您可以从&#x200B;**[!UICONTROL Delivery alerting criteria]**&#x200B;列表中选择任何项目以访问其详细信息。

![](assets/delivery-alerting_criteria_definition.png)

对于每个条件，您可以定义以下设置：

* **[!UICONTROL Indicators to add in alerts]**，表示将针对与所选条件对应的投放在通知的&#x200B;**[!UICONTROL Details]**&#x200B;部分中显示的列。

  ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**，表示在通知摘要中显示在投放条件旁边的标签和颜色。

  ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**：如果一次投放符合某个标准，则在监控期间发送的每个通知中都会重复该标准。 否则，对于一次投放，根据警报条件，每天只发送一个警报（第一次发生时）。

  默认情况下，所有标准的此选项均设置为每天一次。

**相关主题：**

* [正在发送日志](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [警报频率](#alerting-frequency)
* [营销活动的图标和状态](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### 创建投放警报条件 {#creating-a-delivery-alerting-criterion}

您可以创建新的投放警报标准，以更好地满足您的需求。

例如，您可以创建一个新条件，以允许发送列出状态为&#x200B;**[!UICONTROL Finished]**&#x200B;的所有投放的通知。

为此，您首先需要扩展&#x200B;**Delivery**&#x200B;资源并添加一个新的筛选器，以便仅选择具有&#x200B;**[!UICONTROL Finished]**&#x200B;状态的投放。

1. 转到&#x200B;**Adobe Campaign** > **管理** > **开发** > **自定义资源**，然后单击&#x200B;**[!UICONTROL Create]**。
1. 选择&#x200B;**[!UICONTROL Extend an existing resource]**，从下拉列表中选择&#x200B;**[!UICONTROL Delivery]**&#x200B;资源并单击&#x200B;**[!UICONTROL Create]**&#x200B;进行编辑。

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   有关扩展现有资源的详细信息，请参阅[定义资源](../../developing/using/creating-or-extending-the-resource.md)。

1. 在&#x200B;**[!UICONTROL Delivery]**&#x200B;资源中，转到&#x200B;**[!UICONTROL Filter definition]**&#x200B;选项卡并单击&#x200B;**[!UICONTROL Add an element]**&#x200B;以创建筛选器。

   ![](assets/delivery-alerting_new-filter.png)

1. 编辑新的筛选器定义：在&#x200B;**[!UICONTROL Filter definition]**&#x200B;窗口中，将&#x200B;**[!UICONTROL Status]**&#x200B;项拖放到工作区中，并选择&#x200B;**[!UICONTROL Finished]**&#x200B;作为筛选器条件。

   ![](assets/delivery-alerting_filter-status.png)

   有关创建和编辑自定义筛选器的详细信息，请参阅[定义筛选器](../../developing/using/configuring-filter-definition.md)。

1. 保存更改并发布资源。 有关详细信息，请参阅[发布自定义资源](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

   筛选器已创建，现在可以在新的投放警报标准中选择。

1. 转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**，选择&#x200B;**[!UICONTROL Delivery alerting criteria]**&#x200B;并单击&#x200B;**[!UICONTROL Create]**。
1. 在&#x200B;**[!UICONTROL Delivery filter applied by this criterion]**&#x200B;下拉列表中，选择之前创建的过滤器。

   ![](assets/delivery-alerting_cus-filter.png)

   可以使用与默认标准相同的方式定义标准的设置。 请参阅[关于警报条件](#about-alerting-criteria)。

创建后，可以将这些标准以及其他标准添加到投放警报仪表板。 请参阅[关于投放警报仪表板](#about-delivery-alerting-dashboards)。

![](assets/delivery-alerting_new-criterion.png)

**相关主题：**

[添加或扩展资源](../../developing/using/key-steps-to-add-a-resource.md)

## 投放警报参数 {#delivery-alerting-parameters}

### 标准参数 {#criteria-parameters}

在[投放警报仪表板](#creating-a-delivery-alerting-dashboard)的&#x200B;**[!UICONTROL Criteria parameters]**&#x200B;选项卡中，您可以定义应用于该仪表板中所选标准的设置。

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**：例如，如果在此字段中输入100，则仅会为目标等于或大于100个收件人的投放发送通知。 此参数适用于所有标准。
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**：当前时间之前和之后的小时数。 只考虑联系日期在此时间范围内的投放。 此参数适用于所有标准。 默认情况下，此字段值设置为24小时。

  有关联系日期的详细信息，请参阅[关于计划](../../sending/using/about-scheduling-messages.md)。

* **[!UICONTROL Maximum ratio of soft bounce errors]**：对于软退回错误率大于指定值的所有投放，将发送通知。 默认情况下，此字段值设置为0.05 (5%)。

  有关软退回错误的详细信息，请参阅[退回邮件鉴别](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)和[投放失败类型列表](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)。

* **[!UICONTROL Maximum ratio of hard bounce errors]**：对于硬退回错误率大于指定值的所有投放，将发送通知。 默认情况下，此字段值设置为0.05 (5%)。

  有关硬退回错误的更多信息，请参阅[退回邮件鉴别](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)和[投放失败类型列表](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)。

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**：对于其状态为&#x200B;**[!UICONTROL Start pending]**&#x200B;且持续时间长于此字段中指定持续时间的所有投放发送通知，**[!UICONTROL Start pending]**&#x200B;状态表示系统尚未考虑这些消息。
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**： **[!UICONTROL Deliveries with low throughput]**&#x200B;条件只考虑启动时间超过指定持续时间的投放（状态为&#x200B;**[!UICONTROL In progress]**）。
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**： **[!UICONTROL Deliveries with low throughput]**&#x200B;条件只考虑其百分比低于指定百分比的已处理邮件的投放。
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**： **[!UICONTROL Deliveries with low throughput]**&#x200B;条件只考虑吞吐量低于指定值的投放。
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**：只考虑已处理消息百分比高于指定百分比的投放。

### 警报频率 {#alerting-frequency}

**[!UICONTROL Frequency of delivery alerting]**&#x200B;选项允许定义两个警报发送之间的延迟。 默认情况下，设置为10分钟。

您可以通过&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**&#x200B;菜单更改此设置。

>[!NOTE]
>
>此选项适用于Adobe Campaign中定义的所有功能板。 不能为每个仪表板设置特定的频率。

## 投放警报原因 {#delivery-alerting-reasons}

**投放警报**&#x200B;功能可让您通过电子邮件和仪表板，将所有参与的Adobe Campaign用户自动告知投放执行状态。

现在，当您收到投放警报通知时，您可以按照以下提示进行操作。

首先，检查投放的&#x200B;**日志**&#x200B;选项卡以查看与投放和验证相关的所有信息。 利用红色和黄色图标，可识别错误或警告。 红色图标表示阻止启动投放的严重错误。

要查看每次投放的历史记录，请选择&#x200B;**[!UICONTROL Sending logs]**&#x200B;选项卡。 它包含已发送消息的列表及其状态。 在此，您可以检查每个收件人（**[!UICONTROL Sent]**、**[!UICONTROL Pending]**、**[!UICONTROL Failed]**&#x200B;等）的投放状态。 有关此内容的详细信息，请参阅[发送日志](../../sending/using/monitoring-a-delivery.md#sending-logs)。

根据投放所满足的标准，以下是接收警报通知的一些可能原因。

* **[!UICONTROL Deliveries failed]**：此条件会通知您所有状态错误的投放。 原因可能是：

   * 投放服务器（MTA、消息传输代理）出现问题
   * Adobe Campaign投放服务器与接收服务器之间的连接超时
   * 投放能力问题
   * 错误的工作流

  如果通过工作流触发投放，请检查该工作流是否已正确启动。 有关详细信息，请参阅[执行工作流](../../automating/using/about-workflow-execution.md)。 否则，请与Adobe Campaign管理员联系以解决此问题。

* **[!UICONTROL Deliveries with preparation failed]**：在准备投放期间可能会出现以下错误：

   * 投放缺少主题。
   * 个性化字段中存在错误的语法。
   * 目标不见了。
   * 投放超出大小限制。

  有关此内容的详细信息，请参阅[准备发送](../../sending/using/preparing-the-send.md)。 但是，这些错误通常会在消息分析期间发现。 请参阅[控制规则](../../sending/using/control-rules.md)。

* **[!UICONTROL Delivery with bad error ratio for soft bounces]**&#x200B;警报的可能原因可能是：

   * 收件人的服务器已关闭。
   * 收件人的邮箱已满。

  有关详细信息，请检查投放日志的&#x200B;**[!UICONTROL Exclusion logs]**&#x200B;和&#x200B;**[!UICONTROL Exclusion causes]**&#x200B;选项卡。 请参阅[排除日志](../../sending/using/monitoring-a-delivery.md#exclusion-logs)。

  **[!UICONTROL Delivery with bad error ratio for hard bounces]**&#x200B;警报的可能原因可能是：

   * 收件人将添加到阻止列表，这意味着他们不再希望被联系。
   * 收件人的电子邮件地址不存在。
   * 收件人的域不存在。
   * 收件人的服务器正在阻止投放。

  要避免软退回和硬退回错误，请遵循以下最佳实践：

   * 构建过滤分类规则，以在投放分析期间排除部分消息目标，如隔离的收件人。 请参阅[创建筛选规则](../../sending/using/filtering-rules.md)。
   * 定期更新客户数据库以保持良好的隔离管理流程。 请参阅[关于隔离](../../sending/using/understanding-quarantine-management.md#about-quarantines)。
   * 一般而言，请尽可能改善可投放性。 请参阅Adobe Campaign [可投放性](../../sending/using/about-deliverability.md)详细文档，并联系Adobe Campaign管理员以获取帮助。

* **[!UICONTROL Deliveries with long start pending]**：这通常意味着在MTA（消息传输代理）级别有问题。 执行过程正在等待某些资源的可用性。 MTA可能尚未启动。

  **[!UICONTROL Deliveries with low throughput]**：同样地，这是一个可投放性问题，这意味着MTA太慢。

  有关这些问题的更多信息，请与Adobe Campaign管理员联系。

**相关主题：**

* [了解投放失败](../../sending/using/understanding-delivery-failures.md)
* [了解隔离管理](../../sending/using/understanding-quarantine-management.md)
* [关于 Campaign 中的选择启用和选择禁用](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
