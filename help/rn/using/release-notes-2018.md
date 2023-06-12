---
title: 发行说明 2018
description: 本页列出了所有 2018 年版的 Adobe Campaign Standard。
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 17521357-14ae-4751-bd7c-aeabbcf71d07
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '5355'
ht-degree: 3%

---

# 发行说明 2018{#release-notes}

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
   <td> 应用程序内消息传递（测试版）<br /> </td> 
   <td> 应用程序内消息传送功能允许您提供上下文互动，并让您能够联系可能选择退出推送通知的用户，从而更有效地吸引移动应用程序用户。 将应用程序内消息传递与推送通知结合使用，以创建高度个性化的相关体验。 这可以提高应用程序用户的转化率和留存率。<br /> 欲了解更多信息，请参见 <a href="../../channels/using/about-in-app-messaging.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 适用于移动设备应用程序的AdobeLaunch集成（测试版）<br /> </td> 
   <td> 与Adobe Campaign集成的Adobe Launch现在使用Mobile SDK V5简化了Campaign中移动应用程序属性的激活过程并实现了自动化。<br /> 欲了解更多信息，请参见 <a href="https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdk.html">详细文档</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**改进**

* Adobe Campaign Standard现在支持版本4 Amazon S3 API。

**其他变更**

* 在broadlog中，最大连接数和每小时最大消息数之间现在有一个区别。 当达到这些限制时，就可以知道吞吐量为何受限。 以前，同一消息（“达到配额”）同时适用于这两种情况。
* 在Campaign中配置移动应用程序时，用户现在可以知道iOS证书和Android服务器密钥是否已成功上传及其到期日期。

   有关更多信息，请参阅有关如何使用配置移动应用程序的详细文档 [SDK V4](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdkv4.html) 和 [SDK V5](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdk.html).

* 在定义Campaign属性时，通过选择移动设备应用程序定位特定移动设备应用程序上的用户。 此功能适用于推送和应用程序内消息传送渠道。

   有关更多信息，请参阅[详细文档](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification)。

