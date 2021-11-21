---
title: 关于 Campaign-Analytics 集成
description: 通过从Adobe Campaign Standard收集KPI数据，您现在可以与Adobe Analytics共享促销活动数据，以测量来自Adobe Campaign的电子邮件营销量度。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: ada1a5d1-879b-49cd-b4ef-43d7a40bafdb
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 6%

---

# 关于 Campaign-Analytics 集成{#about-campaign-analytics-integration}

借助Adobe Campaign中的Adobe Analytics集成，您现在可以直接在Adobe Analytics中跟踪电子邮件投放是否成功。

Adobe Campaign Standard与Adobe Analytics之间的此集成将允许您：

* 将您的KPI（关键绩效指标）数据从Adobe Campaign Standard共享到Adobe Analytics。
* 使用Adobe Analytics参数扩充跟踪公式。

这将首先创建链接到Adobe Analytics的外部帐户。 然后，技术工作流将自动启动，默认情况下，每15分钟自动执行一次。 然后，您的KPI数据会被推送到Analytics。

此集成仅适用于电子邮件投放。

Adobe Analytics核心服务之间的集成 **触发器** 此外，Adobe Campaign也可供使用。 它允许您向客户发送个性化电子邮件，以对Adobe Analytics在您的网站上跟踪的特定行为作出反应（在15分钟内）。

**相关主题：**

* [Campaign Standard到Analytics集成概述](https://experienceleague.adobe.com/docs/analytics/integration/adobe-campaign.html)
* [配置Campaign Standard集成](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-analytics/configure-campaign-analytics-integration.html)
* [Analytics 中的 Campaign 维度和指标](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)
