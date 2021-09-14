---
title: 早期发行说明
description: 早期发行说明
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 100%

---

# 早期发行说明 {#new-release}

本页介绍了下一个 Campaign Standard 版本中包含的新增功能、改进和修复。

>[!CAUTION]
>
> 在暂存环境升级日期之前，此内容可能会有所变动，恕不另行通知。在[发行计划页面](../../rn/using/release-planning.md)中了解详情。

## 21.3 版 - 2021 年 9 月 {#release-21-3---sept-2021}


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
<!--<p>For more information refer to the <a href="../../start/using/interface-description.md#top-bar">detailed documentation</a>.
</p>-->
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
<!--<p>For more information refer to the <a href="../../administration/using/audit.md">detailed documentation</a>.
</p>-->
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
<!--<p>For more information refer to the <a href="../../administration/using/audit.md">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>

**改进**

* 现在，在工作流中创建链接到 Adobe Experience Manager 内容的定期投放时，发送之前会检查内容批准状态。
* 数据库连接限制现在与 Campaign 包一致，以避免连接错误。
* 在自定义资源中创建索引时添加了一致性检查并改进了错误消息。

**修补程序**

* 修复了从 URL 导入电子邮件内容时出现的超时错误。(CAMP-49054)
* 修复了访问已添加书签的 URL 或从浏览器刷新页面时，会话结束导致的错误 (-69)。(CAMP-49003、CAMP-48930、CAMP-48894)
* 修复了将规则从旧版可交付性服务器同步到新版可交付性服务器时出现的问题。(CAMP-48923)
* 修复了在电子邮件设计工具中加载带有 HTML 标签的电子邮件模板时出现的问题。(CAMP-48243)