* 使用Creative Designer界面选择内容块时，现在将加载并显示列表中的所有内容块。 (CAMP-27311)

   有关详情，请参阅 [详细文档](../../designing/using/personalization.md#adding-a-content-block).

**修补程序**

* 修复了显示事务性电子邮件的电子邮件仪表板和电子邮件摘要报告之间的日志计数存在差异的问题。 (CAMP-28237
* 修复了在通过文件传输活动导入文件时工作流中可能显示错误消息的问题。 (CAMP-27435)
* 修复了包含超过25个服务的登陆页面导致在表单中随机取消选择服务的问题。 (CAMP-26572)
* 修复了在使用文件传输活动时，工作流中阻止使用SFTP URL配置外部帐户的问题。 (CAMP-26475)
* 修复了导致无法更新服务摘要报表的问题。 (CAMP-26301)
* 修复了在使用扩充活动时工作流中阻止自定义字段显示正确日期的问题。 (CAMP-26242)
* 修复了在通过文件导入导入时，无法更新服务订阅日期的问题。
* 修复了阻止工作流导入文件的加载文件活动错误(CAMP-27068)。
* 修复了在服务摘要报告中显示错误订阅数量的问题(CAMP-25587)。
* 修复了Adobe Analytics报表和Adobe Campaign报表之间数据不一致的问题。 (CAMP-25393)
* 修复了可能导致受限访问用户无法登录的问题。 (CAMP-27381)
* 修复了在使用Creative Designer编辑电子邮件时可能阻止显示Adobe Experience Manager内容列表的问题。 (CAMP-27181)
* 修复了可能阻止Creative Designer打开并导致错误的问题。 (CAMP-27304)
* 修复了在使用Internet Explorer 11时，拖放操作在Creative Designer中无法正常工作的问题。
* 修复了导致从相机上传并在纵向模式下拍摄的图片显示在不需要的旋转位置的问题。
* 修复了在Creative Designer中使用查询编辑器界面时显示不清楚选择信息的问题。
* 修复了在Creative Designer中使用查询编辑器界面时无法正确复制元素的问题。
* 修复了即使收件人已通过自动回复取消订阅，仍继续在阻止列表上向其投放短信消息的问题。 (CAMP-27128)
* 修复了导致无法显示错误的问题 **数据库清理** 工作流失败。 (CAMP-26876)
* 修复了可能阻止删除推送通知定义中自定义字段的问题。 (CAMP-25588)

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
   <td> Android的高优先级标记 — 为Android应用程序启用以高优先级投放推送通知的功能，这会导致休眠设备唤醒并运行一些有限处理。 请注意，默认优先级为“正常”，这可能会延迟消息发送以节省电池。 <br /> 欲了解更多信息，请参见 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 适用于移动应用程序订阅者的类型过滤器<br /> </td> 
   <td> 在分类过滤器支持订阅 — 为分类规则指定筛选条件时，可以选择应用程序订阅作为筛选和定位维度，从而提供对具有或不具有用户档案的用户的属性进行筛选的功能。 <br /> 欲了解更多信息，请参见 <a href="../../sending/using/about-typology-rules.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 在消息准备期间从URL自动导入内容<br /> </td> 
   <td> 现在，可以在准备阶段从URL导入电子邮件内容。 对于定期电子邮件投放，每次准备消息时都会检索最新的HTML内容，以确保在发送电子邮件时内容始终保持最新。 此功能还允许您通过URL中的内容创建计划投放，即使内容尚未准备就绪。<br /> 欲了解更多信息，请参见 <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Campaign发布通知消息<br /> </td> 
   <td> 当用户在实例升级到新版本后登录时，现在会显示弹出消息。 该消息指示版本号，并包含指向发行说明的链接。 您可以选择在下一个版本之前隐藏消息。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 用户管理<br /> </td> 
   <td> 从18.7版本开始，地理单位功能现在不适用于新的Campaign Standard实例，以及未创建地理单位的现有实例。<br /> 有关更多信息，请参阅此 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=zh-Hans#release-notes">页面</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**改进**

* Adobe Campaign和Adobe Target集成现在允许您利用Target的 [权限](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html) 功能。 现在，在电子邮件中包含Adobe Target中的动态图像时，您可以指定Target属性（at_property代码）。
* 现在，GDPR隐私访问/删除请求会考虑具有指向用户档案资源的owncopy链接的自定义资源。 对于1个基数简单链接和N个基数收集链接，您需要选择自定义资源中的“删除/复制目标记录意味着删除/复制链接引用的记录”。 对于0或1个基数简单链接，选择“删除/复制记录意味着删除/复制链接引用的目标记录”。

**其他变更**

* 报告共享超时已从1分钟增加到4分钟，以避免出现任何超时错误。
* 在编辑电子邮件的内容时，默认情况下会打开新的Creative Designer。 如果需要，您仍然可以在保存更改后随时返回默认内容编辑器。 有关详情，请参阅 [详细文档](../../designing/using/designing-content-in-adobe-campaign.md).
* 在Creative Designer中，现在可以向电子邮件中添加新的内容组件：轮盘。 有关详情，请参阅 [详细文档](../../designing/using/designing-from-scratch.md#about-content-components).
* 在事务型消息的热击报告中，当您单击 **更改配置文件** 按钮时，现在仅列出链接到为事务型消息定义的事件的测试用户档案。

**修补程序**

* 修复了byEmail查询过滤器无法返回任何结果的问题。 (CAMP-23420)
* 修复了允许标准用户访问仅限管理员使用的某些功能或屏幕的问题(/rest/head/&#42; 端点、事务性消息屏幕、用户档案和受众导入屏幕)。
* 修复了当自定义资源的名称以数字开头时，GDPR隐私删除请求无法处理该资源的问题。
* 修复了阻止“保存受众”活动在Adobe Experience Cloud中共享应用程序订阅者的错误。
* 修复了文件名包含空格时可能发生的文件传输活动问题。 (CAMP-25936)
* 修复了在会话过期后使用重新连接按钮时可能发生的问题。 (CAMP-25560)
* 修复了在发送具有与疲劳规则关联的时区优化的投放时可能导致排除的问题。 (CAMP-25425)
* 修复了使用API GDPR功能时，可能阻止删除具有0-1类型链接的数据的问题。
* 修复了在取消编辑疲劳分类规则时可能导致出现错误消息的问题。
* 修复了在编辑投放内容后预览该内容时可能发生的问题。
* 修复了在使用解压缩选项处理CSV zip文件时可能发生的问题。
* 修复了Creative Designer中的一个问题，在将一些具有内置样式的文本更改为链接或编辑该链接时，该问题会导致不想要的颜色字体和格式。 (CAMP-26001)
* 修复了导致热点击报告无法在包含动态内容的投放中显示每个条件的百分比的问题。 以前，仅显示对默认变体的点击。

## 18.6 版 - 2018 年 6 月 {#release-18-6---june-2018}

**改进**

* 此 **[!UICONTROL History]** API已添加到Adobe.IO。 它允许您访问与用户档案的营销历史相关的信息：接触点数量、已发送投放、镜像页面URL等。 有关详情，请参阅 [专用用例](../../api/using/interacting-with-marketing-history.md) .
* 此 **[!UICONTROL Database cleanup]** 技术工作流已得到优化，以确保数据库备份有更好的性能。
* Creative Designer for Email现在还提供法语和德语版。

**其他变更**

* A **[!UICONTROL Compute stats]** 按钮已添加到 **[!UICONTROL Deployment]** 已发送投放的窗口。 它允许您检索最新的KPI，例如，如果发送结果更新时间过长或未考虑在内。 有关更多信息，请参阅此](../../sending/using/confirming-the-send.md)章节[。
* 在 **可投放性更新** 开箱即用的技术工作流，功能管理员现在可以在 **更新规则** javascript活动。 默认情况下，字段值设置为0，这意味着将忽略所有错误。
* 已优化管理单元访问限制条件时生成的SQL。
* 此 **[!UICONTROL Update]** 活动现在允许您添加、更新或删除与订阅相关的数据（nms：appSubscriptionRcp表）。
* 此 **[!UICONTROL Update delivery execution]** 为了优化性能，已将技术工作流分为两个工作流： - **[!UICONTROL Update delivery execution]**：更新投放的跟踪。 默认情况下，每10分钟启动一次。 **[!UICONTROL Update delivery indicators]**：更新投放的KPI，默认情况下每小时启动一次。 有关技术工作流的详细信息，请参阅此 [部分](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* 当投放发送消息时，状态位于 **[!UICONTROL Deployment]** 部分现在可以具有两个值： **[!UICONTROL Sending]**：正在发送消息。 **[!UICONTROL Sending (retry)]**：正在执行重试过程。
* 具有的用户 **[!UICONTROL Delivery preparation]** 角色现在能够发送校样。 (CAMP-24313)
* 此 **通过SMPP启用TLS** 选项已添加到 **通过SMPP的短信路由** 外部帐户。 有关详细信息，请参阅此 [部分](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

**修补程序**

* 修复了在包含Adobe Target的动态图像时可能阻止发送电子邮件的问题(CAMP-24848)。
* 修复了的问题 **[!UICONTROL Privacy Access/Delete Request]** 技术工作流，如果任何请求失败，这些工作流将不会完成。
* 修复了阻止隐私核心服务从Campaign接收请求状态更新的问题。
* 修复了可能导致 **[!UICONTROL Import shared audience]** 技术工作流正常运行(CAMP-25465)。
* 修复了导致无法在核心Privacy Service中将Campaign隐私请求标记为已完成的问题。
* 修复了可能会阻止某些用户在Adobe ID过长时通过IMS身份验证登录Campaign Standard的问题。 (CAMP-24095)
* 修复了Creative Designer在删除内容模块时可能发生的问题。 (CAMP-25242)
* 修复了为数据库中没有用户档案的订阅者使用推送通知疲劳规则时的问题。 (CAMP-25344)
* 修复了在访问投放排除日志时可能显示错误消息的问题。 (CAMP-24724)
* 修复了阻止在具有扩展发送日志的实例中准备校样的问题。
* 修复了使用发布自定义资源时可能发生的两个问题 **[!UICONTROL Sending log]** 扩展已激活。
* 修复了在定期投放中未考虑投放持续时间的情况下可能发生的问题。
* 修复了对中的数据排序时可能发生的问题 **[!UICONTROL Client data]** 菜单，用于包含超过100,000条记录的自定义资源。 (CAMP-24308)
* 修复了在动态报告中使用搜索功能时未考虑的自定义用户档案维度问题。
* 修复了在动态报告中显示帐户级别的国际数据时存在的问题。
* 现在可以创建没有订阅或退订确认消息的服务。

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
   <td> GDPR：核心服务集成<br /> </td> 
   <td> 通过隐私核心服务集成，您可以通过单个JSON API调用在多解决方案上下文中自动处理GDPR请求。 <br /> 从Privacy Core Service推送到所有Experience Cloud解决方案的GDPR请求现在由Campaign自动处理。 <br /> 欲了解更多信息，请参见 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy.html">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送改进 — 详细的投放反馈<br /> </td> 
   <td> Adobe Campaign现在提供通过MCPNS从提供商(APNS/GCM)接收推送消息的详细反馈（发送日志和排除日志）的功能。<br /> 欲了解更多信息，请参见 <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放日志扩展<br /> </td> 
   <td> 通过投放日志扩展，您可以使用来自工作流的用户档案数据和区段代码来扩展发送日志。 然后，可在动态报告中使用此信息，并允许您在发送投放时保留某些信息的快照。<br /> 还有2个用例：<br /> 
    <ul> 
     <li> 导出包含“冻结”数据的扩展broadlog：作为营销人员，我希望导出区段代码等于“A”（来自工作流引擎）的所有用户档案。 </li> 
     <li> 对“冻结”数据进行分段：作为营销人员，我希望 <strong>重新定位</strong> 自上次发送后获得1000个忠诚度点数或区段代码等于“A”的所有用户档案。 </li> 
    </ul> 有关更多信息，请参阅<a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 使用自定义用户档案数据进行动态报告<br /> </td> 
   <td> 此功能允许您根据在配置文件资源扩展期间创建的自定义配置文件数据创建和管理报表。 您可以按用户档案属性（如忠诚度计划、首选渠道等）划分报表。<br /> 欲了解更多信息，请参见 <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">详细文档</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**改进**

* 应用程序的整体内存和CPU使用率已得到增强

**其他变更**

* “读取受众”工作流活动现在可以读取Experience Cloud受众。 以前，此活动只能读取“查询”和“列表”受众。 请参阅 [详细文档](../../automating/using/read-audience.md). (CAMP-23623)
* 默认共享数据源的标识符现在处于只读模式，无法再更改。 更改此标识符可能会导致与Experience Cloud共享受众时出现一些问题。
* 现在，从Audience Manager导入受众适用于拆分文件。 以前，importSharedAudience技术工作流只导入区段的最后一个文件。
* AWS S3外部帐户现在支持地区和版本4身份验证机制。 请参阅 [详细文档](../../administration/using/external-accounts.md).
* 现在，资源选择窗口应会加载得更快，并允许选择资源，然后退出窗口，而不会出现任何问题。
* 现在，具有管理权限且属于“全部”组织和地理单位的用户可以修改技术工作流的属性和结构。
* 创建新区段时，分段活动界面中已进行增强：添加限制后，现在会直接显示“限制”选项卡。 新区段的名称现在递增（“区段1”、“区段2”等）。
* “nextProcessingDate”字段已添加到工作流资源。 此字段仅通过REST API调用可见，允许您可视化工作流下一个处理日期。
* “sourceId”字段现在显示在跟踪日志资源(nms：trackingLog)中。
* 现在，可以通过工作流将“打开次数总计”和“点击次数总计”值导出到平面文件中。 (CAMP-24186)
* 用户档案的“首选语言”列表中现在提供了“英语 — Danmark”。 (CAMP-23728)
* 现在，使用带有附加数据(targetData)链接的分段活动时，会出现一条消息，告知您数据在工作流之外不可用。 单击分段活动中的计数或预览按钮时，将显示此消息。 (CAMP-23651)
* 已进行增强以优化工作流使用的磁盘空间： (CAMP-21979)：现在默认情况下会删除由“加载文件”活动处理的文件。 利用选项，可针对特定需求保留这些区段。 删除工作流时，其专用文件夹将自动从服务器目录中隐藏。

**修补程序**

* 修复了由于eventDate字段未正确填充，某些原始报告事件没有关联的跟踪事件的问题。
* 修复了阻止个性化字段显示在推送通知投放的预览窗口的问题。
* 修复了阻止文本在预览窗口中对推送通知的消息正文进行文字环绕的问题。
* 修复了在主目标为空时从工作流发送循环投放时出现的问题。
* 修复了当目标映射链接到不存在的架构时无法访问目标映射的问题。
* 修复了通过文件加载活动导入zip文件时可能发生的问题。 (CAMP-24309)
* 修复了在发送定期投放时导致出现PostgreSQL错误的问题。 (CAMP-23613)
* 修复了在发送具有空JSON属性的REST API请求时显示错误消息的问题。 (CAMP-23506)
* 修复了配置文件中的一个问题，该问题将设置为大写“ß”字符后面的字符。 (CAMP-23136)
* 修复了在发送与个性化或动态内容块的资格条件一起使用的投放时，同时使用来自用户档案链接架构的属性的问题。 (CAMP-22751)
* 修复了无法删除服务的问题。 (CAMP-22050)
* 修复了阻止更改测试用户档案中的国家/地区或州值的问题。 (CAMP-20426)
* 修复了可能阻止Creative Designer加载的问题。 (CAMP-24573)
* 修复了删除在电子邮件主题中的个性化字段后添加的字符的问题。 (CAMP-24113)

## 18.4 版 - 2018 年 4 月 {#release-18-4---april-2018}

**修补程序**

_平台_

* 修复了可能阻止正确处理GDPR访问或删除请求的错误。 在某些极少数情况下，当提取的数据包含以下字符之一时，会出现此行为： &amp; &lt; > &quot; &#39;。

_电子邮件、短信消息和直邮_

* 修复了当broadlog同步时间超过一小时时可能导致KPI被错误值覆盖的问题。

_工作流_

* 改进了内存管理，优化了工作流中的性能。

_报告_

* KPI共享工作流现在检索过去2个月（而非过去6个月）的投放值。 修复了KPI共享外部帐户时显示截断日期的问题。
* 修复了可能导致某些邮件在中未被考虑的问题 **已发送**， **已投放** 和 **跳出**&#x200B;量度。
* 修复了当所选时间范围位于 **投放摘要报告** 太长了。

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
   <td> 欧盟通用数据保护条例(GDPR)<br /> </td> 
   <td> GDPR是欧盟(EU)的新隐私法，旨在协调数据保护要求并使之现代化，于2018年5月25日生效。 GDPR 适用于所持有数据的数据主体位于欧盟的 Adobe Campaign 客户。<br /> 除了Adobe Campaign中已有的可用隐私功能（包括同意管理、数据保留设置和用户角色）之外，我们还将以数据处理方的角色利用此机会来包含其他功能，以帮助您作为数据控制方为特定GDPR请求做好准备：<br /> 
    <ul> 
     <li> 访问权：允许数据主体接收其由数据控制者捕获的个人数据的副本，可能包括存储在Adobe Campaign中的数据。 </li> 
     <li> 删除权：允许数据主体擦除其由数据控制者捕获的个人数据，可能包括存储在Adobe Campaign中的数据。 </li> 
    </ul> 有关更多信息，请参阅<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy.html">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 适用于电子邮件的Creative Designer （测试版）<br /> </td> 
   <td> Adobe Campaign的全新Creative Designer在Campaign中提供了完全集成的创建体验，允许快速轻松地创建引人入胜的个性化电子邮件，而无需编写一行代码。 通过其强大的拖放界面，无论用户是从空白板开始，还是利用现有的内容片段或模板，Creative Designer都可以帮助扩展电子邮件创建。 <br /> 主要功能包括：<br /> 
    <ul> 
     <li> 通过拖放界面设计和创建完全个性化、响应式电子邮件，并通过本机Creative Cloud集成加以增强 </li> 
     <li> 创建和保存电子邮件内容模板，并利用保存的模板帮助扩展电子邮件的创建 </li> 
     <li> 创建和保存内容片段（如页眉、页脚、文章等） 以简化内容创建并确保品牌一致性 </li> 
     <li> 在拖放界面中创建和单击按钮直接编辑电子邮件的HTML之间无缝切换 </li> 
    </ul> Creative Designer for Email仅提供英语版。<br /> 欲了解更多信息，请参见 <a href="../../designing/using/designing-content-in-adobe-campaign.md">详细文档</a> 看这个 <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">视频</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 多语言推送投放<br /> </td> 
   <td> 电子邮件和短信渠道中已存在的相同简单多语言界面已添加到推送渠道中，可帮助您吸引客户，而不论其首选语言为何。<br /> 此功能为那些管理跨多个区域的推送营销活动并希望以用户的首选语言定位用户的客户提供了一个可扩展的自动化解决方案。 它允许您只需单击一下，即可通过模板电子表格将所有语言变体上传到单次推送投放中。 然后，Adobe Campaign会根据用户的语言偏好执行自动分段，通过简化工作流和报表来帮助减少冗余。<br /> 欲了解更多信息，请参见 <a href="../../channels/using/creating-a-multilingual-push-notification.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 在事务性消息传递中使用自定义资源<br /> </td> 
   <td> 除了开箱即用字段外，事务型消息传递现在还允许您使用自定义资源来扩充消息的内容。<br />例如：<br /> 
    <ul> 
     <li> 利用自定义字段作为协调条件，将事务型消息与用户档案进行匹配 </li> 
     <li> 利用完整的用户档案、服务和链接的数据进一步个性化事务型消息 </li> 
    </ul> 有关更多信息，请参阅<a href="../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* 修复了阻止从列表中导出5000多条记录的问题。
* 修复了将数据导出到使用个性化字段命名的文件时的问题。

_电子邮件、短信消息和直邮_

* 修复了导致多部分SMS被截断的问题，因为部分大小是以字符而不是字节计算的。
* 添加了一个选项，该选项允许 **[!UICONTROL Delivered]** 或 **[!UICONTROL Bounces + Errors]** 发送投放后要实时更新的KPI。 它们直接从从提供商收到的SR（状态报告）重新计算。
* 修复了投放计划程序中的日历小部件问题。
* 修复了在已发送投放中第二次打开目标时的显示问题。
* 修复了在创建具有延迟发送日期的电子邮件模板时，导致出现请求开始日期的错误消息的问题。
* 修复了在编辑投放内容时可能导致图像渲染问题的问题。
* 修复了复制营销活动时验证的问题。
* 修复了在将投放添加到工作流后，通过导航栏访问活动模板时导致出现错误消息的问题。
* 修复了可能会阻止自动选择A/B测试电子邮件的入选者，从而导致未发送电子邮件的问题。 如果投放处于 **[!UICONTROL retryInProgress]** 省/州。
* 修复了在重新打开A/B测试电子邮件的参数时可能导致出现错误消息的问题。

_受众和查询_

* 修复了无法访问数据以及为从Adobe Campaign Classic复制到Standard的收件人设置查询的问题。
* 修复了在使用之后，在查询编辑器中使用过滤器类型字段时发生的问题 **计数** 或 **预览** 按钮。

_工作流_

* 此 **计费** 工作流已得到优化，以改善投放准备延迟。
* 修复了在使用循环投放活动时，阻止在叫客过渡中显示群体数据的问题。
* 修复了导致拒绝记录无法在之后的过渡中显示的问题。 **更新数据** 活动。
* 修复了可能导致 **deliverabilityUpdate** 技术工作流失败。

_集成_

* 修复了阻止将国际字符正确发送到Adobe Analytics的问题。
* 尝试在消息中插入Experience Cloud资源库中的图像时，资源现在应会加载得更快。
* 修复了在某些情况下可能阻止关闭资产选择窗口的问题。
* 现在，您可以从数据源详细信息直接访问其相关工作流以检查工作流的状态。
* 现在，您可以在定义或编辑触发器事件时直接更新触发器模式。 通过这项更改，您不再需要取消发布触发器并创建另一个触发器。

_事务性消息_

* 修复了扩展投放资源时事务性消息模板出现的错误。
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
   <td> 订阅 — 为用户档案列表订阅或退订多项服务<br /> </td> 
   <td> 此 <strong>订阅服务</strong> 工作流活动现在允许您订阅或取消订阅多个服务的用户档案列表。 在工作流中，导入一个包含用户档案的文件，并为每个用户档案、操作类型和服务。 此 <strong>订阅服务</strong> 活动将能够使用此信息并动态地同时处理您所有用户档案的订阅和退订。<br /> 欲了解更多信息，请参见 <a href="../../automating/using/subscription-services.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 扩充活动 — 根据先前的过渡扩充数据<br /> </td> 
   <td> 新 <span class="uicontrol">扩充</span> 利用工作流活动，可使用集客过渡并使用其他数据完成输出过渡。 如果您定向用户档案，则扩充活动允许您使用未存储在数据库中的附加数据（例如，来自导入的文件）扩充用户档案信息。<br /> 欲了解更多信息，请参见 <a href="../../automating/using/enrichment.md">详细文档</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* Adobe Campaign界面的顶栏已更新为新的Experience Cloud菜单。
* 修复了阻止链接到的问题 **[!UICONTROL Offers]** 从“解决方案”下拉列表中显示出来。

_电子邮件、短信消息和直邮_

* 增强了投放准备阶段以提高性能。
* 修复了在某些小范围情况下可能导致跟踪日志损坏的几个问题。
* 修复了在投放准备和确认之间更改联系日期时发生的联系日期更新问题。 现在，当您在准备后更改联系日期时，需要再次准备投放才能确认发送。 请参阅 [详细文档](../../sending/using/preparing-the-send.md).

_推送通知_

* 修复了导致某些个性化字段无法在iOS推送通知中工作的错误。
* 修复了在推送通知仪表板中将点击率和打开率显示为0%的错误。

_报告_

* 修复了在某些浏览器中将报表列表显示为空的错误。
* 修复了中发生的错误 **[!UICONTROL Report sharing]** 技术工作流。

_工作流_

* 修复了在拖放活动后无法访问活动的问题。
* 修复了可能导致的输出转换顺序的问题 **[!UICONTROL Segmentation]** 活动更改。
* 修复了读取包含枚举类型字段且之前已从工作流中保存的受众时发生的错误
* 修复了导致 **[!UICONTROL Request confirmation before sending messages]** 选项，以便在定义在工作流中创建的投放的计划属性时，即使在取消选中该选项后也保持选中状态。
* 现在可以在中禁用自动删除重复行（DISTINCT子句） **[!UICONTROL Query]** 活动，通过位于 **[!UICONTROL Additional data]** 选项卡。 出于性能原因，建议在定义许多（超过100个）其他元素时禁用此选项。

_集成_

* 我们改进了 **[!UICONTROL Data sources]** 配置屏幕。

_已知问题_

由于可能出现的显示问题，我们建议您不要使用Internet Explorer版本11。

从Campaign界面使用上下文帮助链接时，可能会出现一些问题。 将在18.3中修复它们。

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
   <td> 疲劳管理报告是一个专用的可配置报告，可显示疲劳规则在发送前的指定日期范围内对电子邮件、推送、短信和直邮渠道中的投放产生的影响。 借助能够在一个视图中快速查看所有冲突营销活动的额外洞察，营销人员能够更有效地根据设置疲劳规则来计划营销活动，并优先考虑通信。<br /> 欲了解更多信息，请参见 <a href="../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 报告共享<br /> </td> 
   <td> 通过报表共享，您可以将报表作为电子邮件附件与Adobe Campaign用户共享，包括自动循环。 接收定期报告的用户能够通过每封电子邮件中的专用链接取消订阅这些通信。<br /> 欲了解更多信息，请参见 <a href="../../reporting/using/reporting-interface.md#share-tab">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送新功能<br /> </td> 
   <td> 推送消息预览 — 在测试或执行投放之前，可从推送通知内容编辑器中预览iOS和Android设备上的推送通知，以精确地查看接收人将要看到的内容。<br />有关更多信息，请参阅<a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">详细文档</a>。<br /> 可用内容 — 如果应用程序较长时间未打开，应用程序中的数据可能会过期。 这导致在用户最终打开应用程序时必须更新或替换数据，这可能会导致使用应用程序时出现延迟。 通过增加的“可用内容”支持，Adobe Campaign用户可以在提交推送通知时唤醒其应用程序，以便在后台刷新其数据，从而增强对用户应用程序内体验的一致性和控制。<br /> 可变内容 — 通过增加的“可变内容”支持，Adobe Campaign用户现在可以利用其移动应用程序扩展，进一步对接收到的来自Adobe Campaign的推送通知进行内容或外观上的修改。 例如，用户可以利用可变内容执行以下操作： <br /> 
    <ul> 
     <li> 解密以加密格式传送的数据 </li> 
     <li> 下载图像或其他媒体文件，并将它们作为附件添加到通知中 </li> 
     <li> 更改通知的正文或标题文本 </li> 
     <li> 向通知添加线程标识符 </li> 
    </ul> 有关可用内容和可变内容的更多信息，请参阅 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">详细文档</a>.<br /> <strong>警告：</strong> 这些推送通知更新要求客户升级其移动应用程序。 请参阅 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/push-payload.html">此技术说明</a> 了解更多信息。<br /> </td> 
  </tr> 
  <tr> 
   <td> 时区优化投放<br /> </td> 
   <td> 安排在每个收件人的时区中的特定日期/时间发送定期电子邮件、短信和推送通知，以确保在不设置多个投放的情况下，在正确的时间发送消息。 <br /> 欲了解更多信息，请参见 <a href="../../automating/using/scheduler.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API信号活动触发<br /> </td> 
   <td> 现在，可以直接从Adobe Campaign Standard API触发工作流的信号活动。<br /> 欲了解更多信息，请参见 <a href="/help/api/using/triggering-a-signal-activity.md">详细文档</a> .<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* 配置文件搜索已优化以提高性能。
* 对于标准用户，默认安全组的内部标识符现在处于只读模式。

_电子邮件、短信消息和直邮_

* 修复了在投放内容中插入表情符号时发生的显示问题。
* 修复了允许用户在投放仍处于编辑状态时访问发送日志的问题。
* 此 **[!UICONTROL Scheduler]** 活动现在允许您根据收件人的时区发送投放。
* 短信：选项 **[!UICONTROL Store incoming MO]** 数据库中已添加到外部帐户。 选中后，所有传入的短信都将存储在 **inSMS** 表格。
* 短信：服务现在附加到事件，而不是事务型模板。
* 短信：默认SMTP连接超时已缩短到30秒。

_推送通知_

* 修复了阻止推送通知投放停止的错误。
* 在推送通知高级选项中添加了一个选项，用于通过推送通知唤醒应用程序。
* 为推送通知预览视频添加了暂停按钮。
* 推送通知预览现在适用于各种设备，例如iPhone、Android、平板电脑。

_报告_

* 修复了显示超过100%的费率的错误。
* 修复了阻止用户以CSV格式下载报表的问题。
* 添加了一个新的 **[!UICONTROL Report]** 项目。

_工作流_

* 修复了在查询中使用其他数据并添加包含空格的别名时导致出现错误消息的问题。 非字母数字字符现已替换为“_”。
* 修复了在某些情况下可能默认停止计算KPI的技术工作流的问题。

_用户档案和受众_

* 修复了在受众查询中添加多个过滤器时发生的错误。
* 修复了在更改用户档案图片时发生的显示问题。
* 添加了一个工具提示，在计数查询的群体后显示准确的结果编号。
* 修复了可能阻止用户选择受众或关闭受众选取器窗口的问题。
* 表达式编辑器中的可用函数列表已更新。 此 **格式货币** 和 **ConversionCurrency** 函数已被删除。
