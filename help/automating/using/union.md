---
title: 合并
description: “联合”活动允许您将多个活动的结果重新分组到单个目标中。
page-status-flag: 从未激活
uuid: fafc3ce9-2212-4403-8754-cfbb28ba6e26
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 定位活动
discoiquuid: 99a8c3a5-7d90-4dbb-aa37-1d0a84719cf6
context-tags: union, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 合并{#union}

## 说明 {#description}

![](assets/union.png)

该活 **[!UICONTROL Union]** 动允许您将多个活动的结果重新分组到单个目标中。

>[!NOTE]
>
>这些集合不一定需要是同质的。

## 使用环境 {#context-of-use}

当执 **[!UICONTROL Union]** 行分段、定义受众或准备消息目标时，活动用于合并来自入站过渡的人群。

## 配置 {#configuration}

1. 将活动拖放 **[!UICONTROL Union]** 到工作流中。
1. 将其连接到它前面的其他活动，如查询。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。
1. 选择以 **[!UICONTROL Reconciliation type]** 定义如何处理入站人群之间的对抗中的重复项：

   * **[!UICONTROL Keys only]**:这是默认模式。 当来自不同入站过渡的元素具有相同的键时，该活动仅保留一个元素。 仅当入站群体是同质的时候，才能使用此选项。
   * **[!UICONTROL All shared columns]**:根据与入站过渡相同的所有列对数据进行协调。 因此，您必须选择在出现副本时保留的主集。 如果入站人口定位维度不同，则可以使用此选项。
   * **[!UICONTROL A selection of columns]**:选择此选项可定义将应用数据协调的列列表。 必须首先选择主集（包含源数据），然后选择用于连接的列。

1. 如果 **[!UICONTROL Use common additional data only]** 您希望仅保留所有入站过渡中的其他数据，请选中此框。
1. 如果要限制最终人口的大小，请选中此 **[!UICONTROL Limit size of generated population]** 框。 可以在字段中指定大 **[!UICONTROL Maximum number of records]** 小。
1. 如果需要，可以管理活动的“过 [渡](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) ”以访问计算出的人群的高级选项。
1. 确认活动的配置并保存工作流。

## Example {#example}

以下示例显示了两个查询活动的结果，这些查询活动旨在从Adobe Campaign数据库中重新分组年龄在18到27岁之间的档案和年龄在34到40岁之间的档案。 结果包含两个查询的所有配置文件或配置过程中指定的最大记录数（如果适用）。

![](assets/wkf_union_example.png)