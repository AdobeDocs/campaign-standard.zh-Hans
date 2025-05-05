---
title: 了解隔离管理
description: 了解如何通过隔离管理优化投放能力。
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Deliverability
role: User
level: Intermediate
exl-id: ed269751-78ab-4189-89d9-116bf42c0c90
source-git-commit: 449187bba167f9ce00e644d44a124b36030ba001
workflow-type: tm+mt
source-wordcount: '1430'
ht-degree: 22%

---

# 了解隔离管理{#understanding-quarantine-management}

## 关于隔离 {#about-quarantines}

举例来说，当信箱已满或地址不存在时，可以隔离某个电子邮件地址或电话号码。

无论如何，隔离过程都必须遵循[此章节](#conditions-for-sending-an-address-to-quarantine)所述的具体规则。

### 通过隔离优化投放 {#optimizing-your-delivery-through-quarantines}

在准备消息时，电子邮件地址或电话号码处于隔离状态的用户档案会被自动被排除（请参阅[确定投放的隔离地址](#identifying-quarantined-addresses-for-a-delivery)）。这样可加快投放速度，因为错误率对投放速度有显著的影响。

如果无效地址率过高，某些互联网访问提供商会自动将电子邮件判断为垃圾邮件。因此，隔离可让您避免被这些提供商添加到阻止列表。

此外，隔离还可避免向错误的电话号码投放短信，有助于降低短信发送成本。

有关安全防护和优化投放之最佳做法的更多信息，请参阅[此页面](../../sending/using/delivery-best-practices.md)。

### 隔离与阻止列表 {#quarantine-vs-denylist}

隔离和阻止列表不适用于同一对象：

* **隔离**&#x200B;仅应用于&#x200B;**地址**（或电话号码等），不适用于配置文件本身。 例如，其电子邮件地址被隔离的用户档案可以更新其用户档案并输入新地址，然后再次被投放操作定向。 同样，如果两个用户档案碰巧拥有相同的电话号码，那么隔离该号码将会同时影响这两个用户档案。

  隔离的地址或电话号码显示在[排除日志](#identifying-quarantined-addresses-for-a-delivery)（针对投放）或[隔离列表](#identifying-quarantined-addresses-for-the-entire-platform)（针对整个平台）中。

* 另一方面，如果位于&#x200B;**阻止列表**，则会导致&#x200B;**用户档案**&#x200B;不再被投放定位，例如在取消订阅（选择退出）给定渠道后。 例如，如果电子邮件渠道阻止列表上的用户档案有两个电子邮件地址，则这两个地址都将排除在投放之外。 有关阻止列表过程的详细信息，请参阅[关于Campaign中的选择加入和选择退出](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)。

  您可以在配置文件的&#x200B;**[!UICONTROL General]**&#x200B;选项卡的&#x200B;**[!UICONTROL No longer contact (on denylist)]**&#x200B;部分中检查配置文件是否正在阻止列表一个或多个渠道。 请参阅[此小节](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile)。

>[!NOTE]
>
>隔离包括&#x200B;**在阻止列表**&#x200B;状态，当收件人将您的邮件报告为垃圾邮件或回复带有“STOP”之类关键字的短信邮件时，该隔离将适用。 在这种情况下，会将用户档案中涉及的地址或电话号码添加到隔离，并显示&#x200B;**[!UICONTROL On denylist]**&#x200B;状态。 有关管理STOP SMS消息的更多信息，请参阅[此章节](../../channels/using/managing-incoming-sms.md#managing-stop-sms)。

&lt;！ — 当用户回复的短信带有用于选择退出短信投放的STOP之类的关键字时，其用户档案不会添加到电子邮件选择退出流程之类的阻止列表中。 相反，该用户档案的电话号码将以&#x200B;**[!UICONTROL On denylist]**&#x200B;状态添加到隔离。 此状态仅指电话号码，这意味着该用户档案将继续接收电子邮件。<!-- Also, if the profile has another phone number, he can still receive SMS messages on the other number. For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).-->

## 确定隔离的地址 {#identifying-quarantined-addresses}

可以为特定投放或整个平台显示隔离的地址。

<!--
If you need to remove an address from quarantine, contact your technical administrator.
-->

### 确定投放的隔离地址 {#identifying-quarantined-addresses-for-a-delivery}

在投放准备阶段期间，投放仪表板的 **[!UICONTROL Exclusion logs]** 选项卡中会列出特定投放的隔离地址（请参阅[此章节](../../sending/using/monitoring-a-delivery.md#exclusion-logs)）。有关投放准备的更多信息，请参阅[此章节](../../sending/using/preparing-the-send.md)。

![](assets/exclusion_logs.png)

### 确定整个平台的隔离地址 {#identifying-quarantined-addresses-for-the-entire-platform}

管理员可以从&#x200B;**[!UICONTROL Administration > Channels > Quarantines > Addresses]**&#x200B;菜单访问整个平台隔离区中电子邮件地址的详细列表。

<!--
This menu lists quarantined elements for **Email**, **SMS** and **Push notification** channels.
-->

![](assets/quarantines1.png)

>[!NOTE]
>
>隔离数量的增加是正常的，这与数据库的“老化”有关。 例如，如果将电子邮件地址的生命周期视为三年，而收件人表每年增加50%，则隔离的增加可以按如下方式计算：第1年年末：(1&#42;0.33)/(1+0.5)=22%。 第2年年末：((1.22&#42;0.33)+0.33)/(1.5+0.75)=32.5%。

筛选器可帮助您浏览列表。 您可以根据地址、状态和/或渠道进行过滤。

![](assets/quarantines-filters.png)

您可以编辑或[删除](#removing-a-quarantined-address)每个条目，以及创建新条目。

要编辑条目，请单击相应的行并根据需要修改字段。

![](assets/quarantines-edit.png)

要手动添加新条目，请使用&#x200B;**[!UICONTROL Create]**&#x200B;按钮。

![](assets/quarantines-create-button.png)

定义地址（或电话号码等） 和渠道类型。 您可以设置隔离列表中的状态和错误原因。 您还可以指明发生错误的日期、错误数并输入错误文本。 如果需要，请从下拉列表中选择发送到该地址的最后一次投放。

![](assets/quarantines-create-last-delivery.png)

## 从隔离中删除地址 {#removing-a-quarantined-address}

### 自动更新 {#unquarantine-auto}

数据库清理工作流会自动从隔离列表中删除符合特定条件的地址。 了解有关技术工作流的详细信息，请参阅[此部分](../../administration/using/technical-workflows.md#list-of-technical-workflows)。

在以下情况下，地址会自动从隔离列表中删除：

* 成功投放后，将从隔离列表中删除处于&#x200B;**[!UICONTROL Erroneous]**&#x200B;状态的地址。
* 如果最后一次软退回发生在10天之前，则会从隔离列表中删除处于&#x200B;**[!UICONTROL Erroneous]**&#x200B;状态的地址。 有关软错误管理的详细信息，请参阅[此部分](#soft-error-management)。
* 状态为&#x200B;**[!UICONTROL Erroneous]**&#x200B;且出现&#x200B;**[!UICONTROL Mailbox full]**&#x200B;错误退回的地址将在30天后从隔离列表中删除。

其状态随后更改为&#x200B;**[!UICONTROL Valid]**。

在&#x200B;**[!UICONTROL Erroneous]**&#x200B;状态时执行的最大重试次数和重试之间的最小延迟现在取决于IP在给定域名的历史和当前表现如何。


>[!IMPORTANT]
>
>不会移除地址处于&#x200B;**[!UICONTROL Quarantine]**&#x200B;或&#x200B;**[!UICONTROL Denylisted]**&#x200B;状态的收件人，即使他们收到电子邮件也是如此。


### 手动更新 {#unquarantine-manual}

您还可以手动取消隔离地址。  要从隔离列表中手动删除地址，您可以将其从隔离列表中删除或将其状态更改为&#x200B;**[!UICONTROL Valid]**。

* 从&#x200B;**[!UICONTROL Administration > Channels > Quarantines > Addresses]**&#x200B;列表中选择地址并选择&#x200B;**[!UICONTROL Delete element]**。

  ![](assets/quarantine-delete-address.png)

* 选择地址并将其&#x200B;**[!UICONTROL Status]**&#x200B;更改为&#x200B;**[!UICONTROL Valid]**。

  ![](assets/quarantine-valid-status.png)


### 批量更新 {#unquarantine-bulk}

您可能需要对隔离列表执行批量更新，例如，在ISP中断的情况下。 在这种情况下，电子邮件会错误地标记为跳出，因为它们无法成功传递给收件人。 必须从隔离列表中删除这些地址。

要执行此操作，请创建工作流并在隔离表上添加&#x200B;**[!UICONTROL Query]**&#x200B;活动以过滤掉所有受影响的收件人。 确定后，可以从隔离列表中删除它们，并将其包含在将来的Campaign电子邮件投放中。

根据事件的时间范围，以下是此查询的建议准则。

* **错误文本（隔离文本）**&#x200B;包含“550-5.1.1”且&#x200B;**错误文本（隔离文本）**&#x200B;包含“support.ISP.com”

  其中“support.ISP.com”可以是：例如“support.apple.com”或“support.google.com”

* **更新状态(@lastModified)**&#x200B;在`MM/DD/YYYY HH:MM:SS AM`或之后
* **在`MM/DD/YYYY HH:MM:SS PM`或之前更新状态(@lastModified)**

获得受影响的收件人列表后，添加&#x200B;**[!UICONTROL Update data]**&#x200B;活动以将其电子邮件地址状态设置为&#x200B;**[!UICONTROL Valid]**，以便&#x200B;**[!UICONTROL Database cleanup]**&#x200B;工作流将其从隔离列表中删除。 也可以直接从隔离表中删除它们。

## 将地址添加到隔离的条件 {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign 可根据投放失败类型和在错误消息鉴别过程中分配的原因管理隔离（请参阅[投放失败类型和原因](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)以及[退回邮件鉴别](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)）。

* **已忽略的错误**：已忽略的错误不会将地址添加到隔离。
* **硬错误**：相应的电子邮件地址会立即添加到隔离。
* **软错误**：软错误不会立即将地址添加到隔离，但会增加错误计数。有关此内容的详细信息，请参阅[软错误管理](#soft-error-management)。

  <!--
  When the error counter reaches the limit threshold, the address goes into quarantine. In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error. The error counter threshold can be modified. For more on this, refer to this [page](../../administration/using/configuring-email-channel.md#email-channel-parameters).
  When a delivery is successful after a retry, the error counter of the address which was prior to that quarantined is reinitialized. The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.
  -->

如果用户将电子邮件标记为垃圾邮件（[反馈循环](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops)），则该邮件会自动重定向到由Adobe管理的技术邮箱。 随后，该用户的电子邮件地址会自动添加到隔离，并附加 **[!UICONTROL On denylist]** 状态。此状态仅适用于地址，用户档案不在阻止列表上，因此用户可继续接收短信和推送通知。

>[!NOTE]
>
>Adobe Campaign 中的隔离会区分大小写字母。请确保以小写方式导入电子邮件地址，这样以后就不会重新定向这些地址。

隔离地址列表（请参阅[确定整个平台的隔离地址](#identifying-quarantined-addresses-for-the-entire-platform)）中的&#x200B;**[!UICONTROL Error reason]** 字段，说明了将选定地址置于隔离状态的原因。

![](assets/quarantines2.png)

### 软错误管理 {#soft-error-management}

与硬错误相反，软错误不会立即将地址添加到隔离，而是会增加错误计数。

将在[投放持续时间](../../administration/using/configuring-email-channel.md#validity-period-parameters)期间执行重试。 当错误计数达到限制阈值时，即会将地址添加到隔离。有关详细信息，请参阅投放临时失败后[重试](understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)。

<!--In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error.
The error counter threshold can be modified.-->

如果最后一次重大错误发生在10天之前，则重新初始化错误计数器。 然后，地址状态更改为&#x200B;**有效**，并由&#x200B;**数据库清理**&#x200B;工作流从隔离列表中将其删除。 （有关技术工作流的详细信息，请参阅[此部分](../../administration/using/technical-workflows.md#list-of-technical-workflows)。）
