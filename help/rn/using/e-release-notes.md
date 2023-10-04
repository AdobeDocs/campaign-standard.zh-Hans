---
title: 早期发行说明
description: 早期发行说明
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 46c5454ad712910c88bfda7c067fda0337b043d9
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 83%

---


# 早期发行说明 {#e-new-release}

本页介绍了下一个 Campaign Standard 版本中包含的改进和修复。

>[!CAUTION]
>
> 在暂存环境升级日期之前，此内容可能会有所变动，恕不另行通知。在[发行计划页面](../../rn/using/release-planning.md)中了解详情。

## 23.2 版 - 2023 年秋冬版 {#fall-23}

>[!AVAILABILITY]
>
>此版本仅适用于一组组织（限量发布）。 有关更多信息，请与您的 Adobe 代表联系。

### 改进 {#e-rn-improvements}

* **与 Adobe Experience Manager 集成**。在 Adobe Experience Manager 中为事务型消息创建个性化投放模板时，您现在可以选择并使用下拉菜单中 Campaign Standard 定义的个性化字段。

* **Cookie 过期**  - 默认 Cookie 过期时间现在设置为 6 个月，以符合法国数据保护局 (CNIL) 的建议。

* **配置文件搜索改进**  - 配置文件搜索已优化，因此可以减少搜索超时情况

* **本地化** - 在提及一组旨在接收消息的配置文件时，“受众”一词的翻译在以下语言的所有数字体验产品中都得到了统一：

   * 德语：Zielgruppe
   * 巴西葡萄牙语：público-alvo
   * 西班牙语：público destinatario

  这些更改将在下一个 UI 和文档版本中逐步推出。

### 其他变更 {#e-rn-other-changes}

* 事务型消息传递现在支持使用多个逗号分隔的亲和度。

### 修复 {#e-rn-fixes}

* 修复了在使用大型工作流时可能导致性能问题的回归。 (CAMP-53369)
* 修复了工作流警报或通知中的电子邮件链接无法正常使用的问题。 (CAMP-51874)
