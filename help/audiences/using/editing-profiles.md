---
title: 编辑配置文件
seo-title: 编辑配置文件
description: 编辑配置文件
seo-description: 了解如何编辑现有配置文件和访问联系信息、首选渠道、跟踪日志、订阅等。
page-status-flag: 从未激活
uuid: 6fcdb719-6149-48fc-b400-64c24a51487f
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: 参考
topic-tags: 管理配置文件
discoiquuid: 8d3ba7bf-90ae-4c6d-aeb-a48572a69f2f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 94c7649448aff859daaf2bbe9a4d17a5187ac71f

---


# 编辑配置文件{#editing-profiles}

## 访问配置文件属性 {#accessing-profile-properties}

要编辑现有配置文件并查阅与其关联的数据，或对其进行修改，步骤如下：

1. 在Adobe Campaign主页中，单击卡 **[!UICONTROL Customer profiles]** 或选项卡 **[!UICONTROL Profiles]** 。
1. 选择联系人。
1. 单击该 **[!UICONTROL Edit profile properties]** 图标可访问配置文件的详细信息。

   ![](assets/profile_creation2.png)

   配置文件的属性窗口提供了多个选项卡，这些选项卡允许访问所有配置文件信息。

   其他选项卡也可能会显示，具体取决于在Adobe Campaign中创建或扩展的自定义资源。 有关自定义资源的详细信息，请参 [阅关于自定义资源](../../developing/using/data-model-concepts.md)。

   >[!NOTE]
   >
   >您只能修改选项卡中的信 **[!UICONTROL General]** 息——但部分除外 **[!UICONTROL Traceability]** 。

使用Adobe Campaign Standard API也可以编辑配置文件。 有关详细信息，请参阅专 [用文档](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#updating-profiles) 。

相关主题：

* [整合了客户的用户档案](../../audiences/using/integrated-customer-profile.md)
* [在收件人的时区发送](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## 一般配置文件数据 {#general-profile-data}

该选 **[!UICONTROL General]** 项卡将配置文件的以下信息分组在一起：

* 联系信息，其中包含收件人的名字、姓氏、出生日期、照片、首选语言(适用于多语 [种电子邮件](../../channels/using/creating-a-multilingual-email.md))等。
* 可以联系个人资料的渠道，其中包含收件人的电子邮件地址、手机号码和退出信息。
* 邮政地址( [用于直邮](../../channels/using/about-direct-mail.md))和联系人的时区(用 [于计划其时区中的邮件](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md))。
* 访问授权，指示接收方的组织单位(以管 [理权限](../../administration/using/about-access-management.md))。 另请参阅分 [区配置文件](../../administration/using/organizational-units.md#partitioning-profiles)。

![](assets/profile_creation4.png)

## 发送和跟踪日志 {#sending-and-tracking-logs}

该和 **[!UICONTROL Sending logs]** 选 **[!UICONTROL Tracking logs]** 项卡将发送到配置文件的分发列表以及所有相关跟踪数据分组在一起。

有关发送和跟踪日志的详细信息，请参 [阅交付日志](../../sending/using/monitoring-a-delivery.md#delivery-logs)[和跟踪消息部分](../../sending/using/tracking-messages.md) 。

## 订阅 {#subscriptions}

联系人的订阅列在相应的选项卡中。 有关订阅服务的详细信息，请参 [阅本节](../../audiences/using/about-subscriptions.md)。

该 **[!UICONTROL Mobile App Subscriptions]** 选项卡引用推送通知。 有关详细信息，请参阅推 [送通知渠道](../../channels/using/about-push-notifications.md) 。
