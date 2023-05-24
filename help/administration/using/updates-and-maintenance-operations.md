---
title: 更新和维护操作
description: Adobe Campaign伺服器更新和維護作業的相關資訊。
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 4da0b7b0-a854-4935-9f5f-04bfc764b18d
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 43%

---

# 更新和维护操作{#updates-and-maintenance-operations}

基於維護目的，Adobe Campaign伺服器每天早上6:00重新啟動（伺服器時區）。 請聯絡Adobe以瞭解伺服器時間。 此作業是自動且透明的。 不過，我們建議您不要在重新啟動之前執行任何資料處理作業。 例如，請避免在重新啟動前啟動工作流程，請將工作流程排程在重新啟動後一分鐘開始。

Adobe 通过添加新功能、增强功能和修复错误，不断改进其解决方案。所有 Adobe Campaign Standard 实例都会随每次版本更新一起升级。升级不需要任何操作。升级分两个阶段进行。首先，升级 Stage 实例，使我们的客户能够测试新功能并根据需要调整其配置随后将升级 Production 实例。請參閱 [發行計畫](https://helpx.adobe.com/cn/campaign/kb/acs-release-planning.html) 以瞭解下一個版本何時推出。 另請參考以下清單 [過時和移除的功能](../../rn/using/deprecated-features.md).
