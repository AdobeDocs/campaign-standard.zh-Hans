---
title: 了解隔离管理
description: 了解如何通过隔离管理优化交付能力。
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
source-git-commit: 121ec37cef6193d3a7085b6d0296b6a2e7cafa06
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 1%

---


# 了解隔离管理{#understanding-quarantine-management}

## 关于隔离 {#about-quarantines}

可以隔离电子邮件地址或电话号码，例如，当邮箱已满或地址不存在时。

无论如何，隔离过程都符合本条所述的特定规 [则](#conditions-for-sending-an-address-to-quarantine)。

### 通过投放优化您的隔离 {#optimizing-your-delivery-through-quarantines}

在准备邮件时，其电子邮件地址或电话号码处于隔离的用户档案会自动被排除(请 [参阅识别投放的隔离地址](#identifying-quarantined-addresses-for-a-delivery))。 这将加快投放速度，因为错误率对投放速度有显着影响。

如果无效地址的速率过高，某些互联网访问提供商会自动将电子邮件视为垃圾邮件。 因此，隔离允许您避免被这些提供者添加到块列表。

此外，隔离排除来自投放的错误电话号码有助于降低短信发送成本。

有关保护和优化投放的最佳实践的更多信息，请参 [阅本页](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html)。

### 隔离与块列表 {#quarantine-vs-block-list}

**隔离** 仅适用于地址，而不适用于用户档案本身。 这意味着，如果两个用户档案具有相同的电子邮件地址，那么如果地址被隔离，他们都会受到影响。

同样，被隔离电子邮件地址的用户档案可以更新其用户档案并输入新地址，然后可以再次通过投放操作来定位。

另一方 **面**，位于块列表上将导致用户档案不再被任何投放定位，例如，在退订（选择退出）之后。 有关块列表流程的详细信息，请 [参阅关于选择加入和选择退出活动](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)。

>[!NOTE]
>
>当用户用诸如“STOP”的关键字回复SMS消息以选择不接收SMS投放时，其用户档案不会像电子邮件选择退出过程那样添加到块列表中。 用户档案电话号码将发送给具有状态的 **[!UICONTROL On block list]** 隔离。 此状态仅指电话号码，用户档案不在阻止列表中，因此用户继续接收电子邮件。 如需详细信息，请参阅[此部分](../../channels/using/managing-incoming-sms.md#managing-stop-sms)。

## 识别隔离地址 {#identifying-quarantined-addresses}

可以为特定投放或整个平台列出隔离的地址。

>[!NOTE]
>
>如果需要从隔离中删除地址，请与技术管理员联系。

### 识别投放的隔离地址 {#identifying-quarantined-addresses-for-a-delivery}

特定投放的隔离地址在投放准备阶段列在投放 **[!UICONTROL Exclusion logs]** 仪表板的选项卡中(请参 [阅本节](../../sending/using/monitoring-a-delivery.md#exclusion-logs))。 For more on delivery preparation, refer to [this section](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### 识别整个平台的隔离地址 {#identifying-quarantined-addresses-for-the-entire-platform}

管理员可以从菜单中列表整个平台的隔离 **[!UICONTROL Administration > Channels > Quarantines > Addresses]** 地址。

>[!NOTE]
>
>此菜单列表隔离了 **电子邮件**、 **SMS** 和推 **送通知** 渠道的元素。

![](assets/quarantines1.png)

>[!NOTE]
>
>隔离数量的增加是正常的，与数据库的&quot;磨损&quot;有关。 例如，如果将电子邮件地址的使用期视为三年，并且收件人表每年增加50%，则隔离的增加可以按如下方式计算： 年末1: (1*0.33)/(1+0.5)=22%。 年末2: ((1.22*0.33)+0.33)/(1.5+0.75)=32.5%。

## 向隔离发送地址的条件 {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign根据投放故障类型和在错误消息鉴定过程中分配的原因管理隔离(请参 [阅投放故障类型和原因](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)[以及弹回邮件鉴定](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification))。

* **忽略的错误**: 忽略的错误不会向隔离发送地址。
* **硬错误**: 相应的电子邮件地址会立即发送到隔离。
* **软错误**: 软错误不会立即向隔离发送地址，但会增加错误计数器。 当错误计数器达到限制阈值时，地址将进入隔离。 在默认配置中，阈值设置为5个错误，其中，如果两个错误间隔至少24小时，则它们会显着。 地址在第五个错误处置为隔离。 可以修改错误计数器阈值。 For more on this, refer to this [page](../../administration/using/configuring-email-channel.md#email-channel-parameters).

   在重试后投放成功时，重新初始化在隔离之前的地址的错误计数器。 地址状态将变 **[!UICONTROL Valid]** 为，并在工作流两天后从列表中删除该 **[!UICONTROL Database cleanup]** 地址。

如果用户将电子邮件归为垃圾邮件(反&#x200B;**馈循环**)，则该邮件会自动重定向到由活动管理的技术邮箱。 随后，用户的电子邮件地址会自动发送到具有状态的 **[!UICONTROL On block list]** 隔离。 此状态仅指地址，用户档案不在块列表中，因此用户继续接收SMS消息和推送通知。

>[!NOTE]
隔离Adobe Campaign区区分大小写。 请确保以小写方式导入电子邮件地址，以便以后不重新定位这些地址。

在隔离地址列表(请参 [阅识别整个平台的隔离地址](#identifying-quarantined-addresses-for-the-entire-platform))中， **[!UICONTROL Error reason]** 该字段指示将选定地址置于隔离中的原因。

![](assets/quarantines2.png)

