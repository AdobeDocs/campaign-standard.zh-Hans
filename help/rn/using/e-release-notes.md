---
title: 早期发行说明
description: 早期发行说明
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: ac4a52263482557a6d5c370af6df5d54a42671b4
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 52%

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

Adobe Campaign Standard 24.1现在支持iOS推送通知的p8身份验证证书。 必须调整您的实施以激活这些更改。 请参阅[此技术说明](../../administration/using/push-technote.md)以了解详情。


### 修复 {#e-rn-fixes}

* 修复了在30天后无法从隔离中删除退回电子邮件地址的问题。 (CAMP-52977)
* 修复了导致投放警报工作流停止并出现以下错误的问题： `division by zero`. (CAMP-49786)
