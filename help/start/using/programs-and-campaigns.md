---
title: 计划和营销活动
description: 在Adobe Campaign中，计划和营销活动允许您对与其关联的不同营销活动进行分组和编排。 通过计划和营销活动的报告，您可以分析其影响。
page-status-flag: never-activated
uuid: fe2812a8-196f-4aba-a739-fbbfffd754cb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: marketing-plans
discoiquuid: 21b84028-d1a7-4ad6-891a-862a94565514
context-tags: campaign,overview;campaignExplorer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c26f98c8edd832beeedfedafb8ad27730cc30d25

---


# 计划和营销活动{#programs-and-campaigns}

## 关于计划、计划和营销活动 {#about-plans--programs-and-campaigns}

Adobe Campaign允许您计划市场营销活动，在该活动中可以创建和管理不同类型的活动：电子邮件、SMS消息、推送通知、工作流、登录页面。 这些营销活动及其内容可以收集到项目中。

计划和营销活动允许您重新分组和查看与其关联的不同营销活动。

* 计 **划可能** 包含其他计划以及营销活动、工作流和登陆页面。 它显示在时间轴中，并帮助您组织营销活动：您可以按国家／地区、品牌、单位等分隔它们。
* 营销 **活动** ，使您能够在一个实体下收集您选择的所有营销活动。 营销活动可能包含电子邮件、短信、推送通知、直邮、工作流和登陆页面。

为了更好地组织您的营销计划，Adobe建议采用以下层次结构：“程序”>“子程序”>“营销活动”>“工作流”>“提交”。

通过计划和营销活动的报告，您可以分析其影响。 例如，您可以在营销活动级别构建报表，以汇总该营销活动包含的所有分发的数据。

**相关主题：**

* [时间线](../../start/using/timeline.md)
* [关于动态报告](../../reporting/using/about-dynamic-reports.md)

## 创建程序 {#creating-a-program}

该计划是组织的第一级。 它可以包含子程序、营销活动、工作流或登陆页面。

1. 从Adobe Campaign主页中，选择 **[!UICONTROL Programs & Campaigns]**卡。
1. 单击该按 **[!UICONTROL Create]**钮。
1. 在屏幕 **[!UICONTROL Creation mode]**中，选择程序类型。

   ![](assets/programs_and_campaigns_2.png)

   可用的程序类型基于在 **[!UICONTROL Resources]**>**[!UICONTROL Templates]** >部分中定义的 **[!UICONTROL Program templates]**模板。 有关详细信息，请参阅管理模[板部分](../../start/using/marketing-activity-templates.md)。

1. 在屏幕 **[!UICONTROL Properties]**中，输入程序的名称和ID。

   ![](assets/programs_and_campaigns_3.png)

1. 选择程序的开始和结束日期。 这些日期仅适用于程序本身。

   您可以在父程序中创建程序。 为此，请从现有程序中选择父程序。

1. 单击 **[!UICONTROL Create]**以确认程序的创建。

此时会创建并显示程序。 使用按 **[!UICONTROL Create]**钮可添加子程序、营销活动、工作流或登陆页面。

>[!NOTE]
>
>您还可以从营销活动列表创建计划。

## 创建营销活动 {#creating-a-campaign}

在计划和子计划中，您可以添加营销活动。 营销活动可以包含营销活动，如电子邮件、短信、推送通知、工作流和登陆页面。

1. 从Adobe Campaign主页中，选择卡 **[!UICONTROL Programs & Campaigns]**并访问程序或子程序。
1. 单击该按 **[!UICONTROL Create]**钮并选择**[!UICONTROL Campaign]**。
1. 在屏幕 **[!UICONTROL Creation mode]**中，选择营销活动类型。

   ![](assets/programs_and_campaigns_7.png)

   可用的营销活动类型基于在 **[!UICONTROL Resources]**>**[!UICONTROL Templates]** >中定义的模板 **[!UICONTROL Campaign templates]**。 有关详细信息，请参阅管理模[板部分](../../start/using/marketing-activity-templates.md)。

1. 在屏 **[!UICONTROL Properties]**幕中，输入营销活动的名称和ID。
1. 选择营销活动的开始和结束日期。 这些日期仅适用于营销活动本身。

   ![](assets/programs_and_campaigns_8.png)

1. 单击以 **[!UICONTROL Create]**确认创建营销活动。

系统会创建并显示营销活动。 使用该 **[!UICONTROL Create]**按钮可向营销活动添加营销活动。

>[!NOTE]
>
>根据您的许可协议，您只能访问其中的一些活动。

您还可以从营销活动列表创建营销活动。 您可以选择通过营销活动的属性窗口将营销活动关联到父程序或子程序。

## 计划和营销活动图标和状态 {#programs-and-campaigns-icons-and-statuses}

列表中的每个程序和每个营销活动都有一个可视符号和一个图标，其颜色指示执行状态。 此状态取决于计划或营销活动的有效期。

* 灰色：计划／营销活动尚未开始——状 **[!UICONTROL Editing]**态。
* 蓝色：计划／营销活动正在进行——状 **[!UICONTROL In progress]**态。
* 绿色：计划／营销活动已完成——状 **[!UICONTROL Finished]**态。 默认情况下，当前日期会自动显示为有效起始日期，并根据开始日期(** D+186天&#x200B;**)计算结束日期。 您可以在计划或营销活动属性中更改这些日期。

![](assets/programs_and_campaigns.png)

