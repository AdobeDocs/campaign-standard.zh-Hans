---
title: 关于数据导入和导出
description: 了解通过Adobe Campaign导入和导出数据的各种方法。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 208e8629-c3e2-4f36-bae7-46ffc3f56a1b
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 12%

---

# 关于数据导入和导出{#about-data-import-and-export}

根据您的业务需求，您可以通过多种方法来使用Adobe Campaign导入和导出数据：

* **包**：包是XML文件，可用于将配置和数据集从Adobe Campaign实例导出和导入到另一个实例。 系统更新也通过导入包来执行。
* **列表**：可以配置所有列表屏幕，显示的数据以单独的文件导出。
* **工作流**：从文件导入数据，并使用它更新数据库或发送电子邮件。 您还可以选择要导出到文件中的数据。 工作流是自动执行定期更新（如用户档案导入）的最佳方法。

   * 利用 **[!UICONTROL Load file]** 活动，可将数据导入一个结构化表单，以便在 Adobe Campaign 中使用该数据。数据是临时导入的，需要进行另一个活动才能将其确实集成到Adobe Campaign数据库中。 有关如何使用此活动的详细信息，请参阅[此部分](../../automating/using/load-file.md)。
   * **[!UICONTROL Transfer file]**&#x200B;活动允许您接收或发送文件、测试文件是否存在或列出Adobe Campaign中的文件。 如果您需要从外部源检索文件，可以在&#x200B;**[!UICONTROL Load file]**&#x200B;之前使用此活动。 有关如何使用此活动的详细信息，请参阅[此部分](../../automating/using/transfer-file.md)。

在设计导入流程时，最佳实践是使用可以根据您的需求调整的工作流模板。 有关如何设置工作流模板以导入数据的详细信息，请参阅[此用例](../../automating/using/creating-import-workflow-templates.md)。

Adobe Campaign还提供了执行常规导入的简化方法，包括设计&#x200B;**导入模板**。 导入模板是通过专用屏幕提供的专用工作流模板。 设计完成后，执行导入的用户只需上传文件即可在简化视图中导入。

**相关主题**：

* [使用导入模板导入数据](../../automating/using/importing-data-with-import-templates.md)
* [定义导入模板](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [管理资源包](../../automating/using/managing-packages.md)
