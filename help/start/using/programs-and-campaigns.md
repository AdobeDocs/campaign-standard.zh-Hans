---
title: 计划和营销活动
seo-title: 计划和营销活动
description: 计划和营销活动
seo-description: 在Adobe Campaign中，计划和营销活动允许您分组和编排与这些活动关联的不同营销活动。有关计划和营销活动的报告允许您分析其影响。
page-status-flag: 从未激活
uuid: fe2812a8-196f-4aa-4ab-a739-fbbfd754 cb
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: 营销计划
discoiquuid: 21b84028-d1 a7-4ad6-891a-862a94565514
context-tags: 营销活动，概述；CampaignExplorer，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# Programs and campaigns{#programs-and-campaigns}

## About plans, programs and campaigns {#about-plans--programs-and-campaigns}

Adobe Campaign允许您计划营销活动，在这些活动中，您可以创建和管理不同类型的活动：电子邮件、SMS信息、推送通知、工作流程、着陆页面。这些营销活动及其内容可收集到计划中。

这些程序和营销活动允许您重组和查看与它们关联的不同营销活动。

* **计划** 可能包含其他计划以及营销活动、工作流程和登录页面。它显示在时间轴中，并帮助您组织营销活动：您可以按国家/地区、品牌、单位等划分它们。
* **营销活动** 使您能够在单个实体下收集所选的所有营销活动。营销活动可能包含电子邮件、短信、推送通知、直接邮寄广告、工作流程和登陆页面。

为了更好地组织您的营销计划，Adobe建议您遵循以下层次结构：“计划”&gt;“子程序”&gt;“营销活动”&gt;“工作流”&gt;“交付”。

有关计划和营销活动的报告允许您分析其影响。例如，您可以在营销活动级别构建报告，汇总该营销活动包含的所有分发的数据。

**相关主题：**

* [时间轴](../../start/using/timeline.md)
* [关于动态报告](../../reporting/using/about-dynamic-reports.md)

## Creating a program {#creating-a-program}

该计划是第一个组织级别。它可以包含子程序、营销活动、工作流或登陆页面。

1. From the Adobe Campaign home page, select the **[!UICONTROL Programs & Campaigns]** card.
1. Click on the **[!UICONTROL Create]** button.
1. In the **[!UICONTROL Creation mode]** screen, select a program type.

   ![](assets/programs_and_campaigns_2.png)

   The program types available are based on templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Program templates]** section. For more on this, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. In the **[!UICONTROL Properties]** screen, enter the name and ID of the program.

   ![](assets/programs_and_campaigns_3.png)

1. 为程序选择开始日期和结束日期。这些日期仅适用于计划本身。

   您可以在父程序内创建您的程序。为此，请从现有程序中选择父程序。

1. Click on **[!UICONTROL Create]** to confirm the creation of the program.

创建并显示该程序。Use the **[!UICONTROL Create]** button to add sub-programs, campaigns, workflows or landing pages.

>[!NOTE]
>
>您还可以从营销活动列表中创建计划。

## Creating a campaign {#creating-a-campaign}

在计划和子计划中，您可以添加营销活动。营销活动可包含电子邮件、短信、推送通知、工作流和登陆页面等营销活动。

1. From the Adobe Campaign home page, select the **[!UICONTROL Programs & Campaigns]** card and access a program or sub-program.
1. Click on the **[!UICONTROL Create]** button and select **[!UICONTROL Campaign]**.
1. In the **[!UICONTROL Creation mode]** screen, select a campaign type.

   ![](assets/programs_and_campaigns_7.png)

   The campaign types available are based on templates defined in **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Campaign templates]**. For more on this, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. In the **[!UICONTROL Properties]** screen, enter the name and ID of the campaign.
1. 选择营销活动的开始日期和结束日期。这些日期仅适用于营销活动本身。

   ![](assets/programs_and_campaigns_8.png)

1. Click on **[!UICONTROL Create]** to confirm the creation of the campaign.

创建并显示营销活动。Use the **[!UICONTROL Create]** button to add marketing activities to your campaign.

>[!NOTE]
>
>根据您的许可协议，您只能访问其中一些活动。

您还可以从营销活动列表中创建营销活动。您可以选择通过营销活动的属性窗口将营销活动链接到父计划或子计划。

## Programs and campaigns icons and statuses {#programs-and-campaigns-icons-and-statuses}

每个计划和列表中的每个营销活动都有一个可视符号和一个图标，其颜色指示执行状态。此状态取决于计划或营销活动的有效期。

* Gray: the program/campaign has not yet started - **[!UICONTROL Editing]** status.
* Blue: the program/campaign is in progress - **[!UICONTROL In progress]** status.
* Green: the program/campaign has finished - **[!UICONTROL Finished]** status. By default, the current date is automatically shown as the validity start date and the end date is calculated according to the start date (**D+186 days**). 您可以在计划或营销活动属性中更改这些日期。

![](assets/programs_and_campaigns.png)

