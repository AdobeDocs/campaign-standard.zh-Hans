---
title: 关于 Campaign-Analytics 集成
description: 通过从Adobe Campaign Standard收集KPI数据，您现在可以与Adobe Analytics共享促销活动数据，以从Adobe Campaign衡量电子邮件营销量度。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ada1a5d1-879b-49cd-b4ef-43d7a40bafdb
TQID: 'https://experienceleague.adobe.com/xTX1m0UTCuDt2YMByv8L6vyJG1W0dRme5ETBJuFG-J4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0
    internal-label: Triggers
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: beb7a3c1-66ab-4786-b879-7621375b3c40
    internal-label: Email marketing
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 7%
---
# 关于 Campaign-Analytics 集成{#about-campaign-analytics-integration}

借助Adobe Campaign中的Adobe Analytics集成，您现在可以直接在Adobe Analytics中跟踪电子邮件投放的成功情况。

Adobe Campaign Standard与Adobe Analytics之间的这种集成将允许您：

* 将您的KPI（关键绩效指标）数据从Adobe Campaign Standard共享到Adobe Analytics。
* 使用Adobe Analytics参数扩充跟踪公式。

此操作将首先创建链接到Adobe Analytics的外部帐户。 然后，技术工作流将自动启动，默认情况下每15分钟自动执行一次。 您的KPI数据随后会被推送到Analytics。

此集成仅适用于电子邮件投放。

Adobe Analytics核心服务&#x200B;**触发器**&#x200B;与Adobe Campaign的集成也可用。 它允许您向客户发送个性化电子邮件，以对Adobe Analytics在您的网站上跟踪的特定行为作出反应（在15分钟内）。

**相关主题：**

* [Campaign Standard与Analytics集成概述](https://experienceleague.adobe.com/docs/analytics/integration/adobe-campaign.html?lang=zh-Hans)
* [配置Campaign Standard集成](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-analytics/configure-campaign-analytics-integration.html?lang=zh-Hans)
* [Analytics 中的 Campaign 维度和指标](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)
