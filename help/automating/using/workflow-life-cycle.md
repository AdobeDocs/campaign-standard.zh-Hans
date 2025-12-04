---
title: 工作流生命周期
description: 了解有关工作流生命周期的更多信息
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: ba968add-25a3-4962-9e90-f0a06d9b74a8
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 3%

---

# 工作流生命周期 {#life-cycle}

工作流的生命周期包括三个主要步骤，每个步骤均链接到状态和颜色：

* **正在编辑**（灰色）

  这是工作流的初始设计阶段（请参阅[创建工作流](../../automating/using/building-a-workflow.md#creating-a-workflow)）。 该工作流尚未由服务器处理，可以修改而不存在任何风险。

* **正在进行** （蓝色）

  完成初始设计阶段后，即可启动工作流并由服务器处理。

* **已完成**（绿色）

  一旦没有任何正在进行的任务或操作员已明确停止实例，工作流即完成。

启动后，工作流可能还会具有其他两种状态：

* **警告** （黄色）

  该工作流无法完成，或已使用![](assets/pause_darkgrey-24px.png)或![](assets/check_pause_darkgrey-24px.png)按钮暂停。

* **错误** （红色）

  执行工作流时出错。 工作流已停止，用户必须执行操作。 若要了解有关此错误的更多信息，请使用![](assets/printpreview_darkgrey-24px.png)按钮访问工作流日志（请参阅[监控](../../automating/using/monitoring-workflow-execution.md)）。

营销活动列表允许您显示所有工作流及其状态。 有关此内容的详细信息，请参阅[管理营销活动](../../start/using/marketing-activities.md#about-marketing-activities)。

![](assets/wkf_execution_3.png)
