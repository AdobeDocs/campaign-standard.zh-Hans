---
title: 使用兴趣点数据个性化营销活动消息
seo-title: 使用兴趣点数据个性化营销活动消息
description: 使用兴趣点数据个性化营销活动消息
seo-description: 了解如何通过兴趣点数据集成根据订阅者的位置创建个性化消息。
page-status-flag: 从未激活
uuid: d74c3e55-f130-441b-bc2a-06ddcd5d9784
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 集成
content-type: 参考
topic-tags: 使用Campaign和Analytics for Mobile
discoiquuid: a1736ba3-5121-4d01-bf04-ebb7e701e2e0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 781904d58f520987e978ad5d1cdc9e34871ca876

---


# 使用兴趣点数据个性化营销活动消息{#personalizing-campaign-messages-with-point-of-interest-data}

在Adobe Campaign中，您可以使用从移动应用程序订户收集的兴趣点数据向他们发送个性化的营销消息，如电子邮件。

您只能对兴趣点数据做出标准投放的反应。 [事务性消息](../../channels/using/about-transactional-messaging.md) 不能使用位置数据。

你最早能反应到10分钟左右。

在这种情况下，您决定在过去两周内向访问过您波士顿商店的所有订阅者发送电子邮件。

1. 创建电子邮件营销活动。
1. 定义交付的受众时，将元素拖放到工 **[!UICONTROL Subscriptions to an application]** 作区中。

   ![](assets/poi_subscriptions_app.png)

   定义受众部分详细介绍了 [管理受众](../../audiences/using/creating-audiences.md) 。

1. 在窗 **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** 口中，将元素拖放到 **[!UICONTROL POI Location Subscription]** 工作区中。

   ![](assets/poi_add_rule_profile_subscription.png)

1. 在窗 **[!UICONTROL Add a rule - POI Location Subscription]** 口中，输入要使用的目标点的标签。

   ![](assets/poi_location_subscription.png)

1. 在字段 **[!UICONTROL Filter type]** 中，选择 **[!UICONTROL Relative]**。
1. 选中该 **[!UICONTROL Preceding days]** 选项并在相 **[!UICONTROL 15]** 应的字段中输入。
1. 定义用户必须访问目标点的次数。
1. 单击 **[!UICONTROL Confirm]** 以保存受众。

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. 向电子邮件中添加内容。

   ![](assets/poi_email_content.png)

1. 确认创建活动以查看电子邮件的功能板。
1. 发送您的消息。

具有10%折扣优惠的电子邮件将发送给以下用户：

* 在过去两周内至少访问过您的波士顿商店一次。
* 在访问期间，将您的移动应用程序至少放在前台一次。

**相关主题：**

* [创建电子邮件](../../channels/using/creating-an-email.md)
* [定义内容](../../designing/using/personalization.md#example-email-personalization)
* [发送消息](../../sending/using/confirming-the-send.md)

