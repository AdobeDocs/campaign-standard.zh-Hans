---
title: 两个已优化受众的联合
description: 此使用案例顯示兩個讀取對象活動的聯合。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 6261f800-11bd-4b02-a587-49ddb0da240f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 58%

---

# 两个已优化受众的联合 {#example--union-on-two-refined-audiences}

此示例中定义的工作流展示了两个 **[!UICONTROL Read audience]** 活动的并集。此工作流程的目标，是向 18 至 30 岁的金牌或银牌会员发送电子邮件。系统中已创建特定受众以跟踪金牌和银牌会员。

工作流的设计如下所示：

![](assets/readaudience_activity_example1.png)

* 第一個 [讀取對象](../../automating/using/read-audience.md) 活動，只要選取介於18至30歲的設定檔，即可擷取和改良金級會員對象。
* 其次是 **[!UICONTROL Read audience]** 活动，用于检索银牌会员受众，并通过仅选择 18 到 30 岁之间的用户档案对其进行优化。
* A [聯集](../../automating/using/union.md) 活動可從兩者聯合母體 **[!UICONTROL Read audiences]** 活動會整合為單一最終母體。
* 一個 [電子郵件傳遞](../../automating/using/email-delivery.md) 活動會將電子郵件傳送至來自的母體 **[!UICONTROL Union]** 活動。
