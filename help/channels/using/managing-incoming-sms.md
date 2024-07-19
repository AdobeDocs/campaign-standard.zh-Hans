---
title: 管理传入的短信
description: 了解如何在Adobe Campaign中管理STOP SMS和存储传入的SMS。
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

当某个用户档案回复通过Campaign发送的短信消息时，您可以配置自动发回给他们的消息以及要执行的操作。

此配置在[SMS路由外部帐户](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)的&#x200B;**[!UICONTROL Automatic reply sent to the MO]**&#x200B;部分中定义。 MO表示“发起的移动设备”，这意味着您可以为发送短信的移动设备配置自动回复。

为实现此操作，请执行以下步骤：

1. 从高级菜单中，通过Adobe Campaign徽标，选择&#x200B;**[!UICONTROL Administration > Application settings > External accounts]**，然后选择&#x200B;**[!UICONTROL SMS routing via SMPP]**&#x200B;外部帐户。
1. 在&#x200B;**[!UICONTROL Automatic reply sent to the MO]**&#x200B;类别下，单击&#x200B;**[!UICONTROL Create element]**&#x200B;以开始配置自动回复。

   ![](assets/sms_mo_1.png)

1. 选择将触发此自动回复的关键字。 关键字不区分大小写。 例如，在此处，如果收件人发送关键字“STOP”，他们将收到自动回复。

   如果要发送相同的回复，则无论关键字是什么，请将此列留空。

   >[!IMPORTANT]
   >
   >仅授权字母数字字符。

   ![](assets/sms_mo_2.png)

1. 在&#x200B;**[!UICONTROL Short code]**&#x200B;字段中，指定一个通常用于发送投放并将用作发件人名称的数字。 您还可以决定将&#x200B;**[!UICONTROL Short code]**&#x200B;列留空，以便不论短代码是什么，都发送相同的回复。

   ![](assets/sms_mo_4.png)

1. 在字段&#x200B;**[!UICONTROL Reply]**&#x200B;中键入要发送给收件人的答案。

   要执行操作而不发送回复，请将&#x200B;**[!UICONTROL Reply]**&#x200B;列留空。 例如，这允许您从隔离中删除回复除“STOP”以外的消息的用户的电话号码。

   ![](assets/sms_mo_3.png)

1. 在&#x200B;**[!UICONTROL Additional action]**&#x200B;字段中，将操作链接到您的自动回复：

   * **[!UICONTROL Send to quarantine]**&#x200B;操作会自动隔离配置文件电话号码。
   * **[!UICONTROL Remove from quarantine]**&#x200B;操作将从隔离中删除配置文件电话号码。
   * **[!UICONTROL None]**&#x200B;操作允许您仅将邮件发送给收件人，而不执行操作。

   例如，在下面的配置中，如果收件人发送关键字“STOP”，他们将自动收到退订确认，其电话号码将被添加到隔离区，且状态为&#x200B;**[!UICONTROL On denylist]**。 此状态仅适用于电话号码，其用户档案用于使用户继续接收电子邮件。

   ![](assets/sms_mo.png)

1. 单击 **[!UICONTROL Save]**。

1. 从短信投放&#x200B;**[!UICONTROL Properties]**&#x200B;的&#x200B;**[!UICONTROL Advanced parameters]**&#x200B;中，您可以设置特定的&#x200B;**[!UICONTROL Short code]**&#x200B;以自动排除选择退出的收件人。 有关详情，请参阅[本节](../../administration/using/configuring-sms-channel.md#configuring-sms-properties)。

您的收件人现在可以自动取消订阅您的邮件，并通过此自动回复添加到隔离。 隔离的收件人列在通过&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]**&#x200B;菜单提供的&#x200B;**[!UICONTROL Addresses]**&#x200B;表中。 有关隔离的详细信息，请参阅此[部分](../../sending/using/understanding-quarantine-management.md)。

如果需要，可以存储这些传入的短信。 有关此内容的更多信息，请参阅此[部分](#storing-incoming-sms)。

## 存储传入的短信 {#storing-incoming-sms}

在&#x200B;**[!UICONTROL SMS routing via SMPP]**&#x200B;外部帐户中，您可以选择存储传入消息，例如当订阅者回复“STOP”短信以便从收件人列表中删除时。

![](assets/sms_config_mo_1.png)

通过检查&#x200B;**[!UICONTROL SMPP channel settings]**&#x200B;类别中的&#x200B;**[!UICONTROL Store incoming MO in the database]**，所有短信都将存储在inSMS表格中，并可通过工作流中的查询活动进行检索。

为实现此操作，请执行以下步骤：

1. 在&#x200B;**[!UICONTROL SMPP channel settings]**&#x200B;字段中，选中&#x200B;**[!UICONTROL Store incoming MO in the database]**。

   ![](assets/sms_config_mo_2.png)

1. 在&#x200B;**[!UICONTROL Marketing activities]**&#x200B;选项卡中，单击&#x200B;**[!UICONTROL Create]**，然后选择&#x200B;**[!UICONTROL Workflow]**。

   ![](assets/sms_config_mo_3.png)

1. 选择您的工作流类型。
1. 编辑工作流的属性，然后单击&#x200B;**[!UICONTROL Create]**。 有关创建工作流的详细信息，请参阅此[部分](../../automating/using/building-a-workflow.md)。
1. 拖放&#x200B;**[!UICONTROL Query]**&#x200B;活动并双击该活动。
1. 在查询的&#x200B;**[!UICONTROL Properties]**&#x200B;选项卡中，在&#x200B;**[!UICONTROL Resource]**&#x200B;字段中选择&#x200B;**[!UICONTROL Incoming SMS (inSMS)]**。

   ![](assets/sms_config_mo_4.png)

1. 然后，在&#x200B;**[!UICONTROL Target]**&#x200B;选项卡中，拖放&#x200B;**[!UICONTROL Incoming SMS attributes]**&#x200B;规则。

   ![](assets/sms_config_mo_5.png)

1. 在这里，我们要定位前一天传入的每条消息。 在&#x200B;**[!UICONTROL Field]**&#x200B;类别中选择&#x200B;**[!UICONTROL Creation date (created)]**。
1. 在&#x200B;**[!UICONTROL Filter type]**&#x200B;中，选择&#x200B;**[!UICONTROL Relative]**，然后在&#x200B;**[!UICONTROL Level of precision]**&#x200B;中，选择&#x200B;**[!UICONTROL Day]**。

   ![](assets/sms_config_mo_6.png)

1. 然后，您可以选择从今天、前一天或最近几天检索数据。 配置查询后，单击&#x200B;**[!UICONTROL Confirm]**。

此查询将根据所选的时间范围检索收到的每条STOP消息。

例如，利用活动，可构建群体并更好地个性化投放。
