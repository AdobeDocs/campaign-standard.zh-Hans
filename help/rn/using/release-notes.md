---
solution: Campaign Standard
product: campaign
title: 最新版本
description: 此页面详细描述最新 Campaign Standard 版本的内容
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: 概述
role: Business Practitioner
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: d5bea4a96576dc13aa06939876ef6549115a2b75
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 6%

---


# 最新版本{#latest-release}

## 21.2 版 - 2021 年 6 月{#release-21-2---june-2021}

下面列出了下一个Campaign Standard版本中包含的新增功能、改进和修复。 下面列出了此Campaign Standard版本中包含的新增功能、改进和修复。

**改进**

* 设计登陆页面时，您现在可以添加一个必填复选框，要求用户档案在提交表单前进行选择。 有关更多信息，请参阅[详细文档](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox)。

* 对于Triggers集成，当触发器有效负载中没有协调数据时显示的错误消息已得到改进：&quot;负载中缺少别名数据&quot;。

* 改进了从队列检索推送通知的性能。

**其他变更**

* 已禁用跟踪链接的URL签名机制，以防止在被第三方安全工具修改后导致某些有效的已签名跟踪链接被错误阻止的问题。

* 在多变体投放中，如果删除了默认变体，则用户将无法再创建语言副本。 现在，在语言副本创建期间会显示消息。 (CAMP-48235)

* 现在，默认情况下禁用两步用户档案删除流程（从Campaign 19.4版本开始被弃用）。 以前，必须先从Campaign界面手动禁用该功能，然后才能使用隐私核心服务。 否则，删除请求将在未完成的情况下保持挂起状态。

* 引入了新的“StringAgg”聚合函数，以连接字符串类型列的值。 (CAMP-47077) [了解详情](../../automating/using/list-of-functions.md#aggregates)

* 在动态报告中，**Exclude Proof**&#x200B;区段已被删除。 (CAMP-46161)

* 添加了新的警告消息，以在上传iOS证书时通知用户，而Campaign应用程序中没有platformPrincipal值。

* 默认情况下，电子邮件的最大大小现在设置为100 MB。 利用此限制，可防止可能无限期地增加电子邮件大小的任何错误，这些错误可能会导致系统崩溃。 (CAMP-47445) [了解详情](../../sending/using/design-and-personalize.md#email-size)

* 现在，标准用户可以使用与电子邮件设计器的资产核心服务集成。

* 添加了新消息，以确认成功从v4推送应用程序迁移到v5推送应用程序。

* 在创建JSONWeb令牌以对Campaign StandardAPI进行身份验证期间，产品配置文件现在&#x200B;**被视为**。 这意味着分配给安全组的组织单位和角色（与AdobeIO上的产品配置文件匹配）将应用于Campaign StandardRest API调用所需的IMS技术帐户。 (CAMP-47479)

**修补程序**

* 修复了批量处理日志表(**xtkjoblog**)表的到期选项无法应用的问题。 这会阻止正确清除表。

* 修复了阻止您更改&#x200B;**分段**&#x200B;工作流活动中过滤器顺序的问题。 (CAMP-48357)

* 修复了20.4中的回归，该回归可能会导致投放失败，并出现空值错误。 (CAMP-48591)

* 修复了阻止通过&#x200B;**共享** > **立即发送报表**&#x200B;或&#x200B;**按计划发送报表**&#x200B;菜单发送报表的问题。 (CAMP-47798)

* 修复了由于过滤从Gmail帐户接收的跟踪事件而导致Gmail打开率不正确的回归。 (CAMP-46504)

* 修复了导致Adobe Campaign Standard中的报表与Adobe Analytics中的报表之间存在数据差异的各种问题。 （CAMP-47671 和 CAMP-47296）

* 修复了准备失败后无法访问投放日志的问题。 (CAMP-48296)

* 修复了在尝试编辑、删除或发送自定义报表时可能显示错误消息的问题。 （CAMP-47789 和 CAMP-47798）

* 修复了在创建新的自定义资源并启用&#x200B;**不同步**&#x200B;选项时导致API调用失败的问题。 (CAMP-48014)

* 修复了启用&#x200B;**Do not synchronize**&#x200B;选项的自定义资源可能引用已重新起草或删除的架构的问题。 此问题在发布自定义资源时导致错误。

* 修复了在同一外部帐户上使用多个短代码时短信的选择退出问题。

* 修复了在发布数据库后无法访问新投放警报标准（“您尝试访问的资源不可访问”）的问题。 (CAMP-48221)

* 修复了某些具有动态报告的Campaign实例中缺少跟踪日志的问题。 添加了新的[技术工作流](../../administration/using/technical-workflows.md)以恢复这些跟踪日志。 (CAMP-47885)

* 修复了动态报告中未显示投放数据的问题。 报表被设置为0。 (CAMP-47480)

* 修复了阻止服务器JavaScript HTTP客户端连接到外部URL的问题。

* 修复了在更改工作流的内部名称后重置&#x200B;**增量查询**&#x200B;活动的问题。 当将日期字段用作增量模式时，会发生这种情况。 (CAMP-47674)

* 修复了使用Adobe Experience Manager集成创建多语言电子邮件时，投放摘要中无法显示预览缩略图的问题。 使用&#x200B;**语言副本创建**&#x200B;按钮创建电子邮件变体时，出现此问题。 (CAMP-47810)

* 修复了阻止用户从电子邮件或短信子投放访问父投放的问题。 (CAMP-47986)

* 修复了在通过缺少自定义事件的REST API发送事务型消息时，可能导致CPU和内存消耗过多的问题。 (CAMP-47147)

* 修复了事务性消息传递API的错误，该错误有时会阻止发送实时消息。

* 修复了使用&#x200B;**按计划发送报表**&#x200B;选项后未收到报表的问题。 （CAMP-48583 和 CAMP-47786）

* 修复了使用&#x200B;**立即发送报表选项**&#x200B;后收到的报表不完整且缺少数据的问题。 (CAMP-48583)

* 修复了Email Designer在上传图像时缩小图像尺寸的问题。 (CAMP-47017)

* 修复了在创建投放时阻止显示每个可用Experience Manager模板的问题。 (CAMP-48132)

* 修复了阻止已发送投放的“摘要”页面中的“营销活动”链接将用户重定向到相关营销活动的错误。 (CAMP-48012)

* 修复了Email Designer中的一个问题，即在尝试选择资产时，资产核心服务集成一直失败。 (CAMP-47446)

* 修复了由于Campaign不支持由Journey Orchestration事件发送的具有精确值（即以00结尾）的时间戳，从而阻止某些Journey Orchestration投放的问题。
