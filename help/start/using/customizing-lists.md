---
title: 自定义列表
description: “了解如何在Adobe Campaign Standard中自定义列表屏幕的显示和操作：排序、筛选、删除或复制元素。 列表屏幕会显示一个或多个给定资源的元素。”
audience: start
content-type: reference
topic-tags: discovering-the-interface
feature: Campaigns
role: User
level: Intermediate
exl-id: 651a53b4-e02f-4963-99e6-2e2c324b1c8c
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 2%

---

# 自定义列表{#customizing-lists}

**列表**&#x200B;屏幕允许您显示一个或多个给定资源的元素。

Adobe Campaign有两种类型的列表：

* **同类**&#x200B;列表，当它包含单一类型的资源时。 例如，配置文件列表仅包含配置文件。
* **异类**&#x200B;列表，它包含多种类型的资源。 例如，营销活动列表包含登陆页面、工作流、电子邮件、短信等。

列表将以列的形式显示。每列可以一次按升序或降序排序。

列表中的元素具有一个复选框，允许您选择它们。 通过选择一个或多个元素，您可以执行多种操作，例如编辑、复制和删除这些元素。

将鼠标悬停在列表中的某个元素上时，**快速操作**。 这些操作允许用户对悬停的元素执行各种操作，例如编辑、选择、删除或显示详细信息。

![](assets/overview_list_quickactions.png)

您还可以配置是否显示列表中的列。 添加或删除列：

1. 确保屏幕处于&#x200B;**列表**&#x200B;模式。

   ![](assets/export_list_mode_switch.png)

1. 通过选择操作栏中的![](assets/columnsettings.png)按钮转到列表配置窗口。

   ![](assets/list_configuration1.png)

1. 添加要包含在列表中的列。 为此，请从窗口的左侧选择一列，然后使用操作栏中的![](assets/arrowright.png)按钮添加一列。

   可选择的列对应于列表资源。

   对于每个添加的列，指定是否默认应用排序：

   * **[!UICONTROL NO]**：对列不排序
   * **[!UICONTROL ASC]**：对列应用升序（升序）排序
   * **[!UICONTROL DESC]**：对列应用降序（拒绝）排序。

1. 通过选中与要删除的列对应的框来删除不想显示的列。 然后，使用操作栏中的![](assets/delete.png)按钮确认删除它们。
1. 一旦列表包含正确的列，您就可以通过检查要移动的列来更改它们在列表中的显示顺序。 然后，使用![](assets/arrowdown.png)和![](assets/arrowup.png)箭头。
1. 选择&#x200B;**[!UICONTROL OK]**&#x200B;以确认列表配置。

现在，您的列表会按配置显示。
