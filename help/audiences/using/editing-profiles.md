---
title: 编辑配置文件
seo-title: 编辑配置文件
description: 编辑配置文件
seo-description: 了解如何编辑现有配置文件和访问联系信息、首选渠道、跟踪日志、订阅等。
page-status-flag: 从未激活
uuid: 6fcdb719-6149-48fc-b400-64c24 a51487 f
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 受众
content-type: reference
topic-tags: 管理配置文件
discoiquuid: 8d3ba7bf-90ae-4c6d-aaebeb-a48572 a69 f2 f
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Editing profiles{#editing-profiles}

## Accessing profile properties {#accessing-profile-properties}

要编辑现有配置文件并查阅与之关联的数据或修改该配置文件，以下步骤如下所示：

1. From the Adobe Campaign home page, click the **[!UICONTROL Customer profiles]** card or the **[!UICONTROL Profiles]** tab.
1. 选择联系人。
1. Click the **[!UICONTROL Edit profile properties]** icon to access the profile's detailed information.

   ![](assets/profile_creation2.png)

   配置文件的属性窗口提供了几个选项卡，用于访问所有配置文件信息。

   其他选项卡可能还会根据在Adobe Campaign中创建或扩展的自定义资源而显示。For more information about custom resources, see [About custom resources](../../developing/using/data-model-concepts.md).

   >[!NOTE]
   >
   >You can only modify the information in the **[!UICONTROL General]** tab - except for the **[!UICONTROL Traceability]** section.

还可以使用Adobe Campaign Standard API实现配置文件版本。For more on this, refer to the [dedicated documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#updating-profiles) .

相关主题：

* [集成的客户档案](../../audiences/using/integrated-customer-profile.md)
* [在收件人的时区发送](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## General profile data {#general-profile-data}

**[!UICONTROL General]** 选项卡组提供了有关配置文件的以下信息：

* Contact information, which contains the recipient's first name, last name, date of birth, photo, preferred language (for [multilingual emails](../../channels/using/creating-a-multilingual-email.md)), etc.
* 可在其中联系配置文件的渠道，其中包含收件人的电子邮件地址、移动电话号码、选择退出信息。
* Postal address (for [direct mail](../../channels/using/about-direct-mail.md)), and the contact's time zone (to [schedule messages in its time zone](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)).
* Access authorization, which indicates the recipient's organisational unit (to [manage permissions](../../administration/using/about-access-management.md)). See also [Partitioning profiles](../../administration/using/organizational-units.md#partitioning-profiles).

![](assets/profile_creation4.png)

## Sending and tracking logs {#sending-and-tracking-logs}

**[!UICONTROL Sending logs]****[!UICONTROL Tracking logs]** 这些选项卡将发送到配置文件的交付列表和所有相关跟踪数据分组在一起。

For more on sending and tracking logs, refer to the [delivery logs](../../sending/using/monitoring-a-delivery.md#delivery-logs) and the [tracking messages](../../sending/using/tracking-messages.md) sections.

## Subscriptions {#subscriptions}

联系人的订阅将列在相应的选项卡中。For more on subscribing to a service, refer to [this section](../../audiences/using/about-subscriptions.md).

**[!UICONTROL Mobile App Subscriptions]** 选项卡引用推送通知。For more information, refer to the [Push notification](../../channels/using/about-push-notifications.md) channel.
