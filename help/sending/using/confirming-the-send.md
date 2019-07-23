---
title: 确认发送
seo-title: 确认发送
description: 确认发送
seo-description: 了解如何完成消息准备。
page-status-flag: 从未激活
uuid: easpech32-ffd2-45d0 b4 b4-f97 be59 a1 bd
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 发送
content-type: reference
topic-tags: 发送和跟踪消息
discoiquuid: 8bb160b1-7de9-4c1f-bb89-b2 e5 ftfed41
context-tags: 交付，部署，返回
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: e9dd7c374903d0c57ac4881ed125c3215bd7fe11

---


# Confirming the send{#confirming-the-send}

准备完消息并执行批准步骤后，您可以发送它们。For more on messages preparation, refer to [Preparing the send](../../sending/using/preparing-the-send.md).

Only users with the **[!UICONTROL Start deliveries]** role can confirm send. For more on this, refer to the [List of roles](../../administration/using/list-of-roles.md) section.

没有此角色的用户将看到以下消息：

![](assets/confirm_delivery_2.png)

To send your delivery, click the **[!UICONTROL Confirm send]** button found in the message's action bar.

![](assets/confirm_delivery.png)

You will be asked to finalize the send definitively by clicking the **[!UICONTROL OK]** button.

![](assets/confirm_delivery1.png)

消息将发送。

>[!NOTE]
>
>如果消息已预定，则将在发送时间时发送该消息。For more on scheduling messages, refer to [this section](../../sending/using/about-scheduling-messages.md).

如果您使用的是没有聚合期的定期分发，则可以在发送发送之前请求确认。To do this, open the **[!UICONTROL Schedule]** block of the delivery dashboard, then activate the dedicated option.

![](assets/confirmation_recurring_deliveries.png)

**[!UICONTROL Deployment]** 此块显示发送进度。

Once the message is sent to the contacts, the **[!UICONTROL Deployment]** zone shows your KPIs (Key Performance Indicator) data , including:

* 发送信息的数量
* 发送的消息数
* 传送的消息百分比
* 弹回和错误的百分比
* 开放消息的百分比
* 消息中点击的百分比(电子邮件)

   >[!NOTE]
   >
   >The **[!UICONTROL Open rate]** and **[!UICONTROL Click-through rate]** are updated every hour.

![](assets/sending_delivery.png)

If the KPIs take too long to update or don't take into account the results from the sending logs, click the **[!UICONTROL Compute stats]** button in the **[!UICONTROL Deployment]** window.

![](assets/sending_delivery7.png)

可以在一个客户端配置文件的历史记录中查看该消息，它构成了受众的组成部分。See [Integrated customer profile](../../audiences/using/integrated-customer-profile.md).

发送消息后，您可以跟踪收件人的行为并监控其影响，以衡量其影响。有关此操作的详细信息，请参阅以下几节：

* [跟踪消息](../../sending/using/tracking-messages.md)
* [监控交付](../../sending/using/monitoring-a-delivery.md)

