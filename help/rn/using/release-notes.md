---
solution: Campaign Standard
product: campaign
title: 最新版本
description: 此页面详细描述最新 Campaign Standard 版本的内容
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
translation-type: ht
source-git-commit: a51943e4da04f5d19aaecdfcf956f5c4f3d804c8
workflow-type: ht
source-wordcount: '2412'
ht-degree: 100%

---


# 最新版本{#latest-release}

[发行计划](../../rn/using/release-planning.md) | [控制面板版本](https://docs.adobe.com/content/help/zh-Hans/control-panel/using/release-notes.html) | [文档更新](../../rn/using/documentation-updates.md) | [之前的发行说明](../../rn/using/release-notes-2020.md) | [已弃用的功能](../../rn/using/deprecated-features.md)

![](assets/do-not-localize/cp-icon.png) **新控制面板 10 月版**，其中使用 CNAME 进行域配置并新增数据库监视功能。[了解详情](https://docs.adobe.com/content/help/zh-Hans/control-panel/using/release-notes.html)。

## 20.4 版 - 2020 年 10 月{#release-20-4---october-2020}

**新增功能**

<table> 
<thead> 
<tr> 
<th> <strong>控制组</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>您现在可以使用<strong>控制组</strong>通过排除活动的一部分受众来衡量其影响。然后，便能够将收到消息的目标群体的行为与非目标联系人的行为进行比较。根据发送日志，还可以在将来活动中以控制组为目标。
</p>
<p>有关更多信息，请参阅<a href="../../sending/using/control-group.md">详细文档</a>和<a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/control-groups.html?lang=zh-Hans#communication-channels">教程视频</a>。
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
  <p>Journey AI 使用高级机器学习 (ML)，通过预测每个人的参与偏好，使公司能够优化客户旅程的设计和交付。</p>
  <P>Journey AI 包含两个 ML 功能：</p>
<ul> 
     <li> <strong>预测参与度评分</strong> - 智能确定客户首选的参与度级别，以更好地针对和个性化信息，从而提高转化率和保留率。观看<a href="https://docs.adobe.com/content/help/zh-Hans/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-engagement-scoring.html">教程视频</a>。</li> 
     <li> <strong>预测发送时间优化</strong> - 预测向活动中的每个人发送电子邮件的最佳时间，从而最大化参与率并提高电子邮件活动 ROI。观看<a href="https://docs.adobe.com/content/help/zh-Hans/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-send-time-optimization.html">教程视频</a>。</li>
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

