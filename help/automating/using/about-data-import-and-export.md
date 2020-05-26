---
title: 关于数据导入和导出
description: 了解使用Adobe Campaign导入和导出数据的不同方式。
page-status-flag: never-activated
uuid: f6810364-555c-4b72-8a9c-4ae2fcb2ba63
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: 31215773-6c0c-48f1-9101-da0ea2a366da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0deabe17442b679a340a4497945837b83b4c9207
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 6%

---


# 关于数据导入和导出{#about-data-import-and-export}

根据您的业务需要，您有几种方法可通过Adobe Campaign导入和导出数据：

* **包**: 包是XML文件，允许您将配置和数据集从Adobe Campaign实例导出并导入到另一个实例。 系统更新也通过包导入来执行。
* **列表**: 可以配置所有列表屏幕，并将显示的数据导出到单独的文件中。
* **工作流**: 从文件导入数据，然后使用它更新数据库或发送电子邮件。 您还可以选择要在文件中导出的数据。 工作流是自动执行定期更新(如用户档案导入)的最佳方式。

   * 活动 **[!UICONTROL Load file]** 允许您以一种结构化形式导入数据，以在Adobe Campaign中使用此数据。 数据被临时导入，需要另一个活动将其完全集成到Adobe Campaign数据库中。 有关如何使用此活动的详细信息，请参 [阅本节](../../automating/using/load-file.md)。
   * 活动 **[!UICONTROL Transfer file]** 允许您接收或发送文件、测试是否存在文件或以Adobe Campaign列表文件。 在需要从外部源检索 **[!UICONTROL Load file]** 文件时，可以在文件之前使用此活动。 有关如何使用此活动的详细信息，请参 [阅本节](../../automating/using/transfer-file.md)。

在设计导入流程时，最好使用可以根据需要调整的工作流模板。 有关如何设置工作流模板以导入数据的详细信息，请参 [阅此用例](../../automating/using/creating-import-workflow-templates.md)。

Adobe Campaign还优惠一种简化的方法来执行常规导入，包括设计 **导入模板**。 导入模板是通过专用屏幕提供的专用工作流模板。 设计完成后，执行导入的用户只需上传文件即可以简化的视图导入。

**相关主题**:

* [使用导入模板导入数据](../../automating/using/importing-data-with-import-templates.md)
* [定义导入模板](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [管理包](../../automating/using/managing-packages.md)
