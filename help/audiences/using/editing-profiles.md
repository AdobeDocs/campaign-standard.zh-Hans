---
title: 编辑用户档案
description: 了解如何编辑现有用户档案并访问联系信息、首选渠道、跟踪日志、订阅等。
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: Profiles
role: User
level: Intermediate
exl-id: d0c7dc09-6f2b-4336-b545-7afe3a704164
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 12%

---

# 编辑用户档案{#editing-profiles}

## 访问配置文件属性 {#accessing-profile-properties}

要编辑现有配置文件并查阅与其关联的数据，或对其进行修改，请执行以下步骤：

1. 在 Adobe Campaign 主页中，单击 **[!UICONTROL Customer profiles]** 卡或 **[!UICONTROL Profiles]** 选项卡。
1. 选择联系人。
1. 单击 **[!UICONTROL Edit profile properties]** 图标以访问用户档案的详细信息。

   ![](assets/profile_creation2.png)

   配置文件的“属性”窗口提供了多个选项卡，用于访问所有配置文件信息。

   根据在Adobe Campaign中创建或扩展的自定义资源，可能还会显示其他选项卡。 有关自定义资源的更多信息，请参阅 [关于自定义资源](../../developing/using/data-model-concepts.md).

   >[!NOTE]
   >
   >您只能修改 **[!UICONTROL General]** 选项卡 — 除 **[!UICONTROL Traceability]** 中。

也可以使用Adobe Campaign Standard API编辑用户档案。 有关更多信息，请参阅[专用文档](../../api/using/updating-profiles.md)。

相关主题：

* [Integrated Customer Profile](../../audiences/using/integrated-customer-profile.md)
* [按收件人的时区发送](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## 一般用户档案数据 {#general-profile-data}

的 **[!UICONTROL General]** 选项卡对有关用户档案的以下信息进行分组：

* 联系信息，其中包含收件人的名字、姓氏、出生日期、照片、首选语言(对于 [多语言电子邮件](../../channels/using/creating-a-multilingual-email.md))等。
* 可以联系用户档案的渠道，其中包含收件人的电子邮件地址、手机号码和选择退出信息。
* 邮政地址( [直邮](../../channels/using/about-direct-mail.md))和联系人的时区( [在时区中计划消息](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md))。
* 访问授权，指示收件人的组织单位( [管理权限](../../administration/using/about-access-management.md))。 另请参阅[划分用户档案](../../administration/using/organizational-units.md#partitioning-profiles)。

![](assets/profile_creation4.png)

## 发送和跟踪日志 {#sending-and-tracking-logs}

的 **[!UICONTROL Sending logs]** 和 **[!UICONTROL Tracking logs]** 选项卡可将发送到用户档案的投放列表以及所有相关跟踪数据分组。

有关发送和跟踪日志的更多信息，请参阅 [投放日志](../../sending/using/monitoring-a-delivery.md#delivery-logs) 和 [跟踪消息](../../sending/using/tracking-messages.md) 中。

## 订阅 {#subscriptions}

联系人的订阅列在相应的选项卡中。 有关订阅服务的更多信息，请参阅 [此部分](../../audiences/using/about-subscriptions.md).

的 **[!UICONTROL Mobile App Subscriptions]** 选项卡，请参阅推送通知。 有关更多信息，请参阅 [推送通知](../../channels/using/about-push-notifications.md) 渠道。
