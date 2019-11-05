---
title: 确认发送
description: 了解如何完成消息准备。
page-status-flag: 从未激活
uuid: 1eaecb32-ffd2-45d0-a8b4-f97bee59a1bd
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 发送
content-type: 参考
topic-tags: 发送和跟踪消息
discoiquuid: 8bb160b1-7de9-4c1f-bb89-b2e5fdafed41
context-tags: 交付，部署，返回
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 确认发送{#confirming-the-send}

在您准备完消息并执行了批准步骤后，可以发送这些消息。 有关消息准备的详细信息，请参 [阅准备发送](../../sending/using/preparing-the-send.md)。

只有具有该角色的用 **[!UICONTROL Start deliveries]** 户才能确认发送。 有关详细信息，请参阅角 [色列表部分](../../administration/using/list-of-roles.md) 。

没有此角色的用户将看到以下消息：

![](assets/confirm_delivery_2.png)

要发送您的分发，请单 **[!UICONTROL Confirm send]** 击消息操作栏中的按钮。

![](assets/confirm_delivery.png)

系统将要求您通过单击按钮来确定发送的 **[!UICONTROL OK]** 结束。

![](assets/confirm_delivery1.png)

正在发送消息。

>[!NOTE]
>
>如果消息已预定，则在到达发送时间时发送消息。 For more on scheduling messages, refer to [this section](../../sending/using/about-scheduling-messages.md).

如果您使用的是没有汇总期的重复交付，则可以在发送交付之前请求确认。 为此，请打开交 **[!UICONTROL Schedule]** 付功能板的块，然后激活专用选项。

![](assets/confirmation_recurring_deliveries.png)

块 **[!UICONTROL Deployment]** 显示发送的进度。

将消息发送到联系人后，区域会 **[!UICONTROL Deployment]** 显示您的KPI（关键绩效指标）数据，包括：

* 要传送的消息数
* 发送的消息数
* 已传送消息的百分比
* 弹回和错误的百分比
* 打开消息的百分比
* 消息中（用于电子邮件）的点击率

   >[!NOTE]
   >
   >和 **[!UICONTROL Open rate]** 每 **[!UICONTROL Click-through rate]** 小时更新一次。

![](assets/sending_delivery.png)

如果KPI更新时间过长或未考虑发送日志的结果，请单击窗 **[!UICONTROL Compute stats]** 口中的按 **[!UICONTROL Deployment]** 钮。

![](assets/sending_delivery7.png)

该消息可在构成部分受众的其中一个客户档案的历史记录中查看。 See [Integrated customer profile](../../audiences/using/integrated-customer-profile.md).

发送邮件后，您可以跟踪其收件人的行为并对其进行监视以衡量其影响。 有关此内容的详细信息，请参阅以下各节：

* [跟踪消息](../../sending/using/tracking-messages.md)
* [监控投放](../../sending/using/monitoring-a-delivery.md)

