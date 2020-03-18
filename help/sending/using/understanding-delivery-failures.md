---
title: 了解投放失败
description: 了解如何使用Campaign管理交付失败。
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
source-git-commit: 3be170b5e1560e0b48db02de4eeb5ea96b794b04

---


# 了解投放失败{#understanding-delivery-failures}

## 关于交付失败 {#about-delivery-failures}

当分发无法发送到配置文件时，远程服务器会自动发送一条错误消息，该消息由Adobe Campaign平台选取并有资格确定是否应隔离电子邮件地址或电话号码。 请参阅 [弹回邮件资格](#bounce-mail-qualification)。

>[!NOTE]
>
>**电子邮件** （或“弹回”）错误消息由inMail进程限定。 **MTA进程** （或“状态报告”的“SR”）符合SMS错误消息的条件。

如果地址被隔离或配置文件被列入黑名单，则还可以在准备传送期间排除消息。 排除的消息列在交付功 **[!UICONTROL Exclusion logs]** 能板的选项卡中(请参 [阅此部分](../../sending/using/monitoring-a-delivery.md#exclusion-logs))。

![](assets/exclusion_logs.png)

**相关主题：**

* [了解隔离管理](../../sending/using/understanding-quarantine-management.md)
* [管理Campaign中的黑名单](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## 识别消息的传送失败 {#identifying-delivery-failures-for-a-message}

发送交货后，选项卡(请参 **[!UICONTROL Sending logs]** 阅本节 [](../../sending/using/monitoring-a-delivery.md#sending-logs))允许您查看每个配置文件的交货状态以及关联的失败类型和原因(请参阅交 [货失败类型和原因](#delivery-failure-types-and-reasons))。

![](assets/sending_logs.png)

此外，还提供专门的现成报告。 此报告详细描述了在提交过程中遇到的总体硬错误和软错误以及弹回的自动处理。 如需详细信息，请参阅[此部分](../../reporting/using/bounce-summary.md)。

## 交付失败类型和原因 {#delivery-failure-types-and-reasons}

交付失败时有三种类型的错误：

* **硬**:“硬”错误表示地址无效。 这涉及一条错误消息，明确声明地址无效，例如：“未知用户”。
* **软**:这可能是一个临时错误，或者是无法分类的错误，例如：“无效域”或“邮箱已满”。
* **忽略**:这是一个已知为临时错误（如“办公室外”）或技术错误（例如，如果发送者类型为“postmaster”）。

交付失败的可能原因包括：

* **[!UICONTROL User unknown]** （硬类型）:地址不存在。 不会尝试对此配置文件进行进一步提交。
* **[!UICONTROL Quarantined address]** （硬类型）:地址被隔离了。
* **[!UICONTROL Unreachable]** （软／硬类型）:消息传送链中发生错误（SMTP中继上发生事件，域暂时无法访问等）。 根据提供商返回的错误，地址将直接发送到隔离，或者在Campaign收到将隔离状态证明为合理的错误或错误数量达到5之前，将再次尝试传送。
* **[!UICONTROL Address empty]** （硬类型）:地址未定义。
* **[!UICONTROL Mailbox full]** （可变类型）:此用户的邮箱已满，无法接受更多消息。 可以从隔离列表中删除此地址以再次尝试。 30天后自动删除。

   In order for the address to be automatically removed from the list of quarantined addresses, the **[!UICONTROL Database cleanup]** technical workflow must be started.

* **[!UICONTROL Refused]** （软／硬类型）:由于安全反馈作为垃圾邮件报告，该地址已被置于隔离状态。 根据提供商返回的错误，地址将直接发送到隔离，或者在Campaign收到将隔离状态证明为合理的错误或错误数量达到5之前，将再次尝试传送。
* **[!UICONTROL Duplicate]**:分段中已检测到地址。
* **[!UICONTROL Not defined]** （可变类型）:该地址符合条件，因为错误尚未递增。

   当服务器发送新的错误消息时，会发生此类错误：这可能是一个孤立的错误，但如果再次发生，错误计数器会增加，这将提醒技术团队。

* **[!UICONTROL Error ignored]**:该地址在白名单中，无论如何，都会向其发送电子邮件。
* **[!UICONTROL Blacklisted address]**:地址在发送时被列入黑名单。
* **[!UICONTROL Account disabled]** （软／硬类型）:当Internet访问提供商(IAP)检测到长时间的不活动时，它可以关闭用户帐户：然后，将无法将内容发送到用户地址。 “软”或“硬”类型取决于收到的错误类型：如果帐户因为6个月的不活动而暂时禁用，并且仍可激活，则将分配状 **[!UICONTROL Erroneous]** 态并重新尝试传送。 如果收到错误信号表明帐户已永久停用，则该帐户将直接发送到隔离。
* **[!UICONTROL Not connected]**:在发送消息时，配置文件的移动电话关闭或未连接到网络。
* **[!UICONTROL Invalid domain]** （可变类型）:电子邮件地址的域不正确或不再存在。 此配置文件将再次定位，直到错误计数达到5。 此后，记录将设置为“隔离”状态，之后不会重试。
* **[!UICONTROL Text too long]**:SMS消息中的字符数超出限制。 有关详细信息，请参 [阅SMS编码、长度和音译](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)。
* **[!UICONTROL Character not supported by encoding]**:sms消息包含一个或多个编码不支持的字符。 有关详细信息，请参 [阅字符表-GSM标准版](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard)。

## 交付临时失败后重试 {#retries-after-a-delivery-temporary-failure}

如果消息因“已忽略”类型的临时错误而失 **败** ，则将在交付期间执行重试。 有关错误类型的详细信息，请参阅 [交付失败类型和原因](#delivery-failure-types-and-reasons)。

要修改传送的持续时间，请转至传送或传送模板的高级参数，然后在相应字段中指定所需的持续时间。 本节将介绍高级交付 [属性](../../administration/using/configuring-email-channel.md#validity-period-parameters)。

默认配置允许在一小时间隔内重试五次，然后在四天内每天重试一次。 可以全局更改重试次数（与Adobe技术管理员联系），也可以更改每个交付或交付模板的重试次数(请参 [阅此部分](../../administration/using/configuring-email-channel.md#sending-parameters))。

## 同步和异步错误 {#synchronous-and-asynchronous-errors}

发送后可立即失败（同步错误），或稍后失败（异步错误）。

* **同步错误**:由Adobe Campaign交付服务器联系的远程服务器会立即返回一条错误消息，不允许将分发发送到配置文件的服务器。
* **异步错误**:接收服务器稍后会重新发送弹回邮件或SR。 异步错误最多可能发生到发送交付后的一周。

## 退回邮件资格 {#bounce-mail-qualification}

<!--Delivery failure error messages (or "SMTP bounce responses") are picked up by the Adobe Campaign platform and then processed and qualified as **Hard**, **Soft**, or **Ignored** using the **[!UICONTROL Delivery log qualification]** database.

//Delivery failure error messages (or "bounces") are picked up by the Adobe Campaign platform and qualified by the inMail process to enrich the list of email management rules.(applies to asynchronous (out-of-band) bounces)

This list is available to administrators only and contains all the rules used by Adobe Campaign to qualify delivery failures.-->

>[!IMPORTANT]
>
>升级到增强的MTA后，“营销活动”表格中的弹 **[!UICONTROL Message qualification]** 出资格便不再被使用。

对于同步交付失败错误消息，增强的MTA可确定退回类型和资格，并将该信息发回到Campaign。 有关Adobe Campaign增强型MTA的详细信息，请参阅本 [文档](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)。

inMail进程仍可通过规则对异步弹回进行 **[!UICONTROL Inbound email]** 限定。 要访问这些规则，请单 **[!UICONTROL Adobe Campaign]** 击左上角的标志，然后选择并 **[!UICONTROL Administration > Channels > Email > Email processing rules]** 选择 **[!UICONTROL Bounce mails]**。 For more on this rule, refer to this [section](../../administration/using/configuring-email-channel.md#email-processing-rules).

<!--Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## 使用双选择加入机制优化邮件发送能力 {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

双选择加入机制是发送电子邮件的最佳实践。 它可以保护平台免受错误或无效电子邮件地址、垃圾邮件程序的攻击，并防止可能的垃圾邮件投诉。

其原则是先发送电子邮件确认访客的协议，然后再将其作为“配置文件”存储到您的Campaign数据库中：访客填写在线登录页面，然后收到电子邮件，必须单击确认链接才能完成订阅。

如需详细信息，请参阅[此部分](../../channels/using/setting-up-a-double-opt-in-process.md)。
