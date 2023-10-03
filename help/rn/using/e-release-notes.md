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
ht-degree: 22%

---


# 早期发行说明 {#e-new-release}

本页介绍了下一个 Campaign Standard 版本中包含的改进和修复。

>[!CAUTION]
>
> 在暂存环境升级日期之前，此内容可能会有所变动，恕不另行通知。在[发行计划页面](../../rn/using/release-planning.md)中了解详情。

## 23.2 版 - 2023 年秋冬版 {#fall-23}

>[!AVAILABILITY]
>
>此版本仅适用于一组组织（限量发布）。 有关更多信息，请与您的Adobe代表联系。

### 改进 {#e-rn-improvements}

* **与Adobe Experience Manager集成**. 在Adobe Experience Manager中为事务型消息创建个性化投放模板时，您现在可以选择并使用下拉菜单中Campaign Standard定义的个性化字段。

* **Cookie过期**  — 默认Cookie过期时间现在设置为6个月，以符合法国数据保护局(CNIL)的建议。

* **配置文件搜索改进**  — 配置文件搜索已优化，因此可以减少搜索超时情况

* **本地化**  — 术语“受众”的翻译指一组旨在接收报文的用户档案，在以下语言的所有数字体验产品中得到了统一：

   * 德语： Zielgruppe
   * 巴西葡萄牙语：público-alvo
   * 西班牙语：público destinatario

  这些更改将在下一个UI和文档版本中逐步推出。

### 其他变更 {#e-rn-other-changes}

* 事务型消息传递现在支持使用多个逗号分隔的亲和度。

### 修复 {#e-rn-fixes}

* 修复了在使用大型工作流时可能导致性能问题的回归。 (CAMP-53369)
* 修复了工作流警报或通知中的电子邮件链接无法正常使用的问题。 (CAMP-51874)
