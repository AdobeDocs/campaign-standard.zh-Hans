---
title: Union
seo-title: Union
description: Union
seo-description: 联合活动允许您将多个活动的结果重新转化为单个目标。
page-status-flag: 从未激活
uuid: fafc3ce9-2212-44403-8754-cfbb28 ba6 e26
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 定位活动
discoiquuid: 99a8c3a5-7d9-4dbb-aa37-1d0 a84719 cf6
context-tags: 联合，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Union{#union}

## Description {#description}

![](assets/union.png)

**[!UICONTROL Union]** 活动允许您将多个活动的结果重新转化为单个目标。

>[!NOTE]
>
>这些集合不必是相同的。

## Context of use {#context-of-use}

**[!UICONTROL Union]** 该活动用于在执行分段、定义受众或准备消息目标时将用户从入站过渡组合到一起。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Union]** activity into your workflow.
1. 将其连接到之前的其他活动，如查询。
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Reconciliation type]** to define how duplicates are from the confrontation between inbound populations are handled:

   * **[!UICONTROL Keys only]**：这是默认模式。仅当不同的入站过渡中的元素具有相同的键时，活动才会保留一个元素。只有在入站人群相同时，此选项才可用。
   * **[!UICONTROL All shared columns]**：数据将根据入站过渡的所有列进行协调。因此，您必须选择将在重复情况下保留的主要设置。如果入站人口定位维度不同，则可使用此选项。
   * **[!UICONTROL A selection of columns]**：选择此选项可定义将应用数据排序的列列表。您必须首先选择主集合(其中包含源数据)，然后选择要用于加入的列。

1. Check the **[!UICONTROL Use common additional data only]** box if you would like to keep only the additional data that is in all inbound transitions.
1. If you would like to limit the size of the final population, check the **[!UICONTROL Limit size of generated population]** box. The size can be specified in the **[!UICONTROL Maximum number of records]** field.
1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the calculated population.
1. 确认活动的配置并保存工作流。

## Example {#example}

以下示例展示了两个查询活动的结果，该活动旨在从Adobe Campaign数据库中的18到27岁以及年龄介于34到40岁之间的Adobe Campaign数据库进行重构。结果包含两个查询的所有配置文件，或在配置过程中指定的最大记录数(如果适用)。

![](assets/wkf_union_example.png)