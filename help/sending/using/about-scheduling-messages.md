---
title: 关于计划消息发送
description: 了解如何安排消息。
page-status-flag: 从未激活
uuid: 286fcee-65a9-4cb9-b205-9ce5d024675c
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 发送
content-type: 参考
topic-tags: 调度消息
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: 交付，计划，返回
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 关于计划消息发送{#about-scheduling-messages}

>[!CAUTION]
>
>只要对交付的计划进行更改，您必须在单击确认之前单击准备按钮，以重新准 **备** 交付 ****。

在消息功能板中， **[!UICONTROL Schedule]** 该块允许您定义消息（电子邮件、短信或推送通知）的发送时间。

![](assets/delivery_dashboard.png)

通过 **[!UICONTROL Schedule]** 这些属性，您可以为电子邮件、短信或推送通知设置发送选项：

* **[!UICONTROL Messages to be sent once confirmed]**:消息一经确认即发送。 See [Confirming the send](../../sending/using/confirming-the-send.md).

   ![](assets/delivery_planning_1.png)

* **[!UICONTROL Messages to be sent automatically on the date specified below]**:消息将在以后的日期和时间发送。 在“开始 **发送自** ”字 **段中指定联系日期** 。

   您可以准备并确认发送，但消息将仅从所选日期和时间开始发送。 准备和确认发送在准备发送和确 [认发送部分](../../sending/using/preparing-the-send.md)[中显示](../../sending/using/confirming-the-send.md) 。

   下 **[!UICONTROL Time zone of the contact date]** 拉列表允许您修改发送时间要考虑的时区。 例如，如果您在字段中输入上午9:00，并且如果您在下拉列表中选择布鲁塞尔、哥本哈根、马德里、巴黎(GMT+1)，所有接收方将在巴黎时间上午9:00收到该消息。 **[!UICONTROL Start sending from]****[!UICONTROL Time zone of the contact date]** 因此，位于莫斯科的接收方(GMT+3)将在莫斯科时间上午11:00收到该消息。

   如果要手动确认发送，请选中该选 **[!UICONTROL Request confirmation before sending messages]** 项。 此选项默认处于启用状态。

   ![](assets/delivery_planning.png)

>[!CAUTION]
>
>复制分发时，将删除所有计划设置。 除非您计划新的联系日期，否则在确认发送后，将立即发送重复的发送。

**相关主题**:

* [优化发送时间](../../sending/using/optimizing-the-sending-time.md)
* [按收件人的时区发送消息](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)
* [计算发送日期](../../sending/using/computing-the-sending-date.md)

