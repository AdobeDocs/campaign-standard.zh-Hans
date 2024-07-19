---
title: 确认发送
description: 了解如何完成消息的准备工作。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
context-tags: delivery,deployment,back
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: 0a0fe969-cdfd-4b0c-a746-081038424d86
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 16%

---

# 确认发送{#confirming-the-send}

您完成准备消息并执行批准步骤后，即可发送消息。有关消息准备的更多信息，请参阅[准备发送](../../sending/using/preparing-the-send.md)。

只有具有&#x200B;**[!UICONTROL Start deliveries]**&#x200B;角色的用户才能确认发送。 有关更多信息，请参阅[角色列表](../../administration/using/list-of-roles.md)一节。

<!--Users without this role will see the following message: 

![](assets/confirm_delivery_2.png)-->

## 正在发送消息 {#sending-message}

准备完成后，请按照以下步骤发送消息。

1. 单击消息操作栏中的&#x200B;**[!UICONTROL Confirm send]**&#x200B;按钮。

   ![](assets/confirm_delivery.png)

1. 单击&#x200B;**[!UICONTROL OK]**&#x200B;按钮完成发送。

   ![](assets/confirm_delivery1.png)

1. 正在发送消息，请稍候。 **[!UICONTROL Deployment]** 块可显示发送的进度。

>[!NOTE]
>
>如果设置了消息发送计划，则在达到发送时间时会发送该消息。 有关计划发送消息的更多信息，请参阅[此章节](../../sending/using/about-scheduling-messages.md)。

如果您使用的是没有聚合期的定期投放，则可以在发送投放之前请求确认。配置消息时，打开投放仪表板的&#x200B;**[!UICONTROL Schedule]**&#x200B;块并激活专用选项。

![](assets/confirmation_recurring_deliveries.png)

## 了解消息指示器 {#message-indicators}

将消息发送到联系人后，**[!UICONTROL Deployment]**&#x200B;区域会显示您的KPI（关键绩效指标）数据，包括：

* 要投放的消息数
* 已发送的消息数
* 已投放邮件的百分比
* 退回和错误的百分比
* 打开消息的百分比
* 点击消息的百分比（适用于电子邮件）

  >[!NOTE]
  >
  >**[!UICONTROL Open rate]** 和 **[!UICONTROL Click-through rate]** 每小时更新一次。

![](assets/sending_delivery.png)

如果KPI更新时间过长或未反映来自发送日志的结果，请单击&#x200B;**[!UICONTROL Deployment]**&#x200B;窗口中的&#x200B;**[!UICONTROL Compute stats]**&#x200B;按钮。

![](assets/sending_delivery7.png)

可以在其中一个定向用户档案的历史记录中查看消息。 请参阅[整合后的客户用户档案](../../audiences/using/integrated-customer-profile.md)。

发送消息后，您可以跟踪其收件人的行为并对其进行监视以衡量其影响。 有关更多信息，请参阅一下章节。

* [跟踪消息](../../sending/using/tracking-messages.md)
* [监测投放](../../sending/using/monitoring-a-delivery.md)

### 投放成功报告 {#delivered-status-report}

>[!NOTE]
>
>本节仅适用于电子邮件渠道。

在每封电子邮件的&#x200B;**[!UICONTROL Summary]**&#x200B;视图中，**[!UICONTROL Delivered]**&#x200B;百分比从100%开始，然后在投放[有效期](../../administration/using/configuring-email-channel.md#validity-period-parameters)内逐步下降，因为软退信和硬退信会被报告回<!--from the Enhanced MTA to Campaign-->。

