---
title: 了解投放失败
description: 了解如何使用投放管理活动故障。
page-status-flag: never-activated
uuid: 2735aa05-7b6f-47c9-98c4-a15cc33be39d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: 38452841-4cd4-4f92-a5c3-1dfdd54ff6f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c1287a360cdd1750996b47a27b85a11e90b29df0

---


# 了解投放失败{#understanding-delivery-failures}

## 关于投放故障 {#about-delivery-failures}

当投放无法发送到用户档案时，远程服务器会自动发送一条错误消息，该错误消息由Adobe Campaign平台选取并且有资格确定是否应隔离电子邮件地址或电话号码。 请参阅 [弹回邮件资格](#bounce-mail-qualification)。

>[!NOTE]
>
>**电子邮件** （或“弹回”）错误消息由增强的MTA（同步弹回）或inMail进程（异步弹回）限定。
>
>**MTA进程** （或“状态报告”的“SR”）符合SMS错误消息的条件。

如果地址被隔离或投放已列入黑名单，则还可以在准备用户档案期间排除消息。 排除的消息列在投放 **[!UICONTROL Exclusion logs]** 仪表板的选项卡中(请参 [阅本节](../../sending/using/monitoring-a-delivery.md#exclusion-logs))。

![](assets/exclusion_logs.png)

**相关主题：**

* [了解隔离管理](../../sending/using/understanding-quarantine-management.md)
* [管理活动中的黑名单](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## 识别消息的投放故障 {#identifying-delivery-failures-for-a-message}

发送投放后，选项卡(请参 **[!UICONTROL Sending logs]** 阅本节 [](../../sending/using/monitoring-a-delivery.md#sending-logs))允许您视图每个用户档案的投放状态以及关联的故障类型和原因(请参阅 [投放失败类型和原因](#delivery-failure-types-and-reasons))。

![](assets/sending_logs.png)

此外，还提供专门的现成报告。 此报告详细描述了在投放过程中遇到的整体硬错误和软错误以及弹回的自动处理。 如需详细信息，请参阅[此部分](../../reporting/using/bounce-summary.md)。

## 投放故障类型和原因 {#delivery-failure-types-and-reasons}

投放失败时有三种错误：

* **硬**:“硬”错误表示地址无效。 这涉及一条错误消息，明确声明地址无效，例如：“未知用户”。
* **软**:这可能是一个临时错误，或者是无法分类的错误，例如：“无效域”或“邮箱已满”。
* **忽略**:这是一个已知为临时错误（如“办公室外”）或技术错误（例如，如果发送者类型为“postmaster”）。

投放失败的可能原因有：

* **[!UICONTROL User unknown]** （硬类型）:地址不存在。 本用户档案不会进一步投放。
* **[!UICONTROL Quarantined address]** （硬类型）:地址在隔离。
* **[!UICONTROL Unreachable]** （软／硬类型）:消息投放链中发生错误(如域临时不可到达)。 根据提供者返回的错误，地址将直接发送给隔离，或者投放将再次尝试，直到活动收到错误，该错误使隔离状态正确，或直到错误数达到5。
* **[!UICONTROL Address empty]** （硬类型）:地址未定义。
* **[!UICONTROL Mailbox full]** （可变类型）:此用户的邮箱已满，无法接受更多消息。 可以从隔离列表中删除此地址以再次尝试。 30天后自动删除。

   In order for the address to be automatically removed from the list of quarantined addresses, the **[!UICONTROL Database cleanup]** technical workflow must be started.

* **[!UICONTROL Refused]** （软／硬类型）:由于安全反馈作为垃圾邮件报告而将地址置于隔离中。 根据提供者返回的错误，地址将直接发送给隔离，或者投放将再次尝试，直到活动收到错误，该错误使隔离状态正确，或直到错误数达到5。
* **[!UICONTROL Duplicate]**:分段中已检测到地址。
* **[!UICONTROL Not defined]** （可变类型）:该地址符合条件，因为错误尚未递增。

   当服务器发送新的错误消息时，会发生此类错误：这可能是一个孤立的错误，但如果再次发生，错误计数器会增加，这将提醒技术团队。

* **[!UICONTROL Error ignored]**:该地址在白名单中，无论如何，都会向其发送电子邮件。
* **[!UICONTROL Blacklisted address]**:发送时地址已列入黑名单。
* **[!UICONTROL Account disabled]** （软／硬类型）:当Internet访问提供商(IAP)检测到长时间的不活动时，它可以关闭用户帐户：投放用户的地址将不可能。 “软”或“硬”类型取决于收到的错误类型：如果帐户因为六个月的非活动状态而暂时禁用，并且仍可激活，则将分配状 **[!UICONTROL Erroneous]** 态并重新尝试投放。 如果收到错误信号表明帐户已永久停用，则会直接将其发送到隔离。
* **[!UICONTROL Not connected]**:用户档案的移动电话在发送消息时关闭或未连接到网络。
* **[!UICONTROL Invalid domain]** （可变类型）:电子邮件地址的域不正确或不再存在。 此用户档案将再次定位，直到错误计数达到5。 之后，记录将设置为隔离状态，之后将不再重试。
* **[!UICONTROL Text too long]**:SMS消息中的字符数超出限制。 有关详细信息，请参 [阅SMS编码、长度和音译](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)。
* **[!UICONTROL Character not supported by encoding]**:sms消息包含一个或多个编码不支持的字符。 有关详细信息，请参 [阅字符表-GSM标准版](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard)。

## 重试在投放临时故障后 {#retries-after-a-delivery-temporary-failure}

如果消息因“已忽略”类型的临时错误 **而失败** ，则将在投放持续期间执行重试。 有关错误类型的详细信息，请参阅 [投放失败类型和原因](#delivery-failure-types-and-reasons)。

重试的数量(在发送开始后一天应执行多少重试)和重试之间的最小延迟现在由Adobe Campaign增强MTA管理，这取决于IP在历史和当前给定域的表现情况。 忽略 **重试** (在活动中)的设置。

要修改投放的持续时间，请转到投放或投放模板的高级参数，并编辑“有效性” **[!UICONTROL Delivery duration]** 时段部分 [的字段](../../administration/using/configuring-email-channel.md#validity-period-parameters) 。

>[!IMPORTANT]
>
>**现&#x200B;**[!UICONTROL Delivery duration]**在，只有在设置为3.5天或更少时，才会使用活动投放中的参数。** 如果定义的值高于3.5天，则不会将其考虑在内，因为它现在由Adobe Campaign增强MTA管理。

例如，如果希望投放的重试在一天后停止，您可以将投放持续时间设置为 **1d**，增强的MTA将通过删除一天后重试队列中的消息来执行该设置。

>[!NOTE]
>
>消息在增强的MTA队列中处于3.5天并且无法传送后，将超时，其状态将从 **[!UICONTROL Sent]** 投放日志 **[!UICONTROL Failed]** 更新 [](../../sending/using/monitoring-a-delivery.md#delivery-logs)。

<!--The default configuration allows five retries at one-hour intervals, followed by one retry per day for four days. The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).-->

## 同步和异步错误 {#synchronous-and-asynchronous-errors}

投放在发送后可能立即失败（同步错误），或稍后失败（异步错误）。

* **同步错误**:由Adobe Campaign投放服务器联系的远程服务器立即返回一条错误消息，不允许将投放发送到用户档案服务器。
* **异步错误**:接收服务器稍后会重新发送弹回邮件或SR。 异步错误最多可能发生到发送投放后的一周。

## 退回邮件资格 {#bounce-mail-qualification}

对于同步投放故障错误消息，增强的MTA确定弹出类型和资格，并将该信息发回给活动。

inMail进程仍可通过规则对异步弹回进行 **[!UICONTROL Inbound email]** 限定。 要访问这些规则，请单 **[!UICONTROL Adobe Campaign]** 击左上角的标志，然后选择并 **[!UICONTROL Administration > Channels > Email > Email processing rules]** 选择 **[!UICONTROL Bounce mails]**。 For more on this rule, refer to this [section](../../administration/using/configuring-email-channel.md#email-processing-rules).

>[!NOTE]
>
>现在，弹回邮件资格由Adobe Campaign增强MTA管理。 不再使用活动表中 **[!UICONTROL Message qualification]** 的弹出资格。

<!--Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## 使用多次选择加入机制优化邮件发送能力 {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

多次选择加入机制是发送电子邮件的最佳实践。 它可以保护平台免受错误或无效电子邮件地址、垃圾邮件程序的攻击，并防止可能的垃圾邮件投诉。

其原则是，在将访客作为“用户档案”存储到活动数据库中之前，先发送电子邮件确认协议：该访客填写在线登陆页，然后收到电子邮件，并必须单击确认链接才能最终确定其订阅。

如需详细信息，请参阅[此部分](../../channels/using/setting-up-a-double-opt-in-process.md)。
