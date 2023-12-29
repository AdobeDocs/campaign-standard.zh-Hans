---
title: 配置 Campaign-Analytics 集成
description: 了解如何配置Adobe Analytics集成，以开始衡量电子邮件投放是否成功。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: a6748b4b-36c5-4961-a599-ace73a8504cc
source-git-commit: 26260b9e633d8be1652eeb46c982864a7477da27
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 7%

---

# 配置 Campaign-Analytics 集成{#configure-campaign-analytics-integration}

利用此集成，可直接将关键绩效指标数据从Adobe Campaign共享到Adobe Analytics Standard或Premium。

要启动Adobe Campaign Standard与Adobe Analytics之间的集成，您首先需要配置链接到Adobe Analytics的外部帐户。

外部帐户和技术工作流只能由平台的功能管理员管理。

1. 从高级菜单中，通过Adobe Campaign徽标，选择 **[!UICONTROL Administration > Application settings > External accounts]**.
1. 选择 **[!UICONTROL Share KPIs with Adobe Analytics]** 外部帐户。

   ![](assets/analytics_2.png)

1. 指定您的 **[!UICONTROL Web services user name]** 和 **[!UICONTROL Web services share secret]** 在 **[!UICONTROL Connection]** 字段。

   通过选择可在Analytics中找到这些参数 **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. 单击 **[!UICONTROL Refresh report suites]** 按钮。
1. 在中选择 **[!UICONTROL Analytics default report suite]** 下拉要通过Adobe Campaign数据扩充的Adobe Analytics报表包。

   您的外部帐户现已准备就绪，并与Adobe Analytics关联。 您可以随时通过检查 **[!UICONTROL Enabled]** 盒子。

   ![](assets/analytics.png)

此 **[!UICONTROL Share KPIs with Adobe Analytics]** 技术工作流现在将自动启动，可以通过选择从高级菜单中查看它 **[!UICONTROL Administration > Application settings > Workflow]**. 此技术工作流最多可保留6个月之前的broadlog。 请注意，此工作流是增量工作流，将推送前一天的数据。

![](assets/analytics_3.png)

您的数据现在可在Adobe Analytics中使用。

**相关主题：**

* [外部帐户](../../administration/using/external-accounts.md)
* [技术工作流](../../administration/using/technical-workflows.md)
* [共享KPI以实现集成的活动报告](https://helpx.adobe.com/cn/marketing-cloud/how-to/email-marketing.html) 视频
