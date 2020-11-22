---
solution: Campaign Standard
product: campaign
title: 自定义列表
description: “了解如何自定义显示屏并在Adobe Campaign Standard的列表屏幕上操作：排序、过滤、删除或复制元素。 列表屏幕显示一个或多个给定资源的元素。”
audience: start
content-type: reference
topic-tags: discovering-the-interface
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 1%

---


# 自定义列表{#customizing-lists}

**列表** 屏幕允许您显示一个或多个给定资源的元素。

Adobe Campaign有两种列表:

* 同 **构列表** ，即当它包含单一类型的资源时。 例如，用户档案列表只包含用户档案。
* 异 **构列表** ，即它包含几种类型的资源。 例如，营销活动的列表包含登陆页、工作流、电子邮件、短信等。

列表以列显示。 每列可以按升序或降序一次排序。

列表中的元素有一个复选框，允许您选择这些元素。 通过选择一个或多个元素，您可以执行多个操作，如编辑、复制和删除这些元素。

将指针悬停在列表中的某个元素上时，可 **以快速操作**。 这些操作允许用户对所覆盖的元素执行各种操作，如编辑、选择、删除或显示详细信息。

![](assets/overview_list_quickactions.png)

您还可以配置是否显示列表中的列。 要添加或删除列，请执行以下操作：

1. 确保屏幕处于 **列表** 。

   ![](assets/export_list_mode_switch.png)

1. 通过选择操作栏中的按钮，转 ![](assets/columnsettings.png) 到列表配置窗口。

   ![](assets/list_configuration1.png)

1. 添加要包含在列表中的列。 为此，请从窗口左侧选择一列，然后使用操作 ![](assets/arrowright.png) 栏中的按钮添加一列。

   可选列与列表资源相对应。

   对于添加的每列，指定是否默认应用排序：

   * **[!UICONTROL NO]**:列上没有排序
   * **[!UICONTROL ASC]**:对列应用升序（上升）排序
   * **[!UICONTROL DESC]**:对列应用降序（拒绝）排序。

1. 通过选中要删除的列对应的框，删除您不希望显示的列。 然后，使用操 ![](assets/delete.png) 作栏中的按钮确认删除它们。
1. 列表包含正确的列后，您可以通过检查要移动的列来更改这些列在列表中的显示顺序。 然后，使用 ![](assets/arrowdown.png) 箭头 ![](assets/arrowup.png) 和箭头。
1. 通过选择确认列表配 **[!UICONTROL OK]**&#x200B;置。

您的列表现在会在您配置时显示。
