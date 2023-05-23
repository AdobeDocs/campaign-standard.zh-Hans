---
title: 监测准则
description: 此頁面提供監督Campaign Standard的一般准則
audience: production
feature: Access Management
role: Admin
level: Experienced
exl-id: 5f25f2b2-ca41-4baf-ade2-42bbafb4790d
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 21%

---

# 监测准则 {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">監視系統</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">监控工作流</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">监控投放</a></p></td></tr>
</table>

Campaign Standard提供數種監控執行個體的方式，以確保您的系統運作正常，並最終疑難排解設定工作流程、傳送傳遞等時可能發生的問題。

## 監視系統 {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**系統通知**

Campaign Standard介面會提供通知窗格，讓您隨時瞭解系統中發生的情況：事件狀態、系統更新、所需的動作等。 [了解更多信息](../../start/using/interface-description.md#top-bar)


**技术工作流**

技术工作流是计划在服务器上定期执行的操作或作业。為確保您的執行個體正常運作，您需要確保執行個體隨時正常運作。 [了解更多信息](../../administration/using/technical-workflows.md)

**控制面板**

「控制面板」可以讓您管理執行個體的多項設定：URL許可權、檢查執行個體詳細資訊（例如伺服器的組建版本）、監控作用中設定檔的使用情況等。 它也可讓您監視連線到執行個體的SFTP伺服器上的可用空間。 [阅读更多](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hans)。

>[!NOTE]
>
>所有管理员用户都可访问控制面板。[此页面](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=zh-Hans#discover-control-panel)详细介绍了授予用户管理员访问权限的步骤。

**技术对象**

此 **[!UICONTROL Diagnosis]** 功能表是用於監視和分析應用程式產生的不同技術物件的關鍵工具：資料結構描述、網頁、批次工作等。 [了解更多信息](../../developing/using/monitoring-data-model-changes.md)

**匯出稽核**

匯出稽核可讓您監視執行個體上執行的匯出：從工作流程上傳的檔案、清單匯出以及從直接郵件訊息下載的檔案。
[了解更多信息](../../administration/using/auditing-export-logs.md)

**许可证**

使用 **[!UICONTROL Licenses]** 功能表、監控執行個體的相關資訊：已安裝的授權、組建版本和條款協定接受。
[了解更多信息](../../administration/using/licenses.md)

## 监控工作流 {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**最佳实践和故障排除**

使用工作流程時，遵循最佳實務和疑難排解指南有助於改善效能。
[了解更多信息](../../automating/using/best-practices-workflows.md)

**日志和任务**

工作流程記錄監控是分析工作流程並確保其正常執行的關鍵步驟。
[了解更多信息](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**通知**

Campaign Standard可讓您傳送通知給主管，以監視工作流程的執行並檢視是否有任何需要您注意的錯誤。
[了解更多信息](../../automating/using/monitoring-workflow-execution.md#error-management)

## 监控投放 {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**可投放性**

Campaign Standard提供數種傳遞能力工具，協助您改善成功傳遞的訊息數量：傳遞輸送量報告、傳送時間最佳化、訊息預覽、電子郵件呈現、隔離管理等。
[了解更多信息](../../sending/using/about-deliverability.md)

**投放**

傳送訊息後，詳細的記錄檔可讓您監控傳送並測量行銷活動是否成功，以及追蹤訊息收件者的行為。
[了解更多信息](../../sending/using/monitoring-a-delivery.md)

**傳遞警報**

透過傳送警報功能，您可以設定自動傳送給一組使用者關於傳送執行的警報：傳送或準備失敗、不良跳出率、低輸送量等。
[了解更多信息](../../sending/using/receiving-alerts-when-failures-happen.md)

**動態報告**

動態報告提供各種報告，協助您隨時瞭解傳遞的執行方式：跳出數、收件者檢視次數最多的傳遞、傳遞的輸送量等。
[了解更多信息](../../reporting/using/about-dynamic-reports.md)
