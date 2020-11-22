---
solution: Campaign Standard
product: campaign
title: 用户档案事务型消息
description: 了解如何创建和发布用户档案事务型消息。
audience: channels
content-type: reference
topic-tags: transactional-messaging
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 95%

---


# 用户档案事务型消息{#profile-transactional-messages}

您可以根据客户营销用户档案发送事务型消息，这样可让您：

* 应用营销分类规则，例如 **[!UICONTROL Address on denylist]** 或[疲劳规则](../../sending/using/fatigue-rules.md)。
* 在消息中包含退订链接。
* 将事务型消息添加到全局投放报告。
* 在客户历程中使用事务型消息。

创建并发布事件后（例如上方[示例](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)中的放弃购物车），将自动创建相应的事务型消息。

有关配置步骤，请参见[配置事件以发送用户档案事务型消息](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message)。

为了让事件触发发送事务型消息，您必须对消息进行个性化，然后测试并发布消息。

>[!NOTE]
>
>要访问事务型消息，您必须归属于 **[!UICONTROL Administrators (all units)]** 安全组。
>
>疲劳规则与用户档案事务型消息兼容。请参阅[疲劳规则](../../sending/using/fatigue-rules.md)。

## 发送用户档案事务型消息{#sending-a-profile-transactional-message}

创建、个性化和发布用户档案事务型消息的步骤，与创建事件事务型消息的步骤相同。请参阅[事件事务型消息](../../channels/using/event-transactional-messages.md)。

下方列出了两者之间的差异。

1. 请转至创建的事务型消息以对其进行编辑。
1. 在事务型消息中，单击 **[!UICONTROL Content]** 部分。除了事务型模板之外，您还可以选择定向 **[!UICONTROL Profile]** 的任何电子邮件模板。

   ![](assets/message-center_marketing_templates.png)

1. 选择默认电子邮件模板。

   与所有营销电子邮件相似，该模板也包含退订链接。

   ![](assets/message-center_marketing_perso_unsubscription.png)

   此外，与基于实时事件的配置不同，您可以直接访问所有用户档案信息，以个性化您的信息。请参阅[插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)。

1. 保存更改并发布消息。请参阅[发布事务型消息](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)。

## 监控用户档案事务型消息投放{#monitoring-a-profile-transactional-message-delivery}

发布消息并完成网站集成后，即可对投放进行监控。

1. 要查看消息投放日志，请单击 **[!UICONTROL Deployment]** 块右下方的图标。

   有关访问日志的更多信息，请参阅[监控投放](../../sending/using/monitoring-a-delivery.md)。

1. 选择 **[!UICONTROL Sending logs]** 选项卡。在 **[!UICONTROL Status]** 列中，**[!UICONTROL Sent]** 表示用户档案已选择加入。

   ![](assets/message-center_marketing_sending_logs.png)

1. Select the **[!UICONTROL Exclusions logs]** tab to view recipients who have been excluded from the message target, such as addresses on denylist.

   ![](assets/message-center_marketing_exclusion_logs.png)

对于选择退出的任何用户档案，**[!UICONTROL Address on denylist]** 分类规则将排除对应的收件人。

此规则属于特定分类的一部分，该特定分类会基于 **[!UICONTROL Profile]** 表应用到所有事务型消息。

![](assets/message-center_marketing_typology.png)

**相关主题**：

* [站点集成](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [分类](../../sending/using/about-typology-rules.md)
