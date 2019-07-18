---
title: Intersection
seo-title: Intersection
description: Intersection
seo-description: 通过“相交”活动，您只能保留活动中不同入站人群共有的元素。
page-status-flag: 从未激活
uuid: a60f9811-0158-44b3-952b-392685c006cc
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 定位活动
discoiquuid: 7a107d6b-edc3-44c3-bbb7-ba3 ec8 e43 f9
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Intersection{#intersection}

## Description {#description}

![](assets/intersection.png)

**[!UICONTROL Intersection]** 活动允许您仅保留活动中不同入站人群共有的元素。

## Context of use {#context-of-use}

**[!UICONTROL Intersection]** 该活动通常用于对来自入站过渡的人群进行额外过滤。

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Intersection]** activity into your workflow.
1. 将其连接到之前的其他活动，如查询。
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Reconciliation type]**:

   * **[!UICONTROL Keys only]**：默认模式。仅当不同的入站过渡中的元素具有相同的键时，活动才会保留一个元素。
   * **[!UICONTROL All shared columns]**：数据以与入站过渡相同的列进行协调。因此，您必须选择用作比较基础的主要设置。如果入站人口定位维度不同，则可使用此选项。
   * **[!UICONTROL A selection of columns]**：选择此选项可定义将应用数据排序的列列表。必须首先选择主集合(其中包含源数据的集合)，然后指定要用于加入的字段。

1. Check the **[!UICONTROL Use common additional data only]** box if you would like to keep only the additional data that is in all inbound transitions.
1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.
1. 确认活动的配置并保存工作流。

## Example {#example}

以下示例显示了两个查询活动之间的交叉点。此处正在使用它来查看Adobe Campaign数据库和检索到18到27年的配置文件的配置文件，以及分别提供电子邮件地址的配置文件。

![](assets/wkf_intersection_example.png)

