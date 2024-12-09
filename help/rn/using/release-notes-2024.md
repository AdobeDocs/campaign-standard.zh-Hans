---
title: 2024 年版发行说明
description: 本页列出了所有 2024 年版的 Adobe Campaign Standard
feature: Overview
role: User
level: Beginner
source-git-commit: c70e3058f75ba2b11a8311628198e5c02d489964
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 100%

---

# 2024 年版发行说明 {#release-notes-2024}

## 24.1 版 - 2024 年冬季版 {#winter-24}

### 改进 {#e-rn-improvements}

* **Android 推送通知** - Adobe Campaign Standard 24.1 使用 HTTP v1 API 发送 Android 推送通知消息，确保与即将发布的 FCM 更改相兼容。请参阅[此技术说明](../../administration/using/push-technote.md)以了解详情。

* **iOS 推送通知** - Adobe Campaign Standard 24.1 现在支持使用 p8 身份验证证书发送 iOS 推送通知。必须调整您的实施以激活这些更改。请参阅[此技术说明](../../administration/using/push-technote.md)以了解详情。

* **一键式列表取消订阅** - 从 2024 年 6 月 1 日开始在 Google 和 Yahoo! 上启用将要求发件人使用一键式 List-Unsubscribe 功能。Campaign 现已支持此功能。可在[此部分](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters)中了解详情。

* **基础架构** - Postgres数据库已从版本 11.22 升级到版本 12.17。

* **CTA跟踪** - 现在，当用户打开并单击个性化 URL 后会跟踪已解析的个性化 URL，而不是编码的个性化 URL。默认未启用此选项。要在您的 Campaign 实例中启用该选项，请联系您的 Adobe 代表。

* **个性化字段下拉列表** - 在 Adobe Experience Manager 中创建事务性电子邮件模板时，现在可以从下拉列表中选择个性化字段。默认未启用此选项。要在您的 Campaign 实例中启用该选项，请联系您的 Adobe 代表。

### 修复 {#e-rn-fixes}

* 修复了导致在 30 天后无法从隔离中删除退回电子邮件地址的问题。(CAMP-52977)
* 修复了导致投放警报工作流停止并出现以下错误的问题：`division by zero`。(CAMP-49786)

