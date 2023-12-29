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
ht-degree: 1%

---

# 执行命令 {#execution-commands}

利用操作栏中的图标，可启动、跟踪和修改工作流的执行。 请参阅 [操作栏](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

可用的操作如下：

**开始**

此 ![](assets/play_darkgrey-24px.png) 按钮开始执行工作流，然后该工作流将 **进行中** （蓝色）状态。 如果工作流已暂停，则会恢复它，否则会启动它并激活初始活动。

>[!NOTE]
>
>启动是一个异步过程：请求已保存，并将由工作流执行引擎尽快处理。

**暂停**

此 ![](assets/pause_darkgrey-24px.png) 按钮可暂停执行。 工作流将承受 **警告** （黄色）状态。 在恢复之前，不会激活任何新活动，但不会暂停正在进行的操作。

**停止**

此 ![](assets/stop_darkgrey-24px.png) 按钮停止正在执行的工作流，随后该工作流将 **已完成** （绿色）状态。 如果可能，正在进行的操作会被中断，并且会立即取消导入或正在进行的SQL查询。 您不能从工作流停止的位置恢复工作流。

**重新启动**

此 ![](assets/pauseplay_darkgrey-24px.png) 按钮涉及停止，然后重新启动工作流。 在大多数情况下，这允许您更快地重新启动。 如果停止操作需要花费一定的时间，则自动重新启动也会很有用，因为 ![](assets/play_darkgrey-24px.png) 仅当停止生效时，按钮才可用。

选择工作流中的一个或多个活动后，您还可以执行其他操作，例如：

**立即执行**

此 ![](assets/pending_darkgrey-24px.png) 按钮会尽快启动所选的任何待处理活动。

**正常执行**

此 ![](assets/check_darkgrey-24px.png) 按钮可重新激活任何已暂停或已停用的活动。

**执行已暂停**

此 ![](assets/check_pause_darkgrey-24px.png) 按钮在选定活动处暂停工作流：此任务及其之后的所有任务（在同一分支中）都不会执行。

**无执行**

此 ![](assets/checkdisable.png) 按钮可停用任何选定的活动。

>[!NOTE]
>
>利用快速操作，可访问与某个特定活动相关的不同操作，并在选择活动时显示。
