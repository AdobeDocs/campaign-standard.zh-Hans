---
solution: Campaign Standard
product: campaign
title: 使用兴趣点数据个性化 Campaign 消息
description: 了解如何通过兴趣点数据集成根据用户位置创建个性化消息。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 10%

---


# 使用兴趣点数据个性化 Campaign 消息{#personalizing-campaign-messages-with-point-of-interest-data}

在Adobe Campaign中，您可以使用从移动应用程序订户收集的兴趣点数据向他们发送个性化的营销消息，如电子邮件。

您只能使用标准投放对兴趣点数据做出反应。 [事务性消息](../../channels/using/getting-started-with-transactional-msg.md) 无法使用位置数据。

你最早能做出反应是10分钟左右。

在这种情况下，您决定在过去两周内向访问过您波士顿商店的所有订阅者发送电子邮件。

1. 创建电子邮件营销活动。
1. 定义投放的受众时，将元素拖放 **[!UICONTROL Subscriptions to an application]** 到工作区中。

   ![](assets/poi_subscriptions_app.png)

   管理受众在定义受众 [部分中有](../../audiences/using/creating-audiences.md) 详细说明。

1. In the **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** window, drag and drop the **[!UICONTROL POI Location Subscription]** element into the workspace.

   ![](assets/poi_add_rule_profile_subscription.png)

1. 在窗 **[!UICONTROL Add a rule - POI Location Subscription]** 口中，输入要使用的兴趣点标签。

   ![](assets/poi_location_subscription.png)

1. 在 **[!UICONTROL Filter type]** 字段中，选择 **[!UICONTROL Relative]**。
1. 选中选 **[!UICONTROL Preceding days]** 项并在相 **[!UICONTROL 15]** 应的字段中输入。
1. 定义用户必须访问目标点的次数。
1. Click **[!UICONTROL Confirm]** to save your audience.

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. 向电子邮件中添加内容。

   ![](assets/poi_email_content.png)

1. 确认创建活动以视图电子邮件的仪表板。
1. 发送您的消息。

具有10%折扣优惠的电子邮件将发送给以下用户：

* 在过去两周内至少访问过波士顿商店一次。
* 在访问期间，将您的移动应用程序至少放在前台一次。

**相关主题：**

* [创建电子邮件](../../channels/using/creating-an-email.md)
* [定义内容](../../designing/using/personalization.md#example-email-personalization)
* [发送消息](../../sending/using/confirming-the-send.md)

