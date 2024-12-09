---
title: 最新发行说明
description: 此页面详细描述最新 Campaign Standard 版本的内容
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: c2d2f3843801d108f007fea52a76e41abe16d76c
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 76%

---


# 最新发行说明 {#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->


## 早期发行说明 {#e-new-release}

本部分列出了后续 Campaign Standard 版本中包含的改进和更改。

>[!CAUTION]
>
>在暂存环境升级日期之前，此内容可能会有所变动，恕不另行通知。有关详细信息，请参阅[发行计划页面](../../rn/using/release-planning.md)。

### 25.1 版 - 2025 年冬季版 {#winter-25}

#### 安全修复 {#winter-25-security}

* 此版本提供了安全修复。
* 此版本附带以下安全升级：Apache Tomcat已升级到v10.1.33。

#### 其他修复 {#winter-25-fixes}

* 修复了模板中的重复问题(CAMP-56340)
* 修复了在Adobe Experience Manager模板中使用动态URL时的跟踪回归(CAMP-51932)
* 修复了计费流程的性能问题(CAMP-56796)
* 修复了JSSP网页上`>`字符的HTML编码问题(CAMP-56497)
* 修复了使用&#x200B;**在选定行上显示**&#x200B;选项时动态报告中的问题(CAMP-55895)


## 24.2版 — 2024年夏季版（洛杉矶） {#summer-24}

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
