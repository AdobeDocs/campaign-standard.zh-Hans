---
solution: Campaign Standard
product: campaign
title: 关于计划消息发送
description: 了解计划消息发送的方式。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 100%

---


# 关于计划消息发送{#about-scheduling-messages}

>[!CAUTION]
>
>只要对投放的计划进行更改，您就必须重新准备投放，方法是单击 **Prepare** 按钮，然后再单击 **Confirm**。

在消息仪表板中，利用 **[!UICONTROL Schedule]** 块可定义发送消息（电子邮件、短信或推送通知）的时间。

![](assets/delivery_dashboard.png)

利用 **[!UICONTROL Schedule]** 属性，可以设置电子邮件、短信或推送通知的发送选项：

* **[!UICONTROL Messages to be sent once confirmed]**：确认发送后立即发送消息。请参阅[确认发送](../../sending/using/confirming-the-send.md)。

   ![](assets/delivery_planning_1.png)

* **[!UICONTROL Messages to be sent automatically on the date specified below]**：在将来的日期和时间发送消息。请在 **Start sending from** 字段中指定&#x200B;**联系日期**。

   您可以准备并确认发送，但只有达到所选日期和时间才会开始发送消息。有关准备和确认发送的详情，请参见[准备发送](../../sending/using/preparing-the-send.md)和[确认发送](../../sending/using/confirming-the-send.md)章节。

   利用 **[!UICONTROL Time zone of the contact date]** 下拉列表，可修改与发送时间有关的时区。例如，如果您在 **[!UICONTROL Start sending from]** 字段中输入“9:00 AM”，并在 **[!UICONTROL Time zone of the contact date]** 下拉列表中选择“Brussels, Copenhagen, Madrid, Paris (GMT+1)”，则所有收件人将在巴黎时间上午 9:00 收到该消息。而位于“莫斯科 (GMT+3)”的收件人将在莫斯科时间上午 11:00 收到该消息。

   如果要手动确认发送，请勾选 **[!UICONTROL Request confirmation before sending messages]** 选项。默认启用此选项。

   ![](assets/delivery_planning.png)

>[!CAUTION]
>
>复制投放时，会删除所有计划设置。除非您计划了新的联系日期，否则一旦发送确认，将立即发送复制的投放。

**相关主题**：

* [优化发送时间](../../sending/using/optimizing-the-sending-time.md)
* [按收件人的时区发送消息](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)
* [计算发送日期](../../sending/using/computing-the-sending-date.md)

