---
solution: Campaign Standard
product: campaign
title: 了解隔离管理
description: 了解如何通过隔离管理优化投放能力。
audience: sending
content-type: reference
topic-tags: monitoring-messages
translation-type: tm+mt
source-git-commit: ad7322905c69f9575e11efc9d8f68cf909dc425f
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 82%

---


# 了解隔离管理{#understanding-quarantine-management}

## 关于隔离{#about-quarantines}

举例来说，当信箱已满或地址不存在时，可以隔离某个电子邮件地址或电话号码。

无论如何，隔离过程都必须遵循[此章节](#conditions-for-sending-an-address-to-quarantine)所述的具体规则。

### 通过隔离优化投放{#optimizing-your-delivery-through-quarantines}

在准备消息时，电子邮件地址或电话号码处于隔离状态的用户档案会被自动被排除（请参阅[确定投放的隔离地址](#identifying-quarantined-addresses-for-a-delivery)）。这样可加快投放速度，因为错误率对投放速度有显著的影响。

如果无效地址率过高，某些互联网访问提供商会自动将电子邮件判断为垃圾邮件。因此，隔离允许您避免被这阻止列表些提供商添加到。

此外，隔离还可避免向错误的电话号码投放短信，有助于降低短信发送成本。

有关安全防护和优化投放之最佳做法的更多信息，请参阅[此页面](../../sending/using/delivery-best-practices.md)。

### 隔离与阻止列表{#quarantine-vs-denylist}

**隔离**&#x200B;仅适用于地址，而不适用于用户档案本身。这意味着，如果两个用户档案具有相同的电子邮件地址，那么隔离该地址会同时影响这两个用户档案。

同样，其电子邮件地址被隔离的用户档案可以更新其用户档案并输入新地址，然后即可再次被投放操作定向。

Being on the **Denylist**, on the other hand, will result in the profile no longer being targeted by any delivery, for example after an unsubscription (opt-out). 有关过阻止列表程的详细信息，请参阅[关于选择加入和选择退出活动](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)。

>[!NOTE]
>
>当用户用诸如“STOP”的关键字回复SMS消息以从SMS投放中选择退出时，其不像在电子阻止列表邮件选择退出过程中那样处于用户档案状态。 该用户档案的电话号码将添加到隔离区，并标记 **[!UICONTROL On denylist]** 状态。此状态仅指电话号码，用户档案未处于状阻止列表态，以便用户继续接收电子邮件。 有关更多信息，请参阅[此章节](../../channels/using/managing-incoming-sms.md#managing-stop-sms)。

## 确定隔离的地址{#identifying-quarantined-addresses}

可以针对特定投放或整个平台列出隔离的地址。

>[!NOTE]
>
>如果需要从隔离中删除某个地址，请与技术管理员联系。

### 确定投放的隔离地址{#identifying-quarantined-addresses-for-a-delivery}

在投放准备阶段期间，投放仪表板的 **[!UICONTROL Exclusion logs]** 选项卡中会列出特定投放的隔离地址（请参阅[此章节](../../sending/using/monitoring-a-delivery.md#exclusion-logs)）。有关投放准备的更多信息，请参阅[此章节](../../sending/using/preparing-the-send.md)。

![](assets/exclusion_logs.png)

### 确定整个平台的隔离地址{#identifying-quarantined-addresses-for-the-entire-platform}

管理员可以使用 **[!UICONTROL Administration > Channels > Quarantines > Addresses]** 菜单列出整个平台的隔离地址。

>[!NOTE]
>
>此菜单列出了&#x200B;**电子邮件**、**短信**&#x200B;和&#x200B;**推送通知**&#x200B;渠道的隔离元素。

![](assets/quarantines1.png)

>[!NOTE]
>
>隔离数量的增加是正常的，这与数据库的“老化”有关。例如，如果将电子邮件地址的生命周期视为三年，而收件人表每年增加 50%，则隔离的增加可以按如下公式计算：第 1 年年末：(1*0.33)/(1+0.5)=22%。第 2 年年末：((1.22*0.33)+0.33)/(1.5+0.75)=32.5%。

## 将地址加入隔离的条件{#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign 可根据投放失败类型和在错误消息鉴别过程中分配的原因管理隔离（请参阅[投放失败类型和原因](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)以及[退回邮件鉴别](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)）。

* **已忽略的错误**：已忽略的错误不会将地址添加到隔离。
* **硬错误**：相应的电子邮件地址会立即添加到隔离。
* **软错误**：软错误不会立即将地址添加到隔离，但会增加错误计数。当错误计数达到限制阈值时，即会将地址添加到隔离。在默认配置中，阈值被设置为 5 次错误，其中如果两次错误间隔至少 24 小时，则会将其突出显示。在第 5 次出错后，即会将地址添加到隔离。可修改错误计数阈值。有关更多信息，请参见此[页面](../../administration/using/configuring-email-channel.md#email-channel-parameters)。

   如果重试投放成功，则隔离之前的地址错误计数会重新初始化。地址状态将变为 **[!UICONTROL Valid]**，并在完成 **[!UICONTROL Database cleanup]** 工作流两天后从列表中删除该地址。

如果某个用户将电子邮件标记为垃圾邮件（**反馈机制**），则该邮件会自动重定向到由 Campaign 管理的技术邮箱。随后，该用户的电子邮件地址会自动添加到隔离，并附加 **[!UICONTROL On denylist]** 状态。此状态只指地址，用户档案不在阻止列表程序上，因此用户继续接收SMS消息和推送通知。

>[!NOTE]
Adobe Campaign 中的隔离会区分大小写字母。请确保以小写方式导入电子邮件地址，这样以后就不会重新定向这些地址。

隔离地址列表（请参阅[确定整个平台的隔离地址](#identifying-quarantined-addresses-for-the-entire-platform)）中的&#x200B;**[!UICONTROL Error reason]** 字段，说明了将选定地址置于隔离状态的原因。

![](assets/quarantines2.png)

