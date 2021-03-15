---
solution: Campaign Standard
product: campaign
title: 使用兴趣点数据个性化 Campaign 消息
description: 了解如何通过兴趣点数据集成根据用户位置创建个性化消息。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: 受众
role: 数据架构师
level: 中间
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 10%

---


# 使用兴趣点数据个性化 Campaign 消息{#personalizing-campaign-messages-with-point-of-interest-data}

在Adobe Campaign中，您可以使用从您的移动应用程序订户收集的兴趣点数据向他们发送个性化的营销消息，如电子邮件。

您只能对目标点数据使用标准投放做出反应。 [事务](../../channels/using/getting-started-with-transactional-msg.md) 消息不能使用位置数据。

你最早能做出反应是10分钟左右。

在这种情况下，您决定在过去两周内向访问您波士顿商店的所有订阅者发送电子邮件。

1. 创建电子邮件营销活动。
1. 定义投放的受众时，将&#x200B;**[!UICONTROL Subscriptions to an application]**&#x200B;元素拖放到工作区中。

   ![](assets/poi_subscriptions_app.png)

   [定义受众](../../audiences/using/creating-audiences.md)部分详细介绍了管理受众。

1. 在&#x200B;**[!UICONTROL Add a rule - Profile/Subscriptions to an application]**&#x200B;窗口中，将&#x200B;**[!UICONTROL POI Location Subscription]**&#x200B;元素拖放到工作区中。

   ![](assets/poi_add_rule_profile_subscription.png)

1. 在&#x200B;**[!UICONTROL Add a rule - POI Location Subscription]**&#x200B;窗口中，输入要使用的目标点的标签。

   ![](assets/poi_location_subscription.png)

1. 在 **[!UICONTROL Filter type]** 字段中，选择 **[!UICONTROL Relative]**。
1. 选中&#x200B;**[!UICONTROL Preceding days]**&#x200B;选项，并在相应的字段中输入&#x200B;**[!UICONTROL 15]**。
1. 定义用户必须访问目标点的次数。
1. 单击&#x200B;**[!UICONTROL Confirm]**&#x200B;保存受众。

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. 向电子邮件中添加内容。

   ![](assets/poi_email_content.png)

1. 确认创建活动以视图电子邮件的仪表板。
1. 发送您的消息。

具有10%折扣优惠的电子邮件将发送给以下用户：

* 在过去两周内至少访问过你的波士顿商店一次。
* 在访问期间，将您的移动应用程序至少置于前台一次。

**相关主题：**

* [创建电子邮件](../../channels/using/creating-an-email.md)
* [定义内容](../../designing/using/personalization.md#example-email-personalization)
* [发送消息](../../sending/using/confirming-the-send.md)

