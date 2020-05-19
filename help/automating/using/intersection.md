---
title: 交叉
description: 交叉活动允许您仅保留活动中不同入站群体通用的元素。
page-status-flag: never-activated
uuid: a60f9811-0158-44b3-952b-392685c006cc
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 7a107d6b-edc3-44c3-bbb7-ba3dec8e43f9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---


# 交叉{#intersection}

## 说明 {#description}

![](assets/intersection.png)

活动 **[!UICONTROL Intersection]** 允许您仅保留活动中不同入站群体通用的元素。

## 使用环境 {#context-of-use}

该 **[!UICONTROL Intersection]** 活动通常用于对来自入站过渡的人群进行额外过滤。

## 配置 {#configuration}

1. 将活动拖放 **[!UICONTROL Intersection]** 到工作流中。
1. 将其连接到前面的其他活动，如查询。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。
1. 选择 **[!UICONTROL Reconciliation type]**:

   * **[!UICONTROL Keys only]**: 默认模式。 当来自不同入站活动的元素具有相同的键时，该过渡只保留一个元素。
   * **[!UICONTROL All shared columns]**: 数据根据与入站过渡通用的列进行调节。 因此，您必须选择主集作为比较的基础。 如果入站人口定位维度不同，则可以使用此选项。
   * **[!UICONTROL A selection of columns]**: 选择此选项可定义要应用列表对帐的列的。 必须先选择主集（包含源数据的主集），然后指定用于连接的字段。

1. 如果 **[!UICONTROL Use common additional data only]** 您希望仅保留所有入站过渡中的其他数据，请选中此框。
1. 如果需要，可以管理活动 [的过渡](../../automating/using/activity-properties.md) ，以访问出站人口的高级选项。
1. 确认活动的配置并保存工作流。

## Example {#example}

以下示例显示了两个查询活动之间的交集。 此处使用它来查看Adobe Campaign库并检索年龄在18到27岁之间的用户档案和已提供电子邮件地址的用户档案。

![](assets/wkf_intersection_example.png)

