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
source-wordcount: '942'
ht-degree: 18%

---

# 确认发送{#confirming-the-send}

您完成准备消息并执行批准步骤后，即可发送消息。有关消息准备的更多信息，请参阅[准备发送](../../sending/using/preparing-the-send.md)。

仅限具有以下特征的用户： **[!UICONTROL Start deliveries]** 角色可以确认发送。 有关更多信息，请参阅[角色列表](../../administration/using/list-of-roles.md)一节。

<!--Users without this role will see the following message: 

![](assets/confirm_delivery_2.png)-->

## 发送消息 {#sending-message}

准备完成后，请按照以下步骤发送消息。

1. 单击 **[!UICONTROL Confirm send]** 在消息操作栏中找到按钮。

   ![](assets/confirm_delivery.png)

1. 单击 **[!UICONTROL OK]** 按钮。

   ![](assets/confirm_delivery1.png)

1. 正在发送消息，请稍候。 **[!UICONTROL Deployment]** 块可显示发送的进度。

>[!NOTE]
>
>如果计划发送消息，则在达到发送时间时会发送该消息。 有关计划发送消息的更多信息，请参阅[此章节](../../sending/using/about-scheduling-messages.md)。

如果您使用的是没有聚合期的定期投放，则可以在发送投放之前请求确认。配置消息时，打开 **[!UICONTROL Schedule]** 投放仪表板的块并激活专用选项。

![](assets/confirmation_recurring_deliveries.png)

## 了解消息指示器 {#message-indicators}

将消息发送到联系人后，**[!UICONTROL Deployment]** 区域会显示您的 KPI（关键绩效指标）数据，包括：

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

如果KPI更新时间过长或未反映发送日志的结果，请单击 **[!UICONTROL Compute stats]** 中的按钮 **[!UICONTROL Deployment]** 窗口。

![](assets/sending_delivery7.png)

可以在其中一个目标用户档案的历史记录中查看该消息。 请参阅[整合后的客户用户档案](../../audiences/using/integrated-customer-profile.md)。

发送消息后，您可以跟踪其收件人的行为，并对其进行监控以衡量其影响。 有关更多信息，请参阅一下章节。

* [跟踪消息](../../sending/using/tracking-messages.md)
* [监测投放](../../sending/using/monitoring-a-delivery.md)

### 投放成功报告 {#delivered-status-report}

>[!NOTE]
>
>此部分仅适用于电子邮件渠道。

