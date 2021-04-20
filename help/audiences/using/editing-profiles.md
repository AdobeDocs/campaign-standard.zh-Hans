---
solution: Campaign Standard
product: campaign
title: 编辑用户档案
description: 了解如何编辑现有用户档案和访问联系信息、首选渠道、跟踪日志、订阅等。
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: Profiles
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 11%

---


# 编辑用户档案{#editing-profiles}

## 访问用户档案属性{#accessing-profile-properties}

要编辑现有用户档案并查阅与其关联的数据，或修改它，步骤如下：

1. 在 Adobe Campaign 主页中，单击 **[!UICONTROL Customer profiles]** 卡或 **[!UICONTROL Profiles]** 选项卡。
1. 选择联系人。
1. 单击&#x200B;**[!UICONTROL Edit profile properties]**&#x200B;图标以访问用户档案的详细信息。

   ![](assets/profile_creation2.png)

   用户档案的“属性”窗口会优惠多个选项卡，这些选项卡允许访问所有用户档案信息。

   其他选项卡也可能会显示，具体取决于已在Adobe Campaign中创建或扩展的自定义资源。 有关自定义资源的详细信息，请参阅[关于自定义资源](../../developing/using/data-model-concepts.md)。

   >[!NOTE]
   >
   >您只能修改&#x200B;**[!UICONTROL General]**&#x200B;选项卡中的信息 — **[!UICONTROL Traceability]**&#x200B;部分除外。

用户档案版本也可使用Adobe Campaign Standard API。 有关更多信息，请参阅[专用文档](../../api/using/updating-profiles.md)。

相关主题：

* [整合的客户用户档案](../../audiences/using/integrated-customer-profile.md)
* [在收件人时区发送](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## 一般用户档案数据{#general-profile-data}

**[!UICONTROL General]**&#x200B;选项卡对有关用户档案的以下信息进行了分组：

* 联系信息，包含收件人的名字、姓氏、出生日期、照片、首选语言（适用于[多语言电子邮件](../../channels/using/creating-a-multilingual-email.md)）等。
* 可联系用户档案的渠道，其中包含收件人的电子邮件地址、手机号码和退出信息。
* 邮政地址（用于[直邮](../../channels/using/about-direct-mail.md)）和联系人的时区(到[其时区](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)中的计划邮件)。
* 访问授权，指示收件人的组织单位（[管理权限](../../administration/using/about-access-management.md)）。 另请参阅[划分用户档案](../../administration/using/organizational-units.md#partitioning-profiles)。

![](assets/profile_creation4.png)

## 发送和跟踪日志{#sending-and-tracking-logs}

**[!UICONTROL Sending logs]**&#x200B;和&#x200B;**[!UICONTROL Tracking logs]**&#x200B;选项卡对发送到用户档案的投放的列表以及所有相关跟踪数据进行分组。

有关发送和跟踪日志的详细信息，请参阅[投放日志](../../sending/using/monitoring-a-delivery.md#delivery-logs)和[跟踪消息](../../sending/using/tracking-messages.md)部分。

## 订阅{#subscriptions}

联系人的订阅列在相应的选项卡中。 有关订阅服务的详细信息，请参阅[本节](../../audiences/using/about-subscriptions.md)。

**[!UICONTROL Mobile App Subscriptions]**&#x200B;选项卡引用推送通知。 有关详细信息，请参阅[推送通知](../../channels/using/about-push-notifications.md)渠道。
