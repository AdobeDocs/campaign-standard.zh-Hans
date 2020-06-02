---
title: Microsoft Dynamics 365集成入门
description: 了解如何开始使用Microsoft Dynamics 365集成
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21135f27fd1d8297edd3dd067446d09c39de9f4f
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---


# Microsoft Dynamics 365集成入门

>[!IMPORTANT]
>
>此集成当前不可用。 正在开发新的连接器，并将在将来推出。 有关详细信息，请联系您的Adobe销售代表。

在跨渠道通信中激活CRM数据： 了解如何将联系人从Microsoft Dynamics 365传递给Adobe Campaign，并共享活动性能数据（发送、打开、点击和弹回）从Adobe Campaign传回Microsoft Dynamics 365。

>[!NOTE]
>
>Microsoft Dynamics 365/Adobe Campaign标准版集成仅支 **持Microsoft Dynamics 365销售应用** 。

## 原则

Adobe Campaign与Microsoft Dynamics 365集成支持CRM系统中所有可用的联系人数据的同步，使所有相关的联系人数据都可用于活动活动。

相反，当Adobe Campaign内的用户档案与消息交互时，这些数据(例如： 发送、打开、点击和弹回)会自动流入Microsoft Dynamics 365，以保存联系人记录并包含营销活动。

最新版本的集成还增加了对自定义实体的支持，使Dynamics 365中的自定义实体能够同步到活动中的相应自定义实体。

此集成旨在支持三个主要用例：

1. 将联系人从Dynamics 365同步到活动，以便在营销活动中定位
1. 将电子邮件营销事件（发送、打开、点击、弹回）从活动发送到Dynamics 365，以显示到Dynamics 365界面中的销售存储库
1. 将自定义实体从Dynamics 365同步到活动，以便用于细分和个性化

## 主要优势

* 销售和营销之间的一致消息传递

Adobe Campaign与Microsoft Dynamics 365的集成使系统能够访问客户洞察和电子邮件营销历史，使所有发送给客户的消息能够共享相同的一致消息。

* 全面视图所有潜在客户和客户数据

通过将Adobe Campaign与Dynamics 365集成，可以从CRM系统内共享和访问每个联系人的电子邮件营销历史。

* 在任何渠道激活Dynamics 365数据

通过将联系人数据同步到Adobe Campaign，可以在具有活动的任何在线或离线渠道（包括移动推送、应用程序内、电子邮件或直邮）发送通信。 无论每个联系人的首选渠道如何，活动都能满足您的需求。

>[!CAUTION]
>
>对于“联系人同步”，此集成将Dynamics 365视为真相的来源。  对同步联系人属性所做的任何更改应在Dynamics 365中进行，而不应在活动中进行。  如果更改以活动进行，则最终可能会在同步过程中覆盖它们。
