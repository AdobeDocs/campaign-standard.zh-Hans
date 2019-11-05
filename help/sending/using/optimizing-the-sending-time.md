---
title: 优化发送时间
description: 了解如何设置发送时间和提高消息的打开率。
page-status-flag: 从未激活
uuid: c2c13934-9819-4e18-b5c7-60915c907f37
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 发送
content-type: 参考
topic-tags: 调度消息
discoiquuid: 609355f6-9003-41b9-9981-ea787419fbf5
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 优化发送时间{#optimizing-the-sending-time}

要提高消息的打开率，您可以手动定义每个收件人的发送时间。 每个配置文件都会在指定的日期和时间收到消息（如果可能）。

可以在交付级别或使用工作流来定义发送时间。

对于电子邮件，根据服务器负载和重试次数，将尽力在为每个收件人预定的日期和时间发送消息。

* 重试次数取决于Internet提供商和您的声誉。 在第一次尝试时可能不接受该消息，并且可以执行多次重试。 请参 [阅电子邮件渠道参数列表](../../administration/using/configuring-email-channel.md)。
* 由于带宽不足，可能会导致接收电子邮件的延迟。

您可以查看发送日志中消息发送给每个收件人 [的时间](../../sending/using/monitoring-a-delivery.md#sending-logs)。

有以下几个选项可用：

* **[!UICONTROL No optimization]**:消息在用户的时间发送。

   例如，如果您的时区是GMT+1，并且如果您在字段中输入上午9:00，则位于 **[!UICONTROL Start sending from]** GMT+3时区的收件人将在当地时间上午11:00收到该收件人的消息。

* **[!UICONTROL Send at the recipient's time zone]**:所有收件人都将收到邮件，并将其时区考虑在内。

   例如，如果您在字段中输入上午9:00，则位于 **[!UICONTROL Start sending from]** GMT+3时区的收件人将在当地时间上午9:00收到该收件人的消息。

   See [Sending messages at the recipient's time zone](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Send at a custom date defined by a formula]**:每个收件人将在指定公式配置的日期和时间收到消息。

   See [Computing the sending date](../../sending/using/computing-the-sending-date.md).

