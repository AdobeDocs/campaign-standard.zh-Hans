---
title: 发行说明 2018
description: 本页列出了所有 2018 版的 Adobe Campaign Standard。
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: 17521357-14ae-4751-bd7c-aeabbcf71d07
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '5401'
ht-degree: 4%

---

# 发行说明 2018{#release-notes}

是否正在寻找2018版的Adobe Campaign Standard?

每个版本都提供新功能和修补程序。 单击某个版本以查看其内容。

查看最新 [文档更新](../../rn/using/documentation-updates.md) Adobe Campaign Standard。 如果您正在查找较新版本，请参阅 [页面](../../rn/using/release-notes.md).

## 18.9 版 - 2018 年 9 月 {#release-18-9---september-2018}

**新增功能**

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 说明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 应用程序内消息传送（测试版）<br /> </td> 
   <td> 应用程序内消息可提供上下文互动，并且让您能够联系可能选择退出推送通知的用户，从而使您能够更有效地吸引移动应用程序用户。 将应用程序内消息与推送通知结合使用，可创建高度个性化且相关的体验。 这可以提高应用程序用户的转化率和维系率。<br /> 有关更多信息，请参阅 <a href="../../channels/using/about-in-app-messaging.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe移动应用程序的Launch集成（测试版）<br /> </td> 
   <td> Adobe与Adobe Campaign的Launch集成现在使用Mobile SDK V5简化了Campaign中移动应用程序属性激活的过程并实现了自动化。<br /> 有关更多信息，请参阅 <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">详细文档</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**改进**

* Adobe Campaign Standard现在支持Amazon S3 API版本4。

**其他变更**

* 在广播日志中，每小时的最大连接数和最大消息数之间存在区别。 当达到限制时，就可以知道为什么吞吐量有限。 以前，同一消息（“满足配额”）适用于这两种情况。
* 现在，在Campaign中配置移动应用程序时，用户可以知道iOS证书和Android服务器密钥是否已成功上传以及其过期日期。

   有关更多信息，请参阅有关如何使用配置移动应用程序的详细文档 [SDK V4](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdkv4.html) 和 [SDK V5](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdk.html).

* 在定义促销活动属性时，通过选择移动设备应用程序来定位特定移动设备应用程序上的用户。 此功能适用于推送和应用程序内消息传送渠道。

   有关更多信息，请参阅[详细文档](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification)。

