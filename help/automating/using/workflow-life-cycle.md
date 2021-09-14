---
title: 工作流生命周期
description: 了解有关工作流生命周期的更多信息
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: ba968add-25a3-4962-9e90-f0a06d9b74a8
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 3%

---

# 工作流生命周期 {#life-cycle}

工作流的生命周期包括三个主要步骤，每个步骤都链接到状态和颜色：

* **编辑** （灰色）

   这是工作流的初始设计阶段（请参阅[创建工作流](../../automating/using/building-a-workflow.md#creating-a-workflow)）。 该工作流尚未由服务器处理，可以修改，且不会出现任何风险。

* **进行中** （蓝色）

   初始设计阶段完成后，工作流便可启动并由服务器处理。

* **已完成** （绿色）

   当没有任何正在进行的任务或当运算符明确停止实例时，工作流即告完成。

启动工作流后，该工作流可能还具有两种其他状态：

* **警告** （黄色）

   使用![](assets/pause_darkgrey-24px.png)或![](assets/check_pause_darkgrey-24px.png)按钮无法完成或暂停工作流。

* **错误** （红色）

   执行工作流时出错。 工作流已停止，用户必须执行操作。 要进一步了解此错误，请使用![](assets/printpreview_darkgrey-24px.png)按钮访问工作流日志（请参阅[Monitoring](../../automating/using/monitoring-workflow-execution.md)）。

营销活动列表允许您显示所有工作流及其状态。 有关更多信息，请参阅[管理营销活动](../../start/using/marketing-activities.md#about-marketing-activities)。

![](assets/wkf_execution_3.png)
