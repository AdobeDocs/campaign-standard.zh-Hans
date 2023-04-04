---
title: 早期发行说明
description: 早期发行说明
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 1a8e623c034a2fbacd9ddf37711488a8f6b99442
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---


# 早期发行说明 {#e-new-release}

本页介绍了下一个 Campaign Standard 版本中包含的改进和修复。
>[!CAUTION]
>
> 在暂存环境升级日期之前，此内容可能会有所变动，恕不另行通知。在[发行计划页面](../../rn/using/release-planning.md)中了解详情。

## 22.3.2 版 {#dec-22}

### 安全更新{#rn-security2}

此版本附带以下安全升级：Debian 已升级到 v11.0。

## 22.3 版 - 2022 年秋冬 {#sept-22}

### 安全更新{#rn-security}

此版本附带以下安全升级：Apache Tomcat 已从 v7.0 升级到 v8.0。

### 修复{#e-rn-fixes}

* 修复了计划报表在计划时间之前一小时被触发的问题。(CAMP-51502)
* 修复了投放仪表板中的投放指标与发送日志 (nms:broadLogRcp) 不匹配的问题。(CAMP-51127)
* 修复了导致无法使用 ACS 连接器（高级服务）扩展自定义资源的问题。(CAMP-51033)
* 改进了隐私请求响应的发布流程，以避免延迟。(CAMP-50613)
