---
title: 执行工作流
seo-title: 执行工作流
description: 执行工作流
seo-description: 了解如何执行和监视工作流。
page-status-flag: 从未激活
uuid: ff02b74e-53e8-49c6-bf8 e-0c729 ea7 d25
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 工作流常规操作
discoiquuid: 906c85ea-83b7-4268-86da-cd353 f1 dc593
context-tags: 工作流程，概述；工作流，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: e33cbfbf6376dabfe81b9bd6f7cce817f35d1b75

---


# Executing a workflow{#executing-a-workflow}

## About workflow execution {#about-workflow-execution}

始终手动启动工作流。However, once started, it can remain inactive, depending on the information specified in a [Scheduler](../../automating/using/scheduler.md) activity.

>[!CAUTION]
>
> Adobe建议客户优先处理工作流执行，并运行最多20个并发工作流程执行，以在您的实例中一致地实现最高性能。可以计划多个并发工作流程执行，并且默认情况下将执行顺序执行。您可以通过向客户服务部门提交票证来调整并发工作流程执行的默认设置。

执行相关操作(开始、停止、暂停等)are **asynchronous** processes: the command is saved and will become effective once the server is available to apply it.

在工作流中，每个活动的结果通常通过一个由箭头表示的过渡发送到以下活动。

如果过渡未链接到目标活动，则过渡将断开。

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>仍可以执行包含未结束过渡的工作流：将生成一条警告消息，一旦到达过渡，工作流将暂停，但这不会生成错误。您还可以在没有完全完成设计的情况下启动工作流，并在您继续时完成它。

执行活动后，在过渡中发送的记录数将显示在该活动上方。

![](assets/wkf_transition_count.png)

您可以打开过渡以检查发送的数据在执行工作流期间还是执行后是否正确。您可以查看数据和数据结构。

默认情况下，只能访问工作流最后过渡的详细信息。To be able to access the results of the preceding activities, you need to check the **[!UICONTROL Keep interim results]** option in the **[!UICONTROL Execution]** section of the workflow properties, before starting the workflow.

>[!NOTE]
>
>此选项占用大量内存，旨在帮助构建工作流并确保正确配置和操作。在生产实例上取消选中。

When a transition is open, you can edit its **[!UICONTROL Label]** or link a **[!UICONTROL Segment code]** to it. 为此，请编辑相应的字段并确认您的修改。

## Controlling a workflow from the REST API {#controlling-a-workflow-from-the-rest-api}

Using the REST API, you can **start**, **pause**, **resume** and **stop** a workflow.

