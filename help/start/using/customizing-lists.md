---
title: 自定义列表
seo-title: 自定义列表
description: 自定义列表
seo-description: “了解如何在Adobe Campaign Standard中自定义显示屏幕并对其执行操作：对元素进行排序、筛选、删除或复制。列表屏幕显示一个或多个给定资源的元素”。
page-status-flag: 从未激活
uuid: 3350583c-91ca-4ea5-ac14-6b6 f11 c4 a64 a
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: 发现界面
discoiquuid: ba4f766-fdee-4ff0-8fe4-0612ed2 b69 a4
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Customizing lists{#customizing-lists}

**列表** 屏幕允许您显示一个或多个给定资源的元素。

Adobe Campaign具有两种类型的列表：

* **一个均匀** 列表，它包含单个类型的资源。例如，配置文件列表仅包含配置文件。
* A **heterogeneous** list, which is when it contains several types of resources. 例如，营销活动列表包含登陆页面、工作流、电子邮件、SMS等。

列表以列形式显示。每个列一次只能按升序或降序排序一个。

列表中的元素有一个复选框，允许您选择它们。通过选择一个或多个元素，您可以执行多个操作，例如编辑、复制和删除这些元素。

When hovering over an element in the list, **quick actions**. 这些操作允许用户对鼠标悬停的元素执行各种操作，如编辑、选择、删除或显示详细信息。

![](assets/overview_list_quickactions.png)

您还可以配置是否要显示列表中的列。要添加或删除列，请执行以下操作：

1. Make sure that the screen is in **List** mode.

   ![](assets/export_list_mode_switch.png)

1. Go to the list configuration window by selecting the ![](assets/columnsettings.png) button in the action bar.

   ![](assets/list_configuration1.png)

1. 添加要包含在列表中的列。To do this, select a column from the left-hand side of the window, then use the ![](assets/arrowright.png) button from the action bar to add a column.

   可选列与列表资源相对应。

   对于添加的每个列，指定默认情况下是否要应用排序：

   * **[!UICONTROL NO]**：不对列排序
   * **[!UICONTROL ASC]**：在列上应用升序(上升)排序
   * **[!UICONTROL DESC]**：对列应用降序(拒绝)排序。

1. 通过选中与要删除的列对应的框，删除不希望显示的列。Then, use the ![](assets/delete.png) button from the action bar to confirm deleting them.
1. 列表包含正确的列后，您可以通过选中要移动的列来更改在列表中显示它们的顺序。Then, use the ![](assets/arrowdown.png) and ![](assets/arrowup.png) arrows.
1. Confirm your list configuration by selecting **[!UICONTROL OK]**.

现在，您的列表将显示为已配置。
