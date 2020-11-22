---
solution: Campaign Standard
product: campaign
title: 确认发送
description: 了解如何完成消息的准备工作。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
context-tags: delivery,deployment,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 100%

---


# 确认发送{#confirming-the-send}

您完成准备消息并执行批准步骤后，即可发送消息。有关消息准备的更多信息，请参阅[准备发送](../../sending/using/preparing-the-send.md)。

只有具有 **[!UICONTROL Start deliveries]** 角色的用户才能确认发送。有关更多信息，请参阅[角色列表](../../administration/using/list-of-roles.md)一节。

不具有此角色的用户将看到以下消息：

![](assets/confirm_delivery_2.png)

要发送投放，请单击消息操作栏中的 **[!UICONTROL Confirm send]** 按钮。

![](assets/confirm_delivery.png)

系统将要求您通过单击 **[!UICONTROL OK]** 按钮以最终确定发送。

![](assets/confirm_delivery1.png)

发送消息。

>[!NOTE]
>
>如果为消息安排了发送时间，则会在到达该时间时发送消息。有关计划发送消息的更多信息，请参阅[此章节](../../sending/using/about-scheduling-messages.md)。

如果您使用的是没有聚合期的定期投放，则可以在发送投放之前请求确认。要实现此目的，请打开投放仪表板的 **[!UICONTROL Schedule]** 块，然后激活专用选项。

![](assets/confirmation_recurring_deliveries.png)

**[!UICONTROL Deployment]** 块可显示发送的进度。

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

如果 KPI 更新时间过长或未考虑来自发送日志的结果，请单击 **[!UICONTROL Deployment]** 窗口中的 **[!UICONTROL Compute stats]** 按钮。

![](assets/sending_delivery7.png)

可以在构成受众的其中一个客户用户档案的历史记录中查看消息。请参阅[整合后的客户用户档案](../../audiences/using/integrated-customer-profile.md)。

发送消息后，您可以跟踪其收件人的行为并对其进行监视以衡量其影响。有关更多信息，请参阅一下章节。

* [跟踪消息](../../sending/using/tracking-messages.md)
* [监控投放](../../sending/using/monitoring-a-delivery.md)

