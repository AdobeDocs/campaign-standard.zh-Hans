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
ht-degree: 7%

---

# 编辑用户档案{#editing-profiles}

## 访问配置文件属性 {#accessing-profile-properties}

要编辑现有配置文件并查阅与其关联的数据，或修改它，请执行以下步骤：

1. 在Adobe Campaign主页中，单击&#x200B;**[!UICONTROL Customer profiles]**&#x200B;卡或&#x200B;**[!UICONTROL Profiles]**&#x200B;选项卡。
1. 选择联系人。
1. 单击&#x200B;**[!UICONTROL Edit profile properties]**&#x200B;图标可访问配置文件的详细信息。

   ![](assets/profile_creation2.png)

   配置文件的属性窗口提供了多个选项卡，用于访问所有配置文件信息。

   根据在Adobe Campaign中创建或扩展的自定义资源，还可能会显示其他选项卡。 有关自定义资源的详细信息，请参阅[关于自定义资源](../../developing/using/data-model-concepts.md)。

   >[!NOTE]
   >
   >您只能修改&#x200B;**[!UICONTROL General]**&#x200B;选项卡中的信息 — **[!UICONTROL Traceability]**&#x200B;部分除外。

也可以使用Adobe Campaign Standard API编辑配置文件。 有关更多信息，请参阅[专用文档](../../api/using/updating-profiles.md)。

相关主题：

* [Integrated Customer Profile](../../audiences/using/integrated-customer-profile.md)
* [按收件人的时区发送](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## 常规配置文件数据 {#general-profile-data}

**[!UICONTROL General]**&#x200B;选项卡将有关配置文件的以下信息分组：

* 联系人信息，其中包含收件人的名字、姓氏、出生日期、照片、首选语言（[多语言电子邮件](../../channels/using/creating-a-multilingual-email.md)）等。
* 用于联系用户档案的频道，包含收件人的电子邮件地址、手机号码和选择退出信息。
* 邮政地址（用于[直邮](../../channels/using/about-direct-mail.md)）和联系人的时区（以时区[&#128279;](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)排程邮件）。
* 访问授权，它指示收件人的组织单位（[管理权限](../../administration/using/about-access-management.md)）。 另请参阅[划分用户档案](../../administration/using/organizational-units.md#partitioning-profiles)。

![](assets/profile_creation4.png)

## 发送和跟踪日志 {#sending-and-tracking-logs}

**[!UICONTROL Sending logs]**&#x200B;和&#x200B;**[!UICONTROL Tracking logs]**&#x200B;选项卡将发送到用户档案的投放列表以及所有相关跟踪数据分组。

有关发送和跟踪日志的详细信息，请参阅[投放日志](../../sending/using/monitoring-a-delivery.md#delivery-logs)和[跟踪消息](../../sending/using/tracking-messages.md)部分。

## 订阅 {#subscriptions}

联系人的订阅将列在相应的选项卡中。 有关订阅服务的详细信息，请参阅[此部分](../../audiences/using/about-subscriptions.md)。

**[!UICONTROL Mobile App Subscriptions]**&#x200B;选项卡引用推送通知。 有关详细信息，请参阅[推送通知](../../channels/using/about-push-notifications.md)渠道。
