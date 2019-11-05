---
title: 配置 Campaign-Analytics 集成
description: 了解如何配置Adobe Analytics集成，以开始衡量电子邮件发送的成功程度。
page-status-flag: 从未激活
uuid: bdaa00b0-7445-469c-8268-9d06c53ce2b0
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 集成
content-type: 参考
topic-tags: 使用活动和分析
discoiquuid: 92b9004c-cba0-41fd-a035-32bee1d6a42c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 配置 Campaign-Analytics 集成{#configure-campaign-analytics-integration}

此集成允许您将关键绩效指标数据从Adobe Campaign直接共享到Adobe Analytics Standard或Premium。

要开始Adobe Campaign standard与Adobe Analytics之间的集成，您首先需要配置链接到Adobe Analytics的外部帐户。

外部帐户和技术工作流只能由平台的职能管理员管理。

1. 从高级菜单中，通过Adobe Campaign徽标选择 **[!UICONTROL Administration > Application settings > External accounts]**。
1. 选择外 **[!UICONTROL Share KPIs with Adobe Analytics]** 部帐户。

   ![](assets/analytics_2.png)

1. 在字 **[!UICONTROL Web services user name]** 段中 **[!UICONTROL Web services share secret]** 指定您 **[!UICONTROL Connection]** 的。

   可以通过选择在Analytics中找到这些参数 **[!UICONTROL Admin > Company settings > Web services]**。

   ![](assets/analytics_1.png)

1. Click the **[!UICONTROL Refresh report suites]** button.
1. 在Adobe Analytics报 **[!UICONTROL Analytics default report suite]** 告包的下拉列表中选择，以便用Adobe Campaign数据丰富内容。

   您的外部帐户现已准备就绪，并可与Adobe Analytics关联。 您可以通过选中该框随时禁用该 **[!UICONTROL Enabled]** 功能。

   ![](assets/analytics.png)

技 **[!UICONTROL Share KPIs with Adobe Analytics]** 术工作流现在将自动启动，并可通过选择从高级菜单查看 **[!UICONTROL Administration > Application settings > Workflow]**。 此技术工作流程将每15分钟自动执行一次，并将在Adobe Analytics中推送最多6个月的旧数据。

![](assets/analytics_3.png)

您的数据现在可在Adobe Analytics中使用。

**相关主题：**

* [外部帐户](../../administration/using/external-accounts.md)
* [技术工作流](../../administration/using/technical-workflows.md)
* [分享KPI以实现集成的营销活动报告](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) ，视频

