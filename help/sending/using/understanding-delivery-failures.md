---
title: 了解交付失败
seo-title: 了解交付失败
description: 了解交付失败
seo-description: 了解如何通过Campaign管理交付失败。
page-status-flag: 从未激活
uuid: 2735aa05-7b6f-47c9-98c4-a15 cc33 be39 d
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 发送
content-type: reference
topic-tags: 监视消息
discoiquuid: 38452841-4cd4-4f92-a5 c3-1dfdd54 ff4 f4
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Understanding delivery failures{#understanding-delivery-failures}

## About delivery failures {#about-delivery-failures}

如果无法将分发发送到配置文件，远程服务器会自动发送一条错误消息，该错误消息由Adobe Campaign平台选取，并有资格确定是否应将电子邮件地址或电话号码隔离。See [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

>[!NOTE]
>
>**电子邮件** 错误消息(或“弹回”)由Inmail流程确定。**SMS** 错误消息(或“状态报告”的“SR”)由MTA流程确定。

如果地址被隔离或配置文件列入黑名单，则消息也可以在交付准备过程中排除。Excluded messages are listed in the **[!UICONTROL Exclusion logs]** tab of the delivery dashboard (see [this section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).

![](assets/exclusion_logs.png)

**相关主题：**

* [了解隔离管理](../../sending/using/understanding-quarantine-management.md)
* [管理Campaign中的黑名单](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## Identifying delivery failures for a message {#identifying-delivery-failures-for-a-message}

Once a delivery is sent, the **[!UICONTROL Sending logs]** tab (see [this section](../../sending/using/monitoring-a-delivery.md#sending-logs)) allows you to view the delivery status for each profile and the associated failure type and reason (see [Delivery failure types and reasons](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)).

![](assets/sending_logs.png)

还提供现成的现成报告。此报告详细介绍交付过程中遇到的整体硬错误以及自动处理问题。For more on this, refer to [this section](../../reporting/using/bounce-summary.md).

## Delivery failure types and reasons {#delivery-failure-types-and-reasons}

交付失败时有三种类型的错误：

* **硬**：“硬”错误表示地址无效。This includes a error message that that address is invalid states at the address is invalid，“未知用户”。
* **柔和**：这可能是临时错误或无法分类的错误，例如：“无效域”或“Mailbox完整”。
* **忽略**：这是一个已知为临时的错误，如“退出”或技术错误，例如发送方类型为“postmaster”。

交付失败的可能原因有：

* **[!UICONTROL User unknown]** (硬类型)：地址不存在。本配置文件不会再提供任何其他分发。
* **[!UICONTROL Quarantined address]** (硬类型)：地址被放置在隔离中。
* **[!UICONTROL Unreachable]** (软/硬类型)：消息交付链中出现错误(SMTP传输、域暂时无法恢复等)。根据提供商返回的错误，地址将直接发送到隔离，或者，直到Campaign收到一个错误，该错误会表明“隔离”状态，或直到错误数量达到5。
* **[!UICONTROL Address empty]** (硬类型)：未定义地址。
* **[!UICONTROL Mailbox full]** (柔和类型)：此用户的邮箱已满，不能接受更多消息。此地址可从隔离列表中删除，以进行另一次尝试。30天后将自动删除它。

   In order for the address to be automatically removed from the list of quarantined addresses, the **[!UICONTROL Database cleanup]** technical workflow must be started.

* **[!UICONTROL Refused]** (软/硬类型)：由于安全反馈作为垃圾邮件报告，地址已被隔离。根据提供商返回的错误，地址将直接发送到隔离，或者，直到Campaign收到一个错误，该错误会表明“隔离”状态，或直到错误数量达到5。
* **[!UICONTROL Duplicate]**：已在分段中检测到该地址。
* **[!UICONTROL Not defined]** (柔和类型)：地址之所以符合资格，是因为错误尚未增加。

   服务器发送新的错误消息时会发生此类型的错误：这可能是一个独立的错误，但如果再次发生，错误计数器会增加，这会提醒技术团队。

* **[!UICONTROL Error ignored]**：地址位于白名单中，任何情况下都将向其发送电子邮件。
* **[!UICONTROL Blacklisted address]**：该地址在发送时列入黑名单。
* **[!UICONTROL Account disabled]** (软/硬类型)：当Internet访问提供商(IAP)检测到长时间的不活动时，它可以关闭用户的帐户：随后将无法交付到用户地址。The Soft or Hard type depends upon the type of error received: if the account is temporarily disabled due to six months of inactivity and can still be activated, the status **[!UICONTROL Erroneous]** will be assigned and the delivery will be tried again. 如果收到的错误信号表明帐户被永久停用，则将直接发送到隔离。
* **[!UICONTROL Not connected]**：发送消息时，配置文件的手机会关闭或未连接到网络。
* **[!UICONTROL Invalid domain]** (柔和类型)：电子邮件地址的域不正确或不再存在。在错误计数达到5之前，将再次定位此配置文件。此后，记录将设置为“隔离”状态，不会重试。
* **[!UICONTROL Text too long]**：SMS消息中的字符数超出限制。For more on this, see [SMS encoding, length and transliteration](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).
* **[!UICONTROL Character not supported by encoding]**：SMS消息包含一个或多个不受编码支持的字符。&amp;For more on this, see [Table of characters - GSM Standard](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard).

## Retries after a delivery temporary failure {#retries-after-a-delivery-temporary-failure}

If a message fails due to a temporary error of the **Ignored** type, retries will be performed during the delivery duration. For more on the types of errors, see [Delivery failure types and reasons](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

要修改分发的持续时间，请转到交付或交付模板的高级参数，然后在相应字段中指定所需的持续时间。The advanced delivery properties are presented in [this section](../../administration/using/configuring-email-channel.md#validity-period-parameters).

默认配置允许按小时间隔重试五次，然后在天间隔内重试五天。The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).

## Synchronous and asynchronous errors {#synchronous-and-asynchronous-errors}

发送会在发送(异步错误)后立即失败(同步错误)或稍后出现。

* **同步错误**：由Adobe Campaign交付服务器联系的远程服务器会立即返回一条错误消息，不允许发送将发送到配置文件的服务器。
* **异步错误**：接收服务器稍后恢复弹回邮件或SR。异步错误可能在发送发送后一周内发生。

## Bounce mail qualification {#bounce-mail-qualification}

交付失败的错误消息(或“弹回次数”)由Adobe Campaign平台选取并符合Inmail流程，以丰富电子邮件管理规则的列表。

此列表仅供管理员使用，包含Adobe Campaign使用的所有规则来确定交付失败的条件。

To access it, click the **[!UICONTROL Adobe Campaign]** logo, at the top left, then select **[!UICONTROL Administration > Channels > Email > Email processing rules]**.

For more on this, refer to this [section](../../administration/using/configuring-email-channel.md#email-processing-rules).

退回可具有以下资格状态：

* **[!UICONTROL To qualify]**：退回邮件需要符合资格。必须由适销性团队完成资格，以确保平台交付能力正确。只要不合格，弹出邮件就不会用于丰富电子邮件处理规则的列表。
* **[!UICONTROL Keep]**：退回邮件是合格的，并将由 **更新使用，以与** 现有电子邮件处理规则相比较，并丰富列表。
* **[!UICONTROL Ignore]**：退回邮件是合格的，但不会被 **更新用于提供适销性** 工作流。因此，它不会发送到客户实例。

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)

## Optimizing mail deliverability with double opt-in mechanism {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

在发送电子邮件时，双击机制是最佳实践。它可以保护平台免受错误或无效的电子邮件地址、垃圾邮件的侵害，并防止垃圾邮件投诉。

其原则是发送电子邮件以确认访客协议，然后将其作为“配置文件”存储到Campaign数据库中：访客填写一个在线登录页面，然后收到一封电子邮件，并必须单击确认链接以完成其订阅。

For more on this, refer to [this section](../../channels/using/setting-up-a-double-opt-in-process.md).
