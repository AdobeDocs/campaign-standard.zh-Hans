---
title: 工作流最佳做法
seo-title: 工作流最佳做法
description: 工作流最佳做法
seo-description: 了解如何应用于工作流程的最佳实践。
page-status-flag: 从未激活
uuid: ff02b74e-53e8-49c6-bf8 e-0c729 ea7 d25
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 工作流常规操作
context-tags: 工作流程，概述；工作流，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: e02ca92032c298fe1b5dbc7094de201d0a106be5

---


# Workflow best practices{#workflow-best-practices}

通过Adobe Campaign，您可以设置所有类型的工作流以执行大量任务。但是，在设计和执行工作流时，您需要非常小心，因为实施不当可能导致性能、错误和平台问题。您可以在下面的最佳实践和疑难解答提示列表中找到。

>[!NOTE]
>
>工作流设计和执行必须由Adobe Campaign高级用户执行。

## Naming{#naming}

为了简化工作流程故障排除，Adobe建议您显式命名工作流并为其添加标签。填写工作流的描述字段以总结要执行的进程，以便操作员能够轻松理解。
如果工作流是涉及多个工作流的流程的一部分，则您可以在输入标签时使用数字来清楚地排序。

例如：

* 001-导入-导入收件人
* 002-导入-导入销售
* 003-导入-导入销售详细信息
* 010-导出-导出交付日志
* 011-导出-导出跟踪日志

## Duplicating workflows{#duplicating-workflows}

您可以复制工作流。In the **[!UICONTROL Marketing Activities]**, hover over the workflow and click **[!UICONTROL Duplicate element]**. 复制后，工作流的修改不会传递到工作流的副本。可以编辑工作流的副本。

![](assets/duplicating_workflow.png)

## Execution{#execution}

### 工作流数量

默认情况下，我们建议不要同时运行20多个有效工作流执行。达到该限制后，工作流将排队，而不会影响性能。同样，Adobe建议您逐步推广工作流决策。
在特定环境下，您可能需要运行20多个工作流。它不适用于等待预定执行的工作流。如果需要，您需要与营销活动专家核对使用案例，并联系Adobe客户服务部门以增加限制。

### 频率

不能每隔十分钟自动执行一次工作流。
活动的重复频率不能少于10分钟。如果重复频率设置为0(也是默认值)，则不考虑此选项，工作流将根据执行频率运行。

### 暂停的工作流程

已停止暂停或失败状态超过天的工作流，以减少磁盘空间。清理任务将显示在工作流日志中。

### Transitions

仍可以执行包含未结束过渡的工作流：它将生成一条警告消息，一旦到达过渡，工作流将暂停，但不会生成错误。您还可以在没有完成设计的情况下启动工作流，并在继续时完成它。

For more information, refer to [Executing workflows](../../automating/using//executing-a-workflow.md).

## Activity{#activity}

### 工作流程设计

To ensure that the workflow ends properly, use an **[!UICONTROL End activity]**. 避免退出工作流的最后一次过渡。

To access the detail view of the transitions, check the **[!UICONTROL Keep interim results]** option in the Execution section of the workflow properties.

>[!CAUTION]
>
>此选项占用大量磁盘空间，旨在帮助您构建工作流并确保正确配置和行为。在生产实例上取消选中。

![](assets/keep_interim_best_practices.png)


### Labelling activities{#activity-labeling}

在开发工作流时，将为所有Adobe Campaign对象生成一个名称，以供所有活动使用。虽然活动的名称是由该工具生成的，但无法编辑，但我们建议在配置时使用显式名称对其进行标记。

### Duplicating activities{#activity-duplicating}

要复制现有活动，您可以使用复制粘贴。这样，您就可以保留最初定义的设置。For more information, refer to [Duplicating workflow activities](../../automating/using/workflow-interface.md).

### Scheduler activity{#acheduler-activity}

When building your workflow, only use one **[!UICONTROL Scheduler activity]** per branch. 如果工作流的同一分支有多个调度程序(相互链接)，执行任务的数量将按指数级乘以，这会大幅超载数据库。

You can preview the next ten executions of your workflows by clicking **[!UICONTROL Preview next executions]**.

![](assets/preview_scheduler.png)

For more information, refer to [Scheduler activity](../../automating/using/scheduler.md).

## Calling workflow with parameters{#workflow-with-parameters}

Make sure that the name and number of parameters are identical to what is defined when calling the workflow (see [Defining the parameters when calling the workflow](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)). 参数的类型还必须与所需的值一致。

Make sure that all the parameters have been declared in the **[!UICONTROL External signal activity]**. 否则，运行活动时将发生错误。

For more information, see [Calling a workflow with external parameters](../../automating/using/calling-a-workflow-with-external-parameters.md).

## Exporting packages{#exporting-packages}

要导出包，导出的资源不能包含默认ID。因此，必须使用Adobe Campaign Standard提供作为标准提供的模板的不同名称更改可导出资源的ID。
For more information, see [Managing packages](../../automating/using/managing-packages.md).

## Exporting lists{#exporting-lists}

The export list option allows you to export a maximum of 100,000 lines by default and defined by the **Nms_ExportListLimit option**. This option can be managed by the functional administrator, under **Administration** &gt; **Application settings** &gt; **Options**.
For more information, see [Exporting lists](../../automating/using/exporting-lists.md).

## Troubleshooting{#workflow-troubleshooting}

Adobe Campaign提供各种日志，以更好地了解您的工作流程问题。

### Using workflow logs{#using-workflow-logs}

您可以访问工作流日志以监视活动的执行。它按时间顺序对执行和执行错误的操作进行索引。
For more information, refer to [Monitoring workflow execution](../../automating/using/executing-a-workflow.md#monitoring).

### Using delivery logs{#using-delivery-logs}

交付日志允许监控交付成功。排除日志会在准备发送过程中返回被排除的消息。发送日志提供每个配置文件的交付状态。
For more information, refer to [Understanding delivery failures](../../sending/using/understanding-delivery-failures.md).

### Using delivery alerting{#delivery-alerting}

交付通知功能是一种警报管理系统，它允许一组用户自动接收通知，其中包含执行其交付的信息。
For more information, refer to [Delivery alerting](../../sending/using/receiving-alerts-when-failures-happen.md).
