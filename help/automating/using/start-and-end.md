---
title: 开始和结束
description: “开始”和“结束”活动允许您清楚地标记工作流的开始和结束位置。
page-status-flag: 从未激活
uuid: 146b6337-122c-453d-8ffd-5c157db29217
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 执行活动
discoiquuid: a0a8a725-8ede-4626-9798-b86924b58beb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 开始和结束{#start-and-end}

## 说明 {#description}

![](assets/start.png)

![](assets/end.png)

通过 **[!UICONTROL Start]** 和 **[!UICONTROL End]** 活动，您可以清楚地标记工作流的开始和结束位置。

## 使用环境 {#context-of-use}

执行工作流会从未进行入站过渡的活动开始，并在不再有任何任务正在进行时停止。 但是，您可以添加 **[!UICONTROL Start]** 和活 **[!UICONTROL End]** 动以清楚地标记工作流的开始和结束点。 这对于相对复杂的工作流程特别有用。

最好使用活动，而不 **[!UICONTROL End]** 是单独保留工作流的上次过渡，以确保工作流正确结束。

## 配置 {#configuration}

1. 将某个或活动 **[!UICONTROL Start]** 拖放到 **[!UICONTROL End]** 您的工作流中。
1. 将活 **[!UICONTROL Start]** 动置于查询等其他活动之前，并将活动置于 **[!UICONTROL End]** 一系列活动之后。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。
1. 您可以配置 **End** 对象，使其中断工作流的所有正在执行的任务，包括尚未完成的任务。 为此，请选择相应的选项。
1. 确认活动的配置并保存工作流。

## 触发另一个工作流 {#triggering-another-workflow}

使用活动 **[!UICONTROL External signal]** 的选项卡，您可 **[!UICONTROL End]** 以触发另一个工作流。 请参阅“ [External signal](../../automating/using/external-signal.md) （外部信号）”部分。

## Example {#example}

以下示例显示如何使用活动和多个活动执行复 **[!UICONTROL Start]** 杂的工作 **[!UICONTROL End]** 流。 该 **[!UICONTROL Stop all tasks in progress]** 框已选中第一个活 **[!UICONTROL End]** 动。 相应任务完成后，将停止整个工作流：它将具有与选择按钮相同 ![](assets/stop_darkgrey-24px.png) 的效果(请参阅“操作 [栏](../../automating/using/workflow-interface.md#action-bar) ”部分)。

![](assets/wkf_start_end_example.png)

