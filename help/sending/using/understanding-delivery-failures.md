---
title: 了解投放失败
description: 了解如何通过 Campaign 管理投放失败。
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Deliverability
role: User
level: Intermediate
exl-id: 92a83400-447a-4d23-b05c-0ea013042ffa
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '1281'
ht-degree: 59%

---

# 了解投放失败{#understanding-delivery-failures}

## 关于投放失败 {#about-delivery-failures}

当投放无法发送到轮廓时，远程服务器会自动发送错误消息，该消息会被 Adobe Campaign 平台拾取并进行鉴别，从而确定是否应隔离电子邮件地址或电话号码。请参阅[退回电子邮件鉴定](#bounce-mail-qualification)。

>[!NOTE]
>
>**电子邮件**&#x200B;错误消息（或“退件”）由 Enhanced MTA（同步退回）或 inMail 进程（异步退回）进行鉴别。
>
>**短信**&#x200B;错误消息（或“状态报告”的“SR”）由 MTA 进行鉴别。

列入阻止列表如果地址被隔离或用户档案处于状态，也可以在投放准备期间排除消息。 排除的消息列在投放仪表板的 **[!UICONTROL Exclusion logs]** 选项卡中（请参 阅[此章节](../../sending/using/monitoring-a-delivery.md#exclusion-logs)）。

![](assets/exclusion_logs.png)

**相关主题：**

* [了解隔离管理](../../sending/using/understanding-quarantine-management.md)
* [关于 Campaign 中的选择启用和选择禁用](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
* [退回](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#metrics-for-deliverability)

## 识别消息的投放失败 {#identifying-delivery-failures-for-a-message}

发送投放后，利用 **[!UICONTROL Sending logs]** 选项卡（请[ 阅此章节](../../sending/using/monitoring-a-delivery.md#sending-logs)），可查看每个轮廓的投放状态以及相关失败的类型和原因（请参阅[投放失败类型和原因](#delivery-failure-types-and-reasons)）。

![](assets/sending_logs.png)

此外，还提供了专门的现成报告。该报告会详细描述在投放期间遇到的整体硬错误和软错误，以及退回的自动处理。有关更多信息，请参阅[此章节](../../reporting/using/bounce-summary.md)。

## 投放失败类型和原因 {#delivery-failure-types-and-reasons}

投放的失败，可能是因为三种类型的错误：

* **Hard**：“Hard”错误表示地址无效。这涉及显式声明地址无效的错误消息，如：“未知用户”。
* **Soft**：这可能是临时错误，或者无法分类的错误，例如：“域名无效”或“邮箱已满”。
* **Ignored**：这是一个已知的临时错误，如“不在办公室”，或是一个技术错误，例如，如果发件人类型为“邮递员”。

投放失败可能的原因有：

| 错误标签 | 错误类型 | 说明 |
| ---------|----------|---------|
| **[!UICONTROL User unknown]** | 硬 | 地址不存在。 不再尝试对该轮廓进行投放。 |
| **[!UICONTROL Quarantined address]** | 硬 | 地址被隔离。 |
| **[!UICONTROL Unreachable]** | 软/硬 | 消息投放链中发生错误（例如域名暂时不可访问）。 根据提供商返回的错误，地址将直接被隔离或重试投放，直到 Campaign 收到错误证明处于隔离状态或错误数达到 5 次为止。 |
| **[!UICONTROL Address empty]** | 硬 | 地址未定义。 |
| **[!UICONTROL Mailbox full]** | 柔光 | 此用户的邮箱已满，无法接收更多邮件。 可以从隔离列表中删除此地址，以再次尝试。30天后自动将其删除。 要将地址自动从隔离地址列表中移除，必须启动 **[!UICONTROL Database cleanup]** 技术工作流。 |
| **[!UICONTROL Refused]** | 软/硬 | 由于安全反馈为垃圾邮件报告，该地址已被隔离。 根据提供商返回的错误，地址将直接被隔离或重试投放，直到 Campaign 收到错误证明处于隔离状态或错误数达到 5 次为止。 |
| **[!UICONTROL Duplicate]** | 已忽略 | 分段中已检测到地址。 |
| **[!UICONTROL Not defined]** | 柔光 | 地址正在进行鉴别，因为错误数尚未递增。 当服务器发送新的错误消息时，会发生此类错误： 这可能是一个孤立的错误，但如果再次发生，则错误计数会增加，从而提醒技术团队。 |
| **[!UICONTROL Error ignored]** | 已忽略 | 该地址允许列表，无论如何，都会向其发送电子邮件。 |
| **[!UICONTROL Address on denylist]** | 硬 | 发送时地址已添加到阻止列表。 |
| **[!UICONTROL Account disabled]** | 软/硬 | 当互联网访问提供商(IAP)检测到长时间不活动时，它可以关闭用户的帐户：之后将无法投放到用户的地址。 “Soft”或“Hard”类型取决于收到的错误类型：如果帐户因 6 个月不活动而被暂时禁用，且仍可激活，则将分配 **[!UICONTROL Erroneous]** 状态并重试投放。如果收到错误信号表明该帐户已永久停用，则会将该帐户直接隔离。 |
| **[!UICONTROL Not connected]** | 已忽略 | 用户档案的手机在发送消息时关闭或未连接到网络。 |
| **[!UICONTROL Invalid domain]** | 柔光 | 电子邮件地址的域不正确或不再存在。 此轮廓将被重新定向，直到错误计数达到 5 为止。此后，该记录将设置为隔离状态，并且以后不会再进行重试。 |
| **[!UICONTROL Text too long]** | 已忽略 | 短信消息中的字符数超过限制。 有关更多信息，请参阅[短信编码、长度和音译](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)。 |
| **[!UICONTROL Character not supported by encoding]** | 已忽略 | 短信消息包含一个或多个编码不支持的字符。 有关更多信息，请参阅[字符表 - GSM 标准](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard)。 |


**相关主题：**
* [硬退回](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#hard-bounces)
* [软退回](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#soft-bounces)

## 投放临时失败后重试 {#retries-after-a-delivery-temporary-failure}

如果消息因临时错误而失败，则在投放持续期间将执行重试。 有关错误类型的更多信息，请参阅[投放失败类型和原因](#delivery-failure-types-and-reasons)。

重试次数（在发送开始后一天内应执行多少次重试）和重试之间的最小延迟现在为<!--managed by the Adobe Campaign Enhanced MTA,-->，这基于IP在给定域名的历史和当前表现而定。 Campaign 中的 **Retries** 设置将被忽略。

<!--Please note that Adobe Campaign Enhanced MTA is not available for the Push channel.-->

要修改投放的持续时间，请转至投放或投放模板的高级参数，并编辑 [Validity period](../../administration/using/configuring-email-channel.md#validity-period-parameters) 部分的 **[!UICONTROL Delivery duration]** 字段。

>[!IMPORTANT]
>
>**现在，Campaign 投放中的&#x200B;**[!UICONTROL Delivery duration]**参数，只能使用不超过 3.5 天的设置。**&#x200B;如果定义的值超过 3.5 天，则不会将其考虑在内。

例如，如果希望重试在一天后停止投放，您可以将投放持续时间设置为&#x200B;**1d**，并且重试队列中的消息在一天后将被删除。

>[!NOTE]
>
>消息在重试队列中最多停留3.5天且投放失败后，该消息将超时，其状态将在<!--from **[!UICONTROL Sent]**-->投放日志&#x200B;**[!UICONTROL Failed]**&#x200B;中更新[至](../../sending/using/monitoring-a-delivery.md#delivery-logs)。

<!--MOVED TO configuring-email-channel.md > LEGACY SETTINGS
The default configuration allows five retries at one-hour intervals, followed by one retry per day for four days. The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).-->

## 同步和异步错误 {#synchronous-and-asynchronous-errors}

投放在发送后可能立即失败（同步错误），或稍后失败（异步错误）。

* **同步错误**：Adobe Campaign 投放服务器联系的远程服务器立即返回错误消息，不允许将投放发送到轮廓服务器。
* **异步错误**：接收服务器会在迟些时间发送退回电子邮件或重新发送 SR。最晚的异步错误，可能发生在发送投放的一周之后。

## 退回邮件鉴别 {#bounce-mail-qualification}

对于同步投放失败错误消息，Adobe Campaign Enhanced MTA（消息传输代理）会确定退回类型并进行鉴别，然后将该信息发回至Campaign。

>[!NOTE]
>
>不再使用 Campaign **[!UICONTROL Message qualification]** 表格中的退回鉴定。

异步退回仍然由 inMail 流程通过 **[!UICONTROL Inbound email]** 规则进行鉴别。要访问这些规则，请单击左上角的&#x200B;**Adobe**&#x200B;徽标，然后选择&#x200B;**[!UICONTROL Administration > Channels > Email > Email processing rules]**&#x200B;并选择&#x200B;**[!UICONTROL Bounce mails]**。 有关此规则的更多信息，请参阅[此部分](../../administration/using/configuring-email-channel.md#email-processing-rules)。

有关退回和各种退回的详细信息，请参阅[此部分](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#metrics-for-deliverability)。

<!--MOVED TO configuring-email-channel.md > LEGACY SETTINGS

Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **Adobe** logo, in the top-left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## 使用双重选择加入机制优化电子邮件投放能力 {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

双重选择加入机制属于发送电子邮件的最佳实践。该功能可保护平台，避免错误或无效的电子邮件地址、防护垃圾邮件程序，并防止可能的垃圾邮件投诉。

其原理是，在将访客作为“用户档案”存储到Campaign数据库中之前，先向访客发送一封电子邮件以确认其协议：访客填写在线登陆页面，然后会收到一封电子邮件，并必须单击其中的确认链接才能最终确定订阅。

有关更多信息，请参阅[此小节](../../channels/using/setting-up-a-double-opt-in-process.md)。
