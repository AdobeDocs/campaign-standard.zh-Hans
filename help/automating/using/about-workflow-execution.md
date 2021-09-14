---
title: 关于工作流执行
description: 了解有关工作流执行的更多信息。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 3b95fc66-d6f4-44b2-be33-925c1109a57f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 8%

---

# 关于工作流执行 {#about-workflow-execution}

工作流始终手动启动。 但是，启动后，它可能会保持不活动状态，具体取决于[调度程序](../../automating/using/scheduler.md)活动中指定的信息。

>[!CAUTION]
>
> Adobe建议客户优先考虑执行工作流，并运行多达20个并发工作流，以始终如一地在您的实例中实现最佳性能。 可能计划并发执行超过二十次的工作流，默认情况下将按顺序执行。 您可以通过向客户关怀团队提交票证，为并发工作流执行的最大次数调整默认设置。

与执行相关的操作（开始、停止、暂停等） 是&#x200B;**异步**&#x200B;进程：命令已保存，一旦服务器可用于应用该命令，该命令将生效。

在工作流中，每个活动的结果通常通过过渡发送到下一个活动，由箭头表示。

如果某个过渡未链接到目标活动，则该过渡将取消终止。

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>包含未终止过渡的工作流仍可以执行：将生成警告消息，工作流在到达过渡后将暂停，但不会生成错误。 您还可以在未完全完成设计的情况下启动工作流，并在继续时完成该工作流。

执行活动后，在过渡中发送的记录数会显示在该活动上方。

![](assets/wkf_transition_count.png)

您可以打开过渡，检查在执行工作流期间或执行工作流之后发送的数据是否正确。您可以查看数据和数据结构。

默认情况下，只能访问工作流最后一个过渡的详细信息。 要访问上述活动的结果，您需要先查看工作流属性&#x200B;**[!UICONTROL Execution]**&#x200B;部分中的&#x200B;**[!UICONTROL Keep interim results]**&#x200B;选项，然后再启动工作流。

>[!NOTE]
>
>此选项占用大量内存，旨在帮助构建工作流并确保其配置和行为正确。 在制作实例中，请不要勾选该选项。

打开过渡时，您可以编辑其&#x200B;**[!UICONTROL Label]**&#x200B;或将&#x200B;**[!UICONTROL Segment code]**&#x200B;链接到该过渡。 为此，请编辑相应的字段并确认修改。

使用Campaign StandardREST API，您可以&#x200B;**开始**、**暂停**、**恢复**&#x200B;和&#x200B;**停止**&#x200B;工作流。 您可以在[API文档中找到REST调用的更多详细信息和示例。](../../api/using/controlling-a-workflow.md)
