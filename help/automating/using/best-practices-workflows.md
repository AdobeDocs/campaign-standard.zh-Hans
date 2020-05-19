---
title: 工作流最佳实践
description: 了解如何将最佳实践应用于您的工作流。
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '1046'
ht-degree: 0%

---


# 工作流最佳实践{#workflow-best-practices}

利用Adobe Campaign，您可以设置所有类型的工作流以执行大范围任务。 但是，在设计和执行工作流时，您需要非常谨慎，因为糟糕的实施可能会导致性能、错误和平台问题。 您可以在下面找到一列表最佳实践和疑难解答提示。

>[!NOTE]
>
>工作流设计和执行必须由Adobe Campaign高级用户执行。

## 命名{#naming}

为了简化工作流程疑难解答，Adobe建议明确命名工作流并添加标签。 填写工作流的描述字段以汇总要执行的过程，以便操作员能够轻松理解它。
如果工作流是涉及多个工作流的流程的一部分，您可以在输入标签时使用数字对它们进行清晰排序。

例如：

* 001 —— 导入——导入收件人
* 002 —— 导入——导入销售
* 003 —— 导入——导入销售详细信息
* 010 —— 导出——导出投放日志
* 011 —— 出口——出口跟踪日志

## 复制工作流{#duplicating-workflows}

您可以重复工作流。 在中， **[!UICONTROL Marketing Activities]**&#x200B;将鼠标悬停在工作流上并单击 **[!UICONTROL Duplicate element]**。 复制后，工作流的修改不会转移到工作流的副本中。 可以编辑工作流的副本。

![](assets/duplicating_workflow.png)

## 执行{#execution}

### 工作流数

默认情况下，我们建议不要同时运行20个以上的活动工作流执行。 在达到该限制后，工作流将排队，以免影响性能。 同样，Adobe建议您分散工作流执行时间。
在特定上下文中，您可能需要运行20多个工作流。 它不适用于等待计划执行的工作流。  如果是，您需要与活动专家核实使用案例，并联系Adobe客户服务部门以提高限制。

### 频率

不能多于每十分钟自动执行一次工作流。
活动的重复频率不能少于10分钟。 如果重复频率设置为0（也是默认值），则不考虑此选项，工作流将根据执行频率运行。

### 暂停的工作流

已暂停或失败状态超过7天的工作流将停止，以减少磁盘空间。 清理任务显示在工作流日志中。

### 过渡

仍可以执行包含未结束过渡的工作流： 它将生成一条警告消息，工作流将在到达过渡后暂停，但不会生成错误。 您还可以开始没有完成设计的工作流，并随时完成它。

有关详细信息，请参阅 [执行工作流](../../automating/using/about-workflow-execution.md)。

### 时区

工作流属性允许您定义默认将在其所有活动中使用的特定时区。 默认情况下，工作流的时区是为当前活动运算符定义的时区。


## 活动{#activity}

### 工作流设计

要确保工作流正常结束，请使用 **[!UICONTROL End activity]**。 避免单独保留工作流的最后过渡。

要访问过渡的详细视图，请选 **[!UICONTROL Keep interim results]** 中工作流属性的“执行”部分中的选项。

>[!CAUTION]
>
>此选项占用大量磁盘空间，旨在帮助您构建工作流并确保正确的配置和行为。 在生产实例中不选中它。

![](assets/keep_interim_best_practices.png)


### 标记活动{#activity-labeling}

在开发工作流时，将为每个活动(如所有Adobe Campaign对象)生成一个名称。 虽然活动的名称由工具生成且无法编辑，但我们建议在配置时用显式名称为其添加标签。

### 复制活动{#activity-duplicating}

要重复现有活动，您可以使用复制粘贴。 这样，您就可以保留最初定义的设置。 有关详细信息，请参阅复 [制工作流活动](../../automating/using/workflow-interface.md)。

### 调度程序活动{#acheduler-activity}

在构建工作流时，每个分支只 **[!UICONTROL Scheduler activity]** 使用一个。 如果工作流的同一分支具有多个调度程序（相互链接），则要执行的任务数将呈指数级增长，这将使数据库过载。

您可以通过单击预览工作流的接下来十个执行 **[!UICONTROL Preview next executions]**。

![](assets/preview_scheduler.png)

有关详细信息，请参阅 [调度程序活动](../../automating/using/scheduler.md)。

## 使用参数调用工作流{#workflow-with-parameters}

确保参数的名称和数量与调用工作流时定义的参数相同(请参 [阅在调用工作流时定义参数](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow))。 参数的类型还必须与预期值一致。

确保已在中声明所有参数 **[!UICONTROL External signal activity]**。 否则，运行活动时将出错。

有关详细信息，请参 [阅使用外部参数调用工作流](../../automating/using/calling-a-workflow-with-external-parameters.md)。

## 导出包{#exporting-packages}

要导出包，导出的资源不能包含默认ID。 因此，必须使用与Adobe Campaign标准提供的标准模板不同的名称来更改可导出资源的ID。
有关详细信息，请参 [阅管理包](../../automating/using/managing-packages.md)。

## 导出列表{#exporting-lists}

导出列表选项默认允许导出最多100,000行，并且由Nms_ExportListLimit选项 **定义**。 此选项可由职能管理员管理，位于> **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** 下 **[!UICONTROL Options]**。
有关详细信息，请参阅 [导出列表](../../automating/using/exporting-lists.md)。

## 故障排除{#workflow-troubleshooting}

Adobe Campaign优惠各种日志以更好地了解您的工作流问题。

### 使用工作流日志{#using-workflow-logs}

您可以访问工作流日志以监视活动的执行。 它按时间顺序对执行的操作和执行错误进行索引。 “日志”选项卡包含在所有或某些选定活动的执行历史记录中。
“任务”标签详细列出了活动的执行顺序。 要获取有关活动的更多信息，请单击任务。
有关详细信息，请参阅监 [视工作流执行](../../automating/using/monitoring-workflow-execution.md)。

#### Troubleshooting data management activities{#troubleshooting-data-management-activities}

您可以在日志选项卡中分析SQL查询。

1. 在工作流工作区中，单击 **[!UICONTROL Edit properties]**。
1. 在> **[!UICONTROL General]** 中 **[!UICONTROL Execution]**，检查和 **[!UICONTROL Save SQL queries in the log]** 选项， **[!UICONTROL Execute in the engine]** 然后单击 **[!UICONTROL Confirm]**。

**要在日志中查看SQL查询:**
1. 单击 **[!UICONTROL Log and Tasks]**.
1. 在选项卡 **[!UICONTROL Logs]** 中，打开该 **[!UICONTROL Search]** 面板。
1. 查 **[!UICONTROL Display SQL logs only]**。

查询显示在 **[!UICONTROL Message]** 日志列中。

### 使用投放日志{#using-delivery-logs}

投放日志可以监控投放的成功。 在准备发送时，排除日志会返回被排除的消息。 发送日志可提供每个投放的用户档案状态。
有关详细信息，请参阅了 [解投放失败](../../sending/using/understanding-delivery-failures.md)。

### 使用投放警报{#delivery-alerting}

投放警报功能是使一组用户能够自动接收包含其投放执行信息的通知的警报管理系统。
有关详细信息，请参阅 [投放警报](../../sending/using/receiving-alerts-when-failures-happen.md)。

**相关主题：**

* [错误管理](../../automating/using/monitoring-workflow-execution.md)
