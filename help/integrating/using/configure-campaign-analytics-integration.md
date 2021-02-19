---
solution: Campaign Standard
product: campaign
title: 配置 Campaign-Analytics 集成
description: 了解如何将Adobe Analytics集成配置为开始，以衡量电子邮件投放的成功。
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

此集成允许您将关键绩效指标数据从Adobe Campaign直接共享到Adobe Analytics Standard或Premium。

要开始Adobe Campaign Standard与Adobe Analytics之间的集成，您首先需要配置链接到Adobe Analytics的外部帐户。

外部帐户和技术工作流只能由平台的功能管理员管理。

1. 从高级菜单中，通过Adobe Campaign标志选择&#x200B;**[!UICONTROL Administration > Application settings > External accounts]**。
1. 选择&#x200B;**[!UICONTROL Share KPIs with Adobe Analytics]**&#x200B;外部帐户。

   ![](assets/analytics_2.png)

1. 在&#x200B;**[!UICONTROL Connection]**&#x200B;字段中指定&#x200B;**[!UICONTROL Web services user name]**&#x200B;和&#x200B;**[!UICONTROL Web services share secret]**。

   可以在Analytics中选择&#x200B;**[!UICONTROL Admin > Company settings > Web services]**&#x200B;找到这些参数。

   ![](assets/analytics_1.png)

1. 单击 **[!UICONTROL Refresh report suites]** 按钮。
1. 在&#x200B;**[!UICONTROL Analytics default report suite]**&#x200B;下拉列表中，选择要使用Adobe Campaign数据丰富的Adobe Analytics报表包。

   您的外部帐户现已准备就绪，并已与Adobe Analytics链接。 您可以通过选中&#x200B;**[!UICONTROL Enabled]**&#x200B;框随时禁用它。

   ![](assets/analytics.png)

现在，**[!UICONTROL Share KPIs with Adobe Analytics]**&#x200B;技术工作流将自动启动，并可通过选择&#x200B;**[!UICONTROL Administration > Application settings > Workflow]**&#x200B;从高级菜单查看。 此技术工作流程将每15分钟自动执行一次，并将在Adobe Analytics中推送最多6个月的旧数据。

![](assets/analytics_3.png)

您的数据现已在Adobe Analytics提供。

**相关主题：**

* [外部帐户](../../administration/using/external-accounts.md)
* [技术工作流](../../administration/using/technical-workflows.md)
* [共享KPI以实现集成活动报](https://helpx.adobe.com/cn/marketing-cloud/how-to/email-marketing.html) 告视频

