---
title: 发行说明 2020
description: 本页列出了所有 2020 版的 Adobe Campaign Standard。
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: b6cf7152-2200-43d7-8d0a-d65752bb2c9b
source-git-commit: 1d8baca669235be10d373d985ea62f6f014c16f8
workflow-type: tm+mt
source-wordcount: '5267'
ht-degree: 97%

---

# 2020 年版发行说明{#release-notes-2020}

![](assets/do-not-localize/cp-icon.png) **新的控制面板 6 月版本**，包含活动用户档案监测、子域投放能力审核和 GPG 密钥管理。[了解详情](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=zh-Hans)。

![](assets/do-not-localize/cp-icon.png) **新控制面板 10 月版**，其中使用 CNAME 进行域配置并新增数据库监视功能。[了解详情](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=zh-Hans)。

## 20.4 版 - 2020 年 10 月 {#release-20-4---october-2020}

**新增功能**

<table> 
<thead> 
<tr> 
<th> <strong>对照组</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>您现在可以使用<strong>对照组</strong>通过排除活动的一部分受众来衡量其影响。然后，便能够将收到消息的目标群体的行为与非目标联系人的行为进行比较。根据发送日志，还可以在将来活动中以对照组为目标。
</p>
<p>有关更多信息，请参阅<a href="../../sending/using/control-group.md">详细文档</a>和<a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/control-groups.html">教程视频</a>。
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>外部 API - OAuth 支持</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Adobe Campaign 现在支持使用 OAuth 在<strong>外部 API</strong> 工作流活动中进行身份验证。此新功能使此活动能够与需要 OAuth 支持的系统进行通信。
</p>
<p>有关更多信息，请参阅<a href="../../automating/using/external-api.md">详细文档</a>。
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Journey AI 集成</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>我们很兴奋地宣布为所有 Adobe Campaign Standard 客户推出 Journey AI。</p>
  <p>历程人工智能使用高级机器学习(ML)，通过预测每个人的参与偏好，使企业能够优化客户旅程的设计和交付。</p>
  <P>Journey AI 包含两个 ML 功能：</p>
<ul> 
     <li> <strong>预测参与度评分</strong> - 智能确定客户首选的参与度级别，以更好地针对和个性化信息，从而提高转化率和保留率。观看<a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-engagement-scoring.html">教程视频</a>。</li> 
     <li> <strong>预测发送时间优化</strong> - 预测向活动中的每个人发送电子邮件的最佳时间，从而最大化参与率并提高电子邮件活动 ROI。观看<a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-send-time-optimization.html">教程视频</a>。</li>
    </ul>
  <p>如果您想要了解如何开始使用 Journey AI，请查阅<a href="../../sending/using/predictive.md">详细文档</a>并联系您的客户主管。请注意，尽管现有 Campaign 客户可免费使用 Journey Ai，但实施成本约为 50 个小时。</p>
    </td> 
</tr> 
</tbody> 
</table>

**改进**

* **隐私管理**：**CCPA 选择退出**&#x200B;字段（通过 Campaign 界面和 API 提供）现在也通过隐私核心服务受支持。此字段允许 Adobe Campaign 用户跟踪消费者是否已选择退出出售个人信息。[了解详情](https://helpx.adobe.com/content/help/zh-Hans/campaign/kb/acs-privacy.html#ccpa)
* **工作流执行改进** （Beta 版）：在围绕工作流的全局倡议的背景下，已经制定了一些重大改进来稳定内存管理，减少延迟和优化工作流在执行期间消耗的内存。这些改进目前在 Beta 版中实施，并且仅对部分客户可用。计划于 2021 年初全面可用。
* 为了提高安全性，Campaign 现在使用&#x200B;**签名机制**&#x200B;来跟踪电子邮件中的链接。
* 上传 iOS 证书或 Android 密钥时，移动应用程序配置已通过&#x200B;**提高错误消息清晰度**&#x200B;进行了改进。
* **短信错误管理**&#x200B;已得到改进，以防止将过多用户档案添加到隔离列表。默认情况下，短信错误现在配置为软错误而不是硬错误。请参见[此页面](https://helpx.adobe.com/cn/campaign/kb/sms-connector-protocol-and-settings.html)。

**Email Designer 增强功能**

