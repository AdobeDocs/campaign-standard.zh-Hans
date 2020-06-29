---
title: 外部信号
description: 当在另一个工作流中成功满足某些条件时，外部信号活动会触发一个工作流。
page-status-flag: never-activated
uuid: 884b6daf-bfd9-440b-8336-004b80c76def
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 911c71b5-da8b-4916-b645-13bba6d21715
context-tags: signal,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 16afc307df6902584624d6457954a472b11c5129
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 3%

---


# 外部信号{#external-signal}

## 说明 {#description}

![](assets/signal.png)

当在 **[!UICONTROL External signal]** 另一个工作流或REST API调用中成功满足某些条件时，活动会触发工作流。

## 使用环境 {#context-of-use}

该活动 **[!UICONTROL External signal]** 用于组织和编排不同的流程，这些流程是进入不同工作流的同一客户旅程的一部分。 它允许将一个工作流与另一个工作流进行开始，从而支持更复杂的客户旅程，同时能够更好地监控并在出现问题时做出反应。

该 **[!UICONTROL External signal]** 活动设计为作为工作流的第一个活动。 它可以从另一个工 **[!UICONTROL End]** 作流程的活动或REST API调用中触发(有关详细信息，请参阅 [API文档](../../api/using/triggering-a-signal-activity.md))。

触发时，可以定义外部参数，并在工作流事件变量中可用。 使用外部参数调用工作流的过程在本节中 [有详细介绍](../../automating/using/calling-a-workflow-with-external-parameters.md)。

>[!NOTE]
>
>活动无法比每10分钟触发一次更频繁。

请注意， **[!UICONTROL External signal]** 活动可以从多个不同事件触发。 在这种情况下， **[!UICONTROL External signal]** 一旦执行源工作流或API调用之一，就会触发该调用。 它不要求所有源工作流都已完成。

**相关主题**

* [用例： 外部信号活动和数据导入](../../automating/using/external-signal-data-import.md)。
* [用例： 调用工作流以使用外部参数从文件创建受众](../../automating/using/calling-a-workflow-with-external-parameters.md#use-case)

## Configuration {#configuration}

配置外部信号时，首先在目标工作流中配 **[!UICONTROL External signal]** 置活动很重要。 完成此配置后，此工 **[!UICONTROL External signal]** 作流的活动将可用于配置源工作流 **[!UICONTROL End]** 的活动。

1. 将活动拖放 **[!UICONTROL External signal]** 到目标工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。
1. 编辑活动的标签。 配置触发源工作流时需要此标签 **[!UICONTROL External signal]**。

   如果要使用参数调用工作流，请使用 **[!UICONTROL Parameters]** 区域声明它们。 如需详细信息，请参阅[此部分](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity)。

   ![](assets/external_signal_configuration.png)

1. 确认活动的配置，添加您需要的任何其他活动并保存工作流。

   >[!NOTE]
   >
   >如果要从另一个工作流触发目标工作流，请继续执行以下步骤。 如果要通过REST API调用触发目标工作流，请查阅API [文档](../../api/using/triggering-a-signal-activity.md) ，以获取更多详细信息。

1. 打开源工作流并选择一个 **[!UICONTROL End]** 活动。 如果没有可 **[!UICONTROL End]** 用活动，请在工作流分支的最后一个活动之后添加一个。

   默认情况下，某些活动没有任何出站过渡。 从这些 **[!UICONTROL Properties]** 活动的选项卡中，可以添加出站过渡。

   例如，在活动 **[!UICONTROL Update data]** 中，转到选 **[!UICONTROL Transitions]** 项卡并选中 **[!UICONTROL Add an outbound transition without the population]** 选项。 此选项允许添加不包含任何过渡且不占用系统上任何不必要的空间。 它仅用于连接触发目标工 **[!UICONTROL End]** 作流的额外活动。

   ![](assets/external_signal_empty_transition.png)

1. 在活动 **[!UICONTROL External signal]** 的选项卡 **[!UICONTROL End]** 中，选择目标工作流以及要在该工作流 **[!UICONTROL External signal]** 中触发的活动。

   当您设置活动以触 **[!UICONTROL End]** 发另一个工作流时，其图标会被更新，并带有一个附加的信号符号。

   如果要使用参数调用工作流，请使用该 **[!UICONTROL Parameters and values]** 区域。 如需详细信息，请参阅[此部分](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)。

   ![](assets/external_signal_end.png)

1. 保存源工作流。

一旦执 **[!UICONTROL End]** 行源工作流或REST API调用的活动，将从活动自动触发目标工作流 **[!UICONTROL External signal]** 。

>[!NOTE]
>
>必须手动启动目标工作流，然后才能触发它。 启动时，将 **[!UICONTROL External activity]** 激活源工作流并等待源工作流中的信号。
