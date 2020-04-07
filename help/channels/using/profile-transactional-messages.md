---
title: 用户档案交易消息
description: 了解如何创建和发布用户档案事务性消息。
page-status-flag: never-activated
uuid: a8efe979-74ae-46ff-a305-b86a90679581
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: dcb90afc-42c3-419e-8345-79cddf969e41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3b40a9bba79d04f1635b7522cfc99f9e7566c3c0

---


# 用户档案交易消息{#profile-transactional-messages}

您可以根据客户营销用户档案发送事务性消息，这允许您：

* 应用营销类型规则，如 **[!UICONTROL Blacklisted address]** 疲劳 [规则](../../sending/using/fatigue-rules.md)。
* 在消息中包含退订链接。
* 将事务性消息添加到全球投放报告。
* 利用客户旅程中的事务性消息。

创建并发布事件后(如上例所示，放弃购 [物车](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) )，将自动创建相应的事务性消息。

配置事件以发送用户档案部 [分中介绍了配置步骤](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 。

要使事件触发发送事务性消息，您必须个性化消息，然后测试并发布消息。

>[!NOTE]
>
>要访问事务性消息，您必须是安全组的一 **[!UICONTROL Administrators (all units)]** 部分。
>
>疲劳规则与用户档案事务性消息兼容。 请参阅 [疲劳规则](../../sending/using/fatigue-rules.md)。

## 发送用户档案事务性消息 {#sending-a-profile-transactional-message}

创建、个性化和发布用户档案事务性消息的步骤与创建事件事务性消息的步骤相同。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).

差异如下。

1. 转到创建的事务性消息进行编辑。
1. 在事务性消息中，单击该 **[!UICONTROL Content]** 部分。 除了事务模板之外，您还可以选择任何电子邮件模板定位 **[!UICONTROL Profile]**。

   ![](assets/message-center_marketing_templates.png)

1. 选择默认的电子邮件模板。

   与所有营销电子邮件相似，它包含一个退订链接。

   ![](assets/message-center_marketing_perso_unsubscription.png)

   此外，与基于实时事件的配置不同，您可以直接访问所有用户档案信息以个性化您的信息。 请参 [阅插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)。

1. 保存更改并发布消息。 请参 [阅发布事务性消息](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)。

## 监控用户档案事务性消息投放 {#monitoring-a-profile-transactional-message-delivery}

发布消息并完成站点集成后，您可以监控投放。

1. 要视图消息投放日志，请单击块右下角的图 **[!UICONTROL Deployment]** 标。

   有关访问日志的详细信息，请参阅 [监视投放](../../sending/using/monitoring-a-delivery.md)。

1. 选择选 **[!UICONTROL Sending logs]** 项卡。 在列 **[!UICONTROL Status]** 中， **[!UICONTROL Sent]** 指示用户档案已选择加入。

   ![](assets/message-center_marketing_sending_logs.png)

1. 选择选 **[!UICONTROL Exclusions logs]** 择视图收件人的选项卡，这些目标已被排除在消息中，如已列入黑名单地址。

   ![](assets/message-center_marketing_exclusion_logs.png)

对于已选择退出的任何用户档案, **[!UICONTROL Blacklisted address]** 类型规则将排除相应的收件人。

此规则是特定类型学的一部分，该类型学适用于基于表的所有事务性消息 **[!UICONTROL Profile]** 。

![](assets/message-center_marketing_typology.png)

**相关主题**:

* [站点集成](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [类型](../../sending/using/about-typology-rules.md)

