---
title: 了解隔离管理
description: 了解如何通过隔离管理优化您的可交付性。
page-status-flag: never-activated
uuid: 3c287865-1ada-4351-b205-51807ff9f7ed
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: de3a50b6-ea8f-4521-996b-c49cc1f3c946
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7e361d10d039718c421a3684c518347af2be951

---


# 了解隔离管理{#understanding-quarantine-management}

## 关于检疫 {#about-quarantines}

可以隔离电子邮件地址或电话号码，例如，当邮箱已满或地址不存在时。

无论如何，隔离程序都符合本条所述的特定规 [则](#conditions-for-sending-an-address-to-quarantine)。

### 通过隔离优化您的交付 {#optimizing-your-delivery-through-quarantines}

邮件准备过程中，将自动排除其电子邮件地址或电话号码处于隔离状态的配置文件(请参阅 [识别传送的隔离地址](#identifying-quarantined-addresses-for-a-delivery))。 这将加快交付速度，因为错误率对交付速度有显着影响。

如果无效地址的速率太高，某些Internet访问提供商会自动将电子邮件视为垃圾邮件。 因此，隔离功能可以避免这些提供商的黑名单。

此外，隔离可以排除发送错误的电话号码，从而帮助降低短信发送成本。

有关保护和优化交付的最佳实践的更多信息，请参阅 [本页](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html)。

### 隔离与黑名单 {#quarantine-vs-blacklisting}

**隔离** (Quarantine)仅适用于地址，而不适用于配置文件本身。 这意味着，如果两个配置文件具有相同的电子邮件地址，则在地址被隔离时，这两个配置文件都会受到影响。

同样，其电子邮件地址被隔离的配置文件也可以更新其配置文件并输入新地址，然后可以通过提交操作再次定位。

**另一方面**，黑名单将导致任何分发不再瞄准配置文件，例如在取消订阅（选择退出）后。 有关黑名单流程的详细信息，请参阅在 [Campaign中管理黑名单](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)。

>[!NOTE]
>
>当用户用诸如“STOP”的关键字回复SMS消息以选择退出SMS分发时，其个人资料不会像在电子邮件选择退出过程中那样被列入黑名单。 配置文件电话号码将发送到具有状态的隔 **[!UICONTROL Blacklisted]** 离区。 此状态仅指电话号码，配置文件未列入黑名单，因此用户将继续接收电子邮件。 如需详细信息，请参阅[此部分](../../channels/using/managing-incoming-sms.md#managing-stop-sms)。

## 识别隔离地址 {#identifying-quarantined-addresses}

可以为特定交付或整个平台列出隔离的地址。

>[!NOTE]
>
>如果需要从隔离中删除地址，请与技术管理员联系。

### 识别传送的隔离地址 {#identifying-quarantined-addresses-for-a-delivery}

特定传送的隔离地址在传送准备阶段的传送控制板的选 **[!UICONTROL Exclusion logs]** 项卡中列出(请参 [阅此部分](../../sending/using/monitoring-a-delivery.md#exclusion-logs))。 For more on delivery preparation, refer to [this section](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### 识别整个平台的隔离地址 {#identifying-quarantined-addresses-for-the-entire-platform}

管理员可以从菜单中列出隔离整个平台的地 **[!UICONTROL Administration > Channels > Quarantines > Addresses]** 址。

>[!NOTE]
>
>此菜单列出了电子邮件、 **SMS和推送通**&#x200B;知渠道 **的隔** 离元素 **** 。

![](assets/quarantines1.png)

>[!NOTE]
>
>检疫数量的增加是正常的，与数据库的“磨损”有关。 例如，如果电子邮件地址的有效期被认为是三年，而收件人表每年增加50%，那么隔离的增加可以计算如下：年末1:(1*0.33)/(1+0.5)=22%。 年末2:((1.22*0.33)+0.33)/(1.5+0.75)=32.5%。

## 发送地址到隔离的条件 {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign根据在错误消息资格期间分配的传送失败类型和原因管理隔离(请参阅传送失败类 [型和原因](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) ，以及弹 [回邮件资格](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification))。

* **忽略的错误**:忽略的错误不会发送地址进行隔离。
* **硬错误**:相应的电子邮件地址会立即发送到隔离区。
* **软错误**:软错误不会立即发送要隔离的地址，但会增加一个错误计数器。 当错误计数器达到限制阈值时，地址将进入隔离。 在默认配置中，阈值设置为5个错误，其中，如果两个错误间隔至少24小时，则它们会显着。 地址在第五个错误时被隔离。 可以修改错误计数器阈值。 For more on this, refer to this [page](../../administration/using/configuring-email-channel.md#email-channel-parameters).

   当重试后传送成功时，重新初始化隔离之前的地址的错误计数器。 地址状态将变 **[!UICONTROL Valid]** 为，并在工作流两天后从隔离列表中删除 **[!UICONTROL Database cleanup]** 它。

如果用户将电子邮件归为垃圾邮件(**反馈循环**)，则该邮件会自动重定向到由Campaign管理的技术邮箱。 随后，用户的电子邮件地址会自动发送到具有状态的隔 **[!UICONTROL Blacklisted]** 离区。 此状态仅指地址，配置文件未列入黑名单，因此用户可继续接收SMS消息和推送通知。

>[!NOTE]
Adobe Campaign中的隔离区区分大小写。 确保以小写形式导入电子邮件地址，以便以后不会重新定位。

在隔离地址列表(请参阅 [识别整个平台的隔离地址](#identifying-quarantined-addresses-for-the-entire-platform))中，字段 **[!UICONTROL Error reason]** 指示将选定地址置于隔离中的原因。

![](assets/quarantines2.png)

