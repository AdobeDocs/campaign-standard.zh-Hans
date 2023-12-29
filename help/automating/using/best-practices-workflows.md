---
title: 工作流最佳实践
description: 了解如何将最佳实践应用于您的工作流。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: 9f5ec2dc-7881-4c68-a5bb-403b01b8b7f8
source-git-commit: 6ca3ffe3ba2cf7629e511e4ba035b170b25ad79e
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 77%

---

# 工作流最佳实践{#workflow-best-practices}

利用 Adobe Campaign，您可以设置所有类型的工作流以执行多种任务。但是，在设计和执行工作流时，您需要非常谨慎，因为糟糕的实施可能会导致性能、错误和平台问题。下方提供了一系列最佳实践和疑难解答提示。

>[!NOTE]
>
>工作流的设计和执行必须由 Adobe Campaign 高级用户执行。

## 命名{#naming}

为了简化工作流程疑难解答，Adobe 建议在为工作流命名并添加标签时使用一些意义明确的词汇。填写工作流的描述字段以汇总要执行的流程，以便操作员能够轻松理解。
如果工作流涉及多个工作流的部分流程，则可以在输入标签时使用数字对它们进行明确排序。

例如：

* 00 1– 导入 – 导入收件人
* 002 – 导入 – 导入销售
* 003 – 导入 – 导入销售详细信息
* 010 – 导出 – 导出投放日志
* 011 – 导出 – 导出跟踪日志

## 复制工作流{#duplicating-workflows}

您可以复制工作流。在 **[!UICONTROL Marketing Activities]** 中，将鼠标指针悬停在工作流上并单击 **[!UICONTROL Duplicate element]**。复制后，对于原工作流的修改不会被应用到该工作流的副本。可以对工作流的副本进行编辑。

![](assets/duplicating_workflow.png)

## 执行{#execution}

### 工作流的数量

默认情况下，我们建议 **不可以同时运行20个以上的活动工作流** （这不适用于等待计划执行的工作流）。 在达到该限制后，工作流将排队等候执行，以免影响性能。

在特定环境中，您需要运行的工作流可能会超过 20 个。如果出现这种情况，您需要与 Campaign 专家核实使用案例，并联系 Adobe 客户关怀部门以提高上限。

>[!IMPORTANT]
>
>即使您未达到20个工作流的阈值，Adobe也建议您 **随时间分布您的工作流执行**. 交错执行工作流将确保提高实例的性能。

在启动工作流之前， [!DNL Campaign Standard] 将检查是否有足够的系统物理内存来运行工作流。 如果没有足够的可用内存，则会出现一条消息，通知您工作流执行将延迟，直到服务器上的负载下降并且系统内存增加。

### 频度

工作流自动执行的频度不能超过每 10 分钟一次。活动的重复频度不能少于 10 分钟。如果重复频度设置为 0（这也是默认值），则不会考虑间隔时间选项，工作流将根据指定的执行频度运行。

### 暂停的工作流

处于暂停或失败状态超过 7 天的工作流将停止，以节省磁盘空间。清理任务会显示在工作流日志中。

### 过渡

包含未终止过渡的工作流仍可以执行：它将生成一条警告消息，工作流将在到达过渡后暂停，但不会生成错误。您也可以启动没有完成设计的工作流，并在运行工作流时完成设计。

有关更多信息，请参见[执行工作流](../../automating/using/about-workflow-execution.md)。

### 时区

利用工作流属性，可定义默认用在其所有活动中的特定时区。默认情况下，工作流的时区就是为当前 Campaign 操作人员定义的时区。

## 活动{#activity}

### 每个工作流的活动数 {#number-activities}

我们建议在单个工作流中使用多达100个活动。 超过100个活动，在设计和配置工作流时，您可能会遇到一些性能问题。

### 工作流设计

要确保工作流正常结束，请避免使用单独保留工作流的最后一个过渡。 **[!UICONTROL End activity]**.

要访问过渡的详细视图，请勾选工作流属性“执行”部分中的 **[!UICONTROL Keep interim results]** 选项。

>[!CAUTION]
>
>使用此选项会占用大量磁盘空间，其目的在于帮助您构建工作流并确保配置和行为正确。在制作实例中，请不要勾选该选项。

![](assets/keep_interim_best_practices.png)


### 标签活动{#activity-labeling}

在开发工作流时，会为每个活动生成一个名称（类似于所有 Adobe Campaign 对象）。虽然活动的名称由工具生成且无法编辑，但我们建议在配置时为其添加明确的标签名称。

