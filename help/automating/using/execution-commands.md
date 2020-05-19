---
title: 执行命令
description: 了解如何使用工作流执行命令。
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3ed78fd610b0d134cd1e60f34c93161cb1e5c50f
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---


# 执行命令 {#execution-commands}

操作栏中的图标允许您开始、跟踪和修改工作流的执行。 请参阅 [操作栏](../../automating/using/workflow-interface.md#action-bar)。

![](assets/wkf_execution_2.png)

可用的操作如下：

**开始**

按 ![](assets/play_darkgrey-24px.png) 钮开始执行工作流，然后进入“ **进行** ”（蓝色）状态。 如果工作流已暂停，则它将恢复，否则它将启动，并激活初始活动。

>[!NOTE]
>
>启动是一个异步进程： 此时将保存请求，并且工作流执行引擎将尽快处理该请求。

**暂停**

按 ![](assets/pause_darkgrey-24px.png) 钮暂停执行。 该工作流将处于 **警告** （黄色）状态。 新活动在恢复之前不会激活，但正在进行的操作不会暂停。

**停止**

按 ![](assets/stop_darkgrey-24px.png) 钮将停止正在执行的工作流，然后该工作流将进入“已 **完成** ”（绿色）状态。 正在进行的操作会被中断（如果可能），并立即取消导入或正在进行的SQL查询。 无法从工作流停止的位置恢复该工作流。

**重新启动**

该按 ![](assets/pauseplay_darkgrey-24px.png) 钮涉及停止，然后重新启动工作流。 在大多数情况下，这允许您更快地重新启动。 在停止需要一定时间时自动重新启动也很有用，因为只有在停止 ![](assets/play_darkgrey-24px.png) 有效时，按钮才可用。

选择工作流中的一个或多个活动后，您可以执行其他操作，例如：

**立即执行**

该按 ![](assets/pending_darkgrey-24px.png) 钮会开始所有已选择的待处理活动。

**正常执行**

按钮 ![](assets/check_darkgrey-24px.png) 将重新激活任何已暂停或已取消激活的活动。

**已暂停执行**

该按 ![](assets/check_pause_darkgrey-24px.png) 钮在选定活动暂停工作流： 不执行此任务以及随后（在同一分支中）的所有数据。

**无执行**

该按 ![](assets/checkdisable.png) 钮将停用任何选定活动。

>[!NOTE]
>
>快速操作允许您访问与某个特定活动相关的不同操作，并在选择活动时显示这些操作。
