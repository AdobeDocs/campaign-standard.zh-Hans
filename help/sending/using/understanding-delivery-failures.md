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
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '1302'
ht-degree: 64%

---

# 了解投放失败{#understanding-delivery-failures}

## 关于投放失败 {#about-delivery-failures}

当投放无法发送到用户档案时，远程服务器会自动发送错误消息，该消息会被 Adobe Campaign 平台拾取并进行鉴别，从而确定是否应隔离电子邮件地址或电话号码。请参阅[退回邮件鉴别](#bounce-mail-qualification)。

>[!NOTE]
>
>**电子邮件**&#x200B;错误消息（或“退件”）由 Enhanced MTA（同步退回）或 inMail 进程（异步退回）进行鉴别。
>
>**短信**&#x200B;错误消息（或“状态报告”的“SR”）由 MTA 进行鉴别。

如果地址被隔離或設定檔位於封鎖清單上，也可以在傳送準備期間排除訊息。 排除的消息列在投放仪表板的 **[!UICONTROL Exclusion logs]** 选项卡中（请参 阅[此章节](../../sending/using/monitoring-a-delivery.md#exclusion-logs)）。

![](assets/exclusion_logs.png)

**相关主题：**

* [了解隔离管理](../../sending/using/understanding-quarantine-management.md)
* [关于 Campaign 中的选择启用和选择禁用](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
* [退回数](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#metrics-for-deliverability)

## 识别消息的投放失败 {#identifying-delivery-failures-for-a-message}

发送投放后，利用 **[!UICONTROL Sending logs]** 选项卡（请[ 阅此章节](../../sending/using/monitoring-a-delivery.md#sending-logs)），可查看每个用户档案的投放状态以及相关失败的类型和原因（请参阅[投放失败类型和原因](#delivery-failure-types-and-reasons)）。

![](assets/sending_logs.png)

此外，还提供了专门的现成报告。该报告会详细描述在投放期间遇到的整体硬错误和软错误，以及退回的自动处理。有关更多信息，请参阅[此章节](../../reporting/using/bounce-summary.md)。

## 投放失败类型和原因 {#delivery-failure-types-and-reasons}

投放的失败，可能是因为三种类型的错误：

* **Hard**：“Hard”错误表示地址无效。这涉及显式声明地址无效的错误消息，如：“未知用户”。
* **Soft**：这可能是临时错误，或者无法分类的错误，例如：“域名无效”或“邮箱已满”。
* **Ignored**：这是一个已知的临时错误，如“不在办公室”，或是一个技术错误，例如，如果发件人类型为“邮递员”。

投放失败可能的原因有：

| 錯誤標籤 | 錯誤型別 | 说明 |
| ---------|----------|---------|
| **[!UICONTROL User unknown]** | 硬 | 地址不存在。 不再尝试对该用户档案进行投放。 |
| **[!UICONTROL Quarantined address]** | 硬 | 該地址被置於隔離區。 |
| **[!UICONTROL Unreachable]** | 軟/硬 | 訊息傳遞鏈結中發生錯誤（例如暫時無法存取網域）。 根据提供商返回的错误，地址将直接被隔离或重试投放，直到 Campaign 收到错误证明处于隔离状态或错误数达到 5 次为止。 |
| **[!UICONTROL Address empty]** | 硬 | 未定義地址。 |
| **[!UICONTROL Mailbox full]** | 柔和 | 此使用者的信箱已滿，無法接受更多郵件。 可以从隔离列表中删除此地址，以再次尝试。30 天后自动将其从隔离列表中删除。要将地址自动从隔离地址列表中移除，必须启动 **[!UICONTROL Database cleanup]** 技术工作流。 |
| **[!UICONTROL Refused]** | 軟/硬 | 由於安全反饋為垃圾郵件報告，該地址已被置於隔離狀態。 根据提供商返回的错误，地址将直接被隔离或重试投放，直到 Campaign 收到错误证明处于隔离状态或错误数达到 5 次为止。 |
| **[!UICONTROL Duplicate]** | 已忽略 | 區段中已偵測到該位址。 |
| **[!UICONTROL Not defined]** | 柔和 | 位址正在限定中，因為錯誤並未增加。 | 尚未。 当服务器发送新的错误消息时，会发生此类错误： 这可能是一个孤立的错误，但如果再次发生，则错误计数会增加，从而提醒技术团队。 |
| **[!UICONTROL Error ignored]** | 已忽略 | 該地址在允許清單中，無論如何，都會向其傳送電子郵件。 |
| **[!UICONTROL Address on denylist]** | 硬 | 地址已在傳送時新增至封鎖清單。 |
| **[!UICONTROL Account disabled]** | 軟/硬 | 當網際網路存取提供者(IAP)偵測到長時間的不活動時，它可以關閉使用者帳戶：傳送至使用者位址的作業將無法進行。 “Soft”或“Hard”类型取决于收到的错误类型：如果帐户因 6 个月不活动而被暂时禁用，且仍可激活，则将分配 **[!UICONTROL Erroneous]** 状态并重试投放。如果收到错误信号表明该帐户已永久停用，则会将该帐户直接隔离。 |
| **[!UICONTROL Not connected]** | 已忽略 | 當傳送訊息時，設定檔的行動電話已關閉或未連線至網路。 |
| **[!UICONTROL Invalid domain]** | 柔和 | 電子郵件地址的網域不正確或已不存在。 此用户档案将被重新定向，直到错误计数达到 5 为止。此后，该记录将设置为隔离状态，并且以后不会再进行重试。 |
| **[!UICONTROL Text too long]** | 已忽略 | SMS訊息中的字元數超過限制。 有关更多信息，请参阅[短信编码、长度和音译](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)。 |
| **[!UICONTROL Character not supported by encoding]** | 已忽略 | SMS訊息包含一或多個編碼不支援的字元。 有关更多信息，请参阅[字符表 - GSM 标准](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard)。 |


**相关主题：**
* [硬退回](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#hard-bounces)
* [软退回](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#soft-bounces)

## 在投放临时失败后重试 {#retries-after-a-delivery-temporary-failure}

如果訊息因暫時錯誤而失敗，則會在傳送期間執行重試。 有关错误类型的更多信息，请参阅[投放失败类型和原因](#delivery-failure-types-and-reasons)。

重試次數（開始傳送後一天應執行多少次重試）和兩次重試之間的最小延遲現在為<!--managed by the Adobe Campaign Enhanced MTA,--> 根據IP在歷史和目前指定網域的執行狀況。 Campaign 中的 **Retries** 设置将被忽略。

<!--Please note that Adobe Campaign Enhanced MTA is not available for the Push channel.-->

要修改投放的持续时间，请转至投放或投放模板的高级参数，并编辑 [Validity period](../../administration/using/configuring-email-channel.md#validity-period-parameters) 部分的 **[!UICONTROL Delivery duration]** 字段。

>[!IMPORTANT]
>
>**现在，Campaign 投放中的&#x200B;**[!UICONTROL Delivery duration]**参数，只能使用不超过 3.5 天的设置。**&#x200B;如果定义的值超过 3.5 天，则不会将其考虑在内。

例如，如果您希望某個傳送的重試在一天後停止，您可以將傳送持續時間設為 **1天**，則重試佇列中的訊息將於一天後移除。

>[!NOTE]
>
>訊息在重試佇列中最多停留3.5天且傳遞失敗後，訊息將會逾時並且其狀態將會更新<!--from **[!UICONTROL Sent]**--> 至 **[!UICONTROL Failed]** 在 [傳遞記錄](../../sending/using/monitoring-a-delivery.md#delivery-logs).

<!--MOVED TO configuring-email-channel.md > LEGACY SETTINGS
The default configuration allows five retries at one-hour intervals, followed by one retry per day for four days. The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).-->

## 同步和异步错误 {#synchronous-and-asynchronous-errors}

投放在发送后可能立即失败（同步错误），或稍后失败（异步错误）。

* **同步错误**：Adobe Campaign 投放服务器联系的远程服务器立即返回错误消息，不允许将投放发送到用户档案服务器。
* **异步错误**：接收服务器会在迟些时间发送退回邮件或重新发送 SR。最晚的异步错误，可能发生在发送投放的一周之后。

## 退回邮件鉴别 {#bounce-mail-qualification}

對於同步傳送失敗錯誤訊息，Adobe Campaign Enhanced MTA （訊息傳輸代理程式）會決定退信型別和資格，並將該資訊傳回至Campaign。

>[!NOTE]
>
>不再使用 Campaign **[!UICONTROL Message qualification]** 表格中的退回鉴别。

异步退回仍然由 inMail 流程通过 **[!UICONTROL Inbound email]** 规则进行鉴别。若要存取這些規則，請按一下 **Adobe** 標誌，然後選取「 」 **[!UICONTROL Administration > Channels > Email > Email processing rules]** 並選取 **[!UICONTROL Bounce mails]**. 如需此規則的詳細資訊，請參閱 [本節](../../administration/using/configuring-email-channel.md#email-processing-rules).

如需跳出和各種跳出的詳細資訊，請參閱 [本節](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#metrics-for-deliverability).

<!--MOVED TO configuring-email-channel.md > LEGACY SETTINGS

Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **Adobe** logo, in the top-left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## 使用雙重選擇加入機制最佳化電子郵件傳遞能力 {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

双重选择加入机制属于发送电子邮件的最佳实践。该功能可保护平台，避免错误或无效的电子邮件地址、防护垃圾邮件程序，并防止可能的垃圾邮件投诉。

其原理是，在将访客作为“用户档案”存储到 Campaign 数据库中之前，先向访客发送一封电子邮件以确认其协议：访客填写在线登陆页面，然后会收到一封电子邮件，并必须单击其中的确认链接才能最终确定订阅。

有关更多信息，请参阅[此章节](../../channels/using/setting-up-a-double-opt-in-process.md)。
