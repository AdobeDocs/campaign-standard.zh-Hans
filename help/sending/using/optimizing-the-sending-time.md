---
title: 优化发送时间
seo-title: 优化发送时间
description: 优化发送时间
seo-description: 了解如何设置发送时间并提高消息的打开率。
page-status-flag: 从未激活
uuid: c2c13934-9819-4e18-b5 c7-60915c907 f37
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 发送
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 609355f6-9003-41b9-9981-ea787419 fbf5
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Optimizing the sending time{#optimizing-the-sending-time}

为提高消息的打开率，您可以手动为每个收件人定义发送时间。每个配置文件都将在指定的日期和时间收到消息。

可以在交付级别或使用工作流来定义发送时间。

对于电子邮件，根据服务器负载和重试次数，将会尽力在每个收件人的日期和时间上发送消息。

* 重试取决于互联网提供商和您的声誉。在第一次尝试时可能不接受该消息，可能会执行多次重试。See [List of email channel parameters](../../administration/using/configuring-email-channel.md).
* 由于带宽不足，可能会出现接收电子邮件的延迟。

You can view when the message was sent to each recipient in the [sending logs](../../sending/using/monitoring-a-delivery.md#sending-logs).

有若干选项可用：

* **[!UICONTROL No optimization]**：消息会在用户的时间发送。

   For example, if your time zone is GMT+1 and if you enter 9:00 AM in the **[!UICONTROL Start sending from]** field, a recipient located in the GMT+3 time zone will receive the message at 11:00 AM local time for that recipient.

* **[!UICONTROL Send at the recipient's time zone]**：所有收件人将收到与其时区相关的消息。

   For example, if you enter 9:00 AM in the **[!UICONTROL Start sending from]** field, a recipient located in the GMT+3 time zone will receive the message at 9:00 AM local time for that recipient.

   See [Sending messages at the recipient's time zone](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Send at a custom date defined by a formula]**：每个收件人将在指定的公式配置的日期和时间收到消息。

   See [Computing the sending date](../../sending/using/computing-the-sending-date.md).

