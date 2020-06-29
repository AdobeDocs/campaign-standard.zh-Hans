---
title: 重复数据删除
description: 外部重复数据删除活动允许您删除入站活动结果中的重复。
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 0%

---


# 重复数据删除{#deduplication}

## 说明 {#description}

![](assets/deduplication.png)

该 **[!UICONTROL Deduplication]** 活动允许您删除入站活动结果中的重复。

## 使用环境 {#context-of-use}

该活动 **[!UICONTROL Deduplication]** 通常在目标活动或导入文件之后以及允许使用目标数据的活动之前使用。

在外部重复数据删除期间，将单独处理入站过渡。 例如，如果用户档案“A”出现在查询1的结果中，也出现在查询2的结果中，则不会消除重复。

因此，建议外部重复数据删除仅具有一个入站过渡。 为此，您可以使用与定位需求(如合并活动、交叉点活动等)相对应的活动来组合不同的查询。 例如：

![](assets/dedup_bonnepratique.png)

**相关主题**

* [用例： 在重复之前识别投放](../../automating/using/identifying-duplicated-before-delivery.md)
* [用例： 从导入的文件中消除重复数据](../../automating/using/deduplicating-data-imported-file.md)

## Configuration {#configuration}

要配置外部重复数据删除活动，必须输入标签、方法和外部重复数据删除条件，以及与结果相关的选项。

1. 将活动拖放 **[!UICONTROL Deduplication]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。

   ![](assets/deduplication_1.png)

1. 选择 **[!UICONTROL Resource type]** 要执行外部重复数据删除的位置：

   * **[!UICONTROL Database resource]** 如果对外部重复数据删除库中已存在的数据执行该数据。 根据 **[!UICONTROL Filtering dimension]** 要 **[!UICONTROL Targeting dimension]**&#x200B;消除重复的数据，选择和。 默认情况下，外部重复数据删除对用户档案 **执行**。
   * **[!UICONTROL Temporary resource]** 如果对工作流的临时外部重复数据删除执行该： 选择包 **[!UICONTROL Targeted set]** 含要重复数据消除的数据。 在导入文件后，或者(例如，使用段代码)对数据库中的数据进行了丰富后，可能会遇到此用例。

1. 选择 **[!UICONTROL Number of unique records to keep]**。 此字段的默认值为1。 值0允许您保留所有重复。

   例如，如果记录A和B被视为记录Y的重复，而记录C被视为记录Z的重复:

   * 如果字段的值为1: 只保留Y和Z记录。
   * 如果字段的值为0: 所有记录都保存了。
   * 如果字段的值为2: 记录C和Z被保留，并且A、B和Y的两个记录被保留，偶然地或取决于此后选择的外部重复数据删除方法。

1. 通过在提 **[!UICONTROL Duplicate identification]** 供的列表中添加条件来定义标准。 指定允许标识相同值的字段和／或表达式: 电子邮件地址、名字、姓氏等。 条件的顺序允许您指定要先处理的条件。
1. 在下拉列表中，选择要 **[!UICONTROL Deduplication method]** 使用的：

   * **[!UICONTROL Choose for me]**: 随机选择要从重复中保留的记录。
   * **[!UICONTROL Following a list of values]**: 允许您为一个或多个字段定义值优先级。 要定义值，请选择一个字段或创建表达式，然后将值添加到相应的表中。 要定义新字段，请单击 **[!UICONTROL Add]** 位于值列表上方的按钮。

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**: 这样，您就可以保留选定表达式的值不为空的记录作为优先级。

      ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**: 这样，您就可以保留输入的表达式值最小或最大的记录。

      ![](assets/deduplication_4.png)

1. 如果需要，可以管理活动 [的过渡](../../automating/using/activity-properties.md) ，以访问出站人口的高级选项。
1. 确认活动的配置并保存工作流。
