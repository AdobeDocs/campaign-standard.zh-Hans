---
title: 关于 Campaign-兴趣点数据集成
description: 通过从移动应用程序的订阅者收集Points of Interest数据，可通过Adobe Campaign中的集成向订阅者发送基于位置的营销消息。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 358194f9-34ce-4dd5-b9b2-1a7d541879ab
TQID: https://experienceleague.adobe.com/NMHm-sHLhsjMqprniSnxca27zpoxGEhRGKlt1IJXfVg
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 202
ht-degree: 6%

---

# 关于 Campaign-兴趣点数据集成{#about-campaign-points-of-interest-data-integration}

除了跟踪客户的在线状态外，您还可以利用客户的物理位置。 通过与Adobe Analytics for Mobile集成，您可以使用Adobe Campaign向移动应用程序的订阅者发送基于位置的营销消息。

目标点由纬度、经度和与标签关联的半径组成。 它们是在[Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html)界面中定义的。

当订阅者打开您的移动应用程序时，如果位置与兴趣点匹配，Adobe Campaign将通过Experience Cloud Mobile SDK捕获数据。 您可以使用此信息根据用户的位置发送个性化消息（如电子邮件、推送通知、短信消息）。

例如，您可以向使用您的应用程序并在最近两周内访问您位于波士顿的一家商店的客户发送10%的折扣优惠。

在[使用兴趣点数据个性化Campaign消息](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md)部分中提供了一个用例。
