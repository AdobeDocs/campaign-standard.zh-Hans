---
title: 早期发行说明
description: 早期发行说明
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 602aca18af81625b9756a8f2020b5bc636199b96
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 68%

---


# 早期发行说明 {#e-new-release}

本页介绍了下一个 Campaign Standard 版本中包含的改进和修复。

>[!CAUTION]
>
> 在暂存环境升级日期之前，此内容可能会有所变动，恕不另行通知。在[发行计划页面](../../rn/using/release-planning.md)中了解详情。

## 24.1 版 - 2024 冬季版 {#winter-24}

>[!AVAILABILITY]
>
>此版本仅适用于一组组织（限量发布）。 有关更多信息，请与您的 Adobe 代表联系。

### 改进 {#e-rn-improvements}

Adobe Campaign Standard 24.1使用HTTP v1 API发送Android推送通知消息，以确保与即将发布的FCM更改兼容。 请参阅[此技术说明](../../administration/using/push-technote.md)以了解详情。


### 修复 {#e-rn-fixes}

* 修复了导致投放警报工作流停止并出现以下错误的问题： `division by zero`. (CAMP-49786)
