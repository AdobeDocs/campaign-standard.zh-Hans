---
solution: Campaign Standard
product: campaign
title: 配置 Campaign-Analytics 集成
description: 了解如何将Adobe Analytics集成配置为开始衡量电子邮件投放的成功。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 9%

---


# 配置 Campaign-Analytics 集成{#configure-campaign-analytics-integration}

此集成允许您将关键绩效指标数据从Adobe Campaign直接共享到Adobe Analytics Standard或高级。

要开始Adobe Campaign Standard和Adobe Analytics之间的集成，您首先需要配置与Adobe Analytics链接的外部帐户。

外部帐户和技术工作流只能由平台的功能管理员进行管理。

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration > Application settings > External accounts]**.
1. Select the **[!UICONTROL Share KPIs with Adobe Analytics]** external account.

   ![](assets/analytics_2.png)

1. 在字 **[!UICONTROL Web services user name]** 段中 **[!UICONTROL Web services share secret]** 指定您 **[!UICONTROL Connection]** 的和。

   您可以通过选择在Analytics中找到这些参 **[!UICONTROL Admin > Company settings > Web services]**&#x200B;数。

   ![](assets/analytics_1.png)

1. 单击 **[!UICONTROL Refresh report suites]** 按钮。
1. 从下拉 **[!UICONTROL Analytics default report suite]** 列表中选择要用Adobe Campaign数据丰富的Adobe Analytics报表包。

   您的外部帐户现已准备就绪，并已与Adobe Analytics建立联系。 您可以通过选中该框随时禁用该 **[!UICONTROL Enabled]** 功能。

   ![](assets/analytics.png)

技术 **[!UICONTROL Share KPIs with Adobe Analytics]** 工作流现在将自动启动，并可通过选择从高级菜单查看该工作流 **[!UICONTROL Administration > Application settings > Workflow]**。 此技术工作流程将每15分钟自动执行一次，并将在Adobe Analytics推送最多6个月的旧数据。

![](assets/analytics_3.png)

您的数据现已在Adobe Analytics发布。

**相关主题：**

* [外部帐户](../../administration/using/external-accounts.md)
* [技术工作流](../../administration/using/technical-workflows.md)
* [共享KPI以实现集成活动报告](https://helpx.adobe.com/cn/marketing-cloud/how-to/email-marketing.html) 视频

