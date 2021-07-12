---
solution: Campaign Standard
product: campaign
title: 发行说明 2021
description: 本页列出了所有 2021 版的 Adobe Campaign Standard。
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: 概述
role: User
level: Beginner
exl-id: b6cf7152-2200-43d7-8d0a-d65752bb2c9b
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '2535'
ht-degree: 100%

---

# 发行说明 2021{#release-notes-2021}

[发行计划](../../rn/using/release-planning.md) | [控制面板版本](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=zh-Hans) | [文档更新](../../rn/using/documentation-updates.md) | [之前的发行说明](../../rn/using/release-notes-2020.md) | [已弃用的功能](../../rn/using/deprecated-features.md)

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

* SMS 连接器现在可以随每条消息发送多个可选参数。[了解详情](../../administration/using/sms-protocol.md)

* 具有 DATAMODEL 角色的用户现在可以发布投放日志扩展。(CAMP-46604)

* 在尝试发布针对不再存在的自定义资源的资源时所显示的错误消息变得更清晰。(CAMP-46893)

* 已向&#x200B;**首选语言**&#x200B;列表中添加下列语言：印度尼西亚语 - 印度尼西亚 (in-id)、英语 - 瑞典 (en-se)、英语 - 亚太地区 (en-ap)、英语 - 日本 (en-jp)、西班牙语 - 拉丁美洲 (es-la)。(CAMP-46351)

* 测试登陆页时用于选择用户档案的的选取器现在将使用 profilBase 资源而不是用户档案，以防止超时。

* SMPP 日志格式已得到改进。

* 为匹配 Adobe Campaign Classic API，添加了 cryptString 和 decryptString JS 函数的可选参数。

* 改进了投放准备日志中的警告或错误消息。

* 在尝试连接到 Adobe Identity Management 服务 (IMS) 时改进了错误日志。

* 您现在可以使用动态报告中的搜索栏进一步筛选&#x200B;**投放**&#x200B;和&#x200B;**活动**&#x200B;维度。

* 事务性 SMS 消息有效日期现在可以由事务性消息 API 中为到期参数设置的值定义。(CAMP-36600)

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
