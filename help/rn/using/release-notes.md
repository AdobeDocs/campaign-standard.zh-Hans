---
title: 最新版本
description: 此页面详细信息最新Campaign Standard版本的内容
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: vignes
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 97760e8b5fe0eb4905dcae69e8bbbefa837a461f
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 最新版本{#latest-release}

[发行计划](../../rn/using/release-planning.md) | [控制面板版本](https://docs.adobe.com/content/help/zh-Hans/control-panel/using/release-notes.html) | [文档更新](../../rn/using/documentation-updates.md) | [之前的发行说明](../../rn/using/release-notes-2020.md) | [已弃用的功能](../../rn/using/deprecated-features.md)

## 20.4 版 - 2020 年 10 月{#release-20-4---october-2020}

**新增内容？**

<table> 
<thead> 
<tr> 
<th> <strong>对照组</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>您现在可以使 <strong>用对照组</strong> ，通过排除活动的一部分受众来衡量其影响。 然后，您将能够将收到消息的目标群体的行为与未定位的联系人的行为进行比较。 根据发送日志，您还可以在将来目标对照组。
</p>
<p>For more information refer to the <a href="../../sending/using/control-group.md">detailed documentation</a> and <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/control-groups.html">how-to video</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>外部API - OAuth支持</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Adobe Campaign现在支持OAuth以在外部API工作 <strong>流活动中进</strong> 行身份验证。 此新功能使此活动能够与需要OAuth支持的系统进行通信。
</p>
<p>For more information refer to the <a href="../../automating/using/external-api.md">detailed documentation</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>旅程AI集成</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>我们很兴奋地宣布为所有Adobe Campaign Standard客户推出Journey AI。</p>
  <p>Journey AI使用高级机器学习(ML)，通过预测每个人的参与偏好，使公司能够优化客户旅程的设计和投放。</p>
  <P>Journey AI包含两个ML功能：</p>
<ul> 
     <li> <strong>预测性参与评分</strong> -智能确定客户首选的参与程度，以更好地目标和个性化信息，从而提高转化率和保留率。 观看 <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-engagement-scoring.html">操作方法视频</a>。</li> 
     <li> <strong>预测发送时间优化</strong> -预测向活动中的每位用户发送电子邮件的最佳时间，从而最大化参与率并提高电子邮件活动ROI。 观看 <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-send-time-optimization.html">操作方法视频</a>。</li>
    </ul>
  <p>如果您想要了解如何开始使用Journey AI，请查阅详细 <a href="../../sending/using/predictive.md">文档</a> ，并联系您的客户经理。 请注意，尽管现有活动客户可免费使用旅程人工智能，但实施成本约为50小时。</p>
    </td> 
</tr> 
</tbody> 
</table>

**改进**

* **隐私管理**:CCPA **Opt-Out** （CCPA选择退出）字段可通过活动界面和API获得，现在也通过隐私核心服务受支持。 此字段允许Adobe Campaign用户跟踪消费者是否已选择出售个人信息。 [了解详情](https://helpx.adobe.com/content/help/zh-Hans/campaign/kb/acs-privacy.html#ccpa)
* **工作流执行改进** （测试版）:在围绕工作流的全局倡议的背景下，已经制定了一些重大改进，以稳定内存管理、减少延迟和优化工作流在执行过程中消耗的内存。 这些改进目前采用测试版，并且仅适用于一组客户。 计划于2021年初全面上市。
* 为了提高安全性，活动现在使用签 **名机制** 来跟踪电子邮件中的链接。
* 上传iOS证书或Android密钥时，移动 **应用程序配置已得到改** 进，并显示更清晰的错误消息。
* 新 **投放映射** (mapRtEventAppSubRcp)现在可用于事务推送消息定位用户档案。 这些投放的投放、排除和跟踪日志现在将在broadLogAppSubRcp、excludeLogAppSubRcp和trackingLogAppSubRcp表中可用。 这解决了在使用投放维发送事务推送消息时导致用户档案分析失败 **的问** 题。
* **SMS错误管理** 已得到改进，以防止将过多用户档案添加到隔离列表。 默认情况下，SMS错误现在配置为软错误而不是硬错误。 请参见[此页面](https://helpx.adobe.com/cn/campaign/kb/sms-connector-protocol-and-settings.html)。

**Email Designer 增强功能**

* 我们通过全新的动态上下文帮助改进了电子邮件 **设计器中的用户体验** ，该帮助完全连接了用户界面和文档，提供了对最新帮助内容的轻松访问。
* 修复了在编辑邮件文本版本时删除邮件中换行的问题。 (CAMP-44483)
* 修复了阻止自动生成和同步HTML模板的纯文本版本的问题。 (CAMP-44195)
* 修复了在调整图像大小时可能发生的问题。 发送消息后，图像在Microsoft Outlook中无法正常显示。 (CAMP-44656)
* 修复了插入按钮并将其宽度设置为“auto”时出现的问题。 发送消息后，按钮的内容不会完全显示。 (CAMP-44560)
* 修复了从附加的HTML文件上传内容时发生的问题。 在将消息发送到Gmail地址后，CSS未被应用，导致渲染问题。 (CAMP-44085)
* 修复了在内容模板中直接修改之前在消息中使用的内容片段时，无法更新这些片段的问题。 (CAMP-43973)
* 修复了“片段”搜 **索栏** 的问题。 搜索现有片段时，搜索栏不显示任何结果。 (CAMP-44223)
* 修复了内容块 **和片段搜索****栏的** 问题。 使用搜索栏时，仅当您单击“显示更多结果……” **时，才会显示结果。**. (CAMP-44205)
* 修复了在Microsoft Outlook中无法应用文本和图像之间的填充的问题。 (CAMP-45370)
* 修复了复制片段时的问题。 复制片段后，原始片段缺少HTML行。 (CAMP-45207)
* 修复了在Microsoft Outlook中导致渲染问题的错误。 (CAMP-44749)
* 修复了修改投放模板中结构 **组件填充** 时发生的错误。 CSS标签未结转对填充所做的更改，这会导致渲染问题。 (CAMP-45381)
* 修复了上传图像时的问题。 图像的高度自动设置为0，导致渲染问题。 (CAMP-45366)

**其他更改**

* 在尝试使用读取Experience Platform受众导入受众活动时，如果出错，已添加重 **试机制** 。 (CAMP-43947,CAMP-43366)
* 现在，组织单位会自动设置为与创建用户档案或实体的用户的组织单位匹配。 不能再删除组织单位并将其留空。
* 现在，发布自定义资源时，准备后将显示确认弹出窗口。
* 自定义资源失败时显示的弹出消息已得到改进，以便更清晰。
* 表达式中的工作流编辑器已得到改进，以防止执行错误。 [新增功能](../../automating/using/customizing-workflow-external-parameters.md) :这些变量可用于所有活动，允许您在调用具有外部参数的工作流后使用事件变量。 此外，现在表达式编辑器中会显示工具提示以及函数说明。
* [新过滤器](../../administration/using/configuring-transactional-messaging.md#searching-transactional-events) 已添加到交易事件的列表中。 它们允许您根据事件配置的状态以及上次收到事件的时间来筛选配置。
* 导出包时显示的日志更加具体，并详细说明在出现故障时遇到的错误。
* 发送消息后，您现在可以搜索、过滤和导出跟踪的URL [的列表](../../sending/using/tracking-messages.md)。
* 启 [动项和活动之间的自动同步](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow) 现在为GA，默认情况下处于启用状态。
* 通过删除发送验证导出，工作流导出包的大小已得到优化。
* 添加了一条新消息以在文件传输活动中显示已下载文 **件的大小** 。
* 无效会话令牌的错误消息已得到改进。
* 现在，新机制可防止将跟踪事件代理添加到跟踪日志和报告。
* 已添加新的警告消息，以帮助调试连接到数据管理活动的投放活动。
* 报告工作区中的标签已得到改进。
* 新增了一个验证步骤，以防止删除事务性消息中的技术对象。
* 在事务性消息的“执行投放”选项卡中添加了 **列表状态** 的新筛选器，以改进故障排除。
* 为了提高性能并优化执行时间，已根据350多个客户在初步分析中识别的表的使用情况统计信息删除了未使用的索引。 受影响的表包括：nmsaddressStatus、nmscampaign、nmsdelivery、nmslandingpage、nmsprogram、nmsrecipient、nmsseemember、nmsservice、nmssubhistorcp、nmsaudience、xtkworkflow

**修补程序**

* 修复了在启用跟踪时，阻止您使用推送通知或应用程序内消息传递的目标链接的问题。
* 修复了在大量投放时，事务性消息中的高优先级不受尊重的问题。
* 修复了一个问题，该问题可能会阻止您将品牌分配给交易电子邮件。 发布步骤期间可能显示多条错误消息。 (CAMP-44988)
* 修复了工作流用户界面中的一个问题，该问题可能会阻止信息保存在请求数值的字段中。 (CAMP-44025)
* 修复了在导入模板工作流中使用测试活动时 **可能显** 示错误消息的问题。 (CAMP-42910)
* 修复了在使用包含受众类型字 **段的读取明细列表** 活动时发生并连接到 **合并** 或 **扩充活动的问** 题。 (CAMP-42795)
* 修复了动态报表中使用现成区段筛选报表数据时的问题。 (CAMP-42627)
* 修复了阻止您将调度程序 **活动设** 置为上午12点的问题。 (CAMP-42674)
* 修复了在SMPP连接不稳定时可能中断SMS消息发送的问题。 (CAMP-42789)
* 修复了刷新页面后无 **法显示** “停止准备”按钮的问题。 (CAMP-42721)
* 修复了从URL导入内容时，热点单击报告百分比无法显示的问题。 (CAMP-44468)
* 修复了在选择要在用户档案替换上下文中使用的用户档案时可能显示超时错误的问题。 (CAMP-44746)
* 修复了在部署包含错误链接定义的自定义资源后，可能会阻止实例工作的问题。 (CAMP-44406)
* 修复了创建空链接实体（类型、品牌等）的问题 将投放复制并粘贴到活动模板后。 (CAMP-44765)
* 修复了在Azure上发生验证库崩溃或简单的数据库重新启动时，由于投放准备表处理不正确，导致数据无法发送的问题。
* 修复了一个问题，该问题可能会阻止您在配置了多语言内容的Experience Manager中删除包含投放内容的链接。 (CAMP-44029)
* 修复了动态报表中在尝试筛选维时可能显示错误消息的问题。  (CAMP-43097)
* 修复了在尝试访问使用包含特定链接定义的自定义资源配置的实例上的用户档案时，可能显示空白屏幕的问题。 (CAMP-41009)
* 修复了在使用两个输入工作流的扩充(两个活动资源 **链接在一起** )时，活动中可能发生的问题。 (CAMP-42133)
* 修复了使用文件传输工作流时导致导入活动 **循环的问** 题。 (CAMP-43754)
* 修复了在创建带导出日志的重复时，导致用户档案未被考虑的问题。 (CAMP-45031)
* 修复了导致Adobe Campaign中的报表与PDF文件中导出的报表之间数据不一致的问题。 (CAMP-43010)
* 修复了在函数中使用现有数据字段时导致直接邮件投放工作流失败的错误。 (CAMP-42737)
* 修复了导入包(包括事务事件和消息模板)时的问题。 导入过程停止在5%。 (CAMP-42544)
* 修复了在修改扩充活动并在工作流中添加其他数据后导致错误( **未捕获** 的类型错误)的问题。 (CAMP-41877)
* 修复了阻止删除工作流的错误。 必须清除日志才能删除工作流。 (CAMP-44144)
* 修复了使用HTML代码创建登陆页时出错的问题。 强制复选框未在活动中识别，且在已发布的登陆页中不可用。 (CAMP-44181)
* 修复了在使用等待工作流时导致活动循环 **的问** 题。 (CAMP-43981)
* 修复了在同一事务性消息中发送导致多个电子邮件地址被多次定位的投放时的问题。 (CAMP-44202)
* 修复了在targetData个性化中使用用户档案替换时出错的问题。 (CAMP-44996)
* 修复了在导出包中的投放时导致投放模板预览失败的问题。 (CAMP-44084)
* 修复了在使用自定义验证时无法将用户档案发送到测试目标映射的问题。 (CAMP-43701)
* 修复了使用读取工作流受众并定位 **使用非活动** 定位维度配置的受众时在用户档案中发生 **的错误**。  (CAMP-41885)
* 修复了在updateEventsStatus技术工作流 **检索事件历史** （工作流停止时）所花费的时间过长时导致错误的问题。 未使用的“sumQueueTime”聚合字段已从工作流中删除以解决此问题。 (CAMP-43920)
* 修复了部署自定义资源时的内存问题。 (CAMP-42909)
* 修复了事务消息传递中集合中缺少属性时的问题。 现在，所有缺失的属性都使用默认值进行定义并包含在有效负荷中。 (CAMP-42882)
* 修复了在查询实时事件投放日志时可能影响性能的问题。 (CAMP-42759)
* 修复了在共享资产中使用大写文件扩展名时发生的错误。 (CAMP-44159)
* 修复了在创建外部帐户之前测试与该连接时显示错误消息的问题。 现 **在，仅** 在创建外部帐户后才显示“测试连接”按钮。
* 修复了在配置了共享的实例上重新启动增强的MTA后，消息仍处于挂起状态的问题。
* 修复了可能导致活动用户档案数不匹配已发送投放的有效数量的问题。
* 修复了在工作流的查询编辑器中搜索资源时可能导致延迟的问题。
* 修复了在自定义资 **源的文本搜索选项中选择要考虑的字段** 时出现的问题。 如果字段列表为空，则自定义资源发布失败。
* 修复了在显示包含大量数据的自定义资源概述时的性能问题。
* 修复了阻止您使用投放替换导入用户档案的问题。
* 修复了使用用户档案替换时的问题，该问题会阻止在计划验证时立即发送投放。
* 修复了上传移动应用程序的Android键时发生的问题。 成功上传密钥后显示的消息显示前一个密钥的值。
* 修复了在创建不包含属性的集合的用户档案配置后，无法从事务性消息创建测试事件的问题。
* 修复了在使用聚合创建新过滤器后无法发布自定义资源的问题。
* 修复了由Gmail图像代理导致的Gmail收件人跟踪打开速率不正确的问题。
* 修复了导入包时导致内存不足错误的问题。
* 修复了当Experience Manager内容包含带有“%20”字符的路径时导致Experience Manager取消链接操作失败的问题。
* 修复了复制工作流活动时标签上的错误。
* 修复了选择事务性消息发送消息选项时登陆页中 **的开始选取** 器的问题。
* 修复了事务性消息或重复投放的问题，该问题导致投放状态无法使用右默认值进行初始化。 错误日志也得到改进。
* 修复了使用自定义字 **段将订阅扩展到具有用户档案** 链接的应用程序(appSubscriptionRcp)模式时的问题。 未自动创建索引，这可能会影响推送发送时间。 (CAMP-41120)

