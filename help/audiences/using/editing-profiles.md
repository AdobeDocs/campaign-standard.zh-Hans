---
solution: Campaign Standard
product: campaign
title: 编辑用户档案
description: 了解如何编辑现有用户档案和访问联系信息、首选渠道、跟踪日志、订阅等。
audience: audiences
content-type: reference
topic-tags: managing-profiles
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 11%

---


# 编辑用户档案{#editing-profiles}

## 访问用户档案属性 {#accessing-profile-properties}

要编辑现有用户档案并查阅与其关联的数据，或修改它，步骤如下：

1. 在 Adobe Campaign 主页中，单击 **[!UICONTROL Customer profiles]** 卡或 **[!UICONTROL Profiles]** 选项卡。
1. 选择联系人。
1. 单击图 **[!UICONTROL Edit profile properties]** 标以访问用户档案的详细信息。

   ![](assets/profile_creation2.png)

   用户档案的属性窗口会优惠多个选项卡，这些选项卡允许访问所有用户档案信息。

   其他选项卡也可能会根据已在Adobe Campaign中创建或扩展的自定义资源而出现。 有关自定义资源的详细信息，请参 [阅关于自定义资源](../../developing/using/data-model-concepts.md)。

   >[!NOTE]
   >
   >您只能修改选项卡中的 **[!UICONTROL General]** 信息——除部分之 **[!UICONTROL Traceability]** 外。

用户档案版也可使用Adobe Campaign StandardAPI。 有关更多信息，请参阅[专用文档](../../api/using/updating-profiles.md)。

相关主题：

* [整合的客户用户档案](../../audiences/using/integrated-customer-profile.md)
* [在收件人时区发送](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## 一般用户档案数据 {#general-profile-data}

该选 **[!UICONTROL General]** 项卡将以下有关用户档案的信息分组：

* 联系信息，包含收件人的名字、姓氏、出生日期、照片、首选语言(适用于多 [语言电](../../channels/using/creating-a-multilingual-email.md)子邮件)等。
* 可联系用户档案的渠道，其中包含收件人的电子邮件地址、手机号码和退出信息。
* 邮政地址( [用于直](../../channels/using/about-direct-mail.md)接邮件)和联系人的时区(用 [于计划其时区中的邮件](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md))。
* 访问授权，指示收件人的组织单位(用于 [管理权限](../../administration/using/about-access-management.md))。 另请参阅[划分用户档案](../../administration/using/organizational-units.md#partitioning-profiles)。

![](assets/profile_creation4.png)

## Sending and tracking logs {#sending-and-tracking-logs}

该和 **[!UICONTROL Sending logs]** 选 **[!UICONTROL Tracking logs]** 项卡将发送到该列表的投放以及所有相关的跟踪数据分组。

有关发送和跟踪日志的详细信息，请参 [阅投放日志](../../sending/using/monitoring-a-delivery.md#delivery-logs)[和跟踪消息](../../sending/using/tracking-messages.md) 。

## 订阅 {#subscriptions}

联系人的订阅列在相应的选项卡中。 有关订阅服务的详细信息，请参 [阅本节](../../audiences/using/about-subscriptions.md)。

该选 **[!UICONTROL Mobile App Subscriptions]** 项卡引用推送通知。 有关详细信息，请参阅推 [送通知](../../channels/using/about-push-notifications.md) 渠道。
