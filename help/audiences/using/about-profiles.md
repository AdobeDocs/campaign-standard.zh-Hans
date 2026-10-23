---
title: 关于轮廓
description: 联系人作为轮廓存储在 Campaign 数据库中，并在其整个生命周期内不断更新。
audience: audiences
content-type: reference
topic-tags: managing-profiles
context-tags: recipient,overview
feature: Profiles
role: User
level: Beginner
exl-id: 65310e00-567f-4fae-89bc-b1d5591fca77
TQID: 'https://experienceleague.adobe.com/8netKX93BsN9JxgyckV44tpKK5uPjFMrrnD8F4FCpJM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 74%
---
# 关于轮廓{#about-profiles}

您可以使用Adobe Campaign在联系人的整个生命周期内对其进行管理：创建、导入、定位、操作跟踪、更新等。联系人作为包含相关链接信息的用户档案存储在数据库中：姓氏、名字、地址、订阅、投放等。

>[!NOTE]
>
>Adobe Campaign Standard API 也可以使用轮廓。 有关更多信息，请参阅[专用文档](../../api/using/retrieving-profiles.md)。

![](assets/marketing_history.png)

创建营销策划时，您可以根据简单或高级条件选择轮廓，从而定义投放的目标。 从技术上讲，轮廓是数据库中的一个条目，其中包含定向、鉴别和跟踪行为所需的全部信息。

轮廓可以是：客户、潜在客户、订阅新闻通讯的个人、收件人、用户或任何其他对象，具体取决于您的组织。 要定义各种类型的轮廓，请使用[定向维度](../../automating/using/query.md#targeting-dimensions-and-resources)。
