---
title: 关于Campaign-Point数据整合
seo-title: 关于Campaign-Point数据整合
description: 关于Campaign-Point数据整合
seo-description: 通过收集移动应用程序的用户的兴趣点数据，通过Adobe Campaign中的集成向用户发送基于位置的营销消息。
page-status-flag: 从未激活
uuid: 1e6840c8-0472-4da2-85ed-f9 a65147355 a
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 集成
content-type: reference
topic-tags: 使用营销活动和分析-移动-移动
discoiquuid: bc10c650-80cd-4146-ae82-c5981 fc62 bec
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# About Campaign-Points of Interest data integration{#about-campaign-points-of-interest-data-integration}

除了跟踪客户的在线状态之外，您还可以利用其物理位置。通过与Adobe Analytics for Mobile集成，您可以使用Adobe Campaign向移动应用程序的用户发送基于位置的营销消息。

目标点由纬度、longitude和与标签关联的半径组成。They are defined in the [Adobe Mobile Services](https://marketing.adobe.com/resources/help/en_US/mobile/home.html) interface.

当订阅者打开您的移动应用程序时，如果该位置匹配某个Point of Interest，Adobe Campaign将通过Experience Cloud Mobile SDK捕获该数据。您可以使用此信息根据用户位置(例如电子邮件、推送通知、SMS消息)发送个性化消息。

例如，您可以向使用应用程序的客户发送10%的折扣优惠，并在过去两周内在波士顿访问您的一家商店。

A use case is presented in the [Personalizing Campaign messages with Point of Interest data](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md) section.
