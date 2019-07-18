---
title: 了解隔离管理
seo-title: 了解隔离管理
description: 了解隔离管理
seo-description: 了解如何通过隔离管理优化您的交付能力。
page-status-flag: 从未激活
uuid: 3c287865-1a-4351-b205-51807ff9 f7 ex
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 发送
content-type: reference
topic-tags: 监视消息
discoiquuid: de3a50b6-ea8 f-4521-996b-c49 cc1 f3 c946
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 5b3ea982f08e1198e8c88f78a5faf8a80b935db4

---


# Understanding quarantine management{#understanding-quarantine-management}

## About quarantines {#about-quarantines}

电子邮件地址或电话号码可以隔离，例如，当邮箱已满或地址不存在时。

In any case, the quarantine procedure complies with specific rules described in this [section](../../sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).

### Optimizing your delivery through quarantines {#optimizing-your-delivery-through-quarantines}

The profiles whose email addresses or phone number are in quarantine are automatically excluded during message preparation (see [Identifying quarantined addresses for a delivery](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-a-delivery)). 这将加快交付速度，因为错误率对交付速度有显著影响。

如果无效地址的速率太高，某些Internet访问提供商会自动将电子邮件视为垃圾邮件。因此，隔离允许您避免这些提供者列入黑名单。

此外，Quartic还可以通过排除发送的错误电话号码来帮助降低SMS发送成本。

For more on best practices to secure and optimize your deliveries, refer to [this page](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).

### Quarantine vs blacklisting {#quarantine-vs-blacklisting}

**隔离** 仅应用于地址，而不适用于配置文件本身。这意味着如果两个配置文件具有相同的电子邮件地址，则如果地址被隔离，它们会受到影响。

同样，其电子邮件地址被隔离的配置文件可以更新其配置文件并输入新地址，然后可以再次通过交付操作定位。

**另一方面，黑名单**&#x200B;将导致配置文件不再被任何交付定位，例如在取消订阅后(选择退出)。For more on the blacklisting process, refer to [Managing blacklisting in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!NOTE]
>
>当用户回复含有关键字(如“停止”)的SMS消息以便退出SMS交付时，其配置文件不会在电子邮件选择退出过程中列入黑名单。The profile phone number is sent to quarantine with the **[!UICONTROL Blacklisted]** status. 此状态仅引用电话号码，配置文件未列入黑名单，因此用户继续接收电子邮件。For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

## Identifying quarantined addresses {#identifying-quarantined-addresses}

可以为特定的交付或整个平台列出隔离的地址。

>[!NOTE]
>
>如果您需要从隔离中删除地址，请与技术管理员联系。

### Identifying quarantined addresses for a delivery {#identifying-quarantined-addresses-for-a-delivery}

Quarantined addresses for a specific delivery are listed during the delivery preparation phase, in the **[!UICONTROL Exclusion logs]** tab of the delivery dashboard (see [this section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). For more on delivery preparation, refer to [this section](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### Identifying quarantined addresses for the entire platform {#identifying-quarantined-addresses-for-the-entire-platform}

Administrators can list the addresses in quarantine for the entire platform from the **[!UICONTROL Administration > Channels > Quarantines > Addresses]** menu.

>[!NOTE]
>
>This menu lists quarantined elements for **email**, **SMS** and **Push notification** channels.

![](assets/quarantines1.png)

>[!NOTE]
>
>夸克数量的增加是一种正常效果，与数据库的“磨损”和“撕裂”有关。例如，如果电子邮件地址的有效期被视为三年，而收件人表格每年增加50%，则可以按以下方式计算Quarticion的数量：第一年结束：(1*0.33)/(+0.5)=22%。第二年末：(1.22*0.33)+0.33)/(1.5+0.75)=32.3%。

## Conditions for sending an address to quarantine {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign manages quarantine according to the delivery failure type and the reason assigned during error messages qualification (see [Delivery failure types and reasons](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) and [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)).

* **忽略的错误**：忽略的错误不发送要隔离的地址。
* **硬错误**：相应的电子邮件地址会立即发送到隔离。
* **柔和错误**：软错误不会立即发送地址进行隔离，但会增加错误计数器。当错误计数器达到限制阈值时，地址将进入隔离状态。在默认配置中，阈值设置为五个错误，如果两个错误发生至少24小时，则两个错误很明显。地址在第六个错误处被放置在隔离中。可以修改错误计数器阈值。For more on this, refer to this [page](../../administration/using/configuring-email-channel.md#email-channel-parameters).

   如果在重试后交付成功，则重新初始化该隔离之前的地址的错误计数器。The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.

If a user qualifies an email as a spam (**Feedback loop**), the message is automatically redirected towards a technical mailbox managed by Campaign. The user's email address is then automatically sent to quarantine with the **[!UICONTROL Blacklisted]** status. 此状态仅引用地址，配置文件未列入黑名单，因此用户继续接收SMS消息和推送通知。

>[!NOTE]
Adobe Campaign中的隔离区分大小写。确保以小写形式导入电子邮件地址，以便它们以后不会重新定位。

In the list of quarantined addresses (see [Identifying quarantined addresses for the entire platform](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)), the **[!UICONTROL Error reason]** field indicates why the selected address was placed in quarantine.

![](assets/quarantines2.png)

