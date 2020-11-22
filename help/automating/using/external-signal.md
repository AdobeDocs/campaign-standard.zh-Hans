---
solution: Campaign Standard
product: campaign
title: 外部信号
description: 成功满足另一个工作流中的某些条件时，外部信号活动会触发一个工作流。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: signal,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 96%

---


# 外部信号{#external-signal}

## 说明{#description}

![](assets/signal.png)

成功满足另一个工作流中的某些条件时，或通过 REST API 调用时，**[!UICONTROL External signal]** 活动会触发工作流。

## 使用环境{#context-of-use}

**[!UICONTROL External signal]** 活动用于组织和编排不同的流程，这些流程都是进入不同工作流的同一客户历程的一部分。利用该活动，可从另一个工作流启动一个工作流，从而支持更复杂的客户历程，同时能够更好地进行监控，从而出现问题时作出反应。

**[!UICONTROL External signal]** 活动被设计为工作流的第一个活动。它可以从另一个工作流的 **[!UICONTROL End]** 活动或 REST API 调用触发（有关更多信息，请参阅 [API 文档](../../api/using/triggering-a-signal-activity.md)）。

触发时，可以定义外部参数，并可在工作流事件变量中使用。有关使用外部参数调用工作流的详细流程，请参阅[此章节](../../automating/using/calling-a-workflow-with-external-parameters.md)。

>[!NOTE]
>
>活动的触发频度不能超过每 10 分钟一次。

请注意，**[!UICONTROL External signal]** 活动可通过多种不同事件触发。在这种情况下，一旦执行源工作流之一或 API 调用，就会触发 **[!UICONTROL External signal]** 活动。它不要求所有源工作流都已完成。

**相关主题**

* [用例：外部信号活动和数据导入](../../automating/using/external-signal-data-import.md)。
* [用例：调用工作流以使用外部参数从文件创建受众](../../automating/using/use-case-calling-workflow.md)

## 配置{#configuration}

配置外部信号时，必须首先在目标工作流中配置 **[!UICONTROL External signal]** 活动。完成此配置后，此工作流的 **[!UICONTROL External signal]** 活动将可用于配置源工作流的 **[!UICONTROL End]** 活动。

1. 将 **[!UICONTROL External signal]** 活动拖放到目标工作流中。
1. 选择活动，然后使用所显示快捷操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。
1. 编辑活动的标签。配置触发 **[!UICONTROL External signal]** 的源工作流时需要此标签。

   如果要使用参数调用工作流，请使用 **[!UICONTROL Parameters]** 区域声明它们。有关详细信息，请参见[此页面](../../automating/using/declaring-parameters-external-signal.md)。

   ![](assets/external_signal_configuration.png)

1. 确认活动的配置，添加您需要的所有其他活动并保存工作流。

   >[!NOTE]
   >
   >如果要从另一个工作流触发目标工作流，请继续执行以下步骤。如果要通过 REST API 调用触发目标工作流，请查阅 [API 文档](../../api/using/triggering-a-signal-activity.md)，以了解更多详细信息。

1. 打开源工作流并选择一个 **[!UICONTROL End]** 活动。如果没有可用的 **[!UICONTROL End]** 活动，请在工作流分支的最后一个活动之后添加一个。

   默认情况下，部分活动不包含任何叫客过渡。从这些活动的 **[!UICONTROL Properties]** 选项卡中，可以添加叫客过渡。

   例如，在 **[!UICONTROL Update data]** 活动中，转到 **[!UICONTROL Transitions]** 选项卡并选中 **[!UICONTROL Add an outbound transition without the population]** 选项。利用此选项，可添加不包含任何数据且不占用系统上任何不必要空间的过渡。它仅用于连接触发目标工作流的额外 **[!UICONTROL End]** 活动。

   ![](assets/external_signal_empty_transition.png)

1. 在 **[!UICONTROL End]** 活动的 **[!UICONTROL External signal]** 选项卡中，选择目标工作流以及要在该工作流中触发的 **[!UICONTROL External signal]** 活动。

   当您设置 **[!UICONTROL End]** 活动以触发另一个工作流时，其图标会被更新，添加一个额外的信号标志。

   如果要使用参数调用工作流，请使用 **[!UICONTROL Parameters and values]** 区域。有关详细信息，请参见[此页面](../../automating/using/defining-parameters-calling-workflow.md)。

   ![](assets/external_signal_end.png)

1. 保存源工作流。

一旦执行源工作流的 **[!UICONTROL End]** 活动或 REST API 调用，将自动从 **[!UICONTROL External signal]** 活动触发目标工作流。

>[!NOTE]
>
>必须手动启动目标工作流，然后才能触发该活动。启动时，将激活 **[!UICONTROL External activity]** 并等待来自源工作流的信号。
