---
title: 管理传入的短信
description: 了解如何在Adobe Campaign中管理停止短信和存储传入短信。
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: delivery,smsContent,back
feature: SMS
role: User
level: Intermediate
exl-id: 86cb6f4c-a5a7-4d9d-bbfd-4a70af38cf3a
source-git-commit: 30d0c2552bea3a7cbd8500be4e8c0c74e5a40a99
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---

# 管理传入的短信{#managing-incoming-sms}

## 管理停止短信 {#managing-stop-sms}

当用户档案回复通过Campaign发送的短信消息时，您可以配置自动发回给用户档案的消息以及要执行的操作。

此配置在 **[!UICONTROL Automatic reply sent to the MO]** 部分 [短信路由外部帐户](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing). MO表示“移动设备源”，这意味着您可以配置对发送短信的移动设备的自动回复。

为实现此操作，请执行以下步骤：

1. 从高级菜单中，通过Adobe Campaign徽标，选择 **[!UICONTROL Administration > Application settings > External accounts]** 然后 **[!UICONTROL SMS routing via SMPP]** 外部帐户。
1. 在 **[!UICONTROL Automatic reply sent to the MO]** 类别，单击 **[!UICONTROL Create element]** 开始配置自动回复。

   ![](assets/sms_mo_1.png)

1. 选择将触发此自动回复的关键词。 关键词不区分大小写。 例如，在此处，如果收件人发送关键词“STOP”，他们将收到自动回复。

   如果不管关键词是什么，要发送相同的回复，请将此列留空。

   >[!IMPORTANT]
   >
   >仅授权字母数字字符。

   ![](assets/sms_mo_2.png)

1. 在 **[!UICONTROL Short code]** 字段中，指定通常用于发送投放的数字，并将用作发件人名称。 您还可以决定离开 **[!UICONTROL Short code]** 列为空，以发送相同的回复，而不管是什么短代码。

   ![](assets/sms_mo_4.png)

1. 在字段中键入要发送给收件人的答案 **[!UICONTROL Reply]**.

   要在不发送回复的情况下执行操作，请将 **[!UICONTROL Reply]** 列为空。 例如，这允许您从隔离中删除回复了“STOP”以外消息的用户的电话号码。

   ![](assets/sms_mo_3.png)

1. 在 **[!UICONTROL Additional action]** 字段中，将操作链接到自动回复：

   * 的 **[!UICONTROL Send to quarantine]** 操作会自动隔离用户档案的电话号码。
   * 的 **[!UICONTROL Remove from quarantine]** 操作会将用户档案电话号码从隔离中删除。
   * 的 **[!UICONTROL None]** 通过操作，您只能向收件人发送消息，而无需执行操作。

   例如，在以下配置中，如果收件人发送关键词“STOP”，他们将自动收到退订确认函，其电话号码将随 **[!UICONTROL On denylist]** 状态。 此状态仅指电话号码，其用户档案是为了允许用户继续接收电子邮件。

   ![](assets/sms_mo.png)

1. 单击 **[!UICONTROL Save]**。

1. 从 **[!UICONTROL Advanced parameters]** 短信投放 **[!UICONTROL Properties]**，则可以设置 **[!UICONTROL Short code]** 以自动排除选择退出的收件人。 有关此内容的详细信息，请参阅 [此部分](../../administration/using/configuring-sms-channel.md#configuring-sms-properties).

现在，您的收件人可自动退订您的邮件，并通过此自动回复发送到隔离。 隔离的收件人列在 **[!UICONTROL Addresses]** 表可通过 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** 菜单。 有关隔离的更多信息，请参阅此 [部分](../../sending/using/understanding-quarantine-management.md).

如果需要，可以存储这些传入的短信。 有关此内容的更多信息，请参阅此内容 [部分](#storing-incoming-sms).

## 存储传入短信 {#storing-incoming-sms}

在 **[!UICONTROL SMS routing via SMPP]** 外部帐户中，您可以选择存储传入消息（例如，当订阅者回复“STOP”短信消息时），以便从收件人列表中删除。

![](assets/sms_config_mo_1.png)

通过检查 **[!UICONTROL Store incoming MO in the database]** 在 **[!UICONTROL SMPP channel settings]** 类别中，所有短信都将存储在inSMS表中，并可通过工作流中的查询活动进行检索。

为实现此操作，请执行以下步骤：

1. 在 **[!UICONTROL SMPP channel settings]** 字段，勾选 **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. 在 **[!UICONTROL Marketing activities]** ，单击 **[!UICONTROL Create]** 然后选择 **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. 选择您的工作流类型。
1. 编辑工作流的属性，然后单击 **[!UICONTROL Create]**. 有关创建工作流的更多信息，请参阅此 [部分](../../automating/using/building-a-workflow.md).
1. 拖放 **[!UICONTROL Query]** 活动时，双击该活动。
1. 在 **[!UICONTROL Properties]** ，选择 **[!UICONTROL Incoming SMS (inSMS)]** 在 **[!UICONTROL Resource]** 字段。

   ![](assets/sms_config_mo_4.png)

1. 然后，在 **[!UICONTROL Target]** ，拖放 **[!UICONTROL Incoming SMS attributes]** 规则。

   ![](assets/sms_config_mo_5.png)

1. 在此，我们希望定位前一天开始的每个传入消息。 在 **[!UICONTROL Field]** 类别，选择 **[!UICONTROL Creation date (created)]**.
1. 在 **[!UICONTROL Filter type]**，选择 **[!UICONTROL Relative]** 然后 **[!UICONTROL Level of precision]**，选择 **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. 然后，您可以选择从今天、前一天或最近几天检索数据。 单击 **[!UICONTROL Confirm]** 配置查询时。

此查询将根据所选的时间范围检索收到的每条STOP消息。

例如，利用活动可构建群体，并更好地个性化投放。
