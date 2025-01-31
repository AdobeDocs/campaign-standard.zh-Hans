---
title: 2024 年版发行说明
description: 本页列出了所有 2024 年版的 Adobe Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: 26616ecc-a009-485c-b13d-d4e0c23969f2
source-git-commit: 85f3a3d8fe9e41eaa78fac955bc2d0f3f3d2c35e
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 100%

---

# 2024 年版发行说明 {#release-notes-2024}


## 版本 24.2 - 2024 夏季版 (LA) {#summer-24}

### 改进 {#summer-24-rn-improvements}

**迁移到 OAuth 服务器到服务器凭据**

从此版本开始，随着 Adobe 弃用服务帐户 (JWT) 凭据，Campaign 与 Adobe 解决方案和应用程序的出站集成现在依赖于 OAuth 服务器到服务器凭据。出站集成时，Adobe 将从 JWT 迁移到 OAuth，例如 Campaign-Analytics 集成或 Experience Cloud Triggers 集成。

如果已实现与 Campaign 的入站集成，并且使用的是 [Campaign API](../../api/using/get-started-apis.md)，则必须按照[本文档](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}所述迁移技术帐户。现有服务帐户 (JWT) 凭据将于 **2025 年 1 月 27 日**&#x200B;失效。

### 修复 {#summer-24-rn-fixes}

* 修复了导致工作流调度程序在计划时间之前启动的问题。(CAMP-55412)
* 修复了在事务性推送通知中复制自定义字段时导致错误的问题。(CAMP-54459)
* 修复了影响应用程序内消息传递的时间和日期调度程序可用性的问题。(CAMP-54495)
* 修复了使用自定义跟踪别名功能时导致跟踪不起作用且整个链接是动态链接的问题。(CAMP-56044)
* 修复了使用搜索功能查找特定模板时导致显示的模板数量有限的问题。(CAMP-55273)
* 在首选语言下拉列表中添加了以下语言：en_kz（英语 - 哈萨克斯坦语）和 en_ua（英语 - 乌克兰语）。(CAMP-55336)
* 修复了导致时间调整按钮在调度程序设置中不起作用的问题。(CAMP-53602)
* 修复了与调度程序设置中的时间调整栏相关的若干用户界面问题。(CAMP-55291)


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
