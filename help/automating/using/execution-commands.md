---
title: 执行命令
description: 了解如何使用工作流执行命令。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: fddd88b1-603a-465b-b5e7-624632c0d5cd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 3%

---

# 执行命令 {#execution-commands}

利用操作栏中的图标，可启动、跟踪和修改工作流的执行。 参见 [操作栏](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

可用的操作如下：

**开始**

此 ![](assets/play_darkgrey-24px.png) 按钮开始执行工作流，然后工作流 **进行中** （蓝色）状态。 如果工作流已暂停，则会恢复该工作流，否则会启动该工作流并激活初始活动。

>[!NOTE]
>
>启动是一个异步过程：请求已保存，并将尽快由工作流执行引擎处理。

**暂停**

此 ![](assets/pause_darkgrey-24px.png) 按钮暂停执行。 工作流将承受 **警告** （黄色）状态。 在恢复之前，不会激活任何新活动，但不会暂停正在进行的操作。

**停止**

此 ![](assets/stop_darkgrey-24px.png) 按钮停止正在执行的工作流，该工作流随后将 **已完成** （绿色）状态。 如果可能，正在进行的操作会中断，并且会立即取消导入或正在进行的SQL查询。 不能从工作流停止的位置恢复工作流。

**重新启动**

此 ![](assets/pauseplay_darkgrey-24px.png) 按钮涉及停止，然后重新启动工作流。 在大多数情况下，这允许您更快地重新启动。 一旦停止需要一定时间，自动重新启动也会很有用，因为 ![](assets/play_darkgrey-24px.png) 仅当停止生效时，按钮才可用。

在工作流中选择了一个或多个活动后，您还可以执行其他操作，例如：

**立即执行**

此 ![](assets/pending_darkgrey-24px.png) 按钮会尽快启动任何选定的待处理活动。

**一般执行**

此 ![](assets/check_darkgrey-24px.png) 按钮可重新激活任何已暂停或已停用的活动。

**执行已暂停**

此 ![](assets/check_pause_darkgrey-24px.png) 按钮在选定活动处暂停工作流：不执行此任务及其之后的所有任务（在同一分支中）。

**无执行**

此 ![](assets/checkdisable.png) 按钮可停用任何选定的活动。

>[!NOTE]
>
>通过快速操作，您可以访问与某个特定活动相关的不同操作，并在选择某个活动时显示。
