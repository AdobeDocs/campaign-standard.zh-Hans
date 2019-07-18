---
title: 个人资料信息消息
seo-title: 个人资料信息消息
description: 个人资料信息消息
seo-description: 了解如何创建和发布个人资料信息消息。
page-status-flag: 从未激活
uuid: a fe979-74ae-46ff-a305-b86 a90679581
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: 交易消息传递
discoiquuid: dcb90afc-42c3-419e-8345-79cdf969e41
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Profile transactional messages{#profile-transactional-messages}

您可以根据客户营销档案发送交易消息，允许您：

* Apply marketing typology rules such as **[!UICONTROL Blacklisted address]** or [fatigue rules](../../administration/using/fatigue-rules.md).
* 在消息中包括取消订阅链接。
* 将交易消息添加到全局交付报告。
* 利用客户旅程中的交易消息。

Once you have created and published an event (the cart abandonment as per the [example](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) above), the corresponding transactional message is created automatically.

[配置事件中显示配置步骤以发送配置文件事务消息](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 部分。

要使活动触发发送交易消息，您必须个性化消息，然后对其进行测试并发布。

>[!NOTE]
>
>To access the transactional messages, you must have administration rights or appear in the **[!UICONTROL Message Center agents]** (mcExec) security group. 疲劳规则与个人资料信息消息兼容。See [Fatigue rules](../../administration/using/fatigue-rules.md).

## Sending a profile transactional message {#sending-a-profile-transactional-message}

创建、个性化和发布个人资料消息的步骤与活动交易消息相同。See [Event transactional messages](../../channels/using/event-transactional-messages.md).

以下列出了差异。

1. 转到为编辑而创建的交易消息。
1. In the transactional message, click the **[!UICONTROL Content]** section. In addition to the transactional template, you can also choose the default email template, which targets **[!UICONTROL Profile]**.

   ![](assets/message-center_marketing_templates.png)

1. 选择默认电子邮件模板。

   与所有营销电子邮件相似，它包含取消订阅链接。

   ![](assets/message-center_marketing_perso_unsubscription.png)

   此外，相对于基于实时事件的配置，您可以直接访问所有配置文件信息以个性化您的信息。See [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md).

1. 保存更改并发布消息。See [Publishing a transactional message](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

## Monitoring a profile transactional message delivery {#monitoring-a-profile-transactional-message-delivery}

消息发布后，您可以监控交付情况。

1. To view the message delivery log, click the icon at the bottom right of the **[!UICONTROL Deployment]** block.

   For more information on accessing the logs, see [Monitoring the delivery](../../sending/using/monitoring-a-delivery.md).

1. Select the **[!UICONTROL Sending logs]** tab. **[!UICONTROL Status]** 在列中 **[!UICONTROL Sent]** ，指示配置文件已选择加入。

   ![](assets/message-center_marketing_sending_logs.png)

1. Select the **[!UICONTROL Exclusions logs]** tab to view recipients who have been excluded from the message target, such as blacklisted addresses.

   ![](assets/message-center_marketing_exclusion_logs.png)

For any profile that has opted out, the **[!UICONTROL Blacklisted address]** typology rule excluded the corresponding recipient.

This rule is part of a specific typology that applies to all transactional messages based on the **[!UICONTROL Profile]** table.

![](assets/message-center_marketing_typology.png)

**相关主题**：

* [站点集成](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [Typologies](../../administration/using/about-typology-rules.md)

