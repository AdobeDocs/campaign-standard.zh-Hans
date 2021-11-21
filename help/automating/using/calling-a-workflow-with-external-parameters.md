---
title: 概述
description: 本节详细介绍如何使用外部参数调用工作流。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 538056e6-b5c0-4258-a34b-524fe6e3cbbe
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 2%

---

# 概述 {#calling-a-workflow-with-external-parameters}

Campaign Standard允许您使用参数（要定位的受众名称、要导入的文件名、消息内容的一部分等）调用工作流。 这样，您就可以轻松地将Campaign自动化与外部系统集成。

让我们以下示例为例，我们希望直接从CMS发送电子邮件。 在这种情况下，您可以配置系统以选择受众，并通过电子邮件将内容发送到CMS。 单击发送后，将使用这些参数调用Campaign工作流，以便在工作流中使用它们来定义要在投放中使用的受众和URL内容。

使用参数调用工作流的流程如下所示：

1. 在 **[!UICONTROL External signal]** 活动。 请参阅 [声明外部信号活动中的参数](../../automating/using/declaring-parameters-external-signal.md).
1. 配置 **[!UICONTROL End]** 活动或API调用来定义参数并触发工作流 **[!UICONTROL External signal]** 活动。 请参阅 [本页](../../automating/using/defining-parameters-calling-workflow.md)
1. 触发工作流后，会将参数摄取到工作流的事件变量中，并可在工作流中使用。 请参阅[此页](../../automating/using/customizing-workflow-external-parameters.md)。

![](assets/extsignal_process.png)
