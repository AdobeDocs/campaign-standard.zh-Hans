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
source-git-commit: fd44c6e6d0f6a4ca75b01c99fbae6d9072dd7736

---


# 工作流程最佳做法{#workflow-best-practices}

通过Adobe Campaign，您可以设置所有类型的工作流以执行大量任务。但是，在设计和执行工作流时，您需要非常小心，因为实施不当可能导致性能、错误和平台问题。您可以在下面的最佳实践和疑难解答提示列表中找到。

>[!NOTE]
>
>工作流设计和执行必须由Adobe Campaign高级用户执行。

## 命名命名{#naming}

为了简化工作流程故障排除，Adobe建议您显式命名工作流并为其添加标签。填写工作流的描述字段以总结要执行的进程，以便操作员能够轻松理解。
如果工作流是涉及多个工作流的流程的一部分，则您可以在输入标签时使用数字来清楚地排序。

例如：

* 001-导入-导入收件人
* 002-导入-导入销售
* 003-导入-导入销售详细信息
* 010-导出-导出交付日志
* 011-导出-导出跟踪日志

## 复制工作流{#duplicating-workflows}

您可以复制工作流。在中 **[!UICONTROL Marketing Activities]**，将鼠标悬停在工作流上并单击 **[!UICONTROL Duplicate element]**。复制后，工作流的修改不会传递到工作流的副本。可以编辑工作流的副本。

![](assets/duplicating_workflow.png)

## 执行执行{#execution}

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

有关详细信息，请参阅 [执行工作流](../../automating/using//executing-a-workflow.md)。

## 活动{#activity}

### 工作流程设计

要确保工作流正确结束，请使用一个 **[!UICONTROL End activity]**。避免退出工作流的最后一次过渡。

要访问过渡的详细信息视图，请选中工作流属性的“执行”部分中的 **[!UICONTROL Keep interim results]** 选项。

>[!CAUTION]
>
>此选项占用大量磁盘空间，旨在帮助您构建工作流并确保正确配置和行为。在生产实例上取消选中。

![](assets/keep_interim_best_practices.png)


### 标记活动{#activity-labeling}

在开发工作流时，将为所有Adobe Campaign对象生成一个名称，以供所有活动使用。虽然活动的名称是由该工具生成的，但无法编辑，但我们建议在配置时使用显式名称对其进行标记。

### 复制活动{#activity-duplicating}

要复制现有活动，您可以使用复制粘贴。这样，您就可以保留最初定义的设置。有关详细信息，请参阅 [复制工作流活动](../../automating/using/workflow-interface.md)。

### 调度程序活动{#acheduler-activity}

构建工作流时，每个分支只能使用一 **[!UICONTROL Scheduler activity]** 个分支。如果工作流的同一分支有多个调度程序(相互链接)，执行任务的数量将按指数级乘以，这会大幅超载数据库。

您可以通过单击来预览工作流的下一个执行步骤 **[!UICONTROL Preview next executions]**。

![](assets/preview_scheduler.png)

有关详细信息，请参阅 [调度程序活动](../../automating/using/scheduler.md)。

## 使用参数调用工作流{#workflow-with-parameters}

确保名称和参数的数量与调用工作流时定义的参数相同(请参阅 [在调用工作流时定义参数](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow))。参数的类型还必须与所需的值一致。

确保在中声明了所有参数 **[!UICONTROL External signal activity]**。否则，运行活动时将发生错误。

有关详细信息，请参阅 [调用使用外部参数](../../automating/using/calling-a-workflow-with-external-parameters.md)的工作流。

## 导出包{#exporting-packages}

要导出包，导出的资源不能包含默认ID。因此，必须使用Adobe Campaign Standard提供作为标准提供的模板的不同名称更改可导出资源的ID。
有关详细信息，请参阅 [管理包](../../automating/using/managing-packages.md)。

## 导出列表{#exporting-lists}

导出列表选项允许您默认导出100,000行，并由 **Nms_ ExportListLimit选项定义**。此选项可由职能管理员管理， **[!UICONTROL Administration]** 位于&gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]**。
有关详细信息，请参阅 [导出列表](../../automating/using/exporting-lists.md)。

## 疑难解答{#workflow-troubleshooting}

Adobe Campaign提供各种日志，以更好地了解您的工作流程问题。

### 使用工作流日志{#using-workflow-logs}

您可以访问工作流日志以监视活动的执行。它按时间顺序对执行和执行错误的操作进行索引。“日志”选项卡包含在执行全部或部分选定活动的历史记录中。
任务选项卡详细介绍了活动的执行顺序。要获取有关活动的更多信息，请单击任务。
有关详细信息，请参阅 [监视工作流执行](../../automating/using/executing-a-workflow.md#monitoring)。

#### 数据管理活动疑难解答{#troubleshooting-data-management-activities}

您可以在“日志”选项卡中分析SQL查询。

1. 在工作流工作区中，单击 **[!UICONTROL Edit properties]**。
1. 在 **[!UICONTROL General]** &gt;中 **[!UICONTROL Execution]**，检查和 **[!UICONTROL Save SQL queries in the log]****[!UICONTROL Execute in the engine]** 选择选项并单击 **[!UICONTROL Confirm]**。

**要在日志中查看SQL查询，请执行以下操作：**
1. Click **[!UICONTROL Log and Tasks]**.
1. 在 **[!UICONTROL Logs]** 选项卡中，打开 **[!UICONTROL Search]** 面板。
1. 检查 **[!UICONTROL Display SQL logs only]**。

查询将显示在日志 **[!UICONTROL Message]** 的列中。

### 使用交付日志{#using-delivery-logs}

交付日志允许监控交付成功。排除日志会在准备发送过程中返回被排除的消息。发送日志提供每个配置文件的交付状态。
有关更多信息，请参阅 [了解交付失败](../../sending/using/understanding-delivery-failures.md)。

### 使用交付通知{#delivery-alerting}

交付通知功能是一种警报管理系统，它允许一组用户自动接收通知，其中包含执行其交付的信息。
有关更多信息，请参阅 [交付通知](../../sending/using/receiving-alerts-when-failures-happen.md)。

**相关主题：**

* [错误管理](../../automating/using/executing-a-workflow.md#error-management)
