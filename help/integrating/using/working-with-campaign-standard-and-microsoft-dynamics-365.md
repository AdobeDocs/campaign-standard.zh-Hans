---
title: 使用Campaign Standard和Microsoft Dynamics 365
description: 了解如何使用Campaign Standard和Microsoft Dynamics 365
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 03009c47a66aa1a62c05f632e2a60141a98639d8

---


# 使用Campaign Standard和Microsoft Dynamics 365

激活跨渠道通信的CRM数据：了解如何将联系人从Microsoft Dynamics 365传递到Adobe Campaign，并共享活动性能数据（发送、打开、单击和弹回）从Adobe Campaign传回Microsoft Dynamics 365。

>[!NOTE]
>
>Microsoft Dynamics 365/Adobe Campaign标准版集成仅支持 **Microsoft Dynamics 365销售应用程序** 。

## 优势和使用案例

### 原则

Adobe Campaign与Microsoft Dynamics 365集成使CRM系统中所有可用的联系人数据能够同步，从而使所有相关的联系人数据都可用于活动活动。

相反，当Adobe Campaign内的用户档案与消息交互时，这些数据(例如：发送、打开、点击和弹回)会自动流入Microsoft Dynamics 365，以保留联系人记录并保留营销活动。

最新版本的集成还增加了对自定义实体的支持，使Dynamics 365中的自定义实体能够同步到活动中的相应自定义实体。

此集成旨在支持三个主要用例：

1. 将联系人从Dynamics 365同步到活动，以便在营销活动中定位他们
1. 将电子邮件营销事件（发送、打开、单击、弹回）从活动发送到Dynamics 365，以显示到Dynamics 365界面中的销售存储库
1. 将自定义实体从Dynamics 365同步到活动，以便用于细分和个性化

在此处观看Dynamics 365Campaign Standard集成功能 [视频](https://helpx.adobe.com/campaign/kt/acs/using/acs-ms-dynamics-crm-connector-tutorial.html)。

### 主要优势

* 销售和营销之间的一致消息传递

该Adobe Campaign与Microsoft Dynamics 365的集成使系统能够访问客户洞察和电子邮件营销历史，从而使所有发送给客户的消息共享相同的一致消息。

* 全面视图所有潜在客户和客户数据

通过将Adobe Campaign与Dynamics 365集成，可以在CRM系统内共享和访问每个联系人的电子邮件营销历史。

* 激活任何渠道上的Dynamics 365数据

联系人数据与Adobe Campaign同步后，可以通过任何具有活动的在线或离线渠道发送通信，包括移动推送、应用程序内、电子邮件或直邮。 无论每个联系人的首选渠道如何，活动都能满足您的需求。

>[!CAUTION]
>
>对于“联系人”同步，此集成将Dynamics 365视为真相的来源。  对同步联系人属性的任何更改应在Dynamics 365中完成，而不应在活动中完成。  如果在活动中进行了更改，则最终会在同步过程中覆盖这些更改。
