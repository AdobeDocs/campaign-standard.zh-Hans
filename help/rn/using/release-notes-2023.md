---
title: 2023 年版发行说明
description: 本页列出了所有 2023 年版的 Adobe Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: 5817c4d2-4788-4695-bf9a-ec04cc042190
TQID: 'https://experienceleague.adobe.com/YpZ3cQVh6CeVyCkOChGYLBUo1dMueoWh1AkFj3ycRwk'
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
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: cc72dcf1-72e1-48cc-b434-e7c27d62d67c
    internal-label: Accessibility
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: ht
source-wordcount: '463'
ht-degree: 100%
---
# 2023 年版发行说明 {#release-notes-2023}

## 23.2 版 - 2023 年秋冬版 {#fall-23}

>[!AVAILABILITY]
>
>此版本仅适用于一组组织（限量发布）。 有关更多信息，请与您的 Adobe 代表联系。

### 改进 {#fall-23-rn-improvements}

* **与 Adobe Experience Manager 集成**。 在 Adobe Experience Manager 中为事务型消息创建个性化投放模板时，您现在可以选择并使用下拉菜单中 Campaign Standard 定义的个性化字段。 [了解详情](../../integrating/using/creating-email-experience-manager.md)

* **Cookie 过期** - 为遵守法国数据保护局 (CNIL) 的要求，默认 Cookie 过期时间现在设置为 6 个月。

* **轮廓搜索改进**  - 轮廓搜索已优化，因此可以减少搜索超时情况

* **本地化** - 在提及一组旨在接收消息的轮廓时，“受众”一词的翻译在以下语言的所有数字体验产品中都得到了统一：

  * 德语：Zielgruppe
  * 巴西葡萄牙语：público-alvo
  * 西班牙语：público destinatario

  这些更改将在下一个 UI 和文档版本中逐步推出。


### 其他变更 {#fall-23-rn-other-changes}

* 交易型消息传递现在支持使用多个逗号分隔的关联。 [了解详情](../../sending/using/managing-typologies.md)

### 修复 {#fall-23-rn-fixes}

* 修复了在使用大型工作流时可能导致性能问题的回退。 (CAMP-53369)
* 修复了导致工作流电子邮件警报或通知中的链接无法正常工作的问题。 (CAMP-51874)

## 23.1 版 - 2023 年春/夏季版 {#apr-23}

### 改进 {#e-rn-improvements}

* 推送消息传递服务经过了现代化改进，以便优化支持。 (CAMP-47959)
* 短信消息传递服务经过了现代化改进，以便提供更好的稳定性。 (CAMP-52217)
* Adobe 进行了许多辅助功能修复，以提高应用程序的整体易用性。 以下是一些辅助功能改进示例：
  * 界面的键盘辅助功能已在多个屏幕中得到优化。
  * 根据触摸屏用户的需要对应用程序进行了增强。
  * 更改了界面中多个项目的颜色，以便提高可见性。

### 其他变更 {#e-rn-changes}

* 增添了开箱即用的&#x200B;**报告扩充创建工作流**。 在将目标映射从一个实例导入另一个实例后，只需运行工作流以导入相应的报告扩充条目。 (CAMP-52452)

### 已修复的问题{#e-rn-patches}

* 修复了在显示&#x200B;**热门点击**&#x200B;报告时可能导致超时错误的问题。 (CAMP-51582)
* 修复了可能会阻止您无法使用与&#x200B;**位置**&#x200B;服务的集成的问题。 (CAMP-51923)
* 修复了可能导致工作流程调度程序无法正常工作的问题。 (CAMP-52003)
* 修复了在查看包含大量数据的自定义动态报告的 PDF 版本时，细分详细信息无法显示的问题。 (CAMP-52178)
* 修复了访问报告时可能显示错误的问题。 (CAMP-52500)
* 修复了将&#x200B;**限制此帐户的 MTA 实例**&#x200B;短信连接器参数错误地应用于所有渠道，而不是仅应用于短信的问题。 (CAMP-52640)
