---
title: 最新版本
description: 本页列表了所有最新版本的Adobe Campaign标准。
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
source-git-commit: e59562bd4f258c4259b8e8e5d9648397d5718792
workflow-type: tm+mt
source-wordcount: '1039'
ht-degree: 0%

---


# 最新版本{#latest-release}

[发布计划](../../rn/using/release-planning.md) |控 [制面板版本](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) |文 [档更新](../../rn/using/documentation-updates.md) |先 [前发行说明](../../rn/using/release-notes-2020.md) |已弃 [用功能](../../rn/using/deprecated-features.md)

## 版本20.3 - 2020年5月 {#release-20-3---may-2020}

**新增内容?**

<table> 
<thead> 
<tr> 
<th> <strong>泰国个人数据保护法(PDPA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>泰国的个人数据保护法(PDPA)是新的隐私法，旨在协调泰国的数据保护要求并使之现代化。 本规定适用于为居住在该国的Adobe Campaign主体持有数据的客户。</p>
<p>除了Adobe Campaign中已有的隐私功能（包括同意管理、数据保留设置和用户角色）之外，我们还将利用此机会加入其他功能，以帮助您为PDPA做好准备：</p>
<ul>
<li>访问权和删除权： 我们正在利用为GDPR和CCPA添加的功能。 <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#righttoaccess">了解更多</a> </li>
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
  <td> <p>外 <strong>部API活动</strong> 正在从测试版过渡到GA。 此版本为JSON响应主体分析器带来了更多灵活性。 您现在可以：</p>
<ul>
<li>解析最大深度为10个级别的嵌套JSON。 </li>
<li>将选定属性解析为JSON中的叶节点，并将其拼合到单个表行中。</li>
<li>从JSON中选择并使用数组对象，无需将对象命名为“data”或让其处于顶级。</li>
</ul>
<p><strong>注意：</strong> 客户需要用其 <strong>工作流中的GA External API</strong> 活动替换所有测试版外部API活动。  使用External API测试版的工作流将在20.3中停止工作。</p>
<p>有关详细信息，请参 <a href="../../automating/using/external-api.md">阅详细文档</a><a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">和操作方法视频</a>。</p>
</td> 
</tr> 
</tbody> 
</table>

>[!NOTE]
>
>CNAME子域的证书续订将于5月在活动控制面板中发布。 有关此问题的详细信息，请参 [阅控制面板发行说明](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html)。

**改进**

* 使用目标用户档案测试消 **息** ，前 [缀字段中可使](../../sending/using/testing-messages-using-target.md) 用的字符数从32个增加到500个字符。
* 可在实例上发布的最大实时事件数已从350增加到2000。 (CAMP-41608)
* Adobe Launch与Campaign Standard之间的同步已通过使用syncWithLaunch技术工作流程得到改进。 此工作流程支持将所有Adobe Launch移动属性自动导入到Adobe Standard中。 For more information, refer to [this page](../../administration/using/technical-workflows.md).

   您需要向Adobe客户服务中心（直接或通过您的Adobe联系人）提交票证，以便在活动实例中启用syncWithLaunch技术工作流程。 (CAMP-40082)

**Email Designer增强功能**

* 与严格的W3C相比，电子邮件设计器现在可以处理更灵活的HTML格式。 (CAMP-42529)
* 修复了可单击 [图像的问题](../../designing/using/links.md#inserting-a-link) ，以防止链接显示在内容块中图像旁边。 (CAMP-41586)
* 修复了在跟踪的URL在模板中添加登陆页时 [阻止重定向](../../designing/using/links.md#about-tracked-urls) 到类别的问题。 (CAMP-41537)
* 修复了Outlook中按钮填充的问题。
* 修复了导致HTML标记以纯文本显示的问题。
* 内容块搜索现在显示服务器搜索结果和预加载结果。 (CAMP-41870)

**其他更改**

* 自定义资源发布界面已得到改进，错误消息更清晰。
* 未使用的投放映射已从接口中删除。
* 已从界面中删除了不必要的管理员角色。
* 现在，复选框在登陆页中可为必填项。
* 下载动态报告的CSV文件时，已删除200行的限制。 现在，您可以包含报表的每一行。 (CAMP-40810)
* 为多语言电子邮件添加了开箱即用语言列表的ES-US语言。 (CAMP-42279)
* 现在，使用“传输文件”活动下载的文件将在X天后被删除，其中X由“工作流”属性 **的“执行”菜单****下的“History in days** ”字段决定。 [阅读更多](../../automating/using/managing-execution-options.md)

**Experience Platform集成**

* Adobe Experience Platform激活 [的受众](../../automating/using/aep-targeting-audiences.md) ，从读 **取受众活动改** 进后的，可提供更好的性能和稳定性。 此外，工作流日志在激活工作方面也变得更清晰、更详细，在阅读Adobe Experience Platform受众时可以更轻松地进行监控和故障排除。

**修补程序**

* 修复了导致在自定义资源的发布作业期间创建重影资源的错误。
* 修复了一个问题，该问题可能会阻止用户档案营销历史在自定义资源扩展时显示用户档案资源。 (CAMP-41009)
* 修复了开箱即用登陆页模板在打开编辑器时以法语显示其内容的问题。 (CAMP-41639)
* 修复了动态内容推送通知中可能阻止显示表情符号的问题。 (CAMP-40715)
* 修复了外部重复数据删除 **活动中** ，该问题可能导致分配给其中一个出站补充过渡的段代码不正确。 (CAMP-41400)
* 修复了阻止删除计划报告的错误。 (CAMP-41302)
* 修复了导致投放仪表板与投放摘要报表 **不一致的问** 题。 (CAMP-41145)
* 修复了导致下载的报告中出现字符重叠显示问题的问题。
* 修复了阻止预览投放进行验证替换的问题。
* 修复了删除应用程序内本地通知的自定义字段时出错。
* 修复了charIndex函数无法在工作流中使用 **End** 或 **File传** 输活动的问题。
* 修复了在工作流中使用两个输入的 **扩充** 活动时可能出现的问题，这些输入活动包括在它们之间具有链接的目标资源。 (CAMP-42133)
* 修复了在使用未知函数时可能阻止工作流运行的问题。 (CAMP-41873)
* 修复了在使用多个具有补充出站工作流的“保存受众 **”活动创建受众时可能发** 生的过渡问题。 (CAMP-39992)
* 修复了在交易电子邮件中使用个性化时导致数据不一致的问题。 (CAMP-41842)
* 修复了在推送通知投放中删除自定义字段时发生的问题。 (CAMP-37586)
* 修复了阻止用户更改报告的错误。 (CAMP-42505)
