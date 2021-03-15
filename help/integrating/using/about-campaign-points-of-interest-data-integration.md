---
solution: Campaign Standard
product: campaign
title: 关于 Campaign-兴趣点数据集成
description: 通过从您的移动应用程序用户处收集兴趣点数据，通过集成在Adobe Campaign中向用户发送基于位置的营销消息。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: 受众
role: 数据架构师
level: 中间
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 6%

---


# 关于 Campaign-兴趣点数据集成{#about-campaign-points-of-interest-data-integration}

除了跟踪客户在线状态外，您还可以利用客户的实际位置。 通过与Adobe Analytics for Mobile集成，您可以使用Adobe Campaign向移动应用程序的订户发送基于位置的营销消息。

目标点由纬度、经度和与标签关联的半径组成。 它们在[Adobe Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)接口中定义。

当订阅者打开您的移动应用程序时，如果该位置与目标点匹配，Adobe Campaign将通过Experience Cloud Mobile SDK捕获数据。 您可以使用此信息根据用户的位置（如电子邮件、推送通知、短信）发送个性化消息。

例如，您可以向使用您的应用程序并在过去两周内访问您在波士顿的一家商店的客户发送10%的折扣优惠。

在[使用目标点活动个性化消息部分](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md)中显示了用例。
