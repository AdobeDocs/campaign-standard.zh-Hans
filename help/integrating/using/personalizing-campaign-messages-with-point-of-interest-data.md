---
title: 通过Point of Interest数据个性化营销活动消息
seo-title: 通过Point of Interest数据个性化营销活动消息
description: 通过Point of Interest数据个性化营销活动消息
seo-description: 了解如何通过使用Point of Interest数据集成，根据用户的位置创建个性化消息。
page-status-flag: 从未激活
uuid: d74c3e55-f130-441b-bc2 a-06ddcd5 d9784
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 集成
content-type: reference
topic-tags: 使用营销活动和分析-移动-移动
discoiquuid: a1736ba3-5121-4d01-bf04-eb7 e701 e2 e0
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Personalizing Campaign messages with Point of Interest data{#personalizing-campaign-messages-with-point-of-interest-data}

在Adobe Campaign中，您可以使用从移动应用程序的订阅者那里收集的兴趣点数据来向其发送个性化营销消息，如电子邮件。

您只能通过标准交付对兴趣点数据做出反应。[交易消息](../../channels/using/about-transactional-messaging.md) 无法使用位置数据。

您最早可以做出的反应是约10分钟。

在这种情况下，您决定向在过去两周内访问波士顿商店的所有订户发送电子邮件。

1. 创建电子邮件营销活动。
1. When defining the delivery's audience, drag and drop the **[!UICONTROL Subscriptions to an application]** element into the workspace.

   ![](assets/poi_subscriptions_app.png)

   Managing audiences is detailed in the [Defining audiences](../../audiences/using/creating-audiences.md) section.

1. In the **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** window, drag and drop the **[!UICONTROL POI Location Subscription]** element into the workspace.

   ![](assets/poi_add_rule_profile_subscription.png)

1. In the **[!UICONTROL Add a rule - POI Location Subscription]** window, enter the label of the Point of Interest that you want to use.

   ![](assets/poi_location_subscription.png)

1. In the **[!UICONTROL Filter type]** field, select **[!UICONTROL Relative]**.
1. Check the **[!UICONTROL Preceding days]** option and enter **[!UICONTROL 15]** in the corresponding field.
1. 定义用户访问目标点的次数。
1. Click **[!UICONTROL Confirm]** to save your audience.

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. 向电子邮件中添加内容。

   ![](assets/poi_email_content.png)

1. 确认创建活动以查看电子邮件的仪表板。
1. 发送邮件。

具有10%折扣优惠的电子邮件将发送给以下用户：

* 在过去两周内，您至少曾访问过波士顿商店一次。
* 在访问期间至少在前台有一次移动应用程序。

**相关主题：**

* [创建电子邮件](../../channels/using/creating-an-email.md)
* [定义内容](../../designing/using/example--email-personalization.md)
* [发送消息](../../sending/using/confirming-the-send.md)