* 我们已通过&#x200B;**新的动态上下文帮助**&#x200B;改进了 Email Designer 中的用户体验，该帮助完全连接用户界面和文档，从而提供对最新帮助内容的轻松访问。
* 修复了在编辑消息的文本版本时删除消息中的换行符的问题。(CAMP-44483)
* 修复了阻止自动生成和同步 HTML 模板的纯文本版本的问题。(CAMP-44195)
* 修复了在调整图像大小时可能发生的问题。发送消息后，图像在 Microsoft Outlook 中无法正常显示。(CAMP-44656)
* 修复了在插入按钮并将其宽度设置为“auto”时发生的问题。发送消息后，未完全显示按钮的内容。(CAMP-44560)
* 修复了从附加的 HTML 文件上传内容时发生的问题。在将消息发送到 Gmail 地址后，未应用 CSS，导致呈现问题。(CAMP-44085)
* 修复了在内容模板中直接修改消息中先前使用的内容片段时，阻止更新这些内容片段的问题。(CAMP-43973)
* 修复了&#x200B;**片段**&#x200B;搜索栏的问题。搜索现有片段时，搜索栏未显示任何结果。(CAMP-44223)
* 修复了&#x200B;**内容块**&#x200B;和&#x200B;**片段**&#x200B;搜索栏的问题。使用其中一个搜索栏时，仅当单击&#x200B;**显示更多结果...**&#x200B;时，才会显示结果。(CAMP-44205)
* 修复了阻止在 Microsoft Outlook 中应用文本和图像之间的填充的问题。(CAMP-45370)
* 修复了复制片段时的问题。复制片段后，原始片段缺少 HTML 行。(CAMP-45207)
* 修复了在 Microsoft Outlook 中导致呈现问题的错误。(CAMP-44749)
* 修复了在投放模板中修改&#x200B;**结构组件**&#x200B;填充时发生的错误。CSS 标记未结转对填充所做的更改，从而导致呈现问题。(CAMP-45381)
* 修复了上传图像时的问题。图像的高度自动设置为 0，从而导致呈现问题。(CAMP-45366)

**其他变更**

