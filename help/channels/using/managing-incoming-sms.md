---
solution: Campaign Standard
product: campaign
title: 管理传入的短信
description: 了解如何在Adobe Campaign中管理STOP SMS和存储传入的SMS。
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 7%

---


# 管理传入的短信{#managing-incoming-sms}

## 管理停止SMS {#managing-stop-sms}

当某个用户档案回复通过 Campaign 发送的短信消息时，您可以配置自动发回给他的消息以及要自动执行的操作。

此配置在[SMS路由外部帐户](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)的&#x200B;**[!UICONTROL Automatic reply sent to the MO]**&#x200B;部分中定义。 MO代表“Mobile Suriced”，这意味着您可以配置对发送短信的移动设备的自动回复。

为实现此操作，请执行以下步骤：

1. 从高级菜单中，通过Adobe Campaign标志，选择&#x200B;**[!UICONTROL Administration > Application settings > External accounts]**，然后选择&#x200B;**[!UICONTROL SMS routing via SMPP]**&#x200B;外部帐户。
1. 在&#x200B;**[!UICONTROL Automatic reply sent to the MO]**&#x200B;类别下，单击&#x200B;**[!UICONTROL Create element]**&#x200B;以开始配置自动回复。

   ![](assets/sms_mo_1.png)

1. 选择将触发此自动回复的关键字。 关键字不区分大小写。 例如，此处，如果收件人发送关键字“STOP”，则他们将收到自动回复。

   如果要发送相同的回复，无论关键字是什么，请将此列留空。

   ![](assets/sms_mo_2.png)

1. 在&#x200B;**[!UICONTROL Short code]**&#x200B;字段中，指定一个通常用于发送投放并用作发件人姓名的编号。 您还可以决定将&#x200B;**[!UICONTROL Short code]**&#x200B;列留空，以发送相同的回复，而不管是什么短代码。

   ![](assets/sms_mo_4.png)

1. 在字段&#x200B;**[!UICONTROL Reply]**&#x200B;中键入要发送给收件人的答案。

   要执行操作而不发送回复，请将&#x200B;**[!UICONTROL Reply]**&#x200B;列留空。 例如，这允许您从隔离中删除回复了“STOP”以外消息的用户的电话号码。

   ![](assets/sms_mo_3.png)

1. 在&#x200B;**[!UICONTROL Additional action]**&#x200B;字段中，将操作链接到您的自动回复：

   * **[!UICONTROL Send to quarantine]**&#x200B;动作会自动隔离用户档案电话号码。
   * **[!UICONTROL Remove from quarantine]**&#x200B;操作将从用户档案中删除隔离电话号码。
   * **[!UICONTROL None]**&#x200B;操作允许您仅向收件人发送消息，而不执行操作。

   例如，在以下配置中，如果收件人发送关键字“STOP”，他们将自动收到退订确认，其电话号码将发送到状态为&#x200B;**[!UICONTROL On denylist]**&#x200B;的隔离。 此状态仅指电话号码，用户档案是这样用户继续接收电子邮件。

   ![](assets/sms_mo.png)

您的收件人现在可以自动取消订阅您的消息，并通过此自动回复发送给隔离。 隔离的收件人列在&#x200B;**[!UICONTROL Addresses]**&#x200B;表中，可通过&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]**&#x200B;菜单访问。 有关隔离的详细信息，请参阅此[部分](../../sending/using/understanding-quarantine-management.md)。

如果需要，可以存储这些传入的SMS。 有关此内容的详细信息，请参阅此[部分](#storing-incoming-sms)。

## 存储传入的SMS {#storing-incoming-sms}

在&#x200B;**[!UICONTROL SMS routing via SMPP]**&#x200B;外部帐户中，您可以选择存储传入消息，例如当订阅者回复SMS消息“STOP”以便从您的收件人列表中删除时。

![](assets/sms_config_mo_1.png)

通过检查&#x200B;**[!UICONTROL SMPP channel settings]**&#x200B;类别中的&#x200B;**[!UICONTROL Store incoming MO in the database]**，所有SMS都将存储在inSMS表中，并可以通过工作流中的查询活动进行检索。

为实现此操作，请执行以下步骤：

1. 在&#x200B;**[!UICONTROL SMPP channel settings]**&#x200B;字段中，选中&#x200B;**[!UICONTROL Store incoming MO in the database]**。

   ![](assets/sms_config_mo_2.png)

1. 在&#x200B;**[!UICONTROL Marketing activities]**&#x200B;选项卡中，单击&#x200B;**[!UICONTROL Create]**，然后选择&#x200B;**[!UICONTROL Workflow]**。

   ![](assets/sms_config_mo_3.png)

1. 选择您的工作流类型。
1. 编辑工作流的属性，然后单击&#x200B;**[!UICONTROL Create]**。 有关创建工作流的详细信息，请参阅此[部分](../../automating/using/building-a-workflow.md)。
1. 拖放&#x200B;**[!UICONTROL Query]**&#x200B;活动，然后多次单击活动。
1. 在查询的&#x200B;**[!UICONTROL Properties]**&#x200B;选项卡中，在&#x200B;**[!UICONTROL Resource]**&#x200B;字段中选择&#x200B;**[!UICONTROL Incoming SMS (inSMS)]**。

   ![](assets/sms_config_mo_4.png)

1. 然后，在&#x200B;**[!UICONTROL Target]**&#x200B;选项卡中，拖放&#x200B;**[!UICONTROL Incoming SMS attributes]**&#x200B;规则。

   ![](assets/sms_config_mo_5.png)

1. 在此，我们希望目标前一天收到的每一条消息。 在&#x200B;**[!UICONTROL Field]**&#x200B;类别中，选择&#x200B;**[!UICONTROL Creation date (created)]**。
1. 在&#x200B;**[!UICONTROL Filter type]**&#x200B;中，选择&#x200B;**[!UICONTROL Relative]**，然后在&#x200B;**[!UICONTROL Level of precision]**&#x200B;中选择&#x200B;**[!UICONTROL Day]**。

   ![](assets/sms_config_mo_6.png)

1. 然后，您可以选择从今天、前一天或最近几天检索数据。 配置查询后，单击&#x200B;**[!UICONTROL Confirm]**。

此查询将根据所选时间范围检索收到的每条STOP消息。

例如，该活动使您能够建立人口，并更好地个性化您的投放。
