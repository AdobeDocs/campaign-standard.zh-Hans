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
source-git-commit: 7066cf1d8454ffdefa29bff5092ba2c3e1bac705
workflow-type: tm+mt
source-wordcount: '1766'
ht-degree: 99%

---


# 最新版本{#latest-release}

## 22.1 版 - 2022 年 2 月 {#feb-2022}

**新增功能**

<table> 
<thead> 
<tr> 
<th> <strong>针对 Apache Log4j 安全漏洞的安全更新</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Apache log4j 已修复 Apache log4j 2.17.1 版本中报告的漏洞。Adobe Campaign Standard 使用 Apache log4j，并且在此版本中包含最新的 Apache log4j 2.17.1 版本 </p>
</td> 
</tr> 
</tbody> 
</table>

**安全修复**

* 此版本中包含用于跟踪的新 URL 签名机制。已禁用之前使用的机制，以防止在被第三方安全工具修改后导致某些有效的已签名跟踪链接被错误阻止的问题。(CAMP-48983)

**改进**

* 已改进报告数据的处理，以避免系统过载。(CAMP-47578)
* 发送应用程序内消息后，您现在可以选择停用投放。这样，您就可以删除投放，而不会丢失任何报告数据。(CAMP-48469)
* 为防止出现任何问题，用户不能再为自定义表列使用与数据库中自动主键值相同的名称，`"<dataType><resourceName>Id"`。(CAMP-49358)
* 您现在可以在消息仪表板上通过新的 **Job history** 下拉菜单监测投放和跟踪工作日志。(CAMP-49840)
* 通过减少死元组，提升了在一段时间内跨所有渠道发送大量消息时的稳定性和数据库运行状况。(CAMP-49755、CAMP-49792、CAMP-49849)
* 为确保在数据库崩溃或重新启动时自动刷新数据库连接，已在 Campaign 邮件传输代理 (MTA) 中实施了改进措施。(CAMP-48063)


**修补程序**

* 修复了动态报告中 **Send report now** 选项的问题：当投放包含多变体时，PDF 生成作业会失败。(CAMP-49120)
* 修复了当 AEM 中的重复内容共享相同的键值 (cq:uuid) 时，用户无法从他们的 Adobe Campaign Standard 投放中刷新或取消链接 Adobe Experience Manager (AEM) 内容的问题。(CAMP-49161)
* 修复了访问实例时出现页面未加载、投放无法打开或无法保存任何待处理的修改的错误。(CAMP-50195)
* 修复了当投放警报标准所应用的 **Delivery filter** 字段未填写时该标准无法打开的问题。(CAMP-49093)
* 修复了在应用内投放中编辑 **Secondary** 按钮时导致无法采纳变更的问题。(CAMP-50250)
* 修复了日语实例中导致用户无法在&#x200B;**调度程序**&#x200B;活动中选择“一天数次”作为&#x200B;**执行频率**&#x200B;的错误。(CAMP-50247)
* 修复了在日语用户界面中工作时，在调度程序活动中选择时间时显示错误消息的问题。(CAMP-49289)
* 修复了推送通知报告中将被忽略的推送通知显示为 **Open** 而不是 **Impression** 的问题。(CAMP-45980)
* 修复了可能会在打开报告时导致出现错误的问题。(CAMP-49222)
* 修复了删除指向 AEM 内容的链接后可能导致电子邮件准备失败的问题。(CAMP-49877)
* 为了解决各种问题，已对投放（包括从 URL 导入的内容）的重试机制进行了改进。[了解更多](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time) (CAMP-48888)
* 修复了在自定义资源中创建新筛选条件，然后将其用作登陆页面中的合并关键项后发生的问题。如果自定义资源再次发布，则会从登陆页面的可用合并关键项列表中删除该筛选条件。(CAMP-49516)
* 修复了将动态条件与复选框结合使用时登陆页面中存在的问题。(CAMP-48604)
* 修复了使用“10 月或之前”筛选条件时，**查询**&#x200B;活动中出现的问题。当从设置为欧洲时区的实例工作时，由于时区转换的问题，筛选条件的选定月份显示为 9 月，而不是 10 月。(CAMP-48602)
* 为优化投放能力，Adobe Campaign 现在使用 7 位编码而不是 8 位编码来发送电子邮件。这样可以防止中间中继使 DKIM 签名失效，从而影响邮件的真实性。(CAMP-49016)
* 增强了复制受众时的性能，以避免在处理大量受众时出现任何问题。(CAMP-49639)
* 修复了在&#x200B;**查询**&#x200B;活动中使用自定义筛选条件时可能导致其无法显示正确结果的问题。(CAMP-49417)
* 修复了尝试在投放中使用名称中带有逗号的片段时显示错误消息的错误。此问题已得到解决，现在可以在片段名称中使用逗号。(CAMP-49216)


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
* 自定义资源发布中新增的一致性检查可阻止用户创建重复的索引，以避免导致发布失败。改进后的错误消息会要求用户根据需要重命名索引。[了解详情](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)

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
