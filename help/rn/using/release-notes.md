---
title: 最新版本
description: 此页面详细描述最新 Campaign Standard 版本的内容
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 1d8baca669235be10d373d985ea62f6f014c16f8
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 100%

---


# 最新版本{#latest-release}

![控制面板](assets/do-not-localize/cp-icon.png) **新的控制面板版本**。[了解详情](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=zh-Hans){target="_blank"}。


## 23.2 版 - 2023 年秋冬版 {#fall-23}

>[!AVAILABILITY]
>
>此版本仅适用于一组组织（限量发布）。 有关更多信息，请与您的 Adobe 代表联系。

### 改进 {#fall-23-rn-improvements}

* **与 Adobe Experience Manager 集成**。在 Adobe Experience Manager 中为事务型消息创建个性化投放模板时，您现在可以选择并使用下拉菜单中 Campaign Standard 定义的个性化字段。[了解详情](../../integrating/using/creating-email-experience-manager.md)

* **Cookie 过期** - 为遵守法国数据保护局 (CNIL) 的要求，默认 Cookie 过期时间现在设置为 6 个月。

* **配置文件搜索改进**  - 配置文件搜索已优化，因此可以减少搜索超时情况

* **本地化** - 在提及一组旨在接收消息的配置文件时，“受众”一词的翻译在以下语言的所有数字体验产品中都得到了统一：

   * 德语：Zielgruppe
   * 巴西葡萄牙语：público-alvo
   * 西班牙语：público destinatario

  这些更改将在下一个 UI 和文档版本中逐步推出。


### 其他变更 {#fall-23-rn-other-changes}

* 交易型消息传递现在支持使用多个逗号分隔的关联。[了解详情](../../sending/using/managing-typologies.md)

### 修复 {#fall-23-rn-fixes}

* 修复了在使用大型工作流时可能导致性能问题的回退。 (CAMP-53369)
* 修复了导致工作流电子邮件警报或通知中的链接无法正常工作的问题。(CAMP-51874)

## 23.1 版 - 2023 年春/夏季版 {#apr-23}

### 改进 {#e-rn-improvements}

* 推送消息传递服务经过了现代化改进，以便优化支持。(CAMP-47959)
* 短信消息传递服务经过了现代化改进，以便提供更好的稳定性。(CAMP-52217)
* Adobe 进行了许多辅助功能修复，以提高应用程序的整体易用性。以下是一些辅助功能改进示例：
   * 界面的键盘辅助功能已在多个屏幕中得到优化。
   * 根据触摸屏用户的需要对应用程序进行了增强。
   * 更改了界面中多个项目的颜色，以便提高可见性。

### 其他变更 {#e-rn-changes}

* 增添了开箱即用的&#x200B;**报告扩充创建工作流**。在将目标映射从一个实例导入另一个实例后，只需运行工作流以导入相应的报告扩充条目。(CAMP-52452)

### 已修复的问题{#e-rn-patches}

* 修复了在显示&#x200B;**热门点击**&#x200B;报告时可能导致超时错误的问题。(CAMP-51582)
* 修复了可能会阻止您无法使用与&#x200B;**位置**&#x200B;服务的集成的问题。(CAMP-51923)
* 修复了可能导致工作流程调度程序无法正常工作的问题。(CAMP-52003)
* 修复了在查看包含大量数据的自定义动态报告的 PDF 版本时，细分详细信息无法显示的问题。(CAMP-52178)
* 修复了访问报告时可能显示错误的问题。(CAMP-52500)
* 修复了将&#x200B;**限制此帐户的 MTA 实例**&#x200B;短信连接器参数错误地应用于所有渠道，而不是仅应用于短信的问题。(CAMP-52640)
