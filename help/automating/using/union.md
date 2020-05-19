---
title: 合并
description: 合并活动允许您将多个活动的结果重新分组为单个目标。
page-status-flag: never-activated
uuid: fafc3ce9-2212-4403-8754-cfbb28ba6e26
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 99a8c3a5-7d90-4dbb-aa37-1d0a84719cf6
context-tags: union,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 0%

---


# 合并{#union}

## 说明 {#description}

![](assets/union.png)

该 **[!UICONTROL Union]** 活动允许您将多个活动的结果重新分组为单个目标。

>[!NOTE]
>
>这些集合不一定需要是同质的。

## 使用环境 {#context-of-use}

当执 **[!UICONTROL Union]** 行分段、定义活动或准备消息目标时，受众用于组合来自入站过渡的人口。

## 配置 {#configuration}

1. 将活动拖放 **[!UICONTROL Union]** 到工作流中。
1. 将其连接到前面的其他活动，如查询。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。
1. 选择以 **[!UICONTROL Reconciliation type]** 定义如何处理入站人口之间对抗中的重复:

   * **[!UICONTROL Keys only]**: 这是默认模式。 当来自不同入站活动的元素具有相同的键时，该过渡只保留一个元素。 仅当入站群体是同质的时候，才能使用此选项。
   * **[!UICONTROL All shared columns]**: 根据与入站过渡共同的所有列对帐数据。 因此，您必须选择在发生重复时保留的主集。 如果入站人口定位维度不同，则可以使用此选项。
   * **[!UICONTROL A selection of columns]**: 选择此选项可定义要应用列表协调的列的。 必须先选择主集（其中包含源数据），然后选择用于连接的列。

1. 如果 **[!UICONTROL Use common additional data only]** 您希望仅保留所有入站过渡中的其他数据，请选中此框。
1. 如果要限制最终人口的大小，请选中此 **[!UICONTROL Limit size of generated population]** 框。 可以在字段中指定 **[!UICONTROL Maximum number of records]** 大小。
1. 如果需要，可以管理活动 [的过渡](../../automating/using/activity-properties.md) ，以访问计算人口的高级选项。
1. 确认活动的配置并保存工作流。

## Example {#example}

以下示例显示两个查询活动的结果，这些用户档案旨在从Adobe Campaign数据库重新分组18到27岁的和34到40岁的数据。 结果包含两个查询的所有用户档案或在配置过程中指定的最大记录数（如果适用）。

![](assets/wkf_union_example.png)