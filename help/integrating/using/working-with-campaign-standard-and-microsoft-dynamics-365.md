---
solution: Campaign Standard
product: campaign
title: Microsoft Dynamics 365 集成快速入门
description: 了解如何开始使用Microsoft Dynamics 365集成
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 10%

---


# Microsoft Dynamics 365 集成快速入门

在跨渠道通信中激活CRM数据：了解如何将联系人从Microsoft Dynamics 365传递给Adobe Campaign，并共享活动性能数据（发送、打开、点击和弹回）从Adobe Campaign传回Microsoft Dynamics 365。

本节](#support-software-versions)中列出了[支持的版本。

>[!CAUTION]
>
>此功能并非作为产品的一部分现成可用。实施需要咨询 Adobe。请联系您的 Adobe 代表以了解更多信息。

## 原则

Adobe Campaign与Microsoft Dynamics 365集成支持CRM系统中所有可用联系人数据的同步，使所有相关联系人数据都可用于活动活动。

相反，当Adobe Campaign内的用户档案与消息交互时，这些数据(例如：发送、打开、点击和弹回)会自动流入Microsoft Dynamics 365，以保留联系记录，同时保留营销活动。

该集成还支持自定义实体，使Dynamics 365中的[自定义实体](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md)能够与活动中的相应自定义实体同步。

此集成旨在支持四个主要用例：

1. 将联系人从Dynamics 365同步到活动，以便在营销活动中定位
1. 将自定义实体从Dynamics 365同步到活动，以便用于细分和个性化
1. 将电子邮件营销事件（发送、打开、点击、弹回）从活动发送到Dynamics 365，以显示到Dynamics 365界面中的销售存储库
1. 在Dynamics 365和ACS之间同步退出（例如，不要通过电子邮件发送）状态，以保持客户隐私首选项。

## 主要优势

* 销售和营销之间的一致消息传递

Adobe Campaign与Microsoft Dynamics 365的集成使系统能够访问客户洞察和电子邮件营销历史，使所有发送给客户的消息能够共享相同的一致消息。

* 全面视图所有潜在客户和客户数据

通过将Adobe Campaign与Dynamics 365集成，可以在CRM系统内共享和访问每个联系人的电子邮件营销历史。

* 在任何渠道激活Dynamics 365数据

通过将联系人数据同步到Adobe Campaign，可以在具有活动的任何在线或离线渠道（包括移动推送、应用程序内、电子邮件或直邮）发送通信。 无论每个联系人的首选渠道如何，活动都能满足您的需求。

>[!CAUTION]
>
>对于联系人和自定义实体同步，此集成将Dynamics 365视为真相的来源。  对同步属性所做的任何更改应在Dynamics 365中进行，而不应在活动中进行。  如果更改以活动进行，则最终可能会在同步过程中覆盖它们。

## 支持软件版本{#support-software-versions}

此集成需要以下软件版本：

* 仅限Microsoft Dynamics 365 for Sales Online，最新版本

* Adobe Campaign Standard，最新版本
