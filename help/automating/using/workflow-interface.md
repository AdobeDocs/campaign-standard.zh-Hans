---
title: 工作流界面
description: 了解用于创建、编辑和执行工作流的界面和选项。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
context-tags: workflow,main;workflow,overview
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: a3f35bb9-e61e-4f3f-b855-1d677422f75a
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 4%

---

# 工作流界面{#workflow-interface}

您可以创建工作流以管理营销策划和项目中的整个流程。

工作流编辑屏幕由以下元素组成：

* 引用可用活动的[调色板](#palette)。
* 配置和组织活动的[Workspace](#workspace)。
* [操作栏](#action-bar)由按钮组成，允许您与工作流和/或其组件交互。
* 所选活动周围显示的[快速操作](#quick-actions)允许您与其交互。

![](assets/wkf_overview.png)

![](assets/do-not-localize/how-to-video.png) [了解如何在视频中构建工作流](#video)

## 调色板 {#palette}

面板位于屏幕的左侧。 所有可用的活动都分为几个类别：

* [定位](../../automating/using/about-targeting-activities.md)：特定于定位、处理群体数据和过滤活动的活动
* [执行](../../automating/using/about-execution-activities.md)：特定于组织和执行工作流的活动
* [渠道](../../automating/using/about-channel-activities.md)：表示不同可用通信渠道的活动
* [数据管理(ETL)](../../automating/using/about-data-management-activities.md)：特定于处理数据的活动

要在工作流中使用面板中的活动，请将其拖放到工作区中。

在启动工作流之前，您必须配置从面板添加的每个活动。

![](assets/workflow_palette.png)

## 工作区 {#workspace}

工作区是工作流编辑器中的中心区域。 在此区域中，您可以删除活动，使用过渡将它们链接在一起，然后配置它们。

要链接两个活动，请将箭头的结尾从第一个活动上移动到后续活动，直到它们连接为止。 您还可以将活动向着它后面的箭头点移动，以便将其链接到前一个活动。 如果移动任何活动，则它们将保持链接。

在处理数据的活动之后的过渡包含中间群体。 如果选中工作流属性&#x200B;**[!UICONTROL Keep interim results]**&#x200B;部分中的&#x200B;**[!UICONTROL Execution]**&#x200B;选项，则可以访问它们。

>[!CAUTION]
>
>使用此选项会占用大量磁盘空间，其目的在于帮助您构建工作流并确保配置和行为正确。在生产实例中，请不要勾选该选项。


选择活动后，会在活动周围显示快速操作，以便您与之交互。 例如，要配置活动，请选择该活动，然后使用快速操作中的![](assets/edit_darkgrey-24px_table.png)按钮将其打开。

某些功能仅在工作区中启用：

* 通过在其周围绘制区域来选择多个活动和过渡。
* 按&#x200B;**Ctrl** +左键单击可选择多个活动和/或过渡。
* 按&#x200B;**Enter**&#x200B;查看当前选定活动或过渡的详细信息。
* 按&#x200B;**删除**&#x200B;可删除当前选定的活动。
* 按&#x200B;**Ctrl + C**&#x200B;以复制所选的活动，按&#x200B;**Ctrl + V**&#x200B;以将其粘贴到工作区中。

![](assets/workflow_workspace.png)

## 操作栏 {#action-bar}

根据在工作区中选择的元素或工作流的执行状态，操作栏中可用的按钮可能会有所不同。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>允许您编辑工作流的属性。

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>启动工作流。

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>暂停工作流。

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>中断工作流执行。 无法从停止的位置恢复。

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>重新启动工作流。

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>打开工作流的执行日志。

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>启用多选模式。 工作流必须至少由两个活动组成。

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>禁用多选模式。<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>打开所选的过渡。<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>如果之前已禁用或标记为已暂停，则重新启用选择。<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>在所选活动中暂停工作流。<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>禁用该活动。<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>删除选定的活动。<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>复制选定的活动。

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>粘贴已复制的活动。

## 快速操作 {#quick-actions}

选择活动后，该活动周围会显示快速操作按钮，以便您与之交互。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>打开选定的活动。

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>复制所选的活动。

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>打开所选电子邮件或短信投放活动的高级选项。

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>如果之前已禁用或标记为已暂停，则重新启用选择。

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>在选定活动中暂停工作流。

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>禁用该活动。

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>强制立即处理所选内容。 此按钮仅适用于<span class="uicontrol">计划程序</span>和<span class="uicontrol">等待</span>活动。

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>删除选定的活动。

## 复制工作流活动 {#duplicating-workflow-activities}

利用工作区，您可以复制粘贴到同一工作流中的工作流活动，或复制到同一Campaign实例的其他工作流中，以复制工作流活动。

活动复制后，将保留其整个配置。 对于投放活动（电子邮件、短信、推送通知……），会复制附加到活动的投放对象。

>[!NOTE]
>
>无法将工作流活动从一个实例复制到另一个实例。 技术工作流中的活动无法复制。

要复制活动，请执行以下步骤：

1. 选择活动，然后单击快速操作中的&#x200B;**[!UICONTROL Copy selection]**&#x200B;按钮。

   您还可以使用&#x200B;**Ctrl + C**&#x200B;键盘快捷键。

   ![](assets/wkf_copypaste1.png)

1. 在目标工作流工作区中右键单击，然后单击&#x200B;**[!UICONTROL Paste]**&#x200B;按钮。

   您还可以使用&#x200B;**CTRL + V**&#x200B;键盘快捷键。

   ![](assets/wkf_copypaste2.png)

1. 活动重复，其中包含最初配置的所有设置。

也可以复制粘贴多个活动，从而复制整个工作流。

要实现此目的，请通过在其周围绘制区域来选择活动。 然后单击操作栏中的&#x200B;**[!UICONTROL Copy selection]**&#x200B;按钮（或按&#x200B;**Ctrl + C**）。 然后，可以将它们粘贴到所需的位置。

![](assets/wkf_copypaste3.png)

## 教程视频 {#video}

本视频说明如何创建工作流。

>[!VIDEO](https://video.tv.adobe.com/v/27577?captions=chi_hans&quality=12)

[此处](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hans)提供了其他Campaign Standard操作方法视频。
