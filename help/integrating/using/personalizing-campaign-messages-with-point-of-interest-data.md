---
title: 使用兴趣点数据个性化 Campaign 消息
description: 了解如何通过Point of Interest数据集成，根据订阅者的位置创建个性化消息。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
exl-id: fcc79829-902d-4547-87c5-8a213e1257b7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 10%

---

# 使用兴趣点数据个性化 Campaign 消息{#personalizing-campaign-messages-with-point-of-interest-data}

在Adobe Campaign中，您可以使用从移动应用程序的订阅者收集的兴趣点数据向他们发送个性化的营销消息，如电子邮件。

您只能通过标准投放对目标点数据做出反应。 [事务型](../../channels/using/getting-started-with-transactional-msg.md) 消息不能使用位置数据。

你最早的反应是10分钟左右。

在这种情况下，您决定在过去两周内向所有访问过您波士顿商店的订阅者发送电子邮件。

1. 创建电子邮件营销活动。
1. 定义投放的受众时，将&#x200B;**[!UICONTROL Subscriptions to an application]**&#x200B;元素拖放到工作区中。

   ![](assets/poi_subscriptions_app.png)

   [定义受众](../../audiences/using/creating-audiences.md)一节中详细介绍了如何管理受众。

1. 在&#x200B;**[!UICONTROL Add a rule - Profile/Subscriptions to an application]**&#x200B;窗口中，将&#x200B;**[!UICONTROL POI Location Subscription]**&#x200B;元素拖放到工作区中。

   ![](assets/poi_add_rule_profile_subscription.png)

1. 在&#x200B;**[!UICONTROL Add a rule - POI Location Subscription]**&#x200B;窗口中，输入要使用的目标点的标签。

   ![](assets/poi_location_subscription.png)

1. 在 **[!UICONTROL Filter type]** 字段中，选择 **[!UICONTROL Relative]**。
1. 选中&#x200B;**[!UICONTROL Preceding days]**&#x200B;选项，然后在相应的字段中输入&#x200B;**[!UICONTROL 15]**。
1. 定义用户必须访问目标点的次数。
1. 单击&#x200B;**[!UICONTROL Confirm]**&#x200B;以保存受众。

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. 向电子邮件中添加内容。

   ![](assets/poi_email_content.png)

1. 确认创建活动以查看电子邮件的功能板。
1. 发送您的邮件。

具有10%折扣优惠的电子邮件将发送给以下订阅者：

* 在过去两周内，至少访问了您的波士顿商店一次。
* 在访问期间，将您的移动设备应用程序至少放在前台一次。

**相关主题：**

* [创建电子邮件](../../channels/using/creating-an-email.md)
* [定义内容](../../designing/using/personalization.md#example-email-personalization)
* [发送消息](../../sending/using/confirming-the-send.md)
