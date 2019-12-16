---
title: 添加面板
description: 动态报告允许您添加面板以根据所选时间段更好地过滤数据。
page-status-flag: never-activated
uuid: 8e76e837-5efc-4250-8192-dee1a0bd62fe
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: customizing-reports
discoiquuid: f4e1e676-5ca2-4a58-96d7-d378ff803710
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f78e101b8abea3640ad93db6ff53243a42e07086

---


# 添加面板{#adding-panels}

## 添加空白面板 {#adding-a-blank-panel}

要启动报告，您可以向现成的或自定义报告中添加一组面板。 每个面板都包含不同的数据集，并由自由格式表和可视化组成。

此面板允许您根据需要构建报表。 您可以在报表中添加任意数量的面板，以便按不同的时间段过滤数据。

1. 单击“面 **板** ”图标。 您还可以通过单击“插入”选项卡并选择“ **新建空白面板** ”来 **添加面板**。

   ![](assets/dynamic_report_panel_1.png)

1. 将空白面板拖 **放到功能板** 中。

   ![](assets/dynamic_report_panel.png)

您现在可以向面板中添加自由格式表，以开始定位数据。

## 添加自由格式表 {#adding-a-freeform-table}

自由格式表允许您创建一个表，以使用“组件”表中提供的不同度量和维度分析 **数据** 。

每个表和可视化都可调整大小，并且可以移动以更好地自定义您的报表。

1. 单击“面 **板** ”图标。

   ![](assets/dynamic_report_panel_1.png)

1. 将自由格式项 **目拖放** 到功能板中。

   您还可以通过单击“插入”选项卡并选择“新 **建自由形式** ”(New Freeform **)，或者通过单击空面板中** 的“添加自由形式表 **”(Add a freeform table** )来添加表。

   ![](assets/dynamic_report_panel_2.png)

1. 默认 **[!UICONTROL Exclude proof]** 情况下，区段已被选中。 如果需要，可以将选项卡中的某个图标拖放 **[!UICONTROL Segments]** 到顶 **[!UICONTROL Components]** 部栏中来更改它。

   ![](assets/dynamic_report_panel_3.png)

1. 将“组件”选项卡中的 **项目拖放到列** 和行中，以构建表。

   ![](assets/dynamic_report_freeform_3.png)

1. 单击“ **设置** ”图标以更改数据在列中的显示方式。

   ![](assets/dynamic_report_freeform_4.png)

   其 **[!UICONTROL Column settings]** 中包括：

   * **[!UICONTROL Number]**:允许您在列中显示或隐藏摘要编号。
   * **[!UICONTROL Percent]**:允许您在列中显示或隐藏百分比。
   * **[!UICONTROL Interpret zero as no value]**:允许您在值等于零时显示或隐藏。
   * **[!UICONTROL Background]**:允许您在单元格中显示或隐藏水平进度栏。
   * **[!UICONTROL Include retries]**:允许您在结果中包含重试。 这仅适用于 **[!UICONTROL Sent]** 和 **[!UICONTROL Bounces + Errors]**。

1. 选择一行或多行，然后单击“可视化 **”** 图标。 将添加一个可视化，以反映您选择的行。

   ![](assets/dynamic_report_freeform_5.png)

您现在可以根据需要添加任意数量的组件，还可以添加可视化功能以提供数据的图形表示形式。
