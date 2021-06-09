---
solution: Campaign Standard
product: campaign
title: 关于 Campaign-兴趣点数据集成
description: 通过从移动应用程序的订阅者那里收集目标点数据，通过Adobe Campaign中的集成，向您的订阅者发送基于位置的营销消息。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: 受众
role: Data Architect
level: Intermediate
exl-id: 358194f9-34ce-4dd5-b9b2-1a7d541879ab
source-git-commit: 92365fe416fced72e7ad5818da0dbed5d8f52f15
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 6%

---

# 关于 Campaign-兴趣点数据集成{#about-campaign-points-of-interest-data-integration}

除了跟踪客户的在线状态外，您还可以利用客户的实际位置。 通过与Adobe Analytics for Mobile集成，您可以使用Adobe Campaign向移动应用程序的订阅者发送基于位置的营销消息。

目标点由纬度、经度和与标签关联的半径组成。 它们在[AdobeMobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html)界面中定义。

当订阅者打开您的移动应用程序时，如果位置与目标点匹配，则Adobe Campaign会通过Experience CloudMobile SDK捕获数据。 您可以使用此信息根据用户的位置（如电子邮件、推送通知、短信消息）发送个性化消息。

例如，您可以向使用您的应用程序并在过去两周内访问您在波士顿的一家商店的客户发送10%的折扣优惠。

[使用目标点数据个性化Campaign消息](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md)部分中提供了一个用例。