You can find more details and examples of REST calls in the [API documentation.](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#controlling-a-workflow)

## Life cycle {#life-cycle}

工作流的生命周期包括三个主要步骤，每个步骤都链接到一个状态和颜色：

* **编辑(** 灰色)

   This is the initial design phase of a workflow (refer to [Creating a workflow](../../automating/using/building-a-workflow.md#creating-a-workflow)). 该工作流尚未由服务器处理，并且可以在没有任何风险的情况下进行修改。

* **进行中** (蓝色)

   初始设计阶段完成后，可以启动工作流并由服务器处理。

* **已完成(** 绿色)

   一旦不再执行任何正在进行的任务或操作员显式停止了实例，工作流就会完成。

一旦启动，工作流也可能有两个其他状态：

* **警告(** 黄色)

   The workflow could not finish or was paused using the ![](assets/pause_darkgrey-24px.png) or ![](assets/check_pause_darkgrey-24px.png) buttons.

* **error** (red)

   执行工作流时出错。工作流已停止，用户必须执行一项操作。To find out more about this error, use the ![](assets/printpreview_darkgrey-24px.png) button to access the workflow log (refer to [Monitoring](../../automating/using/executing-a-workflow.md#monitoring)).

营销活动列表允许您显示所有工作流及其状态。For more on this, see [Managing marketing activities](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)

## Execution commands {#execution-commands}

操作栏中的图标允许您启动、跟踪和修改工作流的执行。See [Action bar](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

可用的操作如下所示：

**开始时间**

![](assets/play_darkgrey-24px.png) 按钮将开始执行工作流，然后执行 **“正在进行** ”(蓝色)状态。如果工作流暂停，则恢复该工作流，否则将启动该工作流，然后启动初始活动。

>[!NOTE]
>
>启动是异步过程：系统会保存请求，并将由工作流执行引擎尽快处理。

**暂停**

![](assets/pause_darkgrey-24px.png) 按钮将暂停执行。The workflow takes on the **Warning** (yellow) status. 在继续执行新活动之前，不会激活新活动，但进行中的操作不会暂停。

**停止**

![](assets/stop_darkgrey-24px.png) 按钮将停止正在执行的工作流，然后将执行 **已完成** (绿色)状态。如果可能，正在进行的操作会中断，并且正在进行的导入或SQL查询会立即被取消。您无法从工作流所在的同一位置继续工作。

**重新启动**

![](assets/pauseplay_darkgrey-24px.png) 该按钮包括停止，然后重新启动工作流。在大多数情况下，这允许您更快地重新启动。It can also be useful to automate restarting once stopping takes a certain amount of time, because the ![](assets/play_darkgrey-24px.png) button is only available when the stop is effective.

选择某个工作流中的一个或多个活动时，您可以执行其他操作，例如：

**即时执行**

![](assets/pending_darkgrey-24px.png) 该按钮会尽快启动任何待定的活动。

**正常执行**

![](assets/check_darkgrey-24px.png) 该按钮可重新激活任何暂停或取消激活的活动。

**执行暂停**

![](assets/check_pause_darkgrey-24px.png) 该按钮在选定活动处暂停工作流：不执行此任务以及所有随后(在同一分支中)执行的任务。

**无执行**

![](assets/checkdisable.png) 该按钮将取消激活任何选定的活动。

>[!NOTE]
>
>快速操作可让您访问有关某个特定活动的不同操作，并在选择某个活动时显示该活动。

## Monitoring {#monitoring}

![](assets/printpreview_darkgrey-24px.png) 该图标将打开工作流日志和任务菜单。

The workflow history is saved for the duration specified in the workflow execution options (refer to [Workflow properties](../../automating/using/executing-a-workflow.md#workflow-properties)). 在此期间，即使在重新启动之后，也会保存所有消息。If you do not want to save the messages from a previous execution, you have to purge the history by clicking the ![](assets/delete_darkgrey-24px.png) button.

**[!UICONTROL Log]** 选项卡包含所有活动或所选活动的执行历史记录。它按时间顺序对执行和执行错误的操作进行索引。

![](assets/wkf_execution_4.png)

**[!UICONTROL Tasks]** 选项卡详细介绍了活动的执行顺序。单击任务以获取更多信息。

![](assets/wkf_execution_5.png)

在这两个列表中：

* 单击计数器可查看应用的过滤器总数。默认情况下，如果列表中的元素数量小于30，则会显示计数器。
* **[!UICONTROL Configure list]** 该按钮允许您选择显示的信息，定义列顺序并对列表排序。
* 您可以使用过滤器更快地找到所需的信息。使用搜索字段查找工作流活动名称中的特定文本(例如：“query”)和logs.

## Error management {#error-management}

出现错误时，将暂停工作流，并在遇到错误时执行正在执行的活动。

工作流状态会变为红色，而错误将记录在日志中。

您可以配置工作流，以便它不会暂停并继续执行，而不会出现任何错误。To do this, go to the workflow properties via the ![](assets/edit_darkgrey-24px.png) button and, in the **[!UICONTROL Execution]** section, select the **Ignore** option in the **In case of error** field.

在这种情况下，错误的任务会被中止。此模式特别适合以后重新尝试操作的工作流(定期操作)。

>[!NOTE]
>
>您可以为每个活动单独应用此配置。To do this, select an activity and open it using the quick action ![](assets/edit_darkgrey-24px.png). Then select the error management mode in the **Execution options** tab. See [Activity execution options](../../automating/using/executing-a-workflow.md#activity-execution-options).

The **[!UICONTROL Execution]** section of the workflow properties also allows you to define a number of **[!UICONTROL Consecutive errors]** that are authorized before the workflow execution is automatically suspended. 只要未达到此数量，就会忽略错误的元素，并且其他工作流分支会正常执行。如果达到此数量，则会暂停工作流，并自动通知工作流主管(电子邮件和应用程序内通知)。See [Workflow properties](../../automating/using/executing-a-workflow.md#workflow-properties) and [Adobe Campaign notifications](../../administration/using/sending-internal-notifications.md).

还可以在工作流的执行属性中定义管理者。

## Workflow properties {#workflow-properties}

To modify a workflow's execution options, use the ![](assets/edit_darkgrey-24px.png) button to access the workflow properties and select the **[!UICONTROL Execution]** section.

**[!UICONTROL Default affinity]** 该字段允许您强制在特定机器上执行工作流或工作流活动。

**[!UICONTROL History in days]** 在字段中，指定必须清除历史记录的持续时间。

You can choose to check the **[!UICONTROL Save SQL queries in the log]** and **[!UICONTROL Execute in the engine (do not use in production)]** options if necessary.

Check the **[!UICONTROL Keep interim results]** option if you would like to be able to view the detail of transitions. 警告：选中此选项可能会显著减缓工作流执行。

**[!UICONTROL Severity]** 该字段允许您指定在Adobe Campaign实例中执行工作流的优先级级别。将首先执行关键工作流。

**[!UICONTROL Supervisors]** 在该字段中，您可以在工作流遇到错误时定义要通知的用户组(电子邮件和应用程序内通知)。如果未定义组，则不会通知任何人。For more on Adobe Campaign notifications, refer to [Adobe Campaign notifications](../../administration/using/sending-internal-notifications.md).

**[!UICONTROL In case of error]** 该字段允许您指定活动遇到错误时要执行的操作。有两种可用的选项：

* **暂停流程**：工作流会自动挂起。The workflow status is then **Erroneous** and the color associated turns red. 解决问题后，重新启动该工作流。
* **忽略**：活动不会执行，因此任何后续活动都不会执行(在同一分支中)。这可能对重复任务很有用。如果分支在上游放置了一个调度程序，则此操作应在下一个执行日期触发。

   By selecting this option, you can also define a number of **[!UICONTROL Consecutive errors]** that are authorized:

   * If the number specified is **[!UICONTROL 0]**, or as long as the number specified is not reached, activities that encounter errors are ignored. 其他工作流分支正常执行。
   * If the number specified is reached, the whole of the workflow is suspended and becomes **[!UICONTROL Erroneous]**. 如果定义了监事，则会通过电子邮件自动通知他们。

![](assets/wkf_execution_6.png)

## Activity properties {#activity-properties}

### General properties of an activity {#general-properties-of-an-activity}

Each activity has a **[!UICONTROL Properties]** tab. 此选项卡允许您修改活动的常规参数，特别是标签和ID。配置此选项卡是可选的。

### Managing an activity's outbound transitions {#managing-an-activity-s-outbound-transitions}

默认情况下，某些活动没有出站过渡。You can add one from the **[!UICONTROL Transitions]** tab or from the activity's **[!UICONTROL Properties]** tab to apply other processes to your population in the same workflow.

根据活动，您可以添加多种类型的出站过渡：

* 标准过渡：由活动计算的人口
* 无人口过渡：可以添加此类出站过渡以继续工作流，并且不包含任何不会占用系统上不必要空间的人群。
* 拒绝：被拒绝。例如，如果活动的入站数据不正确或不完整，则无法处理这些数据。
* 补充：执行活动后剩余的用户数。例如，如果分段活动被配置为仅保存入站人口百分比。

If applicable, specify a **[!UICONTROL Segment code]** for the activity's outbound transition. 此区段代码将允许您识别目标人群的子集来自何处，以后可能会为消息个性化目的提供服务。

### Activity execution options {#activity-execution-options}

In the activity's properties screen, there is an **[!UICONTROL Advanced options]** tab that lets you define the activity's execution mode and behavior in case of errors.

To access these options, select an activity in a workflow, then open it using the ![](assets/edit_darkgrey-24px.png) button from the action bar.

![](assets/wkf_advanced_parameters.png)

**[!UICONTROL Execution]** 该字段允许您定义启动任务时要执行的操作。有三个选项可供选择：

* **正常**：活动正常执行。
* **启用但不执行**：活动会暂停，随后的任何后续流程也会随之暂停。如果您希望在任务开始时显示，这可能会很有用。
* **请勿启用**：活动不会执行，因此，随后的所有活动都不会执行(在同一分支中)。

**[!UICONTROL In case of error]** 该字段允许您指定活动遇到错误时要执行的操作。有两种可用的选项：

* **暂停流程**：工作流会自动挂起。The workflow status is then **Erroneous** and the color associated turns red. 解决问题后，重新启动该工作流。
* **忽略**：活动不会执行，因此任何后续活动都不会执行(在同一分支中)。这可能对重复任务很有用。如果分支在上游放置了一个调度程序，则此操作应在下一个执行日期触发。

**[!UICONTROL Behavior]** 该字段允许您定义在使用异步任务时遵循的步骤。有两种可用的选项：

* **已授权多个任务**：可以同时执行多个任务，即使第一个任务未完成也是如此。
* **当前任务具有优先级**：完成任务后，这将优先考虑。只要有一项任务仍在进行，就不会执行任何其他任务。

**[!UICONTROL Max. execution duration]** 该字段允许您指定持续时间(如“30s”或“1h”)。如果在指定的持续时间后活动未完成，则会触发警报。这不会影响工作流程功能。

**[!UICONTROL Affinity]** 该字段允许您强制在特定机器上执行工作流或工作流活动。为此，您必须为相关工作流或活动指定一个或多个相似性。

**[!UICONTROL Time zone]** 该字段允许您选择活动的时区。Adobe Campaign允许您管理同一实例多个国家/地区之间的时间差异。创建实例时将配置应用的设置。

**评论** 字段是一个免费字段，用于添加备注。
