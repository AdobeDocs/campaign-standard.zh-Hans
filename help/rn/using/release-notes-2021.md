---
title: 发行说明 2021
description: 本页列出了所有 2021 版的 Adobe Campaign Standard。
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 225c65cc-2964-4b71-84a9-30fcd22d75bf
source-git-commit: 63cd437c5a19791ffb9d3c0b8690ee1532a4774d
workflow-type: ht
source-wordcount: '4695'
ht-degree: 100%

---

# 2021 年版发行说明{#release-notes-2021}

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
* **更新传递指示器** (updateDeliveryIndicators) 技术工作流已得到改进，可实现更好的性能。
* 应用程序内消息模板现在适用于 Campaign Standard 支持的所有语言。
* 通过减少投放分析期间对跟踪服务器的调用次数，已针对事务型消息优化了投放准备时间。
* 新的警报消息会通知用户高跳出率情况。
* 改进了日志错误消息和警告，以便在无法正确检索跟踪日志时更轻松地进行调试。（CAMP-48939 和 CAMP-47360）
* 您现在可以对 URL 进行完全的个性化设置，包括域名。[了解详情](../../designing/using/personalization.md#personalizing-urls)
* 现在，验证和陷阱用户档案已从动态报告中的投放性能计算中排除。(CAMP-47338)

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


## 21.2 版 - 2021 年 6 月 {#release-21-2---june-2021}

下面列出了下一个 Campaign Standard 版本中包含的新增功能、改进和修复。下面列出了此 Campaign Standard 版本中包含的新增功能、改进和修复。

**改进**

* 设计登陆页面时，您现在可以添加一个必填复选框，要求在提交表单前选择用户档案。有关更多信息，请参阅[详细文档](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox)。

* 对于 Triggers 集成，当触发器有效载荷中没有协调数据时显示的错误消息已得到改进：&quot;负载中缺少别名数据&quot;。

* 改进了从队列检索推送通知的性能。

**其他变更**

* 已禁用跟踪链接的 URL 签名机制，以防止在被第三方安全工具修改后导致某些有效的已签名跟踪链接被错误阻止的问题。

* 在多变体投放中，如果删除了默认变体，则用户将无法再创建语言副本。现在，在语言副本创建期间会显示消息。(CAMP-48235)

* 现在，默认情况下禁用两步用户档案删除流程（从 Campaign 19.4 版本开始被弃用）。以前，必须先从 Campaign 界面手动禁用该功能，然后才能使用隐私核心服务。否则，会导致删除请求在未完成的情况下保持挂起状态。

* 在动态报告中，****“排除验证”区段已被移除。(CAMP-46161)

* 添加了新的警告消息，以便在 Campaign 应用程序中缺少 platformPrincipal 值的情况下上传 iOS 证书时通知用户。

* 现在，电子邮件的最大大小默认设置为 100 MB。利用此限制，可防止出现任何可能无限制地增加电子邮件大小的错误，这些错误可能会导致系统崩溃。(CAMP-47445) [了解详情](../../sending/using/design-and-personalize.md#email-size)

* 现在，标准用户可以使用资产核心服务与电子邮件设计器的集成。

* 添加了新消息，以确认成功从 v4 推送应用程序迁移到 v5 推送应用程序。

* 在创建 JSONWeb 令牌以对 Campaign Standard API 进行身份验证期间，会“考虑”产品配置文件现在&#x200B;****。这意味着分配给安全组的组织单位和角色（与 AdobeIO 上的产品配置文件匹配）将应用于 Campaign Standard Rest API 调用所需的 IMS 技术帐户。(CAMP-47479)

**修补程序**

* 修复了批量处理日志表 (**xtkjoblog**) 的到期选项无法应用的问题。这会阻止正确清除表。

* 修复了阻止您更改“分段”****&#x200B;工作流活动中过滤器顺序的问题。(CAMP-48357)

* 修复了 20.4 中的可能会导致投放失败并出现空值错误的回归问题。(CAMP-48591)

* 修复了阻止通过“共享”**** >****“立即发送报表”或&#x200B;****“按计划发送报表”菜单发送报表的问题。(CAMP-47798)

* 修复了可能会由于过滤从 Gmail 帐户接收的跟踪事件而导致 Gmail 的打开率不正确的回归问题。(CAMP-46504)

* 修复了导致 Adobe Campaign Standard 中的报表与 Adobe Analytics 中的报表之间存在数据差异的各种问题。（CAMP-47671 和 CAMP-47296）

* 修复了准备失败后无法访问投放日志的问题。(CAMP-48296)

* 修复了在尝试编辑、删除或发送自定义报表时可能显示错误消息的问题。（CAMP-47789 和 CAMP-47798）

* 修复了在创建新的自定义资源并启用“不同步”****&#x200B;选项时导致 API 调用失败的问题。(CAMP-48014)

* 修复了启用“不同步”****&#x200B;选项的自定义资源可能引用已重新起草或删除的架构的问题。此问题在发布自定义资源时会导致错误。

* 修复了在同一外部帐户上使用多个短代码时短信的选择退出问题。

* 修复了在发布数据库后无法访问新投放警报标准（“您尝试访问的资源不可访问”）的问题。(CAMP-48221)

* 修复了某些具有动态报告的 Campaign 实例中缺少跟踪日志的问题。 添加了新的[技术工作流](../../administration/using/technical-workflows.md)以恢复这些跟踪日志。(CAMP-47885)

* 修复了动态报告中未显示投放数据的问题。报表被设置为 0。(CAMP-47480)

* 修复了阻止服务器 JavaScript HTTP 客户端连接到外部 URL 的问题。

* 修复了在更改工作流的内部名称后重置“增量查询”****&#x200B;活动的问题。当将日期字段用作增量模式时，会发生这种情况。(CAMP-47674)

* 修复了使用 Adobe Experience Manager 集成创建多语言电子邮件时，投放摘要中无法显示预览缩略图的问题。使用“语言副本创建”****&#x200B;按钮创建电子邮件变体时，出现此问题。(CAMP-47810)

* 修复了阻止用户从电子邮件或短信子投放访问父投放的问题。(CAMP-47986)

* 修复了在通过缺少自定义事件的 REST API 发送事务型消息时，可能导致 CPU 和内存消耗过多的问题。(CAMP-47147)

* 修复了事务性消息传递 API 的错误，该错误有时会阻止发送实时消息。

* 修复了使用“按计划发送报表”****&#x200B;选项后未收到报表的问题。（CAMP-48583 和 CAMP-47786）

* 修复了使用“立即发送报表”选项&#x200B;****&#x200B;后收到的报表不完整且缺少数据的问题。(CAMP-48583)

* 修复了 Email Designer 在上传图像时缩小图像尺寸的问题。(CAMP-47017)

* 修复了在创建投放时阻止显示每个可用 Experience Manager 模板的问题。(CAMP-48132)

* 修复了阻止已发送投放的“Summary”页面中的“Campaign”链接将用户重定向到相关营销活动的错误。(CAMP-48012)

* 修复了 Email Designer 中的一个问题，即在尝试选择资源时，Asset Core Service 集成一直失败。(CAMP-47446)

* 修复了由于 Campaign 不支持由 Journey Orchestration 事件发送的具有精确值（即以 00 结尾）的时间戳，从而阻止某些 Journey Orchestration 投放的问题。

## 21.1 版 - 2021 年 2 月 {#release-21-1---february-2021}

**新增功能**

<table> 
<thead> 
<tr> 
<th> <strong>电子邮件反馈服务</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>电子邮件反馈服务 (EFS) 是一种可扩展服务，它直接从增强型 MTA 捕获反馈，从而提高报告准确性。此功能作为专用测试版发布，并将在未来版本中逐步向所有客户提供。</p>
<ul>
<li>现在可捕获所有类别的反馈，以实现完整且精确的报告。</li>
<li>现在，<b>已传送</b>指示器的计算基于来自增强型 MTA 的实时反馈，以提高准确性和反应性。</li>
<li>EFS 解决了同步软退回报告的延迟问题。</li>
</ul>
<p>有关更多信息，请参阅<a href="../../sending/using/confirming-the-send.md">详细文档</a>。
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Adobe Experience Manager 集成改进</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Campaign 与 Adobe Experience Manager 的集成已得到改进：您现在可以更轻松地从 Adobe Experience Manager 导入多语言内容。 <p>
<p>Adobe Campaign Standard 现在自动从 Adobe Experience Manager 内容中检测语言变体，并允许批量导入和创建变体，从而大幅简化从业者基于 Adobe Experience Manager 内容创建多语言活动所需执行的步骤数。</p>
<p>有关更多信息，请参阅<a href="../../integrating/using/creating-multilingual-email-aem.md">详细文档</a>。
</p>
</td> 
</tr> 
</tbody> 
</table>

<!--
<table> 
<thead> 
<tr> 
<th> <strong>Unified Experience Cloud interface</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Adobe Campaign header bar has been changed to unify and improve your experience across all Experience Cloud products and services. These changes are designed to make your life easier, including:</p>
<ul>
<li>Easier switching between your organizations or to a different application.</li>
<li>Improved User Help – Bringing the Experience League into the product, search results also include results from community forums and more video content, giving you easier access to more content to help get the most out of the application. We've also added a feedback mechanism right in the Help menu, making it easier to report issues or share your ideas.</li>
<li>Improved Notifications – Notifications drop-down now has two tabs: one for your own product notifications, and one for more global product announcements.</li>
</ul>
<p>For more information refer to the <a href="../../start/using/interface-description.md#top-bar">detailed documentation</a>.
</p>
<p>NOTE: This change will be progressively rolled out to all customer environments between Feb 10 and March 1st.
</p>
</td> 
</tr> 
</tbody> 
</table>
-->

**改进**

* **Microsoft Dynamics 365 集成**&#x200B;已通过专用自助服务集成应用程序和经过改进的实施过程得到增强。[了解详情](../../integrating/using/d365-acs-get-started.md)

* 为便于在事务性消息传递过程中遇到问题时进行故障诊断，已做出改进。Adobe 技术管理员现在可以对任何过程使用跟踪，而无需将其重新启动。

* 现在，通过&#x200B;**用户档案**&#x200B;列表可根据以下字段之一搜索记录：在扩展用户档案资源时，已在高级筛选中添加了电子邮件、名字、姓氏或自定义字段。此功能在使用 filterType 参数的 Campaign Standard API 中也可用。[了解详情](../../audiences/using/integrated-customer-profile.md)

* 参数已调整为运行事务性消息传递数据库池进程的容器的数量。借此可将负载均匀分布在所使用的所有容器上并达到最佳性能。

* 使用外部参数调用工作流后，在使用事件变量的活动中现在有新的 **GetOption** 函数可用。通过该函数可返回指定函数的值。[了解详情](../../automating/using/customizing-workflow-external-parameters.md)

* 通过新选项，Campaign Standard 可在启动工作流之前&#x200B;**检查系统上可用的物理内存**。如果内存量太低，则工作流执行将延迟，直到系统内存达到此阈值。这可避免性能进一步降低，并减轻中断的风险。一旦服务器上的负载下降且内存增加，工作流程就将自动恢复。请注意，此选项为只读，无法修改。[了解详情](../../automating/using/best-practices-workflows.md#execution)

* 在 Adobe Campaign Standard 中提供了一个新流程，通过该流程可更轻松地从传统 SDK v4 移动应用程序迁移到 **Adobe Experience Platform Mobile SDK**。请参见[此页面](../../administration/using/sdkv4-migration.md)。

**其他变更**

* 当达到每滚动小时 100 个内容下载的限制时，在消息准备过程中将错误更改为警告。当达到限制时，现在会显示警告，允许继续投放。

* 在丰富事务性消息内容时，当从用户档案表获取数据时，不再检索链接，这会减少消息准备期间的延迟，并避免由于与用户档案表定义的关系不正确而导致用户档案数据为空。

* 为确保稳定性，已对实例技术配置进行优化。(CAMP-45681)

* 为优化内存，已改进会话管理。（CAMP-45901 和 CAMP-46767）

* 现在，**传输文件**&#x200B;活动会生成一个附加变量 (filesCount)，其中包含已上载或已下载的文件数。(CAMP-45842) [了解详情](../../automating/using/transfer-file.md#output-variables)

* 短信连接器现在可以随每条消息发送多个可选参数。[了解详情](../../administration/using/sms-protocol.md)

* 具有 DATAMODEL 角色的用户现在可以发布投放日志扩展。(CAMP-46604)

* 在尝试发布针对不再存在的自定义资源的资源时所显示的错误消息变得更清晰。(CAMP-46893)

* 已向&#x200B;**首选语言**&#x200B;列表中添加下列语言：印度尼西亚语 - 印度尼西亚 (in-id)、英语 - 瑞典 (en-se)、英语 - 亚太地区 (en-ap)、英语 - 日本 (en-jp)、西班牙语 - 拉丁美洲 (es-la)。(CAMP-46351)

* 测试登陆页时用于选择用户档案的的选取器现在将使用 profilBase 资源而不是用户档案，以防止超时。

* SMPP 日志格式已得到改进。

* 添加了 cryptString 和 decryptString JS 函数的可选参数，以匹配 Adobe Campaign Standard API。

* 改进了投放准备日志中的警告或错误消息。

* 在尝试连接到 Adobe Identity Management 服务 (IMS) 时改进了错误日志。

* 您现在可以使用动态报告中的搜索栏进一步筛选&#x200B;**投放**&#x200B;和&#x200B;**活动**&#x200B;维度。

* 事务性短信消息有效日期现在可以由事务性消息 API 中为到期参数设置的值定义。(CAMP-36600)

* 在动态报告中，**投放摘要**&#x200B;内置报告显示取消订阅率指标的错误数据。为修复此问题，添加了名为&#x200B;**唯一取消订阅**&#x200B;的新指标。(CAMP-46445)

**修补程序**

* 修复了由于某些过程而导致投放运行非常缓慢的问题。这是由于为多个参数定义的单位不正确（例如，毫秒而不是秒）。

* 修复了 Mobile SDK 根据 deliveryId/MessageID 不为空的条件发送开放跟踪请求时的问题。这将导致禁用跟踪的投放发生 404 错误。现在，在有效负荷中会发送一个附加变量 (acsDeliveryTracking)，其中包含有关投放跟踪状态的信息。根据设置的跟踪状态，此变量可具有两个值：on 或 off。[了解详情](../../administration/using/push-tracking.md)。

* 修复了在复制粘贴已执行一次并利用临时资源的&#x200B;**重复数据删除**&#x200B;活动时可能发生的工作流中的问题。一旦数据重复，该活动的资源就会自动设置为空，从而导致工作流的其他活动出现问题。粘贴后，该活动的资源现在将保持不变，以便尽快触发错误，而不是稍后在工作流中触发错误。(CAMP-46903)

* 修复了在发送针对用户档案的事务性推送通知时导致投放分析失败的问题，方法是引入新的[目标映射](../../administration/using/target-mappings-in-campaign.md)：**用户档案 - 推送的实时事件** (*mapRtEventAppSubRcp*)。[基于用户档案的事务性推送通知](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile)的投放、排除和跟踪日志现在将存储在 *broadLogAppSubRcp*、*excludeLogAppSubRcp* 和 *trackingLogAppSubRcp* 表中。

  >[!IMPORTANT]
  >
  >由于此更改，如果您使用的是现有的基于用户档案的事务性推送通知（在升级到 Adobe Campaign 21.1 之前创建），建议您将目标映射更新为新目标映射，然后再次发布消息。请参见[此处](../../channels/using/transactional-push-notifications.md#change-target-mapping)的详细步骤。使用上一个目标映射“用户档案 - 实时事件”**** (*mapRtEventRcp*) 可能会导致更长的投放准备时间和性能下降。

* 修复了在显示 5000 行时阻止运行投放报告的问题。
* 修复了在修改投放模板后阻止更新变体 B 的内容的 A/B 测试问题。(CAMP-45235)
* 修复了导致事务性消息传递过程卡住、从而阻止发送消息的问题。
* 修复了在单击内部链接后（例如从证明摘要屏幕访问父投放时）可能导致导航问题的问题。
* 修复了在创建投放时阻止显示所有可用 Experience Manager 模板的问题。(CAMP-45990)
* 修复了工作流中在将&#x200B;**原因**&#x200B;列添加到附加数据选项卡后可能阻止在投放日志中显示故障消息的问题。(CAMP-45139)
* 修复了当两个应用程序订阅调用具有同一 Marketing Cloud ID（“重复键值违反唯一约束”错误）时可能发生的问题。
* 修复了将活动拖放到包含大量&#x200B;**查询**&#x200B;和&#x200B;**读取受众**&#x200B;活动的工作流中时可能导致速度缓慢的问题。(CAMP-44511)
* 修复了在事务性消息准备结束时可能发生的阻止将重定向信息上传到跟踪服务器的错误。
* 修复了在自定义工作流资源后尝试打开导入模板或以往导入作业时可能显示错误消息的问题。(CAMP-46183)
* 修复了在&#x200B;**读取受众**&#x200B;活动配置有动态受众名称时可能阻止该活动运行的问题。(CAMP-46047)
* 修复了阻止显示&#x200B;**导出列表**&#x200B;按钮的问题
* 修复了可能导致&#x200B;**报告聚合**&#x200B;工作流失败的问题。(CAMP-45979)
* 修复了在使用自定义组合键创建自定义资源（文本/日期动态内容）时的问题。
* 修复了可能阻止显示查询转换数据的问题。(CAMP-45669)
* 修复了与自定义资源发布相关的内存消耗问题。
* 修复了将投放配置为在特定日期发送时发生的问题。如果之后将投放设置为在确认后立即发送，则投放准备失败，并且最初指定的日期仍然考虑在内。(CAMP-44107)
* 修复了可能阻止打开事务模板的问题。(CAMP-47181)
* 修复了事务性消息发布过程中可能导致名称超过允许的字符串大小的重复类型和类型规则的问题。(CAMP-47104)
* 修复了在输入参数返回不存在的记录时&#x200B;**外部 API** 活动中发生的问题。(CAMP-47023)
* 修复了可能阻止 SMPP 连接器重新连接的问题。
* 修复了在下载名称中包含点的文件时&#x200B;**文件传输**&#x200B;活动中发生的问题。点后面的字符被视为文件的扩展名。(CAMP-46624)
* 修复了阻止执行数据库池，从而导致事务性消息卡在路由器队列中的问题。
* 修复了未阻止发送已取消的投放日志的错误。
* 修复了使用 **AND-join** 活动时可能导致工作流失败的问题。该活动自动将主集更改为与其连线的最后一个转换，即使它直观显示第一个连线转换也如此。(CAMP-46900)
* 修复了可能导致成功隔离的地址将其状态错误设置为“有效”，从而将其从隔离中移除的问题。
* 修复了在个性化字段包含特殊字符时可能阻止显示这些字段的问题。(CAMP-46805)
* 修复了可能阻止显示用户档案的特定详细视图的问题。如果用户档案资源已通过启用了&#x200B;**添加个性化字段部分**&#x200B;选项的自定义字段进行扩展，则会发生此情况。
* 修复了在发送事务事件时可能返回错误代码 500 的问题。(CAMP-46811)
* 修复了可能阻止您接收电子邮件计划报告的问题。(CAMP-46891)
* 修复了在使用 1 基数简单链接将自定义资源链接到用户档案资源链接时发生的问题。当访问自定义资源字段为空的用户档案时，现在会显示错误消息，而不是空列表。
* 修复了在工作流（选择要替换的用户档案时页面无法加载投放用户档案）中使用用户档案替换时的问题。(CAMP-46522)
* 修复了&#x200B;**数据库清除**&#x200B;技术工作流尝试删除过期数据库工作表导致以下错误的回归：(CAMP-46536)

```
   PGS-220000 PostgreSQL error: ERROR: table ""wkdlv_24439460_data"" does not exist and WDB-200001 SQL statement 'DROP TABLE wkdlv_24448131_data' could not be executed.
```

* 修复了对自定义资源使用自定义过滤器时在某些情况下发生的以下错误：(CAMP-46509)

```
   The 'profile/xxxx' field used in the filter 'xxxxx' does not exist in custom resource 'xxx'
```

* 修复了&#x200B;**推送通知准备**&#x200B;耗费太多时间以致无法完成的问题。这是由于临时工作表中缺少索引而造成。
* 修复了在自定义资源和用户档案资源之间已定义关系的情况下使用&#x200B;**要协调的维度**&#x200B;选项（在工作流中的&#x200B;**协调**&#x200B;活动中）时可能发生的错误。
* 修复了在通过&#x200B;**协调**&#x200B;或&#x200B;**扩充**&#x200B;活动添加链接时发生的问题。所选链接未显示在输出转换中。
* 修复了在工作流中对重复投放使用&#x200B;**分段**&#x200B;活动导致投放发送到错误受众的问题。（CAMP-46275 和 CAMP-46470）
* 修复了在尝试扩展用户档案资源以创建自定义用户档案维度来进行动态报告时自定义资源发布失败的错误。(CAMP-46266)
* 修复了在添加指向文件导入表的链接时发生的错误。在将&#x200B;**扩充**&#x200B;活动添加到&#x200B;**文件导入**&#x200B;活动后，先前配置的链接消失。(CAMP-46557)
* 修复了在使用链接到用户档案数据的自定义资源时，**详细信息**&#x200B;配置屏幕中的显示顺序在保存时发生更改的问题。(CAMP-46312)
* 修复了可能会因基于自定义投放映射的投放而阻止您在动态投放中显示数据的问题。
* 修复了可能会阻止您在工作流&#x200B;**查询**&#x200B;活动中选择具有不正确资源目标的集合的错误。
* 修复了可能导致 InMail 进程错误验证硬退回的问题。
* 修复了在打开用户档案屏幕时由于链接错误而发生的错误。
* 修复了可能会阻止您从清除工作流中删除 GDPR 数据的问题。
* 修复了使用电子邮件投放计划参数中的键盘手动更新计划配置时发生的错误。
* 修复了可能会由于组织单位中的参数不正确而阻止您编辑用户档案的问题。
* 修复了致使&#x200B;**服务**&#x200B;扩展字段为空且在&#x200B;**电子邮件属性**&#x200B;中无法设置的问题，即使在投放模板中进行了设置也如此。
* 修复了可能导致证明处理时间更长的问题。(CAMP-45048)
* 修复了可能会阻止您在用户档案概述屏幕中对列进行排序的问题。
* 修复了在包含中文字符的电子邮件变体中 Azure 上可能发生的缩略图生成问题。(CAMP-47152)
* 修复了在 Campaign 20.4 中引入的回归，该回归可能会由于过滤从 Gmail 帐户接收的事件而导致 Gmail 的打开率不正确。(CAMP-46504)
* 修复了可能会阻止您将 HTML 内容导入事务性消息模板中的问题。(CAMP-47318)
* 修复了可能会减慢&#x200B;**电子邮件呈现报告**&#x200B;中呈现内容的显示速度的问题。(CAMP-46226)
* 修复了可能会阻止您在屏幕定义中发布使用列表类型元素配置的自定义资源的问题。(CAMP-47217)
* 修复了 Email Designer 中阻止行分隔符当置于电子邮件内容顶部时在 **Microsoft Outlook** 中正确呈现的问题。(CAMP-46294)
* 修复了导致 KPI 与&#x200B;**Adobe Analytics** 技术工作流的协调卡住的问题。(CAMP-46576)
* 修复了 **Email Designer** 中在插入内容块时阻止片段自动显示在搜索框中的问题。(CAMP-44205)
* 修复了 **Email Designer** 中在片段中使用表情符号时导致在已发送的电子邮件中显示不需要的字符的问题。(CAMP-46621)
* 修复了 **Email Designer** 20.4 中引入的影响分隔条组件的回归，该回归导致内容中出现更多行高和图像扭曲。(CAMP-46663)
* 修复了在将邮件发送到 Outlook 邮箱时强制现成按钮保持居中的问题，即使这些按钮在 **Email Designer** 中右对齐或左对齐也如此。(CAMP-46466)
* 修复了在 **Email Designer** 预览中搜索用户档案时阻止测试用户档案列表刷新的问题。(CAMP-45265)
* 修复了在 **Email Designer** 预览中搜索用户档案时阻止自定义测试用户档案显示在列表中的问题。(CAMP-45589)
* 修复了在从&#x200B;**投放摘要报告**&#x200B;生成趋势图时导致显示不匹配日期的问题。(CAMP-45521)
