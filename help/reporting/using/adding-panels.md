---
solution: Campaign Standard
product: campaign
title: 添加面板
description: 动态报表允许您添加面板，以便根据所选的时间段更好地过滤数据。
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: 报告
role: Leader
level: Intermediate
exl-id: e48b9630-c5ce-4d5d-90e6-97b77fbe3d50
source-git-commit: 8062995481a889d8865267e6134efa74648753f6
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 1%

---

# 添加面板{#adding-panels}

## 添加空白面板 {#adding-a-blank-panel}

要启动报表，您可以向现成的或自定义报表添加一组面板。 每个面板都包含不同的数据集，并且由自由格式表和可视化组成。

利用此面板，可根据需要构建报表。 您可以在报表中添加所需数量的面板，以便按不同的时间段过滤数据。

1. 单击&#x200B;**面板**&#x200B;图标。 也可以通过单击&#x200B;**插入选项卡**&#x200B;并选择&#x200B;**新建空白面板**&#x200B;来添加面板。

   ![](assets/dynamic_report_panel_1.png)

1. 将&#x200B;**空白面板**&#x200B;拖放到功能板中。

   ![](assets/dynamic_report_panel.png)

您现在可以向面板中添加一个自由格式表，以开始定位数据。

## 添加自由格式表 {#adding-a-freeform-table}

自由格式表允许您创建一个表，以使用&#x200B;**组件**&#x200B;表中提供的不同量度和维度来分析数据。

每个表和可视化图表都可以调整大小，并且可以进行移动以更好地自定义您的报表。

1. 单击&#x200B;**[!UICONTROL Panels]**&#x200B;图标。

   ![](assets/dynamic_report_panel_1.png)

1. 将&#x200B;**[!UICONTROL Freeform]**&#x200B;项目拖放到功能板中。

   您还可以通过单击&#x200B;**[!UICONTROL Insert]**&#x200B;选项卡并选择&#x200B;**[!UICONTROL New Freeform]**&#x200B;或在空面板中单击&#x200B;**[!UICONTROL Add a freeform table]**&#x200B;来添加表。

   ![](assets/dynamic_report_panel_2.png)

1. 在&#x200B;**[!UICONTROL Drop a segment here]**&#x200B;字段中，将&#x200B;**[!UICONTROL Components]**&#x200B;选项卡中的&#x200B;**[!UICONTROL Segment]**&#x200B;添加到顶部栏。

   ![](assets/dynamic_report_panel_3.png)

1. 将&#x200B;**[!UICONTROL Components]**&#x200B;选项卡中的项目拖放到列和行中，以构建表。

   ![](assets/dynamic_report_freeform_3.png)

1. 单击&#x200B;**[!UICONTROL Settings]**&#x200B;图标以更改数据在列中的显示方式。

   ![](assets/dynamic_report_freeform_4.png)

   **[!UICONTROL Column settings]**&#x200B;由以下部分组成：

   * **[!UICONTROL Number]**:允许您在列中显示或隐藏概要数字。
   * **[!UICONTROL Percent]**:允许您在列中显示或隐藏百分比。
   * **[!UICONTROL Interpret zero as no value]**:允许您在值等于零时显示或隐藏。
   * **[!UICONTROL Background]**:用于在单元格中显示或隐藏水平进度栏。
   * **[!UICONTROL Include retries]**:允许您在结果中包含重试。此值仅适用于&#x200B;**[!UICONTROL Sent]**&#x200B;和&#x200B;**[!UICONTROL Bounces + Errors]**。

1. 选择一行或多行，然后单击&#x200B;**[!UICONTROL Visualize]**&#x200B;图标。 将添加一个可视化，以反映您选择的行。

   ![](assets/dynamic_report_freeform_5.png)

您现在可以根据需要添加任意数量的组件，还可以添加可视化图表，以图形形式表示您的数据。
