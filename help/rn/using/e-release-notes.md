---
title: 早期发行说明
description: 早期发行说明
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 93f1a6cb0727859f3c3f645366a9d2dc25795a79
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 19%

---


# 早期发行说明 {#e-new-release}

本页介绍了下一个Campaign Standard版本中包含的改进和修复。

>[!CAUTION]
>
> 在暂存环境升级日期之前，此内容可能会有所变动，恕不另行通知。在[发行计划页面](../../rn/using/release-planning.md)中了解详情。

## 22.3版 — 2022年秋冬 {#e-rn-2022}

### 改进{#e-rn-improvements}

**辅助功能**

Campaign Standard22.3附带了辅助功能修复和改进功能，可帮助用户导航并充分利用Adobe Campaign。

这些功能在有限可用性中发布，并且仅向一组客户推出。 要在促销活动环境中启用这些改进，请联系您的Adobe代表。

<!--
* **Data retention**

    Data retention periods have been reduced to avoid overloading Campaign server. However, you can still modify these values and define a custom period of time based on your needs and data retention policies. To change retention periods, contact Adobe.
-->

### 安全更新{#e-rn-security}

此版本附带以下安全升级：Apache Tomcat已从v7.0升级到v8.0。

### 修复{#e-rn-fixes}

* 修复了计划报表在计划时间之前一小时触发的问题。 (CAMP-51502)
* 修复了投放仪表板中投放指示器与发送日志(nms:broadLogRcp)不匹配的问题。 (CAMP-51127)
* 修复了阻止使用ACS Connector(Prime Offering)扩展自定义资源的问题。 (CAMP-51033)
* 改进了隐私请求响应的发布流程，以避免延迟。 (CAMP-50613)