在 **[!UICONTROL Summary]** 每封电子邮件的视图， **[!UICONTROL Delivered]** 百分比从100%开始，然后在交付过程中逐步下降 [有效期](../../administration/using/configuring-email-channel.md#validity-period-parameters)，因为软退信和硬退信会被报告回来<!--from the Enhanced MTA to Campaign-->.

事实上，所有消息都显示为 **[!UICONTROL Sent]** 在 [发送日志](../../sending/using/monitoring-a-delivery.md#sending-logs) 只要他们成功从Campaign中继到增强型MTA（消息传输代理）。 除非或直至 [跳出](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) ，则该消息会从Enhanced MTA传回Campaign。

从Enhanced MTA报告硬退回消息时，其状态将从 **[!UICONTROL Sent]** 到 **[!UICONTROL Failed]** 和 **[!UICONTROL Delivered]** 百分比亦会相应减少。

当从Enhanced MTA报告软退回消息时，它们仍显示为 **[!UICONTROL Sent]** 和 **[!UICONTROL Delivered]** 百分比尚未更新。 然后，软退回消息 [已重试](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure) 在整个投放有效期内：

* 如果在有效期结束前重试成功，则消息状态将保持为 **[!UICONTROL Sent]** 和 **[!UICONTROL Delivered]** 百分比保持不变。

* 否则，状态将更改为 **[!UICONTROL Failed]** 和 **[!UICONTROL Delivered]** 百分比亦会相应减少。

因此，您必须等到有效期结束才能看到最终版本 **[!UICONTROL Delivered]** 百分比，以及最终数量 **[!UICONTROL Sent]** 和 **[!UICONTROL Failed]** 消息。

### 电子邮件反馈服务（测试版） {#email-feedback-service}

借助电子邮件反馈服务(EFS)功能，每个电子邮件的状态均可准确报告，因为反馈是直接从Enhanced MTA（邮件传输代理）中捕获的。

>[!IMPORTANT]
>
>电子邮件反馈服务目前作为测试版功能提供。

投放开始后， **[!UICONTROL Delivered]** 消息成功从Campaign中继到Enhanced MTA时的百分比。

![](assets/efs-sending.png)

投放日志显示 **[!UICONTROL Pending]** 每个目标地址的状态。

![](assets/efs-pending.png)

当从Enhanced MTA实时报告发送到目标用户档案的消息时，投放日志显示 **[!UICONTROL Sent]** 成功接收消息的每个地址的状态。 此 **[!UICONTROL Delivered]** 百分比会随着每次成功交付而相应增加。

从Enhanced MTA报告硬退回消息时，其日志状态将从 **[!UICONTROL Pending]** 到 **[!UICONTROL Failed]** 和 **[!UICONTROL Bounces + errors]** 百分比亦会相应增加。

当从Enhanced MTA报告软退回消息时，其日志状态也会从 **[!UICONTROL Pending]** 到 **[!UICONTROL Failed]** 和 **[!UICONTROL Bounces + errors]** 百分比亦会相应增加。 此 **[!UICONTROL Delivered]** 百分比保持不变。 然后，在整个投放过程中重试软退回消息 [有效期](../../administration/using/configuring-email-channel.md#validity-period-parameters)：

* 如果在有效期结束前重试成功，则消息状态将更改为 **[!UICONTROL Sent]** 和 **[!UICONTROL Delivered]** 百分比亦会相应增加。

* 否则，状态将保持为 **[!UICONTROL Failed]**. 此 **[!UICONTROL Delivered]** 和 **[!UICONTROL Bounces + errors]** 百分比保持不变。

>[!NOTE]
>
>有关硬退信和软退信的更多信息，请参阅 [本节](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).
>
>有关投放临时失败后重试的更多信息，请参阅 [本节](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--Soft-bouncing messages increment an error counter. When the error counter reaches the limit threshold or when the validity period is over, the address goes into quarantine and the status remains as **[!UICONTROL Failed]**. For more on conditions for sending an address to quarantine, see [this section](../../help/sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).-->

### EFS引入的更改 {#changes-introduced-by-efs}

下表显示了EFS功能引入的KPI和发送日志状态的变化。

**使用电子邮件反馈服务**

| 发送过程中的步骤 | KPI摘要 | 发送日志状态 |
|--- |--- |--- |
| 消息已成功从Campaign中继到增强型MTA | <ul><li>**[!UICONTROL Delivered]** 百分比从0%开始</li><li>**[!UICONTROL Bounces + errors]** 百分比从0%开始</li></ul> | 待处理 |
| 从Enhanced MTA返回硬退回消息 | <ul><li>无更改 **[!UICONTROL Delivered]** 百分比</li><li>**[!UICONTROL Bounces + errors]** 百分比亦相应增加</li></ul> | 已失败 |
| 从Enhanced MTA返回软退回消息 | <ul><li>无更改 **[!UICONTROL Delivered]** 百分比</li><li>**[!UICONTROL Bounces + errors]** 百分比亦相应增加</li></ul> | 已失败 |
| 软退回消息重试成功 | <ul><li>**[!UICONTROL Delivered]** 百分比亦相应增加</li><li>**[!UICONTROL Bounces + errors]** 百分比将相应减少</li></ul> | 已发送 |
| 软退回消息重试失败 | <ul><li> 无更改 **[!UICONTROL Delivered]** 百分比 </li><li> 无更改 **[!UICONTROL Bounces + errors]** 百分比 </li></ul> | 已失败 |

**无电子邮件反馈服务**

| 发送过程中的步骤 | KPI摘要 | 发送日志状态 |
|--- |--- |--- |
| 消息已成功从Campaign中继到增强型MTA | <ul><li>**[!UICONTROL Delivered]** 百分比从100%开始</li><li>**[!UICONTROL Bounces + errors]** 百分比从0%开始</li></ul> | 已发送 |
| 从Enhanced MTA返回硬退回消息 | <ul><li>**[!UICONTROL Delivered]** 百分比将相应减少</li><li>**[!UICONTROL Bounces + errors]** 百分比亦相应增加</li></ul> | 已失败 |
| 从Enhanced MTA返回软退回消息 | <ul><li>无更改 **[!UICONTROL Delivered]** 百分比</li><li>无更改 **[!UICONTROL Bounces + errors]** 百分比</li></ul> | 已发送 |
| 软退回消息重试成功 | <ul><li>无更改 **[!UICONTROL Delivered]** 百分比</li><li>无更改 **[!UICONTROL Bounces + errors]** 百分比</li></ul> | 已发送 |
| 软退回消息重试失败 | <ul><li>**[!UICONTROL Delivered]** 百分比将相应减少</li><li>**[!UICONTROL Bounces + errors]** 百分比亦相应增加</li></ul> | 已失败 |
