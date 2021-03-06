---
title: 关于数据导入和导出
description: 了解使用Adobe Campaign导入和导出数据的不同方式。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: 208e8629-c3e2-4f36-bae7-46ffc3f56a1b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 24%

---

# 关于数据导入和导出{#about-data-import-and-export}

根据您的业务需求，您可以通过多种方法通过Adobe Campaign导入和导出数据：

* **包**:包是XML文件，可用于将配置和数据集从Adobe Campaign实例导出并导入另一个实例。 系统更新也通过包导入来执行。
* **列表**:可以配置所有列表屏幕，并将显示的数据导出到单独的文件中。
* **工作流**:从文件导入数据，然后使用它更新数据库或发送电子邮件。 您还可以选择要在文件中导出的数据。 工作流是自动执行定期更新（如用户档案导入）的最佳方法。

   * 利用 **[!UICONTROL Load file]** 活动，可将数据导入一个结构化表单，以便在 Adobe Campaign 中使用该数据。此时数据属于临时导入，需要进行另一个活动才能将其确实集成到 Adobe Campaign 数据库中。有关如何使用此活动的更多信息，请参阅 [此部分](../../automating/using/load-file.md).
   * 利用 **[!UICONTROL Transfer file]** 活动，可接收或发送文件、测试文件是否存在或列出 Adobe Campaign 中的文件。您可以在 **[!UICONTROL Load file]** 如果您需要从外部源检索文件，请执行以下操作： 有关如何使用此活动的更多信息，请参阅 [此部分](../../automating/using/transfer-file.md).

设计导入流程时，最好使用可根据需要调整的工作流模板。 有关如何设置工作流模板以导入数据的更多信息，请参阅 [此用例](../../automating/using/creating-import-workflow-templates.md).

Adobe Campaign还提供了一种执行常规导入的简化方式，其中包括设计 **导入模板**. 导入模板是通过专用屏幕提供的专用工作流模板。 设计完毕后，执行导入的用户只需上传文件即可在简化视图中导入。

**相关主题**：

* [使用导入模板导入数据](../../automating/using/importing-data-with-import-templates.md)
* [定义导入模板](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [管理资源包](../../automating/using/managing-packages.md)
