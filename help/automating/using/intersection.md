---
title: 交叉
description: “交叉点”活动允许您仅保留活动中不同入站人群的通用元素。
page-status-flag: 从未激活
uuid: a60f9811-0158-44b3-952b-392685c006cc
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 定位活动
discoiquuid: 7a107d6b-edc3-44c3-bbb7-ba3dec8e43f9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 交叉{#intersection}

## 说明 {#description}

![](assets/intersection.png)

活动 **[!UICONTROL Intersection]** 允许您仅保留活动中不同入站人群通用的元素。

## 使用环境 {#context-of-use}

该活 **[!UICONTROL Intersection]** 动通常用于对来自入站过渡的人群进行额外过滤。

## 配置 {#configuration}

1. 将活动拖放 **[!UICONTROL Intersection]** 到工作流中。
1. 将其连接到它前面的其他活动，如查询。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。
1. 选择 **[!UICONTROL Reconciliation type]**:

   * **[!UICONTROL Keys only]**:默认模式。 当来自不同入站过渡的元素具有相同的键时，该活动仅保留一个元素。
   * **[!UICONTROL All shared columns]**:数据根据与入站过渡相同的列进行调节。 因此，您必须选择主集作为比较的基础。 如果入站人口定位维度不同，则可以使用此选项。
   * **[!UICONTROL A selection of columns]**:选择此选项可定义将应用数据协调的列列表。 必须首先选择主集（包含源数据的集），然后指定用于连接的字段。

1. 如果 **[!UICONTROL Use common additional data only]** 您希望仅保留所有入站过渡中的其他数据，请选中此框。
1. 如果需要，可以管理活动的“过 [渡](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) ”以访问出站人群的高级选项。
1. 确认活动的配置并保存工作流。

## Example {#example}

以下示例显示了两个查询活动之间的交集。 此处使用它来查看Adobe Campaign数据库并检索年满18至27周岁的配置文件以及分别提供了电子邮件地址的配置文件。

![](assets/wkf_intersection_example.png)

