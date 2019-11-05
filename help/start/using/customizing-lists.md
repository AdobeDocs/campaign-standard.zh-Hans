---
title: 自定义列表
description: “了解如何在Adobe Campaign Standard中自定义显示屏并在列表屏幕上执行操作：排序、筛选、删除或复制元素。 列表屏幕显示一个或多个给定资源的元素。”
page-status-flag: 从未激活
uuid: 3350583c-91ca-4ea5-ac14-6b6f11c4a64a
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 开始
content-type: 参考
topic-tags: 发现界面
discoiquuid: 4ba4f766-fdee-4ff0-8fe4-0612ed2b69a4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 自定义列表{#customizing-lists}

**列表屏** ，您可以显示一个或多个给定资源的元素。

Adobe Campaign有两种类型的列表：

* 同 **构列表** ，即包含单种资源时。 例如，配置文件列表仅包含配置文件。
* 异 **构列表** ，即包含几种类型的资源时。 例如，营销活动列表包含登录页面、工作流、电子邮件、短信等。

列表以列显示。 每列可以按升序或降序一次排序。

列表中的元素有一个复选框，允许您选择这些元素。 通过选择一个或多个元素，您可以执行多个操作，如编辑、复制和删除这些元素。

将鼠标悬停在列表中的元素上时，可快速 **执行操作**。 这些操作允许用户对悬停的元素执行各种操作，如编辑、选择、删除或显示详细信息。

![](assets/overview_list_quickactions.png)

您还可以配置是否显示列表中的列。 要添加或删除列：

1. 确保屏幕处于“列 **表** ”模式。

   ![](assets/export_list_mode_switch.png)

1. 通过选择操作栏中的按钮，转 ![](assets/columnsettings.png) 到列表配置窗口。

   ![](assets/list_configuration1.png)

1. 添加要包含在列表中的列。 为此，请从窗口左侧选择一列，然后使用操作栏 ![](assets/arrowright.png) 中的按钮添加一列。

   可选列与列表资源相对应。

   对于添加的每列，指定是否默认应用排序：

   * **[!UICONTROL NO]**:不对列排序
   * **[!UICONTROL ASC]**:对列应用升序（上升）排序
   * **[!UICONTROL DESC]**:对列应用降序（正在拒绝）排序。

1. 通过选中要删除的列对应的框，删除不希望显示的列。 然后，使用操 ![](assets/delete.png) 作栏中的按钮确认删除它们。
1. 列表包含正确的列后，您可以通过检查要移动的列来更改它们在列表中的显示顺序。 然后，使用 ![](assets/arrowdown.png) 箭头 ![](assets/arrowup.png) 和箭头。
1. 通过选择确认列表配置 **[!UICONTROL OK]**。

现在，您的列表将随您的配置一起显示。
