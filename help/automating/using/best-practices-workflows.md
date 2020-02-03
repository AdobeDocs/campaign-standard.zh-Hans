---
title: 工作流程最佳实践
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
source-git-commit: accc382ca1543d648e60d53cab338537fd9ea3ef

---


# 工作流最佳实践{#workflow-best-practices}

借助Adobe Campaign，您可以设置所有类型的工作流以执行大范围的任务。 但是，在设计和执行工作流时，您需要非常小心，因为糟糕的实施可能会导致性能、错误和平台问题。 您可以在下面找到最佳实践和疑难解答提示列表。

>[!NOTE]
>
>工作流设计和执行必须由Adobe Campaign高级用户执行。

## 命名{#naming}

为了简化工作流疑难解答，Adobe建议明确命名工作流并为其添加标签。 填写工作流的描述字段以汇总要执行的过程，以便操作员能够轻松理解它。
如果工作流是涉及多个工作流的流程的一部分，您可以在输入标签时使用数字对它们进行清晰排序。

例如：

* 001 —— 导入——导入收件人
* 002 —— 导入——导入销售
* 003 —— 导入——导入销售详细信息
* 010 —— 导出——导出交付日志
* 011 —— 导出——导出跟踪日志

## 复制工作流{#duplicating-workflows}

您可以复制工作流。 在中， **[!UICONTROL Marketing Activities]**将鼠标悬停在工作流上并单击**[!UICONTROL Duplicate element]**。 复制后，工作流的修改不会转移到工作流的副本中。 可以编辑工作流的副本。

![](assets/duplicating_workflow.png)

## 执行{#execution}

### 工作流数

默认情况下，我们建议不要同时运行超过20个活动工作流执行。 达到该限制后，工作流将排队以不影响性能。 同样，Adobe建议您随着时间推移分散工作流程执行。
在特定的上下文中，您可能需要运行20多个工作流。 它不适用于等待计划执行的工作流。  如果是，您需要与Campaign专家核实使用案例，并联系Adobe客户关怀以提高限制。

### 频率

不能多于每十分钟自动执行一次工作流。
活动的重复频率不能少于10分钟。 如果重复频率设置为0（也是默认值），则不考虑此选项，并将根据执行频率运行工作流。

### 暂停的工作流

已暂停或失败状态超过7天的工作流将停止，以消耗较少的磁盘空间。 清理任务显示在工作流日志中。

### 过渡

仍然可以执行包含未结束过渡的工作流：它将生成一条警告消息，工作流将在到达过渡后暂停，但不会生成错误。 您还可以在没有完成设计的情况下启动工作流，并在继续时完成它。

有关详细信息，请参阅执 [行工作流](../../automating/using//executing-a-workflow.md)。

### 时区

工作流属性允许您定义一个特定时区，默认情况下该时区将用于其所有活动。 默认情况下，工作流的时区是为当前营销活动操作员定义的时区。


## 活动{#activity}

### 工作流程设计

要确保工作流正常结束，请使用 **[!UICONTROL End activity]**。 避免将工作流的上次过渡保留在其自身。

要访问过渡的详细视图，请选中工 **[!UICONTROL Keep interim results]**作流属性的“执行”部分中的选项。

>[!CAUTION]
>
>此选项占用大量磁盘空间，旨在帮助您构建工作流并确保正确的配置和行为。 在生产实例中不选中它。

![](assets/keep_interim_best_practices.png)


### 标签活动{#activity-labeling}

在开发工作流程时，会为每个活动（如所有Adobe Campaign对象）生成一个名称。 虽然活动的名称由工具生成且无法编辑，但在配置活动时，我们建议用显式名称对其进行标记。

### 复制活动{#activity-duplicating}

要复制现有活动，您可以使用复制粘贴。 这样，您就可以保留最初定义的设置。 有关详细信息，请参阅复制 [工作流活动](../../automating/using/workflow-interface.md)。

### 调度程序活动{#acheduler-activity}

在构建工作流时，每个分支仅使用 **[!UICONTROL Scheduler activity]**一个。 如果工作流的同一分支有多个调度程序（相互链接），则要执行的任务数将以指数级数增加，这将使数据库过载。

您可以通过单击来预览工作流的接下来十个执行 **[!UICONTROL Preview next executions]**。

![](assets/preview_scheduler.png)

有关详细信息，请参阅 [计划程序活动](../../automating/using/scheduler.md)。

## 使用参数调用工作流{#workflow-with-parameters}

确保参数的名称和数量与调用工作流时定义的参数相同(请参阅 [在调用工作流时定义参数](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow))。 参数的类型还必须与期望值一致。

确保在中声明了所有参数 **[!UICONTROL External signal activity]**。 否则，运行活动时将发生错误。

有关详细信息，请参 [阅使用外部参数调用工作流](../../automating/using/calling-a-workflow-with-external-parameters.md)。

## 导出包{#exporting-packages}

要导出包，导出的资源不得包含默认ID。 因此，必须使用与Adobe Campaign Standard标准提供的模板不同的名称来更改可导出资源的ID。
有关详细信息，请参 [阅管理包](../../automating/using/managing-packages.md)。

## 导出列表{#exporting-lists}

导出列表选项默认允许导出最多100,000行，并由 **Nms_ExportListLimit选项定义**。 此选项可由功能管理员在> **[!UICONTROL Administration]****[!UICONTROL Application settings]** >下管 **[!UICONTROL Options]**理。
有关详细信息，请参阅导[出列表](../../automating/using/exporting-lists.md)。

## 故障排除{#workflow-troubleshooting}

Adobe Campaign提供各种日志，以更好地了解您的工作流问题。

### 使用工作流日志{#using-workflow-logs}

您可以访问工作流日志以监控活动的执行。 它按时间顺序对执行的操作和执行错误进行索引。 “日志”选项卡包含在执行所有或某些选定活动的历史记录中。
任务选项卡详细说明了活动的执行顺序。 要获取有关活动的更多信息，请单击任务。
有关详细信息，请参阅监 [视工作流执行](../../automating/using/executing-a-workflow.md#monitoring)。

#### Troubleshooting data management activities{#troubleshooting-data-management-activities}

您可以在日志选项卡中分析SQL查询。

1. 在工作流工作区中，单击 **[!UICONTROL Edit properties]**。
1. 在 **[!UICONTROL General]**>**[!UICONTROL Execution]**&#x200B;中，选中和 **[!UICONTROL Save SQL queries in the log]**选项并**[!UICONTROL Execute in the engine]** 单击 **[!UICONTROL Confirm]**。

**要在日志中查看SQL查询，请执行以下操作：**
1. 单击 **[!UICONTROL Log and Tasks]**.
1. 在选项卡 **[!UICONTROL Logs]**中，打开该**[!UICONTROL Search]** 面板。
1. 查 **[!UICONTROL Display SQL logs only]**看。

查询显示在日 **[!UICONTROL Message]**志列中。

### 使用交付日志{#using-delivery-logs}

交付日志可监控您的交付成功与否。 排除日志在准备发送期间返回被排除的消息。 发送日志提供每个配置文件的分发状态。
有关详细信息，请参阅了 [解交付失败](../../sending/using/understanding-delivery-failures.md)。

### 使用交付警报{#delivery-alerting}

传送警报功能是一个警报管理系统，它使一组用户能够自动接收包含其传送执行信息的通知。
有关详细信息，请参阅 [交付警报](../../sending/using/receiving-alerts-when-failures-happen.md)。

**相关主题：**

* [错误管理](../../automating/using/executing-a-workflow.md#error-management)
