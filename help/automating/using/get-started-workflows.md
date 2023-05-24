---
title: 流程和数据管理入门
description: 利用工作流实现流程自动化、管理数据和受众、发送消息等。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Workflows
role: Data Architect
level: Beginner
exl-id: 26be942a-c252-458f-a590-eb235567ca67
source-git-commit: 6ca3ffe3ba2cf7629e511e4ba035b170b25ad79e
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 38%

---

# 流程和数据管理入门 {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">工作流活动</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">用例</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">筛选数据</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">匯入/匯出資料</a></p></td></tr>
</table>

Adobe Campaign 提供了一个全面的图形环境，允许您设计包括分段、活动执行、文件处理等在内的复杂流程。例如，您可以使用某个工作流从服务器下载文件、解压缩，然后将其记录导入 Adobe Campaign 数据库。

工作流还可能会涉及用户，为他们分配任务或让他们批准已执行的任务。这意味着，您可以向一个或多个用户分配任务，以处理内容或指定目标，并在发送消息之前批准验证。

工作流可以在不同的上下文中使用，例如：

* 定位以管理受众或发送消息。
* 进行数据管理 (ETL) 以处理数据。
* 将数据导入 Campaign 数据库。
* 数据库清理、恢复跟踪信息等技术流程。

>[!IMPORTANT]
>
> Adobe建議客戶不要同時執行超過20個作用中工作流程，並隨著時間安排工作流程執行的優先順序和分佈。 如需詳細資訊，請參閱中提供的最佳實務 [此頁面](../../automating/using/best-practices-workflows.md).

## 工作流活动 {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

提供各種活動來協助您設計工作流程。

[目標定位活動](../../automating/using/about-targeting-activities.md) 可讓您透過定義集合，並使用交集、聯集或排除作業分割或組合這些集合，來建立一或多個目標。

替換為 [執行活動](../../automating/using/about-execution-activities.md)，協調您的工作流程及其活動，同時 [頻道活動](../../automating/using/about-channel-activities.md) 可讓您合併Campaign Standard通訊頻道，以建立跨頻道工作流程。

最後， [資料管理活動](../../automating/using/about-data-management-activities.md) 可讓您從資料庫操控資料。

了解更多信息:

* [构建工作流](../../automating/using/building-a-workflow.md)
* [执行工作流](../../automating/using/about-workflow-execution.md)
* [工作流最佳实践](../../automating/using/best-practices-workflows.md)

## 筛选数据 {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

善用 **查詢編輯器** 以篩選資料庫中的資料，並建置人口族群，以更妥善地鎖定收件者。 查詢編輯器可在Campaign Standard中執行數個動作：建立查詢型別對象、定義傳遞目標或工作流程活動中的母體。

查詢編輯器隨附 **預先定義的篩選器和規則** 方便快速篩選。 不過，您也可以使用 **進階運算式編輯** 功能。 這可讓您手動輸入條件並使用函式，以便形成自己的規則。

了解更多信息:

* [编辑查询](../../automating/using/editing-queries.md)
* [高级表达式编辑](../../automating/using/advanced-expression-editing.md)
* [函数列表](../../automating/using/list-of-functions.md)

## 匯入/匯出資料 {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard隨附數種內容 **資料管理功能** 以匯入及匯出資料。

[工作流程資料管理活動](../../automating/using/about-data-management-activities.md) 可讓您匯入資料、對欄位執行大量更新、接收或傳送檔案，或將未識別的資料連結至現有資源。

替換為 [匯入範本](../../automating/using/importing-data-with-import-templates.md)，透過簡化的匯入功能管理管理員定義的特定匯入型別。

[匯出記錄檔](../../automating/using/exporting-logs.md) 可讓您透過簡單的工作流程匯出記錄資料，讓您在自己的報告或BI工具中分析行銷活動的結果。

善用 [套件](../../automating/using/managing-packages.md) 在不同的campaign執行個體之間交換資源，例如，複製執行個體的設定，或將資料從伺服器傳輸到另一個包含自訂資源的伺服器。

最後， [匯出清單](../../automating/using/exporting-lists.md) 可讓您從Campaign Standard匯出任何清單，例如測試設定檔清單、隔離區電子郵件地址清單等。

了解更多信息:

* [导入和导出数据](../../automating/using/about-data-import-and-export.md)
* [用例：导出/导入自定义资源](../../automating/using/exporting-importing-custom-resources.md)

## 其他资源

* [流程和資料管理教學課程影片](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/managing-processes-and-data/creating-a-workflow.html?lang=zh-Hans)
* [技术工作流](../../administration/using/technical-workflows.md)
* [Campaign Standard 数据模型快速入门](../../developing/using/get-started-data-model.md)
