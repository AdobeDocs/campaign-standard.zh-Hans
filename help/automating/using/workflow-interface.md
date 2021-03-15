---
solution: Campaign Standard
product: campaign
title: 工作流界面
description: 了解用于创建、编辑和执行工作流的界面和选项。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
context-tags: workflow,main;workflow,overview
feature: 工作流
role: 数据架构师
level: 初学者
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 4%

---


# 工作流界面{#workflow-interface}

您可以创建工作流来管理活动和项目中的整个流程。

工作流编辑屏幕由以下元素组成：

* [调板](#palette)，引用可用活动。
* [工作区](#workspace)，在其中配置和组织活动。
* [操作栏](#action-bar)，由允许您与工作流和/或其组件交互的按钮组成。
* [快速操作](#quick-actions)显示在选定活动周围，允许您与其交互。

![](assets/wkf_overview.png)

## 面板{#palette}

调色板位于屏幕的左侧。 所有可用活动都分为几个类别:

* [定位](../../automating/using/about-targeting-activities.md):活动特定于定位、操作人口数据和过滤活动
* [执行](../../automating/using/about-execution-activities.md):活动特定于组织和执行工作流
* [渠道](../../automating/using/about-channel-activities.md):活动表示不同的可用通信渠道
* [数据管理(ETL)](../../automating/using/about-data-management-activities.md):活动特定于处理数据

要使用工作流中调色板中的活动，请将其拖放到工作区中。

必须先配置从调色板添加的每个活动，然后才能启动工作流。

![](assets/workflow_palette.png)

## 工作区{#workspace}

工作区是工作流编辑器中的中心区域。 您可以在此区域放置活动，使用过渡将它们链接在一起并配置它们。

要链接两个活动，请将箭头的末端从第一个活动移到下一个活动，直到它们连接。 您还可以将活动移向其后面箭头的点，以将其链接到前一个活动。 如果移动任何活动，它们将保持链接。

过渡跟踪处理数据的活动包含中间群体。 如果选中工作流属性的&#x200B;**[!UICONTROL Execution]**&#x200B;部分中的&#x200B;**[!UICONTROL Keep interim results]**&#x200B;选项，则可以访问它们。

>[!CAUTION]
>
>使用此选项会占用大量磁盘空间，其目的在于帮助您构建工作流并确保配置和行为正确。在制作实例中，请不要勾选该选项。


选择活动后，活动周围会显示快速操作，允许您与其交互。 例如，要配置活动，请选择它，然后使用快速操作中的![](assets/edit_darkgrey-24px_table.png)按钮将其打开。

某些功能仅在工作区中启用：

* 通过在活动和过渡周围绘制一个区域来选择它们。
* 按&#x200B;**Ctrl** +左键单击以选择多个活动和/或过渡。
* 按&#x200B;**Enter**&#x200B;视图当前所选活动或过渡的详细信息。
* 按&#x200B;**删除**&#x200B;可删除当前选定的活动。
* 按&#x200B;**Ctrl + C**&#x200B;可复制选定的活动，按&#x200B;**Ctrl + V**&#x200B;可将其粘贴到工作区中。

![](assets/workflow_workspace.png)

## 操作栏{#action-bar}

根据工作区中选择的元素或工作流的执行状态，操作栏中可用的按钮可能会有所不同。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>允许您编辑工作流的属性。

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>开始工作流。

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>暂停工作流。

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>中断工作流执行。无法从停止位置恢复。

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>重新启动工作流。

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>打开工作流的执行日志。

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>启用多选模式。工作流必须由至少两个活动组成。

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>禁用多选模式。<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>打开选定过渡。<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>如果之前已禁用或标记为已暂停，则重新启用选择。<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>在所选活动暂停工作流。<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>禁用活动。<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>删除选定的活动。<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>复制选定的活动。

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>粘贴已复制的活动。

## 快速操作{#quick-actions}

选择活动后，活动周围会显示快速操作按钮，您可以与其交互。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>打开选定活动。

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>复制所选活动。

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>打开选定“电子邮件”或“短信”投放活动的高级选项。

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>如果之前已禁用或标记为已暂停，则重新启用选择。

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>在所选活动暂停工作流。

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>禁用活动。

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>强制立即处理所选内容。此按钮仅适用于<span class="uicontrol">调度程序</span>和<span class="uicontrol">等待</span>活动。

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>删除选定的活动。

## 复制工作流活动{#duplicating-workflow-activities}

通过工作区，您可以通过将工作流活动复制粘贴到同一工作流或从同一活动实例复制到另一个工作流中，来重复工作流。

复制活动后，将保留其整个配置。 对于投放活动（电子邮件、短信、推送通知……），将复制附加到活动的投放对象。

>[!NOTE]
>
>无法将工作流活动从一个实例复制到另一个实例。 无法复制来自技术工作流的活动。

要重复活动，请执行以下步骤：

1. 选择活动，然后单击快速操作中的&#x200B;**[!UICONTROL Copy selection]**&#x200B;按钮。

   您还可以使用&#x200B;**Ctrl + C**&#x200B;键盘快捷键。

   ![](assets/wkf_copypaste1.png)

1. 在目标工作流工作区中右键单击，然后单击&#x200B;**[!UICONTROL Paste]**&#x200B;按钮。

   您还可以使用&#x200B;**CTRL + V**&#x200B;键盘快捷键。

   ![](assets/wkf_copypaste2.png)

1. 该活动是重复的，其中包含已初始配置的所有设置。

您还可以复制粘贴多个活动，从而重复整个工作流。

为此，请通过在活动周围绘制一个区域来选取这些区域。 然后单击操作栏中的&#x200B;**[!UICONTROL Copy selection]**&#x200B;按钮（或按&#x200B;**Ctrl + C**）。 然后，可将其粘贴到所需位置。

![](assets/wkf_copypaste3.png)

