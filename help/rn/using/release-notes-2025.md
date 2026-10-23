---
title: 2025年版发行说明
description: 本页列出了所有2025版的Adobe Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: 9046db34-f610-4721-b6eb-92334149366d
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e8d937ec-9046-41b5-834b-d22a624e0d37
    internal-label: Campaign overview
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 94%
---
# 2025年版发行说明 {#release-notes-2025}

## 版本 25.2 - 2025 夏季版 {#summer-25}

### 安全修复 {#summer-25-security}

* 此版本提供安全修复。
* 此版本附带以下安全升级：PostgreSQL 14.18，已从 CentOS 迁移到 Rocky 以用于 Azure 实例。

### 其他修复 {#summer-25-fixes}

* 改进了对序列耗尽的处理，提高了系统的可靠性。 (CAMP-57281)
* 常规产品稳定性更新。 (CAMP-57339)
* 对“动态报告”进行了改进，从而提高稳健性并减少数据不匹配的情况。 (CAMP-58157)
* 修复了下拉菜单无法正确进行文本换行的问题。 (CAMP-57360)
* 更新了报告功能，防止用户查询早于 2 年以上的数据。 (CAMP-59262)

## 版本 25.1.2 {#25.1.2}

### 安全修复 {#25.1.2-security}

* 此版本提供安全修复。
* 此版本随附以下安全升级：Apache Tomcat 已升级到 v10.1.36。

### 其他修复 {#25.1.2-fixes}

* 修复了可能会阻止用户通过 IMS 登录的令牌解析问题。 (CAMP-57337)
* 改进了自动序列 ID 生成机制，提高了系统的可靠性。 (CAMP-57281)

## 25.1 版 - 2025 年冬季版 {#winter-25}

### 安全修复 {#winter-25-security}

* 此版本提供安全修复。
* 此版本随附以下安全升级：Apache Tomcat 已升级到 v10.1.33。

### 其他修复 {#winter-25-fixes}


* 修复了订阅摘要屏幕中的“数据架构”URL (CAMP-56168、CAMP-56296)
* 修复了使用&#x200B;**要立即发送的消息**&#x200B;选项时绕过疲劳规则的问题 (CAMP-56866、CAMP-57033)
* 修复了模板中的重复问题 (CAMP-56340)
* 修复了在 Adobe Experience Manager 模板中使用动态 URL 时的跟踪回归问题 (CAMP-51932)
* 修复了计费流程的性能问题 (CAMP-56796)
* 修复了 JSSP 网页上 `>` 字符的 HTML 编码问题 (CAMP-56497)
* 修复了使用&#x200B;**在选定行上显示**&#x200B;选项时动态报告中出现的问题 (CAMP-55895)
