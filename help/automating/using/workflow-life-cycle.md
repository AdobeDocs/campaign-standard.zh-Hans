---
solution: Campaign Standard
product: campaign
title: 工作流生命周期
description: 进一步了解工作流生命周期
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 3%

---


# 工作流生命周期 {#life-cycle}

工作流的生命周期包括三个主要步骤，每个步骤都链接到状态和颜色：

* **编辑** （灰色）

   这是工作流的初始设计阶段(请参阅 [创建工作流](../../automating/using/building-a-workflow.md#creating-a-workflow))。 该工作流尚未由服务器处理，可以修改且没有任何风险。

* **进行中** （蓝色）

   初始设计阶段完成后，工作流便可以启动并由服务器处理。

* **已完成** （绿色）

   当不再有任何任务正在进行或操作符明确停止实例时，工作流即完成。

启动工作流后，该工作流还可能有两种其他状态：

* **警告** （黄色）

   工作流无法完成或使用按钮 ![](assets/pause_darkgrey-24px.png) 暂停 ![](assets/check_pause_darkgrey-24px.png) 或。

* **错误** （红色）

   执行工作流时出错。 工作流已停止，用户必须执行操作。 要进一步了解此错误，请使用 ![](assets/printpreview_darkgrey-24px.png) 按钮访问工作流日志(请参 [阅监](../../automating/using/monitoring-workflow-execution.md)视)。

营销活动的列表允许您显示所有工作流及其状态。 For more on this, see [Managing marketing activities](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)
