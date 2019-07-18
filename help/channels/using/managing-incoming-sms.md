---
title: 管理传入的SMS
seo-title: 管理传入的SMS
description: 管理传入的SMS
seo-description: 了解如何在Adobe Campaign中管理停止SMS和存储传入的SMS。
page-status-flag: 从未激活
uuid: f063052b-96ef-41b6-bf1 b-4006de73 f0 b9
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: sms-messages
discoiquuid: ee1970e6-1ed-46e0-94e6-8337768300ee
delivercontext-tags: 交付，SMSContent，返回
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Managing incoming SMS{#managing-incoming-sms}

## Managing STOP SMS {#managing-stop-sms}

当配置文件回复通过Campaign发送的SMS消息时，您可以配置自动发送回他和执行操作的消息。

This configuration is defined in the **[!UICONTROL Automatic reply sent to the MO]** section of the [SMS Routing external account](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing). MO代表“移动发明”，这意味着您可以将自动回复配置为发送SMS的移动设备。

要执行此操作，请执行以下操作：

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration > Application settings > External accounts]** then the **[!UICONTROL SMS routing via SMPP]** external account.
1. Under the **[!UICONTROL Automatic reply sent to the MO]** category, click **[!UICONTROL Create element]** to start configuring your automatic reply.

   ![](assets/sms_mo_1.png)

1. 选择将触发此自动回复的关键字。关键字不区分大小写。例如，如果收件人发送关键字“STOP”，他们将收到自动回复。

   如果您要发送与关键字相同的回复，则将此列保留为空。

   ![](assets/sms_mo_2.png)

1. **[!UICONTROL Short code]** 在字段中，指定一个通常用于发送传送的数字，并用作发送者姓名。You can also decide to leave the **[!UICONTROL Short code]** column empty, to send the same reply no matter what the short code.

   ![](assets/sms_mo_4.png)

1. Type in the answer you want to send to your recipients in the field **[!UICONTROL Reply]**.

   To carry out an action without sending a reply, leave the **[!UICONTROL Reply]** column empty. 例如，这允许您删除使用除“停止”之外的消息进行回复的用户的电话号码。

   ![](assets/sms_mo_3.png)

1. **[!UICONTROL Additional action]** 在字段中，将操作链接到自动回复：

   * **[!UICONTROL Send to quarantine]** 该操作会自动对配置文件电话号码进行隔离。
   * **[!UICONTROL Remove from quarantine]** 此操作将删除隔离中的配置文件电话号码。
   * The **[!UICONTROL None]** action allows you to only send the message to your recipients without carrying an action.
   For example, in the configuration below, if recipients send the keyword "STOP", they will automatically receive an unsubscription confirmation and their phone number will be sent to quarantine with the **[!UICONTROL Blacklisted]** status. 此状态仅引用电话号码，配置文件未列入黑名单，因此用户继续接收电子邮件。

   ![](assets/sms_mo.png)

收件人现在可以自动取消订阅消息并通过此自动回复发送给隔离。The quarantined recipients are listed in the **[!UICONTROL Addresses]** table available through the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Quarantines]** menu. For more information on quarantines, refer to this [section](../../sending/using/understanding-quarantine-management.md).

如果需要，可以存储这些传入的SMS。For more information on this, refer to this [section](../../channels/using/managing-incoming-sms.md#storing-incoming-sms).

## Storing incoming SMS {#storing-incoming-sms}

**[!UICONTROL SMS routing via SMPP]** 在外部帐户中，您可以选择存储传入消息(例如，订阅者将“停止”回复到SMS消息，以便从收件人列表中删除)。

![](assets/sms_config_mo_1.png)

By checking **[!UICONTROL Store incoming MO in the database]** in the **[!UICONTROL SMPP channel settings]** category, all SMS will be stored in the inSMS table and can be retrieved via a query activity in a workflow.

要执行此操作，请执行以下操作：

1. In the **[!UICONTROL SMPP channel settings]** field, check **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. In the **[!UICONTROL Marketing activities]** tab, click **[!UICONTROL Create]** then select **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. 选择工作流类型。
1. Edit the properties of your workflow, then click **[!UICONTROL Create]**. For more on workflows creation, refer to this [section](../../automating/using/building-a-workflow.md).
1. Drag and drop a **[!UICONTROL Query]** activity and double-click the activity.
1. In the **[!UICONTROL Properties]** tab of the query, choose **[!UICONTROL Incoming SMS (inSMS)]** in the **[!UICONTROL Resource]** field.

   ![](assets/sms_config_mo_4.png)

1. Then, in the **[!UICONTROL Target]** tab, drag and drop the **[!UICONTROL Incoming SMS attributes]** rule.

   ![](assets/sms_config_mo_5.png)

1. 此处，我们希望从前一天开始针对每一条消息进行定位。In the **[!UICONTROL Field]** category, select **[!UICONTROL Creation date (created)]**.
1. In **[!UICONTROL Filter type]**, select **[!UICONTROL Relative]** then in **[!UICONTROL Level of precision]**, choose **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. 然后，您可以选择从今天或最近几天检索数据。Click **[!UICONTROL Confirm]** when your query is configured.

此查询将检索根据所选时间范围接收的每个停止消息。

该活动允许您示例构建人群并更好地个性化交付。
