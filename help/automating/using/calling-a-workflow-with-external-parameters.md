---
solution: Campaign Standard
product: campaign
title: 概述
description: 本节详细说明如何使用外部参数调用工作流。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 3%

---


# 概述 {#calling-a-workflow-with-external-parameters}

Campaign Standard允许您使用参数(要导入的受众名、要导入的文件名、消息内容的一部分等)调用工作流。 这样，您就可以轻松地将活动自动化与外部系统集成。

让我们举下例，我们希望从CMS直接发送电子邮件。 在这种情况下，您可以配置系统以选择受众内容并将内容通过电子邮件发送到CMS。 单击“发送”将使用这些参数调用活动工作流，这样您就可以在工作流中使用它们来定义要在投放中使用的受众和URL内容。

使用参数调用工作流的过程如下：

1. 在&#x200B;**[!UICONTROL External signal]**&#x200B;活动中声明参数。 请参阅[在外部信号活动](../../automating/using/declaring-parameters-external-signal.md)中声明参数。
1. 配置&#x200B;**[!UICONTROL End]**&#x200B;活动或API调用以定义参数并触发工作流&#x200B;**[!UICONTROL External signal]**&#x200B;活动。 请参阅[此页](../../automating/using/defining-parameters-calling-workflow.md)
1. 触发工作流后，这些参数将被引入工作流的事件变量中，并可在工作流中使用。 请参阅[此页](../../automating/using/customizing-workflow-external-parameters.md)。

![](assets/extsignal_process.png)
