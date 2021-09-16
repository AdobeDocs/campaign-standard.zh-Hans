---
title: 最新版本
description: 此页面详细描述最新 Campaign Standard 版本的内容
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1074'
ht-degree: 100%

---


# 最新版本{#latest-release}

## 21.3 版 - 2021 年 9 月 {#release-21-3---sept-2021}

下面列出了 Campaign Standard 最新版本中包含的新增功能、改进和修复。

**新增功能**


<table> 
<thead> 
<tr> 
<th> <strong>统一的 Experience Cloud 界面</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Adobe Campaign 标题栏已更改，以统一和改进所有 Experience Cloud 产品和服务中的体验。这些更改旨在使您的生活更轻松，包括：</p>
<ul>
<li>更轻松地在组织之间切换或切换到其他应用程序。</li>
<li>改进的用户帮助 - 将 Experience League 引入到产品中，搜索结果还包括社区论坛中的结果和更多视频内容，使您能够更轻松地访问更多内容，从而充分利用应用程序。我们还在“帮助”菜单中添加了反馈机制，使得报告问题或分享构想更加轻松。</li>
<li>改进的通知 - “通知”下拉列表现在包含两个选项卡：一个用于您自己的产品通知，另一个用于更多全球产品公告。</li>
</ul>
<p>有关更多信息，请参阅<a href="../../start/using/interface-description.md#top-bar">详细文档</a>。
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>审核记录</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>新的审核记录功能可实时捕获在 Adobe Campaign 内发生的操作和事件的全面列表。审核记录功能提供了一种访问数据历史记录的自助方式，可帮助回答以下问题：</p>
<ul>
<li>此工作流发生了什么变化，谁最后进行了更新？</li>
<li>谁进行了最后的改动？</li>
<li>之前的状态是什么样？</li>
</ul>
<p>Adobe Campaign 现在会审核以下项目的创建、编辑和删除操作：工作流、选项、自定义资源。此外，还会跟踪这些项目的修改。</p>
<p>有关更多信息，请参阅<a href="../../administration/using/audit.md">详细文档</a>。</p>
</td> 
</tr> 
</tbody> 
</table>


<table> 
<thead> 
<tr> 
<th> <strong>工作流诊断模式</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>您现在可以在诊断模式下运行 Campaign 工作流。此模式会记录信息，帮助排除执行问题。默认情况下，如果工作流查询花费了超过一分钟时间，则会记录整个执行计划。</p>
<p>有关更多信息，请参阅<a href="../../automating/using/managing-execution-options.md">详细文档</a>。</p>
</td> 
</tr> 
</tbody> 
</table>

**安全性改进**

* 增强了针对 SSRF 攻击的安全性。(CAMP-47836)
* 用户列表现在仅限管理员使用。(CAMP-47260)
* 环境变量不能再用作 URL 中参数扩展的一部分。(CAMP-47268)

**改进**

* 现在，在工作流中创建链接到 Adobe Experience Manager 内容的定期投放时，发送之前会检查内容批准状态。
* 数据库连接限制现在与 Campaign 包一致，以避免连接错误。
* 自定义资源发布中新增的一致性检查可阻止用户创建重复的索引，以避免导致发布失败。改进后的错误消息会要求用户根据需要重命名索引。

**其他变更**

* 现已在 Campaign Standard 中弃用 Adobe Experience Platform Data Connector 和 Audience Destinations 服务。如果您正在使用这些功能，则需要转到 Adobe Sources 与 Destinations 并调整实施。[了解详情](../../integrating/using/get-started-sources-destinations.md)
* [此页面](deprecated-features.md)中列出了已弃用和已删除的功能。
* 引入了新的“StringAgg”聚合函数，以连接字符串类型列的值。(CAMP-47077) [了解详情](../../automating/using/list-of-functions.md#aggregates)
* **更新投放指标** (updateDeliveryIndicators) 技术工作流已得到改进，可实现更好的性能。
* 应用程序内消息模板现在适用于 Campaign Standard 支持的所有语言。
* 通过减少投放分析期间对跟踪服务器的调用次数，已针对事务型消息优化了投放准备时间。
* 新的警报消息会通知用户高跳出率情况。
* 改进了日志错误消息和警告，以便在无法正确检索跟踪日志时更轻松地进行调试。（CAMP-48939 和 CAMP-47360）
* 您现在可以对 URL 进行完全的个性化设置，包括域名。[了解详情](../../designing/using/personalization.md#personalizing-urls)

**修补程序**

* 修复了从 URL 导入电子邮件内容时出现的超时错误。(CAMP-49054)
* 修复了访问已添加书签的 URL 或从浏览器刷新页面时，由会话结束导致的错误 (-69)。(CAMP-49003、CAMP-48930、CAMP-48894)
* 修复了将规则从旧版可交付性服务器同步到新版可交付性服务器时出现的问题。(CAMP-48923)
* 修复了在电子邮件设计工具中加载带有 HTML 标签的电子邮件模板时出现的问题。(CAMP-48243)
* 修复了使用 Email Designer 创建事务型消息时 Adobe Experience Manager 内容无法加载的错误。(CAMP-49075)
* 修复了界面中顶部栏和内容之间添加的内边距过多的问题。
* 修复了有关事务型消息的问题，即在 Adobe Experience Manager 内容中使用 Campaign 内容块时可能导致发布错误的问题。(CAMP-49233)
* 修复了在身份验证失败时可能导致出现错误消息的问题。现在，用户将被重定向到登录页面。
* 修复了可能阻止用户编辑或共享报表的令牌显示问题。
* 修复了使用具有 1-n 表关系的过滤器表达式发布自定义资源期间出现的问题。(CAMP-48740)
* 修复了导致无法在工作流过渡中检索投放联系日期的日期格式问题。(CAMP-48871)
* 修复了在创建自定义用户档案维度期间导致无法扩展发送日志的问题。
* 修复了可能导致具有多种语言变体的投放失败的问题。从现在起，如果用户删除默认语言变体，则在创建语言副本之前，必须将另一个语言变体设置为默认语言变体。(CAMP-48235)
* 修复了在设计消息时，如果用户选择了 **Only show on mobile devices** 选项，会导致电子邮件在 Outlook 中显示额外空格的问题。(CAMP-48902)
* 修复了在运行增量查询工作流后，**Processed Data** 选项卡中缺失增量查询活动字段的上次执行日期的问题。(CAMP-48879)
* 修复了导致无法在&#x200B;**分段**&#x200B;工作流活动中正确定义动态段代码的问题。(CAMP-48727)
* 修复了在编辑工作流后尝试保存该工作流时随机发生的错误。(CAMP-48695)
* 修复了由于触发器的数据架构即使在删除触发器后仍然存在而导致无法发布自定义资源的问题。(CAMP-48523)
* 修复了由于 InMail 进程无法检索投放日志以进行更新而无法处理反馈循环请求的问题。(CAMP-48705)
* 修复了导致无法在&#x200B;**排除**&#x200B;工作流活动中正确定义排除选项的问题。(CAMP-48355)
* 修复了当工作流中的扩充活动涉及服务订阅或退订时发生的问题。这个问题会导致崩溃。
* 修复了可能阻止工作流运行的问题。
* 修复了可能阻止用户从用户界面重命名或删除开箱即用的安全组的问题。
* 修复了可能阻止用户删除未完成的事件发布作业的问题。
* 修复了数据库清理工作流失败并出现错误的问题。(CAMP-49097)
