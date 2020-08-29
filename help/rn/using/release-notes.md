---
title: 最新版本
description: 本页列出了所有最新版本的 Adobe Campaign Standard。
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f45985c030c3d5059bfef444287c10b842298f49
workflow-type: tm+mt
source-wordcount: '1160'
ht-degree: 90%

---


# 最新版本{#latest-release}

[发行计划](../../rn/using/release-planning.md) | [控制面板版本](https://docs.adobe.com/content/help/zh-Hans/control-panel/using/release-notes.html) | [文档更新](../../rn/using/documentation-updates.md) | [之前的发行说明](../../rn/using/release-notes-2020.md) | [已弃用的功能](../../rn/using/deprecated-features.md)

![](assets/do-not-localize/cp-icon.png) **新的控制面板 6 月版本**，包含活动用户档案监测、子域投放能力审核和 GPG 密钥管理。[了解详情](https://docs.adobe.com/content/help/zh-Hans/control-panel/using/release-notes.html)。

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
<li>访问权和删除权：我们将充分利用 GDPR 和 CCPA 所增加的权利。<a href="https://helpx.adobe.com/content/help/zh-Hans/campaign/kb/acs-privacy.html#righttoaccess">了解更多</a> </li>
<li><p>创建隐私请求时，“隐私核心服务”中添加了 PDPA 法规类型。您应将此方法应用于所有访问和删除请求。将 Campaign API 和接口用于访问和删除请求的方法已被弃用。请参阅<a href="../../rn/using/deprecated-features.md">已弃用和已删除的功能</a>一文。</p></li>
</ul>
<p>请参阅<a href="https://docs.adobe.com/content/help/zh-Hans/campaign-standard-learn/tutorials/privacy/privacy-overview.translate.html">操作方法视频</a>。</p>
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
<p>有关更多信息，请参阅<a href="../../automating/using/external-api.md">详细文档</a>和<a href="https://docs.adobe.com/content/help/zh-Hans/campaign-standard-learn/tutorials/managing-processes-and-data/data-management-activities/external-api-activity.translate.html">操作方法视频</a>。</p>
</td> 
</tr> 
</tbody> 
</table>

**其他功能** （从7月13日开始）

* **AI驱动的发送时间优化和用户档案评分** -您现在可以优化客户旅程的设计和投放，以预测每个人的参与偏好。 Adobe Campaign可以借助Journey AI分析和预测开放率、最佳发送时间以及基于历史互动指标的可能客户流失。 [了解详情](../../sending/using/predictive.md)
* **巴西新的隐私法规** -除了活动已具备的隐私功能外，Adobe还有助于您为巴西Lei Geral de Proteçao de Datos(LGPD)做好准备。 创建隐私请求时，LGPD规定已添加到Adobe隐私核心服务。 [了解详情](https://helpx.adobe.com/cn/campaign/kb/campaign-privacy-overview.html)

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

* 从&#x200B;**读取受众**&#x200B;活动激活 Adobe [Experience Platform 受众](../../automating/using/aep-targeting-audiences.md)的过程进行了改进，以提供更好的性能和稳定性。此外，还可为激活作业提供更清晰、更详细的工作流日志，以便在读取 Adobe Experience Platform 受众时更轻松地进行监控和疑难解答。

**修补程序**

* 修复了导致在自定义资源的发布作业期间创建资源备份的错误。
* 修复了使用自定义资源扩展用户档案资源时可能会阻止显示用户档案营销历史的问题。(CAMP-41009)
* 修复了打开编辑器时即装即用登陆页面模板以法语显示其内容的问题。(CAMP-41639)
* 修复了推送通知中的动态内容可能阻止显示表情符号的问题。(CAMP-40715)
* 修复了&#x200B;**重复数据删除**&#x200B;活动中可能导致分配给其中一个叫客补码过渡的段码不正确的问题。(CAMP-41400)
* 修复了阻止删除调度报告的错误。(CAMP-41302)
* 修复了导致投放仪表板与&#x200B;**投放摘要**&#x200B;报表不一致的问题。(CAMP-41145)
* 修复了导致下载的报告中显示字符重叠的问题。
* 修复了阻止预览投放进行校样替换的问题。
* 修复了删除应用程序内本地通知的自定义字段时出错的问题。
* 修复了 charIndex 函数无法用于工作流中&#x200B;**“结束”**&#x200B;或&#x200B;**“文件传输”**&#x200B;活动的问题。
* 修复了使用&#x200B;**扩充**&#x200B;活动添加两个包含定向资源的输入活动（两者之间具有链接）时，可能发生的工作流问题。(CAMP-42133)
* 修复了在使用未知函数时可能阻止工作流运行的问题。(CAMP-41873)
* 修复了在使用具有补码叫客过渡的多个&#x200B;**“保存受众”**&#x200B;活动创建受众时，可能发生的工作流问题。(CAMP-39992)
* 修复了在事务型电子邮件中使用个性化功能导致数据不一致的问题。(CAMP-41842)
* 修复了删除推送通知投放中自定义字段时发生的问题。(CAMP-37586)
* 修复了会阻止用户更改报告的错误。(CAMP-42505)


![](assets/do-not-localize/cp-icon.png) **新控制面板可以发行** ，并为CNAME子域续订证书。 [了解详情](https://docs.adobe.com/content/help/zh-Hans/control-panel/using/release-notes.html)。
