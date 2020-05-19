---
title: 管理执行选项
description: 了解如何管理工作流执行选项。
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
source-git-commit: 422f5eb7011dfcc1d923079e7346394a64934a9a
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 0%

---


# 管理执行选项 {#managing-execution-options}

要修改工作流的执行选项，请使 ![](assets/edit_darkgrey-24px.png) 用按钮访问工作流属性并选择 **[!UICONTROL Execution]** 部分。

![](assets/wkf_execution_6.png)

可能的选项包括：

* **[!UICONTROL Default affinity]**: 此字段允许您强制在特定计算机上执行工作流或工作流活动。

* **[!UICONTROL History in days]**: 指定必须清除历史记录的天数。 历史记录包含与工作流相关的元素： 日志、任务、事件（链接到工作流操作的技术对象）以及活动下载的 **[!UICONTROL Transfer file]** 文件。 现成工作流模板的默认值为30天。

   清除历史记录由数据库清除技术工作流执行，默认情况下每天执行该工作流(请参 [阅技术工作流列表](../../administration/using/technical-workflows.md))。

   >[!IMPORTANT]
   >
   >如果 **[!UICONTROL History in days]** 字段留空，其值将视为“1”，这意味着历史记录将在1天后清除。

* **[!UICONTROL Save SQL queries in the log]**: 允许您将工作流中的SQL查询保存到日志中。

* **[!UICONTROL Keep interim results]**: 如果要视图过渡的详细信息，请选中此选项。 警告： 选中此选项可能会显着减慢工作流执行速度。

* **[!UICONTROL Execute in the engine (do not use in production)]**: 允许您在本地执行工作流，以便进行开发环境测试。

* **[!UICONTROL Severity]**: 允许您指定在工作流实例中执行Adobe Campaign的优先级。 将首先执行关键工作流。

该 **[!UICONTROL Error management]** 部分提供了其他选项，允许您管理工作流在出错时的行为方式。 这些选项在“错误管理” [部分中有](#error-management) 详细说明。
