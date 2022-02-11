---
title: 早期发行说明
description: 早期发行说明
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: fcc4dc0789a02f2a58abed858561f023a53a9d95
workflow-type: ht
source-wordcount: '736'
ht-degree: 100%

---

# 早期发行说明 {#new-release}

本页介绍了下一个 Campaign Standard 版本中包含的新增功能、改进和修复。

>[!CAUTION]
>
> 在暂存环境升级日期之前，此内容可能会有所变动，恕不另行通知。在[发行计划页面](../../rn/using/release-planning.md)中了解详情。

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
* 为了解决各种问题，已对投放（包括从 URL 导入的内容）的重试机制进行了改进。[了解详情](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time) (CAMP-48888)
* 修复了在自定义资源中创建新筛选条件，然后将其用作登陆页面中的合并关键项后发生的问题。如果自定义资源再次发布，则会从登陆页面的可用合并关键项列表中删除该筛选条件。(CAMP-49516)
* 修复了将动态条件与复选框结合使用时登陆页面中存在的问题。(CAMP-48604)
* 修复了使用“10 月或之前”筛选条件时，**查询**&#x200B;活动中出现的问题。当从设置为欧洲时区的实例工作时，由于时区转换的问题，筛选条件的选定月份显示为 9 月，而不是 10 月。(CAMP-48602)
* 为优化投放能力，Adobe Campaign 现在使用 7 位编码而不是 8 位编码来发送电子邮件。这样可以防止中间中继使 DKIM 签名失效，从而影响邮件的真实性。(CAMP-49016)
* 增强了复制受众时的性能，以避免在处理大量受众时出现任何问题。(CAMP-49639)
* 修复了在&#x200B;**查询**&#x200B;活动中使用自定义筛选条件时可能导致其无法显示正确结果的问题。(CAMP-49417)
* 修复了尝试在投放中使用名称中带有逗号的片段时显示错误消息的错误。此问题已得到解决，现在可以在片段名称中使用逗号。(CAMP-49216)