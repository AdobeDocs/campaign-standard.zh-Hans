---
title: 优化发送时间
description: 了解如何设置发送时间并提高消息的打开率。
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Send Time Optimization
role: User
level: Intermediate
exl-id: f35b46c6-de88-4efa-b3b7-8bb9024e40a8
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 100%

---

# 优化发送时间{#optimizing-the-sending-time}

要提高消息的打开率，您可以手动定义针对每个收件人的发送时间。只要有可能，每个用户档案都将在指定的日期和时间收到消息。

定义发送时间可以在投放级别完成，也可使用工作流完成。

对于电子邮件，将根据服务器负载和重试数量，尽量按每个收件人预定的日期和时间发送消息。

* 重试情况依赖于互联网提供商和您的声誉。第一次尝试时收件人可能不会接受该消息，可能需要执行多次重试。请参阅[电子邮件渠道参数的列表](../../administration/using/configuring-email-channel.md)。
* 如果带宽不足，可能会延迟收到电子邮件。

您可以在[发送日志](../../sending/using/monitoring-a-delivery.md#sending-logs)中查看消息何时发送到每个收件人。

提供了以下几个选项：

* **[!UICONTROL No optimization]**：以用户的时间发送消息。

   例如，如果您的时区是 GMT+1，并且如果您在 **[!UICONTROL Start sending from]** 字段中输入了“9:00 AM”，则位于 GMT+3 时区的收件人将在本地时间上午 11:00 收到该消息。

* **[!UICONTROL Send at the recipient's time zone]**：所有收件人都将收到考虑了当地时区时间的消息。

   例如，如果您在 **[!UICONTROL Start sending from]** 字段中输入了“9:00 AM”，则位于 GMT+3 时区的收件人将在本地时间上午 9:00 收到该消息。

   请参阅[按收件人的时区发送消息](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)。

* **[!UICONTROL Send at a custom date defined by a formula]**：每个收件人都将在使用指定公式配置的日期和时间收到消息。

   请参阅[计算发送日期](../../sending/using/computing-the-sending-date.md)。
