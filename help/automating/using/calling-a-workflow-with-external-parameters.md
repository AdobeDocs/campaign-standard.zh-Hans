---
solution: Campaign Standard
product: campaign
title: 概述
description: 本节详细介绍如何使用外部参数调用工作流。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 2%

---


# 概述 {#calling-a-workflow-with-external-parameters}

Campaign Standard允许您调用包含参数(受众名称要目标、要导入的文件名、消息内容的一部分等)的工作流。 这样，您便可以轻松地将活动自动化与外部系统集成。

让我们举一个例子，我们希望直接从CMS发送电子邮件。 在这种情况下，您可以配置系统以选择受众内容并将内容通过电子邮件发送到CMS。 单击“发送”将使用这些参数调用活动工作流，这样您就可以在工作流中使用这些参数来定义要在投放中使用的受众和URL内容。

使用参数调用工作流的过程如下：

1. 在活动中声明参 **[!UICONTROL External signal]** 数。 See [Declaring the parameters in the External signal activity](../../automating/using/declaring-parameters-external-signal.md).
1. 配置 **[!UICONTROL End]** 活动或API调用以定义参数并触发工作流 **[!UICONTROL External signal]** 活动。 See [this page](../../automating/using/defining-parameters-calling-workflow.md)
1. 触发工作流后，参数将被引入工作流的事件变量中，并可在工作流中使用。 请参阅[此页](../../automating/using/customizing-workflow-external-parameters.md)。

![](assets/extsignal_process.png)
