---
title: 更新和维护操作
description: 有关Adobe Campaign服务器的更新和维护操作的信息。
audience: administration
content-type: reference
topic-tags: application-settings
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 4da0b7b0-a854-4935-9f5f-04bfc764b18d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 43%

---

# 更新和维护操作{#updates-and-maintenance-operations}

出于维护目的，Adobe Campaign服务器每天早上6点（服务器时区）重新启动。 联系Adobe以了解服务器时间。 此操作是自动和透明的。 但是，我们建议您不要在重新启动之前执行任何数据处理操作。 例如，避免在重新启动之前启动工作流，请将它们安排为在重新启动后一分钟启动。

Adobe 通过添加新功能、增强功能和修复错误，不断改进其解决方案。所有 Adobe Campaign Standard 实例都会随每次版本更新一起升级。升级不需要任何操作。升级分两个阶段进行。首先，升级 Stage 实例，使我们的客户能够测试新功能并根据需要调整其配置随后将升级 Production 实例。请查阅 [发行计划](https://helpx.adobe.com/cn/campaign/kb/acs-release-planning.html) 以了解下一个版本的发布时间。 另请查阅 [已弃用和已删除的功能](../../rn/using/deprecated-features.md).
