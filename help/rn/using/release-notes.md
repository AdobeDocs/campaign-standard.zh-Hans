---
title: 最新发行说明
description: 此页面详细描述最新 Campaign Standard 版本的内容
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 4df02bb5bbac105057a33d61a7158482bbc48a53
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 49%

---


# 最新发行说明 {#latest-release}

<!--
## Release notes {#e-new-release}


This section lists improvements and changes included in the next Campaign Standard release.

>[!CAUTION]
>
>This content is subject to changes without prior notice until the stage environments upgrade date. Learn more in the [Release planning page](../../rn/using/release-planning.md).

-->

## 26.1版(LA) {#26.1}

>[!AVAILABILITY]
>
>此版本仅适用于一组组织（限量发布）。 有关更多信息，请与您的 Adobe 代表联系。

### 安全修复 {#winter-26-security}

* 此版本提供安全修复。
* 此版本附带以下安全升级：Debian 12和PostgreSQL 17。

### 其他修复 {#winter-26-fixes}

* 对“动态报告”进行了改进，从而提高稳健性并减少数据不匹配的情况。 (CAMP-58964)
* 改进了IMS登录机制以提高可靠性。 (CAMP-59418)
* 改进了AEM内容集成，针对分页请求提供了更好的URL处理。 (CAMP-59540)
* 在“选项”屏幕中添加了密码类型输入支持，并带有自动散列功能。 (CAMP-60206)
* 修复了临时工作流使用错误序列ID的问题。 (CAMP-59824)
* 修复了在检索AEM促销活动内容时可能导致错误的问题。 (CAMP-59926)
