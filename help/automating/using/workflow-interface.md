---
title: 工作流界面
seo-title: 工作流界面
description: 工作流界面
seo-description: 了解用于创建、编辑和执行工作流的界面和选项。
page-status-flag: 从未激活
uuid: aafe33ed-fa07-4dd9-825e-242099334f1a
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: about-workflows-and-data-management
discoiquuid: 147fbb0d-17d2-444b-a215-9ad14179c549
context-tags: 工作流，主；工作流，概述
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# 工作流界面{#workflow-interface}

您可以创建工作流来管理营销活动和计划中的整个流程。

工作流编辑屏幕由以下元素组成：

* 调 [色板](#palette)，它引用可用活动。
* 在工 [作区中](#workspace)，可在其中配置和组织活动。
* “ [操作栏](#action-bar)”，它由允许您与工作流和／或其组件交互的按钮组成。
* 快 [速操作](#quick-actions)（显示在所选活动周围）允许您与其交互。

![](assets/wkf_overview.png)

## 调色板 {#palette}

调色板位于屏幕的左侧。 所有可用活动都分为几个类别：

* [定位](../../automating/using/about-targeting-activities.md):特定于定位、操作人口数据和过滤活动的活动
* [执行](../../automating/using/about-execution-activities.md):特定于组织和执行工作流的活动
* [渠道](../../automating/using/about-channel-activities.md):表示不同可用通信渠道的活动
* [数据管理(ETL)](../../automating/using/about-data-management-activities.md):操作数据的特定活动

要使用工作流中调色板中的活动，请将其拖放到工作区中。

必须先配置从调色板添加的每个活动，然后才能启动工作流。

![](assets/workflow_palette.png)

## 工作区 {#workspace}

工作区是工作流编辑器中的中心区域。 正是在此区域，您可以放置活动，使用过渡将它们链接在一起，并配置它们。

要链接两个活动，请将箭头的结尾从第一个活动移动到下一个活动，直到它们连接。 您还可以将活动移到其后面的箭头点，以将其链接到前一个活动。 如果移动任何活动，它们将保持链接。

处理数据的活动之后的过渡包含中间人群。 如果选中工作流属性部分中 **[!UICONTROL Keep interim results]** 的选项，则 **[!UICONTROL Execution]** 可以访问它们。

选择活动后，活动周围会显示快速操作，以便您与其交互。 例如，要配置活动，请选择该活动，然后使用快速操作中 ![](assets/edit_darkgrey-24px_table.png) 的按钮将其打开。

某些功能仅在工作区中启用：

* 通过在活动和过渡周围绘制一个区域来选择这些活动和过渡。
* 按 **Ctrl** +左键单击可选择多个活动和／或过渡。
* 按 **Enter** 可查看当前选定活动或过渡的详细信息。
* 按 **删除** ，以删除当前选定的活动。
* 按 **Ctrl + C** ，复制选定的活动， **** 按Ctrl + v将活动粘贴到工作区中。

![](assets/workflow_workspace.png)

## 操作栏 {#action-bar}

根据工作区中选择的元素或工作流的执行状态，操作栏中可用的按钮可能会有所不同。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>允许您编辑工作流的属性。

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>启动工作流。

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>暂停工作流。

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>中断工作流执行。 无法从停止位置恢复。

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>重新启动工作流。

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>打开工作流的执行日志。

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>启用多选模式。 该工作流必须由至少两个活动组成。

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>禁用多选模式。<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>打开选定的过渡。<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>如果之前已禁用或标记为已暂停，则重新启用选择。<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>在所选活动处暂停工作流。<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>禁用活动。<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>删除选定的活动。<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>复制选定的活动。

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>粘贴已复制的活动。

## 快速操作 {#quick-actions}

选择活动后，活动周围会显示快速操作按钮，允许您与其交互。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>打开选定的活动。

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>复制选定的活动。

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>打开选定电子邮件或短信发送活动的高级选项。

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>如果之前已禁用或标记为已暂停，则重新启用选择。

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>在所选活动处暂停工作流。

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>禁用活动。

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>强制立即处理选择。 此按钮仅可用于“调度程序 <span class="uicontrol">”和</span> “等 <span class="uicontrol">待</span> ”活动。

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>删除选定的活动。

## 复制工作流活动 {#duplicating-workflow-activities}

通过工作区，您可以将工作流活动复制粘贴到同一工作流中或从同一Campaign实例复制到另一个工作流中，从而复制工作流活动。

复制活动后，将保留其整个配置。 对于交付活动（电子邮件、SMS、推送通知……），与活动相连的交付对象重复。

>[!NOTE]
>
>不能将工作流活动从一个实例复制到另一个实例。 无法复制来自技术工作流程的活动。

要复制活动，请按照以下步骤操作：

1. 选择活动，然后单击快 **[!UICONTROL Copy selection]** 速操作中的按钮。

   您还可以使用 **Ctrl + C** （键盘）快捷键。

   ![](assets/wkf_copypaste1.png)

1. 在目标工作流工作区中右键单击，然后单击按 **[!UICONTROL Paste]** 钮。

   您还可以使用 **CTRL + V** Keyboard快捷键。

   ![](assets/wkf_copypaste2.png)

1. 该活动会重复，并且会复制最初配置的所有设置。

还可以复制粘贴多个活动，从而复制整个工作流。

为此，请通过在活动周围绘制一个区域来选择活动。 然后，单 **[!UICONTROL Copy selection]** 击操作栏中的按钮(或按 **Ctrl + C**)。 然后，您可以将它们粘贴到所需位置。

![](assets/wkf_copypaste3.png)

