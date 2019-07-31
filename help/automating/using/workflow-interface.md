---
title: 工作流界面
seo-title: 工作流界面
description: 工作流界面
seo-description: 学习创建、编辑和执行工作流的界面和选项。
page-status-flag: 从未激活
uuid: aafe33ed-fa07-4dd9-825e-2420939334f1 a
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 关于工作流和数据管理
discoiquuid: 147fbb0d-444b-a215-9ad147 c549 c549
context-tags: 工作流程，主要；工作流，概述
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 6748e59aaeafce9dc6e77dc0664a9024a53c3e35

---


# Workflow interface{#workflow-interface}

您可以创建工作流来管理营销活动和计划中的整个流程。

工作流编辑屏幕由以下元素组成：

* The [Palette](../../automating/using/workflow-interface.md#palette), which references the available activities.
* [在](../../automating/using/workflow-interface.md#workspace)其中配置和组织活动的工作区。
* [操作栏](../../automating/using/workflow-interface.md#action-bar)，由允许您与工作流和/或组件交互的按钮组成。
* [在选定活动周围出现的快速操作](../../automating/using/workflow-interface.md#quick-actions)允许您与之交互。

![](assets/wkf_overview.png)

## Palette {#palette}

调色板位于屏幕的左侧。所有可用的活动都分为几类：

* [定位](../../automating/using/about-targeting-activities.md)：专门用于定位、处理人口数据和过滤活动的活动
* [执行](../../automating/using/about-execution-activities.md)：特定于组织和执行工作流的活动
* [渠道](../../automating/using/about-channel-activities.md)：代表不同可用通信渠道的活动
* [数据管理(ETL)](../../automating/using/about-data-management-activities.md)：用于处理数据的活动

要在工作流中使用调色板中的活动，请将其拖放到工作区中。

在启动工作流之前，必须配置调色板中添加的每个活动。

![](assets/workflow_palette.png)

## Workspace {#workspace}

工作区是工作流编辑器中的中心区域。您可以在此区域中放下活动，使用过渡将它们链接到一起，并对其进行配置。

要链接两个活动，请将箭头的结尾从第一个活动移至以下活动，直到其连接为止。您还可以将活动移动到其后箭头的点，以便将其链接到之前的活动。如果您移动任何活动，它们将保持链接。

过渡处理数据中包含中间人群的活动。You can access them if you check the **[!UICONTROL Keep interim results]** option in the **[!UICONTROL Execution]** section of the workflow properties.

选择活动后，活动周围会出现快速操作，允许您与之交互。For example, to configure an activity, select it then open it using the ![](assets/edit_darkgrey-24px_table.png) button in the quick actions.

某些功能仅在工作区中启用：

* 通过在周围绘制一个区域，选择多个活动和过渡。
* Press **Ctrl** + left click to select several activities and/or transitions.
* Press **Enter** to view the detail of the currently selected activity or transition.
* Press **Delete** to delete the currently selected activity.
* Press **Ctrl + C** to copy the selected activities, and **Ctrl + V** to paste them into the workspace.

![](assets/workflow_workspace.png)

## Action bar {#action-bar}

根据工作区中选择的元素或工作流的执行状态，操作栏中可用的按钮可能会有所不同。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>允许您编辑工作流的属性。

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>启动工作流。

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>暂停工作流。

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>中断工作流执行。无法从停止位置继续。

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>重新启动工作流。

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>打开工作流的执行日志。

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>启用多选模式。工作流必须至少由两个活动组成。

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>禁用多选模式。<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>打开选定的过渡。<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>如果之前已禁用或标记为暂停，则重新启用选择。<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>在选定活动暂停工作流。<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>禁用活动。<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>删除已选中的活动。<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>复制所选活动。

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>粘贴已复制的活动。

## Quick actions {#quick-actions}

选择活动后，活动周围会出现快速操作按钮，允许您与之交互。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>打开选定活动。

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>复制选定活动。

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>打开选中的电子邮件或SMS交付活动的高级选项。

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>如果之前已禁用或标记为暂停，则重新启用选择。

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>在选定活动暂停工作流。

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>禁用活动。

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>强制立即处理选择。This button is only available for the <span class="uicontrol">Scheduler</span> and <span class="uicontrol">Wait</span> activities.

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>删除已选中的活动。

## Duplicating workflow activities {#duplicating-workflow-activities}

工作区可通过将工作流活动复制到同一工作流中，或从同一Campaign实例中复制到另一个工作流，从而重复工作流活动。

复制活动后，将保留其整个配置。对于交付活动(电子邮件、SMS、推送通知…)，附加到活动的交付对象重复。

>[!NOTE]
>
>不能将工作流活动从实例复制到其他实例。技术工作流程中的活动无法重复。

要复制活动，请按照以下步骤操作：

1. Select the activity, then click the **[!UICONTROL Copy selection]** button from the quick actions.

   You can also use the **Ctrl + C** keyboard shortcut.

   ![](assets/wkf_copypaste1.png)

1. Right-click in the target workflow workspace, then click the **[!UICONTROL Paste]** button.

   You can also use the **CTRL + V** keyboard shortcut.

   ![](assets/wkf_copypaste2.png)

1. 活动重复，所有最初配置的设置都是重复的。

还可以复制多个激活项，使您能够复制整个流程。

为此，请通过在周围绘制一个区域来选择活动。then click the **[!UICONTROL Copy selection]** button from the action bar (or press **Ctrl + C**). 然后，您可以将其粘贴到所需的位置。

![](assets/wkf_copypaste3.png)

