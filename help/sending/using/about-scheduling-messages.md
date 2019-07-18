---
title: 关于计划消息
seo-title: 关于计划消息
description: 关于计划消息
seo-description: 了解如何安排消息。
page-status-flag: 从未激活
uuid: 286fcee-65a9-4cb9-b205-9ce5 d024675 c
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 发送
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3 c-8cb1-873397a acd27
context-tags: 交付，计划，返回
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# About scheduling messages{#about-scheduling-messages}

>[!CAUTION]
>
>Whenever making changes to a delivery’s schedule, you must re-prepare the delivery by clicking on the **Prepare** button before clicking **Confirm**.

In the message dashboard, the **[!UICONTROL Schedule]** block allows you to define when messages (email, SMS or Push notifications) will be sent.

![](assets/delivery_dashboard.png)

**[!UICONTROL Schedule]** 通过属性，您可以设置电子邮件、SMS或推送通知的发送选项：

* **[!UICONTROL Messages to be sent once confirmed]**：发送确认消息后发送消息。See [Confirming the send](../../sending/using/confirming-the-send.md).

   ![](assets/delivery_planning_1.png)

* **[!UICONTROL Messages to be sent automatically on the date specified below]**：消息将在以后的日期和时间发送。Specify the **contact date** in the **Start sending from** field.

   您可以准备并确认发送，但只会发送选定的日期和时间。Preparing and confirming the send are presented in the [Preparing the send](../../sending/using/preparing-the-send.md) and [Confirming the send](../../sending/using/confirming-the-send.md) sections.

   The **[!UICONTROL Time zone of the contact date]** drop-down list allows you to modify the time zone that will be taken into account for the sending time. For example, if you enter 9:00 AM in the **[!UICONTROL Start sending from]** field and if you select Brussels, Copenhagen, Madrid, Paris (GMT+1) in the **[!UICONTROL Time zone of the contact date]** drop-down list, all recipients will receive the message at 9:00 AM Paris time. 因此，位于莫斯科(GMT+3)的收件人将在莫斯科时间11：00收到邮件。

   If you would like to manually confirm the send, check the **[!UICONTROL Request confirmation before sending messages]** option. 默认情况下启用此选项。

   ![](assets/delivery_planning.png)

>[!CAUTION]
>
>复制分发时，将删除所有日程安排设置。除非您计划了新的联系日期，否则一旦发送确认，将发送重复的分发。

**相关主题**：

* [优化发送时间](../../sending/using/optimizing-the-sending-time.md)
* [在收件人的时区发送消息](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)
* [计算发送日期](../../sending/using/computing-the-sending-date.md)

