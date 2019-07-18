---
title: 配置Campaign-Analytics集成
seo-title: 配置Campaign-Analytics集成
description: 配置Campaign-Analytics集成
seo-description: 了解如何配置Adobe Analytics集成以开始评估电子邮件交付的成功。
page-status-flag: 从未激活
uuid: bda00b0-7445-469c-8268-9d06c53ce2b0
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 集成
content-type: reference
topic-tags: 使用营销活动和分析
discoiquuid: 92b9004c-cba0-41fd-a035-32be1 d42 c
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Configure Campaign-Analytics integration{#configure-campaign-analytics-integration}

此集成允许您将关键绩效指标数据直接从Adobe Campaign共享到Adobe Analytics Standard或Premium。

要开始Adobe Campaign Standard与Adobe Analytics之间的集成，您首先需要配置链接到Adobe Analytics的外部帐户。

外部帐户和技术工作流只能由平台的职能管理员管理。

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration > Application settings > External accounts]**.
1. Select the **[!UICONTROL Share KPIs with Adobe Analytics]** external account.

   ![](assets/analytics_2.png)

1. Specify your **[!UICONTROL Web services user name]** and **[!UICONTROL Web services share secret]** in the **[!UICONTROL Connection]** field.

   These parameters can be found in Analytics by selecting **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Click the **[!UICONTROL Refresh report suites]** button.
1. Select in the **[!UICONTROL Analytics default report suite]** drop-down the Adobe Analytics report suite you want to enrich with Adobe Campaign data.

   您的外部帐户现已准备好并与Adobe Analytics链接。You can disable it at any time by checking the **[!UICONTROL Enabled]** box.

   ![](assets/analytics.png)

**[!UICONTROL Share KPIs with Adobe Analytics]** 技术工作流现在将自动启动，并可通过选择从高级菜单进行查看 **[!UICONTROL Administration > Application settings > Workflow]**。此技术工作流程将每隔15分钟自动执行一次，并将在Adobe Analytics中最多推送个月的数据。

![](assets/analytics_3.png)

您的数据现在在Adobe Analytics中可用。

**相关主题：**

* [外部帐户](../../administration/using/external-accounts.md)
* [技术工作流程](../../administration/using/technical-workflows.md)
* [共享KPI以获得集成的Campaign报告](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) 视频

