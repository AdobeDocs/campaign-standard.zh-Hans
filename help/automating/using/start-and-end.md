---
title: 开始和结束
description: 利用 Start 和 End 活动，可明确地标记工作流的开始位置和结束位置。
audience: automating
content-type: reference
topic-tags: execution-activities
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 1dfc547f-747d-403e-a5b7-a68f56191c71
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 97%

---

# 开始和结束{#start-and-end}

## 说明 {#description}

![](assets/start.png)

![](assets/end.png)

利用 **[!UICONTROL Start]** 和 **[!UICONTROL End]** 活动，可明确地标记工作流的开始位置和结束位置。

## 使用环境 {#context-of-use}

执行的工作流属于此类情况：在没有集客过渡的情况下开始执行活动，并在没有任何正在进行的任务时停止。此时，您就可以添加 **[!UICONTROL Start]** 和 **[!UICONTROL End]** 活动明确地标记工作流的开始位置和结束位置。这尤其适合用于相对较复杂的工作流。

最好的做法是使用 **[!UICONTROL End]** 活动，而不是任其留在工作流的最后一个过渡处，以确保工作流正确结束。

## 配置 {#configuration}

1. 将 **[!UICONTROL Start]** 或 **[!UICONTROL End]** 活动拖放到您的工作流中。
1. 将 **[!UICONTROL Start]** 活动放在其他活动（如查询）之前，将 **[!UICONTROL End]** 活动放在一系列活动之后。
1. 选择活动，然后使用所显示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。
1. 您可以配置 **End** 对象，以中断工作流的所有正在进行的任务，包括尚未完成的任务。要实现此目的，请选择相应的选项。
1. 确认活动的配置并保存工作流。

## 触发另一个工作流 {#triggering-another-workflow}

使用 **[!UICONTROL End]** 活动的 **[!UICONTROL External signal]** 选项卡，可以触发另一个工作流。请参阅[外部信号](../../automating/using/external-signal.md)一节。

## 示例 {#example}

以下示例显示如何使用一个 **[!UICONTROL Start]** 活动和多个 **[!UICONTROL End]** 活动执行复杂的工作流。已经为第一个 **[!UICONTROL End]** 活动勾选了 **[!UICONTROL Stop all tasks in progress]** 方框。一旦相应的任务完成，整个工作流将停止：它与选择 ![](assets/stop_darkgrey-24px.png) 按钮具有相同的效果（请参阅[操作栏](../../automating/using/workflow-interface.md#action-bar)一节）。

![](assets/wkf_start_end_example.png)
