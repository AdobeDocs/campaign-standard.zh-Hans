---
title: 最新版本
description: 本页列表了所有最新版本的Adobe Campaign标准版。
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
source-git-commit: 86302762a46a814ecc9b14a5fe1bfe1a4a4e0437

---


# 最新版本{#latest-release}

[发布计划](../../rn/using/release-planning.md) |控 [制面板版本](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) |文 [档更新](../../rn/using/documentation-updates.md) |先 [前发行说明](../../rn/using/release-notes-2020.md) |已弃 [用功能](../../rn/using/deprecated-features.md)

## 版本20.3 - 2020年5月 {#release-20-3---may-2020}

**新增内容?**

<table> 
<thead> 
<tr> 
<th> <strong>泰王国的个人数据保护法(PDPA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>泰国的个人数据保护法(PDPA)是一项新的隐私法，它协调了泰国的数据保护要求并使其现代化。 本规定适用于持有居住在本国的数据主体数据的Adobe Campaign客户。</p>
<p>除了Adobe Campaign中已有的隐私权（包括同意管理、数据保留设置和用户角色）外，我们还将利用此机会加入其他功能，以帮助您做好PDPA准备：</p>
<ul>
<li>访问权和删除权：我们正在利用为GDPR和CCPA添加的功能。 <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#righttoaccess">了解更多</a> </li>
<li><p>创建隐私请求时，PDPA规定类型已添加到隐私核心服务中。 此方法是您应用于所有访问和删除请求的方法。 不建议使用活动API和接口访问和删除请求。  请参阅已弃 <a href="../../rn/using/deprecated-features.md">用和已删除功能文章</a>。</p></li>
</ul>
<p>请参阅 <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">操作方法视频</a>。</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>外部API活动(GA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>外部 <strong></strong> API活动正在从测试版过渡到GA。 此版本为JSON响应正文分析器带来了额外的灵活性。 您现在可以：</p>
<ul>
<li>解析最大深度为10个级别的嵌套JSON。 </li>
<li>将选定属性解析为JSON中的叶节点，并将其拼合到单个表行中。</li>
<li>从JSON中选择并使用数组对象，无需将对象命名为“data”，也不必将其命名为顶级。</li>
</ul>
<p><strong>注意：</strong> 客户需要用其 <strong>工作流中的GA External API</strong> 活动替换所有测试版外部API活动。  使用External API测试版的工作流将在20.3中停止工作。</p>
<p>有关详细信息，请参 <a href="../../automating/using/external-api.md">阅详细文档</a><a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">和操作方法视频</a>。</p>
</td> 
</tr> 
</tbody> 
</table>

**改进**

* “前缀”字段中可用于使用目 **标用户档案** 测试消息的字符数 [](../../sending/using/testing-messages-using-target.md) ，已从32个增加到500个。
* 可在实例上发布的实时事件的最大数目已从350增加到2000。 (CAMP-41608)

**Email Designer增强功能**

* 与严格的W3C相比，电子邮件设计人员现在可以处理更灵活的HTML格式。 (CAMP-42529)
* 修复了可单击 [图像的问题](../../designing/using/links.md#inserting-a-link) ，以防止链接显示在内容块中图像旁边。 (CAMP-41586)
* 修复了在被跟踪的URL中添加了登陆页时， [阻止重定向到类别](../../designing/using/links.md#about-tracked-urls) 的问题。 (CAMP-41537)
* 修复了Outlook中按钮填充的问题。
* 修复了导致HTML标记以纯文本显示的问题。
* 内容块搜索现在显示服务器搜索结果以及预加载的结果。 (CAMP-41870)

**其他更改**

* 自定义资源发布界面已得到改进，错误消息更清晰。
* 未使用的投放映射已从接口中删除。
* 从界面中删除了不必要的管理员角色。
* 现在，复选框在登陆页中可为必填项。
* 下载动态报告的CSV文件时，已删除200行的限制。 您现在可以包含报表的每一行。 (CAMP-40810)
* 为多语言电子邮件添加了开箱即用语言列表的ES-US语言。 (CAMP-42279)
* 现在，使用“传输文件”活动下载的文件将在X天后删除，其中X由“工作流”属性中“执行”菜单下的“ **History in days** ”字段 **** 确定。 [阅读更多](../../automating/using/executing-a-workflow.md#workflow-properties)

**Experience Platform集成**

* Adobe [Experience Platform受众的](../../automating/using/aep-targeting-audiences.md) “读取 **受众”激活的活动已得到改进** ，可提供更好的性能和稳定性。 此外，工作流日志在激活作业方面已变得更清晰、更详细，从而在阅读Adobe Experience Platform受众时可以更轻松地进行监控和疑难解答。

**修补程序**

* 修复了导致在自定义资源的发布作业期间创建重影资源的错误。
* 修复了在用户档案资源扩展自定义资源时，可能会阻止用户档案显示的问题。 (CAMP-41009)
* 修复了开箱即用的登陆页模板在打开编辑器时以法语显示其内容的问题。 (CAMP-41639)
* 修复了动态内容推送通知中可能阻止显示emoji的问题。 (CAMP-40715)
* 修复了外部重复数据删除 **活动中的问题** ，该问题可能导致分配给其中一个出站补充过渡的段代码不正确。 (CAMP-41400)
* 修复了阻止删除计划报告的错误。 (CAMP-41302)
* 修复了导致投放仪表板与投放摘要报表不 **一致的问题** 。 (CAMP-41145)
* 修复了导致下载的报告中出现字符重叠显示问题的问题。
* 修复了阻止预览投放进行验证替换的问题。
* 修复了删除应用程序内本地通知的自定义字段时出现的错误。
* 修复了charIndex函数无法在工作流中使用 **End** 或 **** File传输活动的问题。
* 修复了工作流中的一个问题，该问题在对两个输入活动(包括目标资源)使用 **** 扩充活动时可能会发生。 (CAMP-42133)
* 修复了使用未知函数时可能阻止工作流运行的问题。 (CAMP-41873)
* 修复了在使用多个具有补充出站工作流的“保存受众 **** ”活动创建受众时可能发生的过渡问题。 (CAMP-39992)
* 修复了在交易电子邮件中使用个性化时导致数据不一致的问题。 (CAMP-41842)
* 修复了在推送通知投放中删除自定义字段时发生的问题。 (CAMP-37586)
* 修复了阻止用户更改报告的错误。 (CAMP-42505)
