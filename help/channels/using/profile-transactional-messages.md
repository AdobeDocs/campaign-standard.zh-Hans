---
title: 用户档案交易消息
description: 了解如何创建和发布个人资料交易消息。
page-status-flag: 从未激活
uuid: a8efe979-74ae-46ff-a305-b86a90679581
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 频道
content-type: 参考
topic-tags: 事务消息传递
discoiquuid: dcb90afc-42c3-419e-8345-79cddf969e41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 用户档案交易消息{#profile-transactional-messages}

您可以根据客户营销档案发送交易消息，这允许您：

* 应用营销类型学规则，如 **[!UICONTROL Blacklisted address]** 或疲劳 [规则](../../administration/using/fatigue-rules.md)。
* 在消息中包含取消订阅链接。
* 将事务性消息添加到全局交付报告。
* 在客户旅程中利用交易信息。

创建并发布活动(如上例所示，放弃购物车 [](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) )后，将自动创建相应的交易消息。

配置事件以发送配置文 [件事务消息部分中介绍了配置步骤](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 。

为了使活动触发发送交易消息，您必须个性化消息，然后测试并发布消息。

>[!NOTE]
>
>要访问事务性消息，您必须是安全组的一 **[!UICONTROL Administrators (all units)]** 部分。
>
>疲劳规则与个人资料事务性消息兼容。 请参阅 [疲劳规则](../../administration/using/fatigue-rules.md)。

## 发送个人资料交易消息 {#sending-a-profile-transactional-message}

创建、个性化和发布个人资料事务消息的步骤与活动事务消息的步骤相同。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).

差异如下。

1. 转到为编辑而创建的交易消息。
1. 在事务性消息中，单击该 **[!UICONTROL Content]** 部分。 除了事务模板之外，您还可以选择任何电子邮件模板定位 **[!UICONTROL Profile]**。

   ![](assets/message-center_marketing_templates.png)

1. 选择默认的电子邮件模板。

   与所有营销电子邮件类似，它包含取消订阅链接。

   ![](assets/message-center_marketing_perso_unsubscription.png)

   此外，与基于实时事件的配置不同，您可以直接访问所有配置文件信息以个性化您的信息。 请参 [阅插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)。

1. 保存更改并发布消息。 请参 [阅发布交易消息](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)。

## 监控个人资料交易消息传送 {#monitoring-a-profile-transactional-message-delivery}

在发布消息并完成站点集成后，您可以监控交付情况。

1. 要查看消息传送日志，请单击该块右下方的图 **[!UICONTROL Deployment]** 标。

   有关访问日志的详细信息，请参阅 [监视交付](../../sending/using/monitoring-a-delivery.md)。

1. 选择选 **[!UICONTROL Sending logs]** 项卡。 在列中， **[!UICONTROL Status]** 指示 **[!UICONTROL Sent]** 配置文件已选择加入。

   ![](assets/message-center_marketing_sending_logs.png)

1. 选择选 **[!UICONTROL Exclusions logs]** 项卡可查看已从消息目标中排除的收件人，如列入黑名单的地址。

   ![](assets/message-center_marketing_exclusion_logs.png)

对于已选择退出的任何配置文件，排 **[!UICONTROL Blacklisted address]** 版规则会排除相应的收件人。

此规则是特定类型学的一部分，该类型学应用于基于表的所有事务性消 **[!UICONTROL Profile]** 息。

![](assets/message-center_marketing_typology.png)

**相关主题**:

* [站点集成](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [类型](../../administration/using/about-typology-rules.md)

