---
title: 添加面板
description: 动态报表允许您添加面板，以便根据所选的时间段更好地过滤数据。
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: e48b9630-c5ce-4d5d-90e6-97b77fbe3d50
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 1%

---

# 添加面板{#adding-panels}

## 添加空白面板 {#adding-a-blank-panel}

要启动报表，您可以向现成的或自定义报表添加一组面板。 每个面板都包含不同的数据集，并且由自由格式表和可视化组成。

利用此面板，可根据需要构建报表。 您可以在报表中添加所需数量的面板，以便按不同的时间段过滤数据。

1. 单击 **面板** 图标。 您还可以通过单击 **“插入”选项卡** 选择 **新建空白面板**.

   ![](assets/dynamic_report_panel_1.png)

1. 拖放 **空白面板** 进入功能板。

   ![](assets/dynamic_report_panel.png)

您现在可以向面板中添加一个自由格式表，以开始定位数据。

## 添加自由格式表 {#adding-a-freeform-table}

自由格式表允许您创建一个表格，以使用 **组件** 表。

每个表和可视化图表都可以调整大小，并且可以进行移动以更好地自定义您的报表。

1. 单击 **[!UICONTROL Panels]** 图标。

   ![](assets/dynamic_report_panel_1.png)

1. 拖放 **[!UICONTROL Freeform]** 项目放入功能板。

   您还可以通过单击 **[!UICONTROL Insert]** 选项卡，选择 **[!UICONTROL New Freeform]** 或 **[!UICONTROL Add a freeform table]** 中。

   ![](assets/dynamic_report_panel_2.png)

1. 在 **[!UICONTROL Drop a segment here]** 字段，添加 **[!UICONTROL Segment]** 从 **[!UICONTROL Components]** 选项卡。

   ![](assets/dynamic_report_panel_3.png)

1. 从 **[!UICONTROL Components]** 选项卡来构建表。

   ![](assets/dynamic_report_freeform_3.png)

1. 单击 **[!UICONTROL Settings]** 图标以更改数据在列中的显示方式。

   ![](assets/dynamic_report_freeform_4.png)

   的 **[!UICONTROL Column settings]** 由以下组成：

   * **[!UICONTROL Number]**:允许您在列中显示或隐藏概要数字。
   * **[!UICONTROL Percent]**:允许您在列中显示或隐藏百分比。
   * **[!UICONTROL Interpret zero as no value]**:允许您在值等于零时显示或隐藏。
   * **[!UICONTROL Background]**:用于在单元格中显示或隐藏水平进度栏。
   * **[!UICONTROL Include retries]**:允许您在结果中包含重试。 此选项仅适用于 **[!UICONTROL Sent]** 和 **[!UICONTROL Bounces + Errors]**.

1. 选择一行或多行，然后单击 **[!UICONTROL Visualize]** 图标。 将添加一个可视化，以反映您选择的行。

   ![](assets/dynamic_report_freeform_5.png)

您现在可以根据需要添加任意数量的组件，还可以添加可视化图表，以提供数据的图形表示形式。
