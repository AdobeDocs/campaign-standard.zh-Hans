---
title: 了解投放失败
description: 了解如何通过投放管理活动故障。
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
source-git-commit: d05d2692607117e056c360e81d85b7d64c4077a3
workflow-type: tm+mt
source-wordcount: '1279'
ht-degree: 1%

---


# 了解投放失败{#understanding-delivery-failures}

## 关于投放失败 {#about-delivery-failures}

当投放无法发送到用户档案时，远程服务器会自动发送错误消息，该消息由Adobe Campaign平台拾取，并且有资格确定是否应隔离电子邮件地址或电话号码。 请参阅 [弹回邮件资格](#bounce-mail-qualification)。

>[!NOTE]
>
>**电子邮件** 错误消息（或“弹回”）由增强的MTA（同步弹回）或inMail进程（异步弹回）限定。
>
>**MTA进** 程会对SMS错误消息（或“状态报告”的“SR”）进行限定。

如果地址被隔离或投放已列入黑名单，也可以在用户档案准备过程中排除邮件。 排除的消息列在投放 **[!UICONTROL Exclusion logs]** 仪表板的选项卡中(请参 [阅本节](../../sending/using/monitoring-a-delivery.md#exclusion-logs))。

![](assets/exclusion_logs.png)

**相关主题：**

* [了解隔离管理](../../sending/using/understanding-quarantine-management.md)
* [管理活动中的黑名单](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## 识别消息的投放失败 {#identifying-delivery-failures-for-a-message}

发送投放后，选项卡 **[!UICONTROL Sending logs]** (请参 [阅本节](../../sending/using/monitoring-a-delivery.md#sending-logs))允许您视图每个用户档案的投放状态以及关联的故障类型和原因(请参阅 [投放故障类型和原因](#delivery-failure-types-and-reasons))。

![](assets/sending_logs.png)

此外，还提供专门的现成报告。 此报告详细描述了在投放期间遇到的整体硬错误和软错误以及弹回的自动处理。 如需详细信息，请参阅[此部分](../../reporting/using/bounce-summary.md)。

## 投放故障类型和原因 {#delivery-failure-types-and-reasons}

投放失败时有三种错误：

* **硬**: “硬”错误表示地址无效。 这涉及显式声明地址无效的错误消息，如： “未知用户”。
* **软**: 这可能是临时错误，或者无法分类的错误，例如： “无效域”或“邮箱已满”。
* **已忽略**: 这是一个已知为临时的错误，如“办公室外”，或是一个技术错误，例如，如果发送者类型为“邮递员”。

投放失败的可能原因有：

| 错误标签 | 错误类型 | 说明 |
---------|----------|---------
| **[!UICONTROL User unknown]** | 硬 | 地址不存在。 不再尝试对此用户档案进行投放。 |
| **[!UICONTROL Quarantined address]** | 硬 | 地址已置于隔离。 |
| **[!UICONTROL Unreachable]** | 软／硬 | 消息投放链中发生错误(如域临时不可到达)。 根据提供者返回的错误，地址将直接发送给隔离，或者在活动收到错误证明隔离状态正确或错误数达到5之前再次尝试投放。 |
| **[!UICONTROL Address empty]** | 硬 | 地址未定义。 |
| **[!UICONTROL Mailbox full]** | 柔和 | 此用户的邮箱已满，无法接受更多邮件。 可以从隔离列表中删除此地址，以再次尝试。 30天后自动删除。 In order for the address to be automatically removed from the list of quarantined addresses, the **[!UICONTROL Database cleanup]** technical workflow must be started. |
| **[!UICONTROL Refused]** | 软／硬 | 由于作为垃圾邮件报告的安全反馈，该地址已置于隔离中。 根据提供者返回的错误，地址将直接发送给隔离，或者在活动收到错误证明隔离状态正确或错误数达到5之前再次尝试投放。 |
| **[!UICONTROL Duplicate]** | 已忽略 | 分段中已检测到地址。 |
| **[!UICONTROL Not defined]** | 柔和 | 地址已被限定，因为错误尚未递增。 当服务器发送新的错误消息时，会发生此类错误： 这可能是一个孤立的错误，但如果再次发生，错误计数器会增加，这将提醒技术团队。 |
| **[!UICONTROL Error ignored]** | 已忽略 | 地址在白名单中，无论如何，都会向其发送电子邮件。 |
| **[!UICONTROL Blacklisted address]** | 硬 | 发送时地址已列入黑名单。 |
| **[!UICONTROL Account disabled]** | 软／硬 | 当Internet访问提供商(IAP)检测到长时间的非活动时，它可以关闭用户帐户： 投放到用户地址将不可能。 “软”或“硬”类型取决于收到的错误类型： 如果帐户因为6个月的非活动而暂时禁用，并且仍可激活，则将分配状 **[!UICONTROL Erroneous]** 态并重试投放。 如果收到错误信号表明帐户已永久停用，则帐户将直接发送给隔离。 |
| **[!UICONTROL Not connected]** | 已忽略 | 发送消息时，用户档案的移动电话关闭或未连接到网络。 |
| **[!UICONTROL Invalid domain]** | 柔和 | 电子邮件地址的域不正确或不再存在。 此用户档案将再次定位，直到错误计数达到5。 此后，记录将设置为隔离状态，并且以后不会重试。 |
| **[!UICONTROL Text too long]** | 已忽略 | SMS消息中的字符数超过限制。 有关此方面的详细信息， [请参阅SMS编码、长度和音译](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)。 |
| **[!UICONTROL Character not supported by encoding]** | 已忽略 | SMS消息包含一个或多个编码不支持的字符。 有关此的详细信息，请参 [阅字符表- GSM标准](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard)。 |

## 重试在投放临时故障后 {#retries-after-a-delivery-temporary-failure}

如果消息因“已忽略”类型的临时错误而 **失败** ，将在投放持续期间执行重试。 有关错误类型的详细信息，请参阅 [投放失败类型和原因](#delivery-failure-types-and-reasons)。

重试的数量(在发送开始后一天应执行多少重试)和重试之间的最小延迟现在由Adobe Campaign增强MTA管理，这取决于IP在历史和当前给定域的执行情况。 忽略 **重试** 中的活动设置。

要修改投放的持续时间，请转至投放或投放模板的高级参数，并编辑“有效 **[!UICONTROL Delivery duration]** 期”部分 [的字段](../../administration/using/configuring-email-channel.md#validity-period-parameters) 。

>[!IMPORTANT]
>
>**现&#x200B;**[!UICONTROL Delivery duration]**在，只有设置为3.5天或更少时，才使用活动投放中的参数。** 如果定义的值高于3.5天，则不会考虑该值，因为它现在由Adobe Campaign增强MTA管理。

例如，如果希望重试在一天后停止投放，可以将投放持续时间设置为 **1d**，增强的MTA将通过删除一天后重试队列中的消息来执行该设置。

>[!NOTE]
>
>消息在增强的MTA队列中处于3.5天并且无法传送后，将超时，其状态将从投放日志 **[!UICONTROL Sent]** 更 **[!UICONTROL Failed]** 新为 [](../../sending/using/monitoring-a-delivery.md#delivery-logs)。

<!--The default configuration allows five retries at one-hour intervals, followed by one retry per day for four days. The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).-->

## 同步和异步错误 {#synchronous-and-asynchronous-errors}

投放在发送后可能立即失败（同步错误），或稍后失败（异步错误）。

* **同步错误**: 由Adobe Campaign投放服务器联系的远程服务器立即返回错误消息，不允许将投放发送到用户档案服务器。
* **异步错误**: 接收服务器稍后会重新发送弹回邮件或SR。 异步错误最长可能发生到发送投放后的一周。

## 退回邮件资格 {#bounce-mail-qualification}

对于同步投放故障错误消息，增强的MTA将确定退回类型和资格，并将该信息发回给活动。

inMail进程仍通过规则对异步弹回进行 **[!UICONTROL Inbound email]** 限定。 要访问这些规则，请单 **[!UICONTROL Adobe Campaign]** 击左上角的标志，然后选择 **[!UICONTROL Administration > Channels > Email > Email processing rules]** 并选择 **[!UICONTROL Bounce mails]**。 For more on this rule, refer to this [section](../../administration/using/configuring-email-channel.md#email-processing-rules).

>[!NOTE]
>
>现在，弹回邮件资格由Adobe Campaign增强MTA管理。 不再使用活动表 **[!UICONTROL Message qualification]** 中的退回资格。

<!--Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## 使用多次选择加入机制优化邮件发送能力 {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

多次选择加入机制是发送电子邮件的最佳实践。 它可保护平台免遭错误或无效的电子邮件地址、垃圾邮件程序，并防止可能的垃圾邮件投诉。

其原则是，在将访客作为“用户档案”存储到活动数据库中之前，先发送一封电子邮件，确认其协议： 访客填写在线登陆页，然后收到电子邮件，并必须单击确认链接才能最终确定订阅。

如需详细信息，请参阅[此部分](../../channels/using/setting-up-a-double-opt-in-process.md)。
