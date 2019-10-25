---
title: 管理传入的SMS
seo-title: 管理传入的SMS
description: 管理传入的SMS
seo-description: 了解如何在Adobe Campaign中管理停止SMS和存储传入的SMS。
page-status-flag: 从未激活
uuid: f063052b-96ef-41b6-bf1b-4006de73f0b9
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 频道
content-type: 参考
topic-tags: sms消息
discoiquuid: ee1970e6-1ced-46e0-94e6-833768300ee
delivercontext-tags: 交付，sms内容，返回
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# 管理传入的SMS{#managing-incoming-sms}

## 管理停止SMS {#managing-stop-sms}

当个人资料回复通过Campaign发送的SMS消息时，您可以配置自动发回给他的消息以及要执行的操作。

此配置在 **[!UICONTROL Automatic reply sent to the MO]** SMS路由外部帐户的一 [节中定](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)义。 MO代表“手机源”，这意味着您可以配置对发送手机短信的手机的自动回复。

为此，请执行以下操作：

1. 从高级菜单中，通过Adobe Campaign徽标，选择外 **[!UICONTROL Administration > Application settings > External accounts]** 部帐 **[!UICONTROL SMS routing via SMPP]** 户。
1. 在类别 **[!UICONTROL Automatic reply sent to the MO]** 下，单击以 **[!UICONTROL Create element]** 开始配置自动回复。

   ![](assets/sms_mo_1.png)

1. 选择将触发此自动回复的关键字。 关键字不区分大小写。 例如，如果收件人在此处发送关键字“STOP”，则他们将收到自动回复。

   如果要发送相同的回复（无论关键字是什么），请将此列留空。

   ![](assets/sms_mo_2.png)

1. 在字 **[!UICONTROL Short code]** 段中，指定通常用于发送分发的编号，并用作发送者姓名。 您还可以决定将列留空， **[!UICONTROL Short code]** 以发送相同的回复，而不管是什么简短的代码。

   ![](assets/sms_mo_4.png)

1. 在字段中键入要发送给收件人的答案 **[!UICONTROL Reply]**。

   要在不发送回复的情况下执行操作，请将该列留 **[!UICONTROL Reply]** 空。 例如，这允许您从隔离中删除用“STOP”以外的消息回复的用户的电话号码。

   ![](assets/sms_mo_3.png)

1. 在该字 **[!UICONTROL Additional action]** 段中，将操作链接到您的自动回复：

   * 该操 **[!UICONTROL Send to quarantine]** 作会自动隔离配置文件的电话号码。
   * 该操 **[!UICONTROL Remove from quarantine]** 作将从隔离中删除配置文件电话号码。
   * 该 **[!UICONTROL None]** 操作允许您仅向收件人发送消息，而不携带操作。
   例如，在以下配置中，如果收件人发送关键字“STOP”，他们将自动收到取消订阅的确认函，并且其电话号码将以状态发送到隔离 **[!UICONTROL Blacklisted]** 区。 此状态仅指电话号码，配置文件未列入黑名单，因此用户将继续接收电子邮件。

   ![](assets/sms_mo.png)

您的收件人现在可以自动取消订阅您的消息，并通过此自动回复发送到隔离。 隔离的收件人列在通过&gt; **[!UICONTROL Addresses]****[!UICONTROL Administration]** &gt;菜单提供的表 **[!UICONTROL Channels]** 中 **[!UICONTROL Quarantines]** 。 For more information on quarantines, refer to this [section](../../sending/using/understanding-quarantine-management.md).

如果需要，可以存储这些传入的SMS。 For more information on this, refer to this [section](#storing-incoming-sms).

## 存储传入的SMS {#storing-incoming-sms}

在外部 **[!UICONTROL SMS routing via SMPP]** 帐户中，您可以选择存储传入消息，例如当订阅者回复SMS消息的“STOP”时，以便从收件人列表中删除。

![](assets/sms_config_mo_1.png)

通过检 **[!UICONTROL Store incoming MO in the database]** 查类别， **[!UICONTROL SMPP channel settings]** 所有SMS都将存储在inSMS表中，并且可以通过工作流中的查询活动来检索。

为此，请执行以下操作：

1. 在字段 **[!UICONTROL SMPP channel settings]** 中，选中 **[!UICONTROL Store incoming MO in the database]**。

   ![](assets/sms_config_mo_2.png)

1. 在选项卡 **[!UICONTROL Marketing activities]** 中，单击， **[!UICONTROL Create]** 然后选择 **[!UICONTROL Workflow]**。

   ![](assets/sms_config_mo_3.png)

1. 选择您的工作流类型。
1. 编辑工作流的属性，然后单击 **[!UICONTROL Create]**。 For more on workflows creation, refer to this [section](../../automating/using/building-a-workflow.md).
1. 拖放活动 **[!UICONTROL Query]** 并双击该活动。
1. 在查 **[!UICONTROL Properties]** 询的选项卡中，在字 **[!UICONTROL Incoming SMS (inSMS)]** 段中选 **[!UICONTROL Resource]** 择。

   ![](assets/sms_config_mo_4.png)

1. 然后，在选 **[!UICONTROL Target]** 项卡中拖放规 **[!UICONTROL Incoming SMS attributes]** 则。

   ![](assets/sms_config_mo_5.png)

1. 在此，我们希望从前一天开始针对每一条传入的消息。 在类别 **[!UICONTROL Field]** 中，选择 **[!UICONTROL Creation date (created)]**。
1. 在中 **[!UICONTROL Filter type]**，选择 **[!UICONTROL Relative]** 然后在 **[!UICONTROL Level of precision]**&#x200B;中，选择 **[!UICONTROL Day]**。

   ![](assets/sms_config_mo_6.png)

1. 然后，您可以选择从今天、前一天或前几天检索数据。 配 **[!UICONTROL Confirm]** 置查询后单击。

此查询将根据所选的时间范围检索收到的每条STOP消息。

例如，此活动使您能够建立人口并更好地个性化交付。
