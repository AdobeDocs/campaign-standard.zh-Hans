---
title: 最新发行说明
description: 此页面详细描述最新 Campaign Standard 版本的内容
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 44c436a74a0a4aa688427bfb36d506566d57ac3a
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 100%

---


# 最新发行说明 {#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->


## 早期发行说明 {#e-new-release}

本部分列出了后续 Campaign Standard 版本中包含的改进和更改。

>[!CAUTION]
>
>在暂存环境升级日期之前，此内容可能会有所变动，恕不另行通知。有关详细信息，请参阅[发行计划页面](../../rn/using/release-planning.md)。

**版本 24.2 - 2024 夏季版**

* **发行日期**：2024 年 8 月（限时发布）- [了解详情](../../rn/using/release-planning.md)。

* **迁移到 OAuth 服务器到服务器凭据**

  从此版本开始，随着 Adobe 弃用服务帐户 (JWT) 凭据，Campaign 与 Adobe 解决方案和应用程序的出站集成现在依赖于 OAuth 服务器到服务器凭据。出站集成时，Adobe 将从 JWT 迁移到 OAuth，例如 Campaign-Analytics 集成或 Experience Cloud Triggers 集成。

  如果已实现与 Campaign 的入站集成，并且使用的是 [Campaign API](../../api/using/get-started-apis.md)，则必须按照[本文档](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}所述迁移技术帐户。现有服务帐户 (JWT) 凭据将于 **2025 年 1 月 27 日**&#x200B;失效。


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