* 现在，使用Creative Designer界面选择内容块时，将加载并显示列表中的所有内容块。 (CAMP-27311)

   有关更多信息，请参阅 [详细文档](../../designing/using/personalization.md#adding-a-content-block).

**修补程序**

* 修复了电子邮件仪表板与事务电子邮件的电子邮件摘要报表之间的日志计数不一致的问题。 (CAMP-28237
* 修复了通过文件传输活动导入文件时工作流中可能显示错误消息的问题。 (CAMP-27435)
* 修复了包含25项以上服务的登陆页面导致在表单中随机取消选择服务的问题。 (CAMP-26572)
* 修复了工作流中使用文件传输活动时无法使用SFTP URL配置外部帐户的问题。 (CAMP-26475)
* 修复了阻止更新服务摘要报表的问题。 (CAMP-26301)
* 修复了使用扩充活动时工作流中阻止自定义字段显示正确日期的问题。 (CAMP-26242)
* 修复了通过文件导入导入时无法更新服务订阅日期的问题。
* 修复了加载文件活动中阻止工作流导入文件的错误(CAMP-27068)。
* 修复了在服务摘要报告中显示错误订阅数的问题(CAMP-25587)。
* 修复了Adobe Analytics报表和Adobe Campaign报表之间数据不一致的问题。 (CAMP-25393)
* 修复了可能阻止有限访问用户登录的问题。 (CAMP-27381)
* 修复了在使用Creative Designer编辑电子邮件时可能阻止显示Adobe Experience Manager内容列表的问题。 (CAMP-27181)
* 修复了可能阻止Creative Designer打开并导致错误的问题。 (CAMP-27304)
* 修复了使用Internet Explorer 11时，Creative Designer中的拖放功能无法正常工作的问题。
* 修复了从相机上传并以纵向模式拍摄的图片在不需要的旋转位置显示的问题。
* 修复了在Creative Designer中使用查询编辑器界面时显示不明确选择信息的问题。
* 修复了在Creative Designer中使用查询编辑器界面时无法正确复制元素的问题。
* 修复了即使收件人已通过自动回复取消订阅，仍阻止列表在上向收件人投放短信消息的问题。 (CAMP-27128)
* 修复了无法显示导致 **数据库清理** 工作流失败。 (CAMP-26876)
* 修复了可能阻止删除推送通知定义中的自定义字段的问题。 (CAMP-25588)

## 18.7 版 - 2018 年 7 月 {#release-18-7---july-2018}

**新增功能**

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 说明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Android推送通知的高优先级标记<br /> </td> 
   <td> Android的高优先级标记 — 为Android应用程序启用高优先级的推送通知传送功能，这会导致睡眠设备唤醒并运行一些有限的处理。 请注意，默认优先级为“正常”，这可能会延迟邮件投放以节省电池。 <br /> 有关更多信息，请参阅 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 适用于移动设备应用程序订阅者的分类过滤器<br /> </td> 
   <td> 在分类过滤器中支持订阅 — 在为分类规则指定筛选条件时，可以选择应用程序订阅作为筛选和定向维度，以便能够对具有或不具有配置文件的用户的属性进行筛选。 <br /> 有关更多信息，请参阅 <a href="../../sending/using/about-typology-rules.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 在消息准备期间从URL自动导入内容<br /> </td> 
   <td> 现在，可以在准备阶段期间从URL导入电子邮件内容。 对于定期电子邮件投放，每次准备消息时均会检索最新的HTML内容，以确保该内容在发送电子邮件时始终保持最新。 此功能还允许您创建包含URL中内容的计划投放，即使该内容尚未准备就绪。<br /> 有关更多信息，请参阅 <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Campaign发布通知消息<br /> </td> 
   <td> 现在，当用户在实例升级到新版本后登录时，会显示一条弹出消息。 该消息指示版本号，并包含指向发行说明的链接。 您可以选择在下一个版本之前隐藏消息。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 用户管理<br /> </td> 
   <td> 从18.7版本开始，地理单位功能现在不可用于新Campaign Standard实例以及未创建地理单位的现有实例。<br /> 有关更多信息，请参阅 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=zh-Hans#release-notes">页面</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**改进**

* 现在，Adobe Campaign和Adobe Target集成允许您利用Target的 [权限](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html) 功能。 现在，在电子邮件中包含来自Adobe Target的动态图像时，您可以指定Target属性（at_property代码）。
* 现在，GDPR隐私访问/删除请求会考虑具有指向用户档案资源的自定义资源。 对于1个基数简单链接和N个基数集合链接，您需要在自定义资源中选择“删除/复制目标记录意味着删除/复制链接引用的记录”。 对于0或1个基数简单链接，选择“删除/复制记录意味着删除/复制链接引用的目标记录”。

**其他变更**

* 报表共享超时时间已从1分钟增加到4分钟，以避免发生任何超时错误。
* 编辑电子邮件的内容时，默认情况下会打开新的Creative Designer。 如果需要，您仍可以在保存更改后随时返回默认内容编辑器。 有关更多信息，请参阅 [详细文档](../../designing/using/designing-content-in-adobe-campaign.md).
* 在Creative Designer中，现在可以将新的内容组件添加到电子邮件中：轮播。 有关更多信息，请参阅 [详细文档](../../designing/using/designing-from-scratch.md#about-content-components).
* 在事务型消息热点单击报表中，当您单击 **更改用户档案** 按钮时，现在只会列出链接到您为事务型消息定义的事件的测试用户档案。

**修补程序**

* 修复了byEmail查询过滤器无法返回任何结果的问题。 (CAMP-23420)
* 修复了允许标准用户访问限制为管理员的某些功能或屏幕（/rest/head/*端点、事务性消息屏幕、用户档案和受众导入屏幕）的问题。
* 修复了当GDPR隐私删除请求的名称以数字开头时，阻止其处理自定义资源的问题。
* 修复了在Adobe Experience Cloud中保存受众活动无法共享应用程序订阅者的错误。
* 修复了文件传输活动在文件名包含空格时可能发生的问题。 (CAMP-25936)
* 修复了在会话过期后使用重新连接按钮时可能发生的问题。 (CAMP-25560)
* 修复了在发送与疲劳规则关联的时区优化投放时可能导致排除的问题。 (CAMP-25425)
* 修复了使用API GDPR功能时可能会阻止删除具有0-1类型链接的数据的问题。
* 修复了在取消疲劳分类规则的版本时可能导致错误消息的问题。
* 修复了在编辑投放内容后预览该内容时可能发生的问题。
* 修复了使用解压缩选项处理CSV zip文件时可能发生的问题。
* 修复了Creative Designer中的一个问题，该问题会在将具有内置样式的某些文本更改为链接或编辑该链接时，导致不需要的颜色字体和格式。 (CAMP-26001)
* 修复了热点单击报告无法显示包含动态内容的投放中每个条件的百分比的问题。 以前，只显示对默认变体的单击。

## 18.6 版 - 2018 年 6 月 {#release-18-6---june-2018}

**改进**

* 的 **[!UICONTROL History]** API已添加到Adobe.IO。 它允许您访问与用户档案的营销历史相关的信息：接触点数、已发送投放数、镜像页面URL数等。 有关更多信息，请参阅 [专用用例](../../api/using/interacting-with-marketing-history.md) .
* 的 **[!UICONTROL Database cleanup]** 技术工作流已得到优化，以确保数据库备份的性能更好。
* Creative Designer for Email现在也提供法语和德语版。

**其他变更**

* A **[!UICONTROL Compute stats]** 按钮 **[!UICONTROL Deployment]** 已发送投放的窗口。 利用此功能，可检索最新KPI，例如，如果发送的结果更新时间过长或未被考虑在内。 有关更多信息，请参阅此](../../sending/using/confirming-the-send.md)章节[。
* 在 **可投放性更新** 现在，功能管理员可以定义要在 **更新规则** javascript活动。 默认情况下，字段值设置为0，这意味着将忽略所有错误。
* 优化了管理单元访问限制条件时生成的SQL。
* 的 **[!UICONTROL Update]** 活动现在允许您添加、更新或删除与订阅相关的数据（nms:appSubscriptionRcp表）。
* 的 **[!UICONTROL Update delivery execution]** 为了优化性能，技术工作流分为两个工作流：- **[!UICONTROL Update delivery execution]**:更新投放的跟踪。 默认情况下，每10分钟启动一次。 **[!UICONTROL Update delivery indicators]**:更新投放的KPI，默认情况下每小时启动一次。 有关技术工作流的更多信息，请参阅此 [部分](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* 投放发送消息时， **[!UICONTROL Deployment]** 部分现在可以有两个值： **[!UICONTROL Sending]**:正在发送消息。 **[!UICONTROL Sending (retry)]**:正在进行重试传递。
* 具有 **[!UICONTROL Delivery preparation]** 角色现在可以发送校样。 (CAMP-24313)
* 的 **通过SMPP启用TLS** 选项 **通过SMPP的短信路由** 外部帐户。 如需详细信息，请参阅 [部分](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

**修补程序**

* 修复了在包含来自Adobe Target的动态图像时可能阻止发送电子邮件的问题(CAMP-24848)。
* 修复了 **[!UICONTROL Privacy Access/Delete Request]** 技术工作流，当任何请求失败时，该工作流无法完成。
* 修复了隐私核心服务无法从Campaign接收请求状态更新的问题。
* 修复了可能阻止 **[!UICONTROL Import shared audience]** 技术工作流正常工作(CAMP-25465)。
* 修复了阻止在核心Privacy Service中将Campaign隐私请求标记为已完成的问题。
* 修复了在Adobe ID过长时，可能会阻止某些用户通过IMS身份验证登录到Campaign Standard的问题。 (CAMP-24095)
* 修复了在Creative Designer中删除内容模块时可能发生的问题。 (CAMP-25242)
* 修复了在对数据库中没有用户档案的订阅者使用推送通知疲劳规则时的问题。 (CAMP-25344)
* 修复了访问投放排除日志时可能显示错误消息的问题。 (CAMP-24724)
* 修复了在具有扩展发送日志的实例中阻止准备校样的问题。
* 修复了在使用 **[!UICONTROL Sending log]** 扩展已激活。
* 修复了在定期投放中未考虑投放持续时间时可能发生的问题。
* 修复了在 **[!UICONTROL Client data]** 菜单，用于具有10万条以上记录的自定义资源。 (CAMP-24308)
* 修复了在动态报告中使用搜索功能时未考虑的自定义用户档案维度问题。
* 修复了在动态报告中显示帐户级别的国际数据时出现的问题。
* 现在，可以创建无订阅或退订确认消息的服务。

## 18.5 版 - 2018 年 5 月 {#release-18-5---may-2018}

**新增功能**

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 说明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> GDPR:核心服务集成<br /> </td> 
   <td> 隐私核心服务集成允许您通过单个JSON API调用，在多解决方案上下文中自动处理GDPR请求。 <br /> 现在，从隐私核心服务推送到所有Experience Cloud解决方案的GDPR请求将由Campaign自动处理。 <br /> 有关更多信息，请参阅 <a href="https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=zh-Hans">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送改进 — 详细的投放反馈<br /> </td> 
   <td> Adobe Campaign现在提供了通过MCPNS从提供程序(APNS/GCM)接收推送消息的详细反馈（发送日志和排除日志）的功能。<br /> 有关更多信息，请参阅 <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放日志扩展<br /> </td> 
   <td> 投放日志扩展允许您使用来自工作流的用户档案数据和段代码扩展发送日志。 此信息随后可在动态报告中使用，并允许您在投放发送时保存一些信息的快照。<br /> 还有2个用例：<br /> 
    <ul> 
     <li> 导出包含“冻结”数据的扩展广播：作为营销人员，我希望导出区段代码等于“A”的所有用户档案（来自工作流引擎）。 </li> 
     <li> 对“冻结”数据进行分段：作为营销人员，我想 <strong>重定位</strong> 自上次发送后或区段代码等于“A”时已赢得1000个会员积分的所有用户档案。 </li> 
    </ul> 有关更多信息，请参阅<a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 使用自定义用户档案数据进行动态报告<br /> </td> 
   <td> 此功能允许您根据在用户档案资源扩展期间创建的自定义用户档案数据创建和管理报表。 您可以按用户档案属性（如忠诚度计划、首选渠道等）划分报表。<br /> 有关更多信息，请参阅 <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">详细文档</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**改进**

* 应用程序的总内存和CPU使用率已得到增强

**其他变更**

* “读取受众”工作流活动现在可以读取Experience Cloud受众。 以前，此活动只能读取查询和列表受众。 请参阅 [详细文档](../../automating/using/read-audience.md). (CAMP-23623)
* 默认共享数据源的标识符现在处于只读模式，不能再更改。 更改此标识符可能会在与Experience Cloud共享受众时导致一些问题。
* 现在，从Audience Manager导入受众可以处理拆分文件。 以前，只有区段的最后一个文件是由importSharedAudience技术工作流导入的。
* AWS S3外部帐户现在支持地区和版本4身份验证机制。 请参阅 [详细文档](../../administration/using/external-accounts.md).
* 现在，资产选择窗口应该加载速度更快，并且允许选择资产，然后退出该窗口，而不会出现任何问题。
* 技术工作流的属性和结构现在可由具有管理权限且属于“所有”组织和地理单位的用户修改。
* 在创建新区段时，“分段”活动界面中增强了以下功能：现在，在添加限制后，“限制”选项卡会直接显示。 新区段的名称现在会递增（“区段1”、“区段2”等）。
* “nextProcessingDate”字段会添加到工作流资源中。 此字段仅通过REST API调用可见，它允许您将工作流的下一个处理日期可视化。
* “sourceId”字段现在显示在跟踪日志资源(nms:trackingLog)中。
* “打开总数”和“点击总数”值现在可以通过工作流在平面文件中导出。 (CAMP-24186)
* “英语 — Danmark”现在在用户档案的“首选语言”列表中提供。 (CAMP-23728)
* 现在，在将分段活动与附加数据(targetData)链接一起使用时，会出现一条消息，告知您该数据在工作流外部不可用。 单击分段活动中的计数或预览按钮时，将显示此消息。 (CAMP-23651)
* 已进行增强，以优化工作流使用的磁盘空间：(CAMP-21979):现在，默认情况下，“加载文件”活动处理的文件会被删除。 利用选项，可保留这些量度以满足特定需求。 删除工作流后，其专用文件夹将自动从服务器目录中禁止显示。

**修补程序**

* 修复了由于eventDate字段填充不正确，因此某些原始报表事件没有关联跟踪事件的问题。
* 修复了阻止在推送通知投放的预览窗口中显示个性化字段的问题。
* 修复了阻止文本在预览窗口中对推送通知的消息正文进行自动换行的问题。
* 修复了主目标为空时从工作流发送定期投放的问题。
* 修复了在目标映射链接到不存在的架构时无法访问该映射的问题。
* 修复了通过文件加载活动导入zip文件时可能发生的问题。 (CAMP-24309)
* 修复了在发送定期投放时导致PostgreSQL错误的问题。 (CAMP-23613)
* 修复了在发送具有空JSON属性的REST API请求时显示错误消息的问题。 (CAMP-23506)
* 修复了配置文件中“ß”字符后面的字符设置为大写的问题。 (CAMP-23136)
* 修复了在使用链接的用户档案架构中的属性发送与个性化或动态内容块的资格条件一起使用的投放时的问题。 (CAMP-22751)
* 修复了无法删除服务的问题。 (CAMP-22050)
* 修复了阻止更改测试用户档案中的国家/地区或州值的问题。 (CAMP-20426)
* 修复了可能会阻止加载Creative Designer的问题。 (CAMP-24573)
* 修复了删除在电子邮件主题的个性化字段后添加的字符的问题。 (CAMP-24113)

## 18.4 版 - 2018 年 4 月 {#release-18-4---april-2018}

**修补程序**

_平台_

* 修复了可能阻止正确处理GDPR访问或删除请求的错误。 在极少数情况下，如果提取的数据包含以下字符之一，则会观察到此行为：&amp; &lt; > &quot; &#39;。

_电子邮件、短信和直邮_

* 修复了在broadlog同步花费超过一小时时可能导致KPI被错误值覆盖的问题。

_工作流_

* 改进了内存管理并优化了工作流中的性能。

_报告_

* 现在，KPI共享工作流可检索过去2个月（而不是过去6个月）的交付值。 修复了KPI共享外部帐户时显示截断日期的问题。
* 修复了可能导致在 **已发送**, **已交付** 和 **跳出**&#x200B;量度。
* 修复了 **投放摘要报表** 太长了。

_自定义资源_

* 修复了导致自定义资源准备失败的错误。

## 18.3 版 - 2018 年 3 月 {#release-18-3---march-2018}

**新功能**

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 说明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 欧盟《通用数据保护条例》(GDPR)<br /> </td> 
   <td> GDPR是欧盟(EU)的新隐私法，旨在协调数据保护要求并使之现代化，于2018年5月25日正式生效。 GDPR 适用于所持有数据的数据主体位于欧盟的 Adobe Campaign 客户。<br /> 除了Adobe Campaign中已有的可用隐私功能（包括同意管理、数据保留设置和用户角色）之外，我们还将利用我们作为数据处理者的角色提供的这一机会，加入其他功能，以帮助您作为数据控制者为某些GDPR请求做好准备：<br /> 
    <ul> 
     <li> 访问权：允许数据主体接收其由数据控制者捕获的个人数据的副本，可能包括存储在Adobe Campaign中的数据。 </li> 
     <li> 删除权：授权数据主体擦除“数据控制者”捕获的个人数据，这可能包括存储在Adobe Campaign中的数据。 </li> 
    </ul> 有关更多信息，请参阅<a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Creative Designer for Email（测试版）<br /> </td> 
   <td> Adobe Campaign的新Creative Designer在Campaign中提供了完全集成的创作体验，从而快速轻松地直观创建引人入胜的个性化电子邮件，而无需编写一行代码。 无论用户是从头开始，还是利用现有内容片段或模板，Creative Designer都通过其强大的拖放界面帮助扩展电子邮件创建。 <br /> 主要功能包括：<br /> 
    <ul> 
     <li> 通过拖放界面以可视方式设计和创建完全个性化的响应式电子邮件，并通过本机Creative Cloud集成加以增强 </li> 
     <li> 创建和保存电子邮件内容模板并利用保存的模板来帮助扩展电子邮件创建 </li> 
     <li> 创建和保存内容片段（例如页眉、页脚、文章等） 简化内容创建过程，确保品牌一致性 </li> 
     <li> 在拖放界面中创建和单击按钮直接编辑电子邮件HTML之间无缝切换 </li> 
    </ul> 适用于电子邮件的Creative Designer仅提供英文版。<br /> 有关更多信息，请参阅 <a href="../../designing/using/designing-content-in-adobe-campaign.md">详细文档</a> 看这个 <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">视频</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 多语言推送投放<br /> </td> 
   <td> 电子邮件和短信渠道上已存在的相同简单多语言界面，已添加到推送渠道中，无论客户的首选语言如何，都可帮助您吸引客户。<br /> 对于管理跨多个区域的推送促销活动并希望以其首选语言定位用户的客户，此功能提供了一个可扩展且自动的解决方案。 它允许您通过模板电子表格将所有语言变体上传到单次推送投放，只需一次单击即可。 然后，Adobe Campaign会根据用户的语言首选项执行自动分段，从而通过简化工作流和报告来帮助减少冗余。<br /> 有关更多信息，请参阅 <a href="../../channels/using/creating-a-multilingual-push-notification.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 在事务型消息传递中使用自定义资源<br /> </td> 
   <td> 除了现成的字段外，事务型消息传递现在还允许您使用自定义资源来丰富消息的内容。<br />例如：<br /> 
    <ul> 
     <li> 利用自定义字段作为协调条件，将事务型消息与用户档案匹配 </li> 
     <li> 利用完整的用户档案、服务和链接数据进一步个性化事务型消息 </li> 
    </ul> 有关更多信息，请参阅<a href="../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* 修复了无法从列表导出5000条以上记录的问题。
* 修复了将数据导出到使用个性化字段命名的文件时的问题。

_电子邮件、短信和直邮_

* 修复了由于部分大小是以字符而不是字节计算，导致多部分短信被截断的问题。
* 添加了一个选项，该选项允许 **[!UICONTROL Delivered]** 或 **[!UICONTROL Bounces + Errors]** 在发送投放后要实时更新的KPI。 它们将根据从提供商收到的SR（状态报告）直接重新计算。
* 修复了投放计划程序中日历小组件的问题。
* 修复了在已发送投放中第二次打开目标时的显示问题。
* 修复了在创建发送日期延迟的电子邮件模板时，导致出现请求开始日期的错误消息的问题。
* 修复了在编辑投放的内容时可能导致图像呈现问题的问题。
* 修复了复制营销活动时校样出现的问题。
* 修复了在向工作流添加投放后，通过导航栏访问营销活动模板时导致出现错误消息的问题。
* 修复了可能阻止自动选择A/B测试电子邮件入选者，从而导致未发送电子邮件的问题。 如果投放位于 **[!UICONTROL retryInProgress]** 状态。
* 修复了在重新打开A/B测试电子邮件的参数时可能导致显示错误消息的问题。

_受众和查询_

* 修复了无法访问数据以及为从Adobe Campaign Classic复制到Standard的收件人设置查询的问题。
* 修复了在使用 **计数** 或 **预览** 按钮。

_工作流_

* 的 **帐单** 工作流已进行优化以改进投放准备延迟。
* 修复了在使用定期投放活动时阻止在叫客过渡中显示群体数据的问题。
* 修复了在 **更新数据** 活动。
* 修复了可能导致 **deliverabilityUpdate** 技术工作流失败。

_集成_

* 修复了无法将国际字符正确发送到Adobe Analytics的问题。
* 现在，在尝试从消息中的Experience Cloud资产库插入图像时，的加载速度应该会更快。
* 修复了在某些情况下可能阻止关闭资产选择窗口的问题。
* 现在，您可以从数据源详细信息中直接访问其相关的工作流，以检查工作流的状态。
* 现在，您可以在定义或编辑触发器事件时直接更新触发器架构。 在进行此更改后，您不再需要取消发布触发器并创建另一个触发器。

_事务性消息_

* 修复了扩展投放资源时事务型消息模板的错误。
* 现在可以删除事务型消息。

## 18.2 版 - 2018 年 2 月 {#release-18-2---february-2018}

**新功能**

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 说明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 订阅 — 为一系列用户档案订阅或退订多项服务<br /> </td> 
   <td> 的 <strong>订阅服务</strong> 现在，工作流活动允许您向多项服务订阅或取消订阅用户档案列表。 在工作流中，导入包含用户档案的文件，并针对每个用户档案、操作类型和服务导入文件。 的 <strong>订阅服务</strong> 活动将能够使用此信息并同时动态处理所有用户档案订阅和退订。<br /> 有关更多信息，请参阅 <a href="../../automating/using/subscription-services.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 扩充活动 — 根据以前的过渡扩充数据<br /> </td> 
   <td> 新 <span class="uicontrol">扩充</span> 利用工作流活动，可使用集客过渡并使用附加数据完成输出过渡。 如果您定向用户档案，利用扩充活动，可使用未存储在数据库中的附加数据（例如来自导入的文件）扩充用户档案信息。<br /> 有关更多信息，请参阅 <a href="../../automating/using/enrichment.md">详细文档</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* Adobe Campaign界面的顶部栏已更新为新的Experience Cloud菜单。
* 修复了阻止链接到 **[!UICONTROL Offers]** 从显示在解决方案下拉列表中。

_电子邮件、短信和直邮_

* 投放准备阶段已得到增强，以提高性能。
* 修复了可能导致跟踪日志在某些小众情况下损坏的几个问题。
* 修复了在投放准备和确认之间更改联系日期时发生的联系日期更新问题。 现在，当您在准备后更改联系日期时，您需要再次准备投放，然后才能确认发送。 请参阅 [详细文档](../../sending/using/preparing-the-send.md).

_推送通知_

* 修复了导致某些个性化字段无法在iOS推送通知中工作的错误。
* 修复了在推送通知功能板中将点击和打开率显示为0%的错误。

_报告_

* 修复了在某些浏览器中将报表列表显示为空的错误。
* 修复了 **[!UICONTROL Report sharing]** 技术工作流的过期时间限制。

_工作流_

* 修复了拖放活动后无法访问活动的问题。
* 修复了可能导致 **[!UICONTROL Segmentation]** 活动。
* 修复了读取包含枚举类型字段的受众以及之前从工作流中保存的受众时出现的错误
* 修复了导致 **[!UICONTROL Request confirmation before sending messages]** 选项，即使在定义在工作流中创建的投放的计划属性时取消选中它，该选项仍保持选中状态。
* 现在，可以在 **[!UICONTROL Query]** 活动，通过 **[!UICONTROL Additional data]** 选项卡。 出于性能原因，在定义多个（超过100个）其他元素时建议禁用此选项。

_集成_

* 对 **[!UICONTROL Data sources]** 配置屏幕。

_已知问题_

由于可能出现显示问题，我们建议您不要使用Internet Explorer版本11。

使用Campaign界面中的上下文帮助链接时，可能会出现一些问题。 它们将在18.3中修复。

## 18.1 版 - 2018 年 1 月 {#release-18-1---january-2018}

**新功能**

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 说明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 疲劳管理报告<br /> </td> 
   <td> 疲劳管理报告是一种专用的可配置报告，可显示疲劳规则对发送前指定日期范围内电子邮件、推送、短信和直邮渠道投放的影响。 通过增加在单个视图中快速查看所有冲突营销活动的洞察力，营销人员能够根据设置疲劳规则更有效地规划营销活动，并排定通信的优先级。<br /> 有关更多信息，请参阅 <a href="../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 报表共享<br /> </td> 
   <td> 通过报表共享，您可以将报表作为电子邮件附件（包括自动定期）与Adobe Campaign用户共享。 接收定期报告的用户能够通过每个电子邮件中的专用链接取消订阅这些通信。<br /> 有关更多信息，请参阅 <a href="../../reporting/using/reporting-interface.md#share-tab">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送新功能<br /> </td> 
   <td> 推送消息预览 — 在测试或执行投放之前，可从推送通知内容编辑器中预览iOS和Android设备上的推送通知，以准确查看收件人将看到的内容。<br />有关更多信息，请参阅<a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">详细文档</a>。<br /> 可用内容 — 如果应用程序较长时间未打开，应用程序中的数据可能会过期。 这会导致用户在最终打开应用程序时必须更新或替换数据，这可能会导致使用应用程序时出现延迟。 借助“可用内容”的新增支持，Adobe Campaign用户可以在发送推送通知时唤醒应用程序以在后台刷新其数据，从而提高用户应用程序内体验的一致性和控制力。<br /> 可变内容 — 通过增加的“可变内容”支持，Adobe Campaign用户现在可以利用其移动应用程序扩展进一步修改从Adobe Campaign发送的推送通知的内容或外观。 例如，用户可以利用可变内容： <br /> 
    <ul> 
     <li> 解密以加密格式传送的数据 </li> 
     <li> 下载图像或其他媒体文件，并将它们作为附件添加到通知中 </li> 
     <li> 更改通知的正文或标题文本 </li> 
     <li> 向通知添加线程标识符 </li> 
    </ul> 有关可用内容和可变内容的更多信息，请参阅 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">详细文档</a>.<br /> <strong>警告：</strong> 推送通知的这些更新要求客户升级其移动应用程序。 请参阅 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/push-payload.html">此技术说明</a> 以了解更多信息。<br /> </td> 
  </tr> 
  <tr> 
   <td> 时区优化投放<br /> </td> 
   <td> 将定期电子邮件、短信和推送通知安排在每个收件人时区的特定日/时间发送，以确保您的消息在正确的时间发送，而无需设置多次投放。 <br /> 有关更多信息，请参阅 <a href="../../automating/using/scheduler.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API信号活动触发<br /> </td> 
   <td> 现在，可以直接从Adobe Campaign Standard API触发工作流的信号活动。<br /> 有关更多信息，请参阅 <a href="/help/api/using/triggering-a-signal-activity.md">详细文档</a> .<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* 配置文件搜索已进行优化以提高性能。
* 默认安全组的内部标识符现在为标准用户的只读模式。

_电子邮件、短信和直邮_

* 修复了在投放内容中插入表情符号时出现的显示问题。
* 修复了当投放仍在版本中时允许用户访问发送日志的问题。
* 的 **[!UICONTROL Scheduler]** 活动现在允许您根据收件人的时区发送投放。
* 短信：选项 **[!UICONTROL Store incoming MO]** 已将数据库中的帐户添加到外部帐户。 选中此选项后，所有传入的短信都将存储到 **短信中** 表。
* 短信：现在，服务会附加到事件，而不是事务型模板。
* 短信：默认的SMTP连接超时已缩短为30秒。

_推送通知_

* 修复了阻止停止推送通知投放的错误。
* 在推送通知高级选项中添加了一个选项，用于通过推送通知唤醒应用程序。
* 为推送通知预览视频添加了暂停按钮。
* 推送通知预览现在可用于不同的设备，如iPhone、Android、平板电脑。

_报告_

* 修复了显示率超过100%的错误。
* 修复了阻止用户以CSV格式下载报表的问题。
* 添加了 **[!UICONTROL Report]** 项目。

_工作流_

* 修复了在查询中使用附加数据并添加包含空格的别名时导致出现错误消息的问题。 非字母数字字符现在由“_”替换。
* 修复了默认情况下，技术工作流可停止计算KPI的问题。

_用户档案和受众_

* 修复了在受众查询中添加多个过滤器时发生的错误。
* 修复了更改用户档案图片时出现的显示问题。
* 添加了工具提示，其中显示了在计算查询的群体后的确切结果编号。
* 修复了可能阻止用户选择受众或关闭受众选取器窗口的问题。
* 表达式编辑器中可用函数的列表已更新。 的 **FormatCurrency** 和 **ConvertCurrency** 函数已被删除。