事实上，一旦消息从Campaign成功中继到增强型MTA（消息传输代理），则所有消息在[发送日志](../../sending/using/monitoring-a-delivery.md#sending-logs)中都会显示为&#x200B;**[!UICONTROL Sent]**。 除非或直到该消息的[退回](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)从Enhanced MTA传回Campaign，否则它们将保持该状态。

当从增强型MTA报告硬退回邮件时，其状态从&#x200B;**[!UICONTROL Sent]**&#x200B;更改为&#x200B;**[!UICONTROL Failed]**，**[!UICONTROL Delivered]**&#x200B;百分比相应减少。

从Enhanced MTA报告软退回邮件时，它们仍显示为&#x200B;**[!UICONTROL Sent]**，并且&#x200B;**[!UICONTROL Delivered]**&#x200B;百分比尚未更新。 然后，软退回邮件在投放有效期内将重试[](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)：

* 如果在有效期结束前重试成功，则消息状态将保留为&#x200B;**[!UICONTROL Sent]**，**[!UICONTROL Delivered]**&#x200B;百分比将保持不变。

* 否则，状态将更改为&#x200B;**[!UICONTROL Failed]**，**[!UICONTROL Delivered]**&#x200B;百分比将相应减少。

因此，您必须等到有效期结束才能看到最终的&#x200B;**[!UICONTROL Delivered]**&#x200B;百分比，以及&#x200B;**[!UICONTROL Sent]**&#x200B;和&#x200B;**[!UICONTROL Failed]**&#x200B;条消息的最终数量。

### 电子邮件反馈服务（测试版） {#email-feedback-service}

借助电子邮件反馈服务(EFS)功能，可以直接从Enhanced MTA（消息传输代理）获取反馈，从而准确报告每个电子邮件的状态。

>[!IMPORTANT]
>
>电子邮件反馈服务目前作为测试版功能提供。

投放开始后，当消息成功从Campaign中继到增强型MTA时，**[!UICONTROL Delivered]**&#x200B;百分比没有变化。

![](assets/efs-sending.png)

投放日志显示每个目标地址的&#x200B;**[!UICONTROL Pending]**&#x200B;状态。

![](assets/efs-pending.png)

当从Enhanced MTA实时报告发送到目标用户档案的消息投放时，投放日志显示成功接收消息的每个地址的&#x200B;**[!UICONTROL Sent]**&#x200B;状态。 每次成功投放后，**[!UICONTROL Delivered]**&#x200B;百分比都会相应增加。

当从增强型MTA报告硬退回消息时，其日志状态从&#x200B;**[!UICONTROL Pending]**&#x200B;更改为&#x200B;**[!UICONTROL Failed]**，**[!UICONTROL Bounces + errors]**&#x200B;百分比相应增加。

从增强MTA报告软退回消息时，其日志状态也从&#x200B;**[!UICONTROL Pending]**&#x200B;更改为&#x200B;**[!UICONTROL Failed]**，**[!UICONTROL Bounces + errors]**&#x200B;百分比相应增加。 **[!UICONTROL Delivered]**&#x200B;百分比保持不变。 然后，在投放[有效期](../../administration/using/configuring-email-channel.md#validity-period-parameters)内重试软退回邮件：

* 如果在有效期结束前重试成功，则消息状态将更改为&#x200B;**[!UICONTROL Sent]**，并相应地增加&#x200B;**[!UICONTROL Delivered]**&#x200B;百分比。

* 否则，状态将保留为&#x200B;**[!UICONTROL Failed]**。 **[!UICONTROL Delivered]**&#x200B;和&#x200B;**[!UICONTROL Bounces + errors]**&#x200B;百分比保持不变。

>[!NOTE]
>
>有关硬退信和软退信的详细信息，请参阅[此部分](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)。
>
>有关投放临时失败后重试的详细信息，请参阅[此部分](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)。

<!--Soft-bouncing messages increment an error counter. When the error counter reaches the limit threshold or when the validity period is over, the address goes into quarantine and the status remains as **[!UICONTROL Failed]**. For more on conditions for sending an address to quarantine, see [this section](../../help/sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).-->

### EFS引入的更改 {#changes-introduced-by-efs}

下表显示了EFS功能引入的KPI和发送日志状态的变化。

**电子邮件反馈服务**

| 发送过程中的步骤 | KPI摘要 | 发送日志状态 |
|--- |--- |--- |
| 消息已成功从Campaign中继到增强型MTA | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比从0%开始</li><li>**[!UICONTROL Bounces + errors]**&#x200B;百分比从0%开始</li></ul> | 待处理 |
| 从Enhanced MTA返回硬退回消息 | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比无变化</li><li>**[!UICONTROL Bounces + errors]**&#x200B;百分比将相应增加</li></ul> | 已失败 |
| 从Enhanced MTA返回软退回消息 | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比无变化</li><li>**[!UICONTROL Bounces + errors]**&#x200B;百分比将相应增加</li></ul> | 已失败 |
| 软退回消息重试成功 | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比将相应增加</li><li>**[!UICONTROL Bounces + errors]**&#x200B;百分比将相应减少</li></ul> | 已发送 |
| 软退回消息重试失败 | <ul><li> **[!UICONTROL Delivered]**&#x200B;百分比无变化 </li><li> **[!UICONTROL Bounces + errors]**&#x200B;百分比无变化 </li></ul> | 已失败 |

**没有电子邮件反馈服务**

| 发送过程中的步骤 | KPI摘要 | 发送日志状态 |
|--- |--- |--- |
| 消息已成功从Campaign中继到增强型MTA | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比从100%开始</li><li>**[!UICONTROL Bounces + errors]**&#x200B;百分比从0%开始</li></ul> | 已发送 |
| 从Enhanced MTA返回硬退回消息 | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比将相应减少</li><li>**[!UICONTROL Bounces + errors]**&#x200B;百分比将相应增加</li></ul> | 已失败 |
| 从Enhanced MTA返回软退回消息 | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比无变化</li><li>**[!UICONTROL Bounces + errors]**&#x200B;百分比无变化</li></ul> | 已发送 |
| 软退回消息重试成功 | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比无变化</li><li>**[!UICONTROL Bounces + errors]**&#x200B;百分比无变化</li></ul> | 已发送 |
| 软退回消息重试失败 | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比将相应减少</li><li>**[!UICONTROL Bounces + errors]**&#x200B;百分比将相应增加</li></ul> | 已失败 |