* 在尝试使用&#x200B;**读取受众**&#x200B;活动导入 Experience Platform 受众时出错的情况下，添加了重试机制。（CAMP-43947 和 CAMP-43366）
* 现在，组织单位自动设置为与创建用户档案或实体的用户的组织单位匹配。不能再删除组织单位并将其留空。
* 现在，发布自定义资源时，准备后将显示确认弹出窗口。
* 自定义资源失败时显示的弹出消息已得到改进，从而提高清晰度。
* 工作流中的表达式编辑器已得到改进，以防止执行错误。提供[新函数](../../automating/using/customizing-workflow-external-parameters.md)：可在所有活动中使用这些函数，从而能够在使用外部参数调用工作流后使用事件变量。此外，现在带有函数说明的表达式编辑器中会显示工具提示。
* [已向事务事件列表中添加了新筛选器。](../../channels/using/configuring-transactional-event.md#searching-transactional-events)它们允许您根据事件配置的状态以及上次收到事件的时间来筛选配置。
* 导出包时显示的日志更加具体，并详细说明在失败情况下遇到的错误。
* 发送消息后，现在可以搜索、筛选和导出[跟踪的 URL](../../sending/using/tracking-messages.md) 的列表。
* [Launch 和 Campaign 之间的自动同步](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow)现在为 GA，默认情况下处于启用状态。
* 通过删除发送校样导出，工作流导出包的大小已得到优化。
* 添加了新消息，以在&#x200B;**文件传输**&#x200B;活动中显示已下载的文件的大小。
* 无效会话令牌的错误消息已得到改进。
* 现在，新机制可防止将来自代理的跟踪事件添加到跟踪日志和报告。
* 已添加新的警告消息，以帮助调试连接到投放活动的数据管理活动。
* 报告工作区中的标签已得到改进。
* 添加了新的验证步骤，以防止删除事务性消息中的技术对象。
* 在事务性消息的&#x200B;**执行列表**&#x200B;选项卡中添加了新的投放状态筛选器，以改进故障排除。
* 为了提高性能和优化执行时间，已根据对 350 多个客户的初步分析中所识别的使用情况统计信息表删除了未使用的索引。受影响的表包括：nmsaddressStatus、nmscampaign、nmsdelivery、nmslandingpage、nmsprogram、nmsrecipient、nmsseedmember、nmsservice、nmssubhistorcp、nmsaudience、xtkworkflow

**修补程序**

* 修复了在启用跟踪时，阻止使用推送通知或应用程序内消息传递的目标链接的问题。
* 修复了在批量投放时未遵循事务性消息中的高优先级的问题。
* 修复了阻止将品牌分配给事务电子邮件的问题。在发布步骤期间可能显示若干错误消息。(CAMP-44988)
* 修复了工作流用户界面中可能会阻止信息保存在请求数值的字段中的问题。(CAMP-44025)
* 修复了在导入模板工作流中使用&#x200B;**测试**&#x200B;活动时可能显示错误消息的问题。(CAMP-42910)
* 修复了在使用&#x200B;**读取受众**&#x200B;活动（包含枚举类型字段并已连接到&#x200B;**合并**&#x200B;或&#x200B;**扩充**&#x200B;活动）时发生的问题。(CAMP-42795)
* 修复了使用现成区段筛选报告中的数据时动态报告中的问题。(CAMP-42627)
* 修复了阻止将&#x200B;**调度程序**&#x200B;活动设置为中午 12 点的问题。(CAMP-42674)
* 修复了在 SMPP 连接不稳定时可能中断发送短信消息的问题。(CAMP-42789)
* 修复了在刷新页面后阻止显示&#x200B;**停止准备**&#x200B;按钮的问题。(CAMP-42721)
* 修复了在从 URL 导入内容时阻止显示热门点击报告百分比的问题。(CAMP-44468)
* 修复了在选择要在用户档案替换上下文中使用的用户档案时可能显示超时错误的问题。(CAMP-44746)
* 修复了在部署包含错误链接定义的自定义资源后可能阻止实例工作的问题。(CAMP-44406)
* 修复了在将投放复制并粘贴到活动模板后创建空链接实体（类型和品牌等）的问题。(CAMP-44765)
* 修复了在 Azure 上发生数据库崩溃或简单数据库重新启动的情况下，由于投放准备表处理不正确而阻止发送校样的问题。
* 修复了可能会阻止在配置有多语言内容的投放中删除包含 Experience Manager 内容的链接的问题。(CAMP-44029)
* 修复了动态报告中在尝试筛选维度时可能显示错误消息的问题。  (CAMP-43097)
* 修复了在尝试访问使用包含特定链接定义的自定义资源配置的实例上的用户档案时可能显示空白屏幕的问题。(CAMP-41009)
* 修复了在使用具有两个将目标资源链接在一起的输入活动的&#x200B;**扩充**&#x200B;活动时工作流中可能发生的问题。(CAMP-42133)
* 修复了在使用&#x200B;**文件传输**&#x200B;活动时导致导入工作流循环的问题。(CAMP-43754)
* 修复了在使用导出的日志创建用户档案时导致未考虑重复项的问题。(CAMP-45031)
* 修复了导致 Adobe Campaign 中的报告与 PDF 文件中导出的报告之间数据不一致的问题。(CAMP-43010)
* 修复了在函数中使用现有数据字段时导致直接邮件投放工作流失败的错误。(CAMP-42737)
* 修复了导入包含事务事件和消息模板的包时的问题。导入过程在 5% 处停止。(CAMP-42544)
* 修复了在修改&#x200B;**扩充**&#x200B;活动并在工作流中添加其他数据后导致错误（未捕获类型错误）的问题。(CAMP-41877)
* 修复了阻止删除工作流的错误。必须清除日志才能删除工作流。(CAMP-44144)
* 修复了使用 HTML 代码创建登陆页时的错误。强制复选框在 Campaign 中未被识别，且在已发布的登陆页中不可用。(CAMP-44181)
* 修复了在使用&#x200B;**等待**&#x200B;活动时导致工作流循环的问题。(CAMP-43981)
* 修复了在发送事务性消息时导致在同一投放中多次将多个电子邮件地址作为目标的问题。(CAMP-44202)
* 修复了将用户档案替换用于 targetData 个性化时的错误。(CAMP-44996)
* 修复了在导出包中的投放模板时导致投放预览失败的问题。(CAMP-44084)
* 修复了在使用自定义目标映射时阻止将校样发送到测试用户档案的问题。(CAMP-43701)
* 修复了在使用&#x200B;**读取受众**&#x200B;活动并以配置有除&#x200B;**用户档案**&#x200B;以外的目标维度的受众为目标时工作流中发生的错误。  (CAMP-41885)
* 修复了在 **updateEventsStatus** 技术工作流花费过多时间检索事件历史记录（当工作流已停止时）时导致错误的问题。已从工作流中删除未使用的“sumQueueTime”聚合字段来解决此问题。(CAMP-43920)
* 修复了部署自定义资源时的内存问题。(CAMP-42909)
* 修复了当集合中缺少属性时事务性消息传递中的问题。现在，所有缺失属性都使用默认值进行定义并包含在有效负载中。(CAMP-42882)
* 修复了在查询实时事件投放日志时可能影响性能的问题。(CAMP-42759)
* 修复了在对共享资产使用大写文件扩展名时发生的错误。(CAMP-44159)
* 修复了在创建外部帐户之前测试与该帐户的连接时显示错误消息的问题。现在，仅在创建外部帐户后才会显示&#x200B;**测试连接**&#x200B;按钮。
* 修复了在使用分片配置的实例上重新启动增强型 MTA 后消息保持处于挂起状态的问题。
* 修复了可能导致活动用户档案计数与已发送投放的有效数量不匹配的问题。
* 修复了在工作流中的查询编辑器中搜索资源时可能导致延迟的问题。
* 修复了在自定义资源中选择&#x200B;**指定在文本搜索中要考虑的字段**&#x200B;选项时的问题。如果字段列表留空，则自定义资源发布失败。
* 修复了在显示包含大量数据的自定义资源概述时的性能问题。
* 修复了阻止使用用户档案替换来导入投放的问题。
* 修复了在使用用户档案替换时阻止在已计划投放的情况下立即发送校样的问题。
* 修复了在上传移动应用程序的 Android 密钥时发生的问题。成功上传密钥后显示的消息显示了前一个密钥的值。
* 修复了在使用不含任何属性的集合创建事件配置后阻止从事务性消息创建测试用户档案的问题。
* 修复了在使用聚合创建新筛选器后阻止发布自定义资源的问题。
* 修复了 Gmail 图像代理所导致的 Gmail 收件人的跟踪打开率不正确的问题。
* 修复了在导入包时导致内存不足错误的问题。
* 修复了在 Experience Manager 内容包含具有“%20”字符的路径时导致 Experience Manager 取消链接操作失败的问题。
* 修复了在复制工作流活动时标签上的错误。
* 修复了在选择&#x200B;**开始发送消息**&#x200B;选项时登陆页中的事务性消息选取器的问题。
* 修复了阻止使用正确的默认值对投放状态进行初始化的事务性消息或定期投放问题。错误日志也已得到改进。
* 修复了在使用自定义字段通过用户档案链接来扩展&#x200B;**应用程序订阅** (appSubscriptionRcp) 模式时的问题。未自动创建索引，这可能会影响推送发送时间。(CAMP-41120)



## 20.3 版 - 2020 年 5 月 {#release-20-3---may-2020}

**新增功能**

<table> 
<thead> 
<tr> 
<th> <strong>泰国个人数据保护法 (PDPA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>泰国的个人数据保护法 (PDPA) 是新的隐私法，旨在将泰国的数据保护要求现代化并协调一致。此法规适用于所持有数据的数据主体居住于泰国的 Adobe Campaign 客户。</p>
<p>除了 Adobe Campaign 已提供的隐私功能（包括同意管理、数据保留设置和用户角色）之外，我们还利用此机会加入了额外的功能，以帮助您为 PDPA 做好准备：</p>
<ul>
<li>访问权和删除权：我们将充分利用 GDPR 和 CCPA 所增加的权利。<a href="https://helpx.adobe.com/content/help/zh-Hans/campaign/kb/acs-privacy.html#righttoaccess">了解详情</a> </li>
<li><p>创建隐私请求时，“隐私核心服务”中添加了 PDPA 法规类型。您应将此方法应用于所有访问和删除请求。将 Campaign API 和接口用于访问和删除请求的方法已被弃用。请参阅<a href="../../rn/using/deprecated-features.md">已弃用和已删除的功能</a>一文。</p></li>
</ul>
<p>请参阅<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">操作方法视频</a>。</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>External API 活动 (GA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p><strong>External API</strong> 活动正在从测试版过渡到 GA。此版本让 JSON 响应主体分析器变得更加灵活。您现在可以：</p>
<ul>
<li>解析最大深度为 10 级的嵌套 JSON。 </li>
<li>将选定属性解析为 JSON 中的叶节点，并将其拼合到单个表行中。</li>
<li>从 JSON 中选择并使用数组对象，而无需将对象命名为“data”或让其处于顶级。</li>
</ul>
<p><strong>注意：</strong>客户需要用其工作流中的 GA External API 活动替换所有<strong>测试版 External API 活动</strong>。从 20.3 版起，使用 External API 测试版的工作流将被废除。</p>
<p>有关更多信息，请参阅<a href="../../automating/using/external-api.md">详细文档</a>和<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">操作方法视频</a>。</p>
</td> 
</tr> 
</tbody> 
</table>

**其他功能** （从 7 月 13 日开始）

* **AI 支持的发送时间优化和用户档案评分** - 您现在可以优化客户旅程的设计和交付，以预测每个人的参与偏好。Adobe Campaign 凭借 Journey AI 提供技术支持，可以根据历史参与度分析和预测开放率、最佳发送时间以及可能的客户流失。[了解详情](../../sending/using/predictive.md)
* **巴西的新隐私法规** — 除了Campaign中已提供的隐私功能外，Adobe还可帮助您为巴西的Lei Geral de Proteçao de Datos (LGPD)做好准备。 在创建隐私请求时，已向 Adobe Privacy Core Service 添加 LGPD 法规。[了解详情](https://helpx.adobe.com/cn/campaign/kb/campaign-privacy-overview.html)

**改进**

* [使用已定向用户档案的测试消息](../../sending/using/testing-messages-using-target.md)，其&#x200B;**前缀**&#x200B;字段中可使用的字符数从 32 个增加到了 500 个。
* 可在实例上发布的实时事件最大数目从 350 增加到了 2000。(CAMP-41608)
* Adobe Launch 与 Campaign Standard 之间的同步，已通过使用 syncWithLaunch 技术工作流进行了改进。此工作流支持将所有 Adobe Launch 移动属性自动导入到 Adobe Campaign Standard 中。有关详细信息，请参见[此页面](../../administration/using/technical-workflows.md)。

  您需要向 Adobe 客户关怀（直接或通过您的 Adobe 联系人）提交票证，以便在 Campaign 实例中启用 syncWithLaunch 技术工作流。(CAMP-40082)

**Email Designer 增强功能**

* 与严谨的 W3C 相比，现在 Email Designer 可以处理更灵活的 HTML 格式。(CAMP-42529)
* 修复了[可单击图像](../../designing/using/links.md#inserting-a-link)的问题，以防止链接显示在内容块中的图像旁边。(CAMP-41586)
* 修复了相关问题，以防止在模板中为[跟踪的 URL](../../designing/using/links.md#about-tracked-urls) 添加类别时，重定向到登陆页面。(CAMP-41537)
* 修复了 Outlook 中按钮文字填充的问题。
* 修复了导致 HTML 标记以纯文本显示的问题。
* 内容块搜索现在可显示服务器搜索结果和预加载结果。(CAMP-41870)

**其他变更**

* 自定义资源发布界面进行了改进，以进一步突出错误消息。
* 从界面中删除了未使用的投放映射。
* 从界面中删除了不必要的管理员角色。
* 现在，登陆页面中的复选框为必选项。
* 取消了下载动态报告 CSV 文件的 200 行限制。现在，您可以获得包含所有内容的完整报告。(CAMP-40810)
* 为多语言电子邮件的即装即用语言列表添加了 ES-US 语言。(CAMP-42279)
* 现在，使用“传输文件”活动下载的文件将在 X 天后被删除，其中 X 由“工作流”属性中&#x200B;**“执行”**&#x200B;菜单下的&#x200B;**“历史天数”**&#x200B;字段决定。[了解更多](../../automating/using/managing-execution-options.md)

**Experience Platform 集成**

* 从&#x200B;**读取受众**&#x200B;活动激活Adobe Experience Platform受众的过程进行了改进，以提供更好的性能和稳定性。 此外，还可为激活作业提供更清晰、更详细的工作流日志，以便在读取 Adobe Experience Platform 受众时更轻松地进行监控和疑难解答。

**修补程序**

* 修复了导致在自定义资源的发布作业期间创建资源备份的错误。
* 修复了使用自定义资源扩展用户档案资源时可能会阻止显示用户档案营销历史的问题。(CAMP-41009)
* 修复了打开编辑器时即装即用登陆页面模板以法语显示其内容的问题。(CAMP-41639)
* 修复了推送通知中的动态内容可能阻止显示表情符号的问题。(CAMP-40715)
* 修复了&#x200B;**重复数据删除**&#x200B;活动中可能导致分配给其中一个叫客补充过渡的段码不正确的问题。(CAMP-41400)
* 修复了阻止删除调度报告的错误。(CAMP-41302)
* 修复了导致投放仪表板与&#x200B;**投放摘要**&#x200B;报表不一致的问题。(CAMP-41145)
* 修复了导致下载的报告中显示字符重叠的问题。
* 修复了阻止预览投放进行校样替换的问题。
* 修复了删除应用程序内本地通知的自定义字段时出错的问题。
* 修复了 charIndex 函数无法用于工作流中&#x200B;**“结束”**&#x200B;或&#x200B;**“文件传输”**&#x200B;活动的问题。
* 修复了使用&#x200B;**扩充**&#x200B;活动添加两个包含定向资源的输入活动（两者之间具有链接）时，可能发生的工作流问题。(CAMP-42133)
* 修复了在使用未知函数时可能阻止工作流运行的问题。(CAMP-41873)
* 修复了在使用具有补充叫客过渡的多个&#x200B;**“保存受众”**&#x200B;活动创建受众时，可能发生的工作流问题。(CAMP-39992)
* 修复了在事务型电子邮件中使用个性化功能导致数据不一致的问题。(CAMP-41842)
* 修复了删除推送通知投放中自定义字段时发生的问题。(CAMP-37586)
* 修复了会阻止用户更改报告的错误。(CAMP-42505)


![](assets/do-not-localize/cp-icon.png) **新控制面板 5 月发布**， 为 CNAME 子域提供证书续订功能。[了解详情](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=zh-Hans)。

## 20.2 版 - 2020 年 4 月 {#release-20-2---april-2020}

**新增功能**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Azure Blob 集成</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Azure Blob Storage 连接器可用于通过<strong>传输文件</strong>工作流活动将数据导入或导出 Adobe Campaign。 </p>
    <p>有关详细信息，请参阅<a href="../../administration/using/external-accounts.md#microsoft-azure-external-account">详细文档</a>。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>使用定向的用户档案测试电子邮件</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>除了测试用户档案之外，您现在还可以在真正的定向用户档案上测试电子邮件。利用此功能，可了解用户档案将收到之以下消息的精确表示形式：自定义字段、动态和个性化信息，包含来自工作流的附加数据等。 </p>
    <p>有关更多信息，请参阅<a href="../../sending/using/testing-messages-using-target.md">详细文档</a>和<a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html">教程视频</a>。 </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>新功能将于 4 月在 Campaign 控制面板中发布，包括 Google TXT 记录管理、数据库空间监控和电子邮件警报。有关这些功能的更多信息，请参阅[控制面板发行说明](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=zh-Hans)。

**改进**

* 增强了事务型消息传递的用户体验，提升了界面的一致性。[了解更多](../../channels/using/getting-started-with-transactional-msg.md)
* 现在，可通过 Campaign Standard 使用来自工作流的附加数据向测试用户档案发送校样。
* 更新了 External API 活动的防护。[了解更多](../../automating/using/external-api.md)

**Email Designer 增强功能**

* 修复了在个性化图像上多次点击时影响逃逸的问题。
* 修复了复制动态文本组件时可能导致复制错误行的问题。(CAMP-41249)
* 修复了在表格级而不是 div 层级定义文字填充时 Outlook 中的文字填充问题。
* 修复了在切换到 HTML 模式时导致图像宽度被修改的问题。(CAMP-41116)
* 修复了为图标提供替代文本时无法访问社交媒体组件的问题。(CAMP-41345)
* 修复了在 Email Designer 中使用复制粘贴导致显示 `<br>` 标记的问题。
* 修复了从 HTML 内容切换为纯文本后，导致 HTML 标记显示在电子邮件中的问题。(CAMP-41138)
* 修复了仅定义一个边框时无法呈现按钮的问题。
* 修复了 Microsoft Outlook 中 HTML 缩进导致电子邮件页脚向左移动的问题。(CAMP-40987)
* 修复了切换为纯文本模式时，导致以纯文本内容复制 HTML 中定义的定向集合属性的个性化字段的问题。(CAMP-40365)
* 修复了阻止在选定文本段中插入链接的问题。(CAMP-41406)
* 修复了在查询编辑器中选择时区时导致日期更改的问题。(CAMP-38277)

**其他变更**

* 现在，**与 Adobe Analytics 协调 KPI** 这个现成工作流运行到当前日期，而不是只运行一天。
* MCPNS 不支持将 APNS 和 APNS-SANDBOX 作为平台添加到应用程序中。现在，在 Adobe Campaign Standard 中成功添加证书后，无法再重新更改设置，因为只能向 MCPNS 应用程序添加一个 APNS 平台（作品或沙盒）。

**Experience Platform 集成**

>[!NOTE]
>
>Campaign Standard 中的 Adobe Experience Platform 功能目前处于测试阶段，可能会频繁更新，恕不另行通知。请参阅详细文档：Experience Platform数据连接器、受众目标

* 现在，Campaign 在工作流日志中，每 10 分钟显示一次当前正在运行的作业已处理的记录数。
* 修复了导入已从数据库删除的 Adobe Experience Platform 时可能发生的问题。
* 修复了工作流日志中显示导入记录总数结果不正确的问题。

**修补程序**

* 修复了在 **Alias** 字段中添加空格（这会创建新的行项）时，可能出现的&#x200B;**扩充**&#x200B;工作流活动问题。(CAMP-39229)
* 修复了在发送校样消息时，可能会定向所有测试用户档案的问题。
* 修复了取消发布和删除事件配置后发生的问题。[了解更多](../../channels/using/publishing-transactional-event.md#deleting-an-event)
* 修复了在对工作流进行更改后，**保存**&#x200B;按钮消失的问题。
* 修复了在 Campaign 中进行隐私请求处理后手动删除改请求时的问题，该问题会阻止删除与请求关联的数据，即使在清除后也无法删除。
* 修复了在预览或发送包含 Adobe Experience Manager 特殊字符的消息时可能发生的问题。
* 修复了在执行具有多个集客过渡的活动时，工作流中可能发生的问题。
* 修复了阻止标准用户在工作流查询或投放中将“订阅应用程序”用作定向维度的问题。(CAMP-37618)

## 20.1.4版 — 2020年2月 {#release-20-1-4---february-2020}

* 修复了在现有工作流上打开&#x200B;**读取受众**&#x200B;活动时发生的问题。(CAMP-41002)

## 20.1.3版 — 2020年2月 {#release-20-1-3---february-2020}

* 修复了 20.1 版引入的可能导致客户使用漏洞的退化问题 (CAMP-39273)。CAMP-39273 之前已被修复。

## 20.1.2版 — 2020年2月 {#release-20-1-2---february-2020}

**Email Designer 增强功能**

* 修复了在修补过期片段并保存内容时向其中添加 HTML 标记元素的问题。(CAMP-40685)
* 修复了在使用动态内容时添加空格的问题。(CAMP-40605)
* 修复了配置事务性电子邮件模板时的问题。(CAMP-40604)

## 20.1 版 - 2020 年 2 月 {#release-20-1---february-2020}

**新增功能**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Adobe Experience Platform Data Connector (beta)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Experience Platform Data Connector 现在集成到了 Adobe Standard 中。您可以将 XTK 数据（Campaign 摄取的数据）映射到 Adobe Experience Platform 数据模型 (XDM)，从而使 Campaign 数据在 Adobe Experience Platform 上可用。 </p>
    <p>请注意，此功能仅适用于Azure上托管的客户。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Audience Destinations (beta) </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>利用 Audience Destinations，可将来自 Adobe Experience Platform 的区段共享到 Adobe Campaign。</p>
    <p>请注意，此功能仅适用于Azure上托管的客户。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

**改进**

* 增强 MTA 的全局可用性： 消息（包括事务型消息）现在由 Adobe Campaign Enhanced MTA 发送，该集成升级了发送基础结构，以改进投放能力、吞吐量和退件处理。[了解更多](https://helpx.adobe.com/cn/campaign/kb/campaign-enhanced-mta.html)

* 增强了时区管理。您现在可以定义用于整个工作流的[特定时区](../../automating/using/building-a-workflow.md)。选定的时区将应用于工作流的所有活动。现在，界面中会显示为操作员或服务器配置的时区信息（在日志中以及选择时区后）。(CAMP-37672)

* 现在，可利用 Campaign Standard API 在使用大型表格时，通过向调用 URL 添加 `_forcePagination=true` 参数来执行分页。[了解更多](../../api/using/pagination.md)

* 现在，所有定向维度的投放日志和跟踪日志资源中，都可使用投放日志 ID（每个日志的唯一标识符）。例如，这允许在导出时识别发送或跟踪日志。[了解更多](../../automating/using/exporting-logs.md)

**Email Designer 增强功能**

* 添加了创建受众时的缺失必填文本说明。
* 修复了在旧版电子邮件编辑器向导中单击 **Change content** 按钮时发生的问题。
* 修复了阻止标头与服务摘要报告中的内容保持一致的问题。(CAMP-38103)
* 修复了无法在不影响主题行其余部分的情况下删除动态内容变体的问题。(CAMP-40096)
* 修复了在主题行上使用 B 变体时的 A/B 测试问题。(CAMP-40327)
* 修复了使用上传 HTML 导入功能时无法拖放文件的问题。(CAMP-39326)
* 修复了阻止您从文本编辑器复制和粘贴文本的问题。(CAMP-39028)
* 修复了阻止显示建议文字的问题。(CAMP-38970)
* 修复了阻止用户保存片段的问题。(ATU-2447)
* 修复了阻止动态结构复制的问题。(CAMP-38367)
* 修复了复制后动态内容无法保留条件的问题。(CAMP-39051)

**其他变更**

* “准备失败的投放”过滤器现在会考虑投放的创建日期，而不是上次修改日期。
* 管理员安全组的组织单元不能再更改。
* 现在创建用户档案时，必须填写 Organizational unit 字段。
* 现在，仅当删除了事件和与其链接的事务型模板时，才能删除 Experience Cloud 触发器。
* [!DNL Adobe Creative SDK] 已停用。现在，Campaign Standard 已将其弃用。请参阅[已弃用和已删除的功能](../../rn/using/deprecated-features.md)页面。


**修补程序**

* 修复了执行删除隐私请求时阻止删除排除日志中用户数据的问题。(CAMP-39003)
* 修复了在容器元素中调整文本大小时导致可访问性故障的问题。
* 修复了阻止用户取消将鼠标悬停在营销活动上弹出日历窗口的问题。
* 修复了在 **[!UICONTROL External API]** 活动中即使未修改任何数据也会显示 **[!UICONTROL Confirm]** 按钮的问题。
* 修复了对带有不同定向维度的查询使用 **[!UICONTROL Union]** 活动的问题。过渡数据只显示来自主集定向维度的记录。(CAMP-36831)
* 修复了在特定环境中使用 **[!UICONTROL Reconciliation]** 活动（例如，两个集客活动，其中一个是排除活动）时可能导致错误的问题。(CAMP-37490)
* 修复了在选择和更新测试用户档案时可能发生的性能问题。(CAMP-37976)
* 修复了通过登陆页面订阅或退订时可能显示错误页面的问题。(CAMP-37771)
* 修复了以 zip 格式上传内容时发生的问题，在 HTML 中引用的 PNG 文件的扩展名会变成大写字母。(CAMP-37913)
* 修复了在向投放添加测试用户档案时阻止发送应用程序内消息的问题。
* 修复了 External API 工作流活动链接到扩充活动时失败的错误。
* 修复了可能导致短信消息状态显示不正确的问题。
* 修复了自定义资源导致重复条目在 API 端点下显示不同的问题。
* 修复了发布后登陆页面无法使用的问题。(CAMP-38695)
* 修复了显示来自两个不同资源的交集过渡的数据时发生的错误。(CAMP-38974)
* 修复了导致投放模板中枚举值设置不正确的问题。(CAMP-38388)
* 修复了电子邮件批量投放错误，该错误会将投放状态显示为“待处理”，将“已发送”状态显示为“已完成”。(CAMP-35355)
* 修复了在动态报告中错误地显示发件人域名的错误。(CAMP-33123)
* 修复了导致动态报告中退订计数不一致的问题。(CAMP-39949)
* 修复了发送应用程序内消息时，发送日志屏幕中不显示地址的问题。
* 修复了短信发送日志无法更新正确退件数量的问题。(CAMP-38395)
* 修复了允许应用程序订阅后调用以更新推送通知令牌的漏洞。(CAMP-39273)
