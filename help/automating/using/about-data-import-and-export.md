---
title: 关于数据导入和导出
description: 瞭解透過Adobe Campaign匯入和匯出資料的各種方式。
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

根據您的業務需求，您有數種方式可以使用Adobe Campaign匯入和匯出資料：

* **套件**：套件是XML檔案，可讓您將設定和資料集從Adobe Campaign執行個體匯出和匯入至另一個執行個體。 系統更新也會透過套件匯入來執行。
* **清單**：您可以設定所有清單畫面，並將顯示的資料匯出至個別檔案。
* **工作流程**：從檔案匯入資料，並用來更新資料庫或傳送電子郵件。 您也可以選取要匯出到檔案中的資料。 工作流程是自動化定期更新（如設定檔匯入）的最佳方式。

   * 利用 **[!UICONTROL Load file]** 活动，可将数据导入一个结构化表单，以便在 Adobe Campaign 中使用该数据。此时数据属于临时导入，需要进行另一个活动才能将其确实集成到 Adobe Campaign 数据库中。有關如何使用此活動的詳細資訊，請參閱 [本節](../../automating/using/load-file.md).
   * 利用 **[!UICONTROL Transfer file]** 活动，可接收或发送文件、测试文件是否存在或列出 Adobe Campaign 中的文件。您可在「 」之前使用此活動 **[!UICONTROL Load file]** 以備您需要從外部來源擷取檔案時使用。 有關如何使用此活動的詳細資訊，請參閱 [本節](../../automating/using/transfer-file.md).

在設計匯入程式時，最佳實務是使用您可以根據需求調整的工作流程範本。 有關如何設定工作流程範本以匯入資料的詳細資訊，請參閱 [此使用案例](../../automating/using/creating-import-workflow-templates.md).

Adobe Campaign也提供執行定期匯入的簡化方式，包括設計 **匯入範本**. 匯入範本是專用工作流程範本，可透過專用畫面使用。 設計完成後，執行匯入的使用者只需上傳檔案，即可在簡化的檢視中匯入。

**相关主题**：

* [使用导入模板导入数据](../../automating/using/importing-data-with-import-templates.md)
* [定义导入模板](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [管理资源包](../../automating/using/managing-packages.md)
