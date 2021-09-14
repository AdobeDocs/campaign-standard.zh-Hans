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
ht-degree: 2%

---

# 执行命令 {#execution-commands}

利用操作栏中的图标，可启动、跟踪和修改工作流的执行。 请参阅[操作栏](../../automating/using/workflow-interface.md#action-bar)。

![](assets/wkf_execution_2.png)

可用的操作如下：

**开始**

![](assets/play_darkgrey-24px.png)按钮开始执行工作流，然后执行工作流&#x200B;**正在进行**（蓝色）状态。 如果暂停了工作流，则会恢复该工作流，否则会启动该工作流，然后激活初始活动。

>[!NOTE]
>
>启动是一个异步过程：请求已保存，工作流执行引擎会尽快处理该请求。

**暂停**

![](assets/pause_darkgrey-24px.png)按钮会暂停执行。 该工作流将处于&#x200B;**警告**（黄色）状态。 在恢复之前不会激活任何新活动，但正在进行的操作不会暂停。

**停止**

![](assets/stop_darkgrey-24px.png)按钮会停止正在执行的工作流，该工作流随后将进入&#x200B;**已完成**（绿色）状态。 正在进行的操作会在可能时中断，并且正在进行的导入或SQL查询会立即取消。 您无法从停止工作流的同一位置恢复工作流。

**重新启动**

![](assets/pauseplay_darkgrey-24px.png)按钮涉及停止，然后重新启动工作流。 在大多数情况下，这允许您更快地重新启动。 在停止需要一定时间后自动重新启动也会非常有用，因为![](assets/play_darkgrey-24px.png)按钮仅在停止有效时才可用。

选择工作流中的一个或多个活动后，您可以执行其他一些操作，例如：

**立即执行**

![](assets/pending_darkgrey-24px.png)按钮会尽快启动所有选定的待定活动。

**正常执行**

![](assets/check_darkgrey-24px.png)按钮可重新激活任何已暂停或已停用的活动。

**已暂停执行**

![](assets/check_pause_darkgrey-24px.png)按钮会在选定的活动中暂停工作流：不会执行此任务及其后所有任务（在同一分支中）。

**不执行**

![](assets/checkdisable.png)按钮可停用任何选定的活动。

>[!NOTE]
>
>快速操作允许您访问与某个特定活动有关的不同操作，并在选择活动时显示该操作。