### 复制活动{#activity-duplicating}

要复制现有活动，您可以使用复制粘贴操作。这样，您就可以保留最初定义的设置。有关更多信息，请参见[复制工作流](../../automating/using/workflow-interface.md)。

### “调度程序”活动{#acheduler-activity}

在构建工作流时，只能为每个分支使用一个 **[!UICONTROL Scheduler activity]**。如果工作流的同一分支具有多个调度程序（相互链接），则要执行的任务数量将呈指数级增长，这将使数据库严重过载。

您可以通过单击 **[!UICONTROL Preview next executions]** 预览工作流接下来的十项执行。

![](assets/preview_scheduler.png)

有关更多信息，请参见[调度程序活动](../../automating/using/scheduler.md)。

在设计包含多个活动的已计划工作流时，您需要确保在该工作流完成之前不会重新计划该工作流。 要实现此目的，您需要配置工作流，以防止在先前执行的一个或多个任务仍然等待执行时执行该工作流。 有关详细信息，请参见[此页面](../../automating/using/scheduled-workflows-execution.md)。

## 使用参数调用工作流{#workflow-with-parameters}

确保参数的名称和数量与调用工作流时定义的参数相同(请参阅 [此页面](../../automating/using/defining-parameters-calling-workflow.md). 参数的类型还必须与预期值一致。

确保已在 **[!UICONTROL External signal activity]** 中声明了所有的参数。否则，运行活动时将出错。

有关更多信息，请参阅[使用外部参数调用工作流](../../automating/using/calling-a-workflow-with-external-parameters.md)。

## 导出资源包{#exporting-packages}

要导出资源包，导出的资源不能包含默认 ID。因此，必须将可导出资源的 ID 更改为与 Adobe Campaign Standard 标准模板不同的名称。有关更多信息，请参阅[管理资源包](../../automating/using/managing-packages.md)。

## 导出列表{#exporting-lists}

默认情况下，导出列表选项允许导出最多 100,000 行，具体行数由 **Nms_ExportListLimit 选项**&#x200B;定义。功能管理员可通过 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** 管理此选项。
有关更多信息，请参阅[导出列表](../../automating/using/exporting-lists.md)。

## 故障排除{#workflow-troubleshooting}

Adobe Campaign 提供了各种日志以更好地了解您的工作流问题。

### 使用工作流日志{#using-workflow-logs}

您可以访问工作流日志，以监视活动的执行情况。工作流日志按时间顺序对执行的操作和执行错误进行索引。所有或部分选定活动的执行历史记录中包含“日志”选项卡。
“任务”选项卡详细列出了活动的执行顺序。要了解关于活动的更多信息，请单击任务。
有关更多信息，请参见[监控工作流的执行情况](../../automating/using/monitoring-workflow-execution.md)。

#### 数据管理活动的疑难解答{#troubleshooting-data-management-activities}

您可以在 Log 选项卡中分析 SQL 查询。

1. 在工作流的工作区中，单击 **[!UICONTROL Edit properties]**。
1. 在 **[!UICONTROL General]** > **[!UICONTROL Execution]** 中，勾选 **[!UICONTROL Save SQL queries in the log]** 和 **[!UICONTROL Execute in the engine]** 选项，然后单击 **[!UICONTROL Confirm]**。

**要在日志中查看 SQL 查询，请执行以下步骤：**
1. 单击 **[!UICONTROL Log and Tasks]**。
1. 在 **[!UICONTROL Logs]** 选项卡中，打开 **[!UICONTROL Search]** 面板。
1. 勾选 **[!UICONTROL Display SQL logs only]**。

查询显示在日志的 **[!UICONTROL Message]** 列中。

### 使用投放日志{#using-delivery-logs}

利用投放日志，可监控投放成功与否。在发送准备期间，排除日志会返回被排除的消息。发送日志可提供每个用户档案的投放状态。
有关更多信息，请参见[了解投放的失败情况](../../sending/using/understanding-delivery-failures.md)。

### 使用投放警报{#delivery-alerting}

投放警报功能是一个警报管理系统，利用该系统可让一组用户自动接收包含其投放执行信息的通知。
有关更多信息，请参见[投放警报](../../sending/using/receiving-alerts-when-failures-happen.md)。

**相关主题：**

* [错误管理](../../automating/using/monitoring-workflow-execution.md)
