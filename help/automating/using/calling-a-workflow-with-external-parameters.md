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

通过Campaign Standard，可使用参数（要定位的受众名称、要导入的文件名、消息内容的一部分等）调用工作流。 这样，您就可以轻松地将Campaign自动化与外部系统集成。

让我们举以下示例，我们希望直接从CMS发送电子邮件。 在这种情况下，您可以配置系统以选择受众，并将电子邮件内容发送至CMS。 单击发送后，将使用这些参数调用Campaign工作流，从而允许您在工作流中使用它们来定义要在投放中使用的受众和URL内容。

使用参数调用工作流的流程如下所示：

1. 在&#x200B;**[!UICONTROL External signal]**&#x200B;活动中声明参数。 请参阅[声明外部信号活动](../../automating/using/declaring-parameters-external-signal.md)中的参数。
1. 配置&#x200B;**[!UICONTROL End]**&#x200B;活动或API调用以定义参数并触发工作流&#x200B;**[!UICONTROL External signal]**&#x200B;活动。 查看[此页面](../../automating/using/defining-parameters-calling-workflow.md)
1. 触发工作流后，参数将摄取到工作流的事件变量中，并可在工作流中使用。 请参阅[此页](../../automating/using/customizing-workflow-external-parameters.md)。

![](assets/extsignal_process.png)
