---
solution: Campaign Standard
product: campaign
title: 管理执行选项
description: 了解如何管理工作流执行选项。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: 工作流
role: 数据架构师
level: 初学者
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 13%

---


# 管理执行选项 {#managing-execution-options}

要修改工作流的执行选项，请使用![](assets/edit_darkgrey-24px.png)按钮访问工作流属性并选择&#x200B;**[!UICONTROL Execution]**&#x200B;部分。

![](assets/wkf_execution_6.png)

可能的选项有：

* **[!UICONTROL Default affinity]**:此字段允许您强制在特定计算机上执行工作流或工作流活动。

* **[!UICONTROL History in days]**:指定必须清除历史记录的天数。历史记录包含与工作流相关的元素：日志、任务、事件（链接到工作流操作的技术对象）以及由&#x200B;**[!UICONTROL Transfer file]**&#x200B;活动下载的文件。 现成工作流模板的默认值为30天。

   清除历史记录由数据库清理技术工作流执行，默认情况下每天执行该工作流(请参阅[技术工作流的列表](../../administration/using/technical-workflows.md))。

   >[!IMPORTANT]
   >
   >如果&#x200B;**[!UICONTROL History in days]**&#x200B;字段留空，其值将视为“1”，这意味着历史记录将在1天后清除。

* **[!UICONTROL Save SQL queries in the log]**:允许您将工作流中的SQL查询保存到日志中。

* **[!UICONTROL Keep interim results]**:如果要视图过渡的详细信息，请选中此选项。

   >[!CAUTION]
   >
   >使用此选项会占用大量磁盘空间，其目的在于帮助您构建工作流并确保配置和行为正确。在制作实例中，请不要勾选该选项。

* **[!UICONTROL Execute in the engine (do not use in production)]**:允许您在本地执行该工作流，以便进行开发环境测试。

* **[!UICONTROL Severity]**:允许您指定在Adobe Campaign实例中执行工作流的优先级。此字段仅供Adobe团队用于监控目的。

**[!UICONTROL Error management]**&#x200B;部分提供了其他选项，允许您管理工作流在出错时的行为方式。 这些选项在[错误管理](../../automating/using/monitoring-workflow-execution.md#error-management)部分中有详细介绍。
