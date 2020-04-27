---
title: 发行说明 2018
description: 本页列表了所有2018版Adobe Campaign标准版。
page-status-flag: never-activated
uuid: 99f92a54-4b3d-48b9-b08d-e98b24e75f62
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: e54f8305-7e32-4193-8e5a-b5d87b03038c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ffdbeb7031697c7b00edc658096f55df815b0f63

---


# 发行说明 2018{#release-notes}

是否正在寻找2018年发布的Adobe Campaign标准版？

每个版本都提供新功能和修补程序。 单击某个版本可视图其内容。

视图最新 [的Adobe Campaign](../../rn/using/documentation-updates.md) Standard文档更新。 如果要寻找较新的版本，请查阅此 [页](../../rn/using/release-notes.md)。

## 18.9版- 2018年9月 {#release-18-9---september-2018}

**新增内容?**

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
   <td> 应用程序内消息传递允许您通过提供上下文交互和触及可能已选择退出推送通知的用户，更有效地吸引移动应用程序用户。 将应用程序内消息传递与推送通知结合使用，以创建高度个性化的相关体验。 这可以提高App用户的转化率和保留率。<br /> 有关详细信息，请参阅详 <a href="../../channels/using/about-in-app-messaging.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 适用于移动应用程序的Adobe Launch集成（测试版）<br /> </td> 
   <td> Adobe Launch与Adobe Campaign的集成现在使用Mobile SDK V5简化和自动化了活动中移动应用程序属性激活的过程。<br /> 有关详细信息，请参阅详 <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**改进**

* Adobe Campaign标准版现在支持Amazon S3 API的版本4。

**其他更改**

* 在广播中，现在可以区分每小时最大连接数和最大消息数。 当达到这些限制时，可以知道为什么吞吐量有限。 以前，两种情况都使用相同的消息（“配额满足”）。
* 在活动中配置手机应用程序时，用户现在可以知道iOS证书和Android服务器密钥是否已成功上传及其过期日期。

   有关详细信息，请参阅有关如何使用 [SDK V4和](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) SDK V5配置移动应用程序的详细文档 [](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)。

* 在定义目标属性时，通过选择移动应用程序，在特定移动应用程序上活动用户。 此功能适用于推送和应用程序内消息传递渠道。

   有关详细信息，请参阅详 [细文档](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification)。

* 当使用Creative Designer界面选择内容块时，现在将加载并显示列表中的所有内容块。 (CAMP-27311)

   有关详细信息，请参阅详细 [文档](../../designing/using/personalization.md#adding-a-content-block)。

**修补程序**

* 修复了电子邮件仪表板与交易电子邮件的电子邮件摘要报告之间日志计数不一致的问题。 (CAMP-28237)
* 修复了工作流中的一个问题，该问题导致在通过文件传输活动导入文件时可能显示错误消息。 (CAMP-27435)
* 修复了包含超过25项服务的登陆页导致在表单中随机取消选择服务的问题。 (CAMP-26572)
* 修复了工作流中的一个问题，该问题导致在使用文件传输活动时无法使用SFTP URL配置外部帐户。 (CAMP-26475)
* 修复了无法更新服务摘要报告的问题。 (CAMP-26301)
* 修复了使用工作流活动时，自定义字段无法显示正确日期的问题。 (CAMP-26242)
* 修复了通过文件导入导入时无法更新服务订阅日期的问题。
* 修复了加载文件活动导致工作流无法导入文件的错误(CAMP-27068)。
* 修复了在服务摘要报告中显示错误订阅数的问题(CAMP-25587)。
* 修复了Adobe Analytics和Adobe Campaign报告之间的数据不一致问题。 (CAMP-25393)
* 修复了阻止受限访问用户登录的问题。 (CAMP-27381)
* 修复了在使用Creative Designer编辑电子邮件时，可能无法显示Adobe Experience Manager内容的列表的问题。 (CAMP-27181)
* 修复了可能阻止Creative Designer打开并导致错误的问题。 (CAMP-27304)
* 修复了在使用Internet Explorer 11时，拖放在Creative Designer中无法正确工作的问题。
* 修复了一个问题，该问题导致从相机上传的照片以及以纵向模式拍摄的照片在不需要的旋转位置显示。
* 修复了在Creative Designer中使用查询编辑器界面时显示选择信息不明确的问题。
* 修复了在Creative Designer中使用查询编辑器界面时无法正确复制元素的问题。
* 修复了一个问题，该问题导致即使已列入黑名单收件人已通过自动回复取消订阅，仍然会向这些用户发送SMS消息。 (CAMP-27128)
* 修复了阻止显示导致“数据库清除”工作流失 **败的错误** 的问题。 (CAMP-26876)
* 修复了一个问题，该问题可能会阻止删除推送通知定义中的自定义字段。 (CAMP-25588)

## 18.7版- 2018年7月 {#release-18-7---july-2018}

**新增内容?**

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
   <td> Android的高优先级标志——支持为Android应用程序提供高优先级的推送通知，这会导致休眠设备唤醒并运行一些有限的处理。 请注意，默认优先级为“正常”，这可能会延迟消息投放以节省电池。 <br /> 有关详细信息，请参阅详 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 针对移动App用户的排版过滤器<br /> </td> 
   <td> 支持排版订阅筛选——在为类型规则指定筛选条件时，可以选择应用程序订阅作为筛选和定位维度，从而为具有或没有用户档案的用户提供筛选属性的能力。 <br /> 有关详细信息，请参阅详 <a href="../../sending/using/about-typology-rules.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 在准备消息期间从URL自动导入内容<br /> </td> 
   <td> 现在，可以在准备阶段从URL导入电子邮件内容。 对于重复的电子邮件投放，每次准备消息时都会检索最新的HTML内容，确保内容在发送电子邮件时始终处于最新状态。 此功能还允许您创建包含URL中内容的预定交付，即使该内容尚未准备好。<br /> 有关详细信息，请参阅详 <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 活动发布通知消息<br /> </td> 
   <td> 现在，当用户在实例升级到新版本后登录时，会显示一条弹出消息。 该消息指示版本号，并包含指向发行说明的链接。 您可以选择在下一个版本之前隐藏消息。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 用户管理<br /> </td> 
   <td> 从18.7版本开始，新Campaign Standard实例以及没有创建地理单位的现有实例现在都无法使用地理单位功能。<br /> 有关详细信息，请参阅本 <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">页</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**改进**

* Adobe Campaign和Adobe目标集成现在允许您利用目标的“权限” [功能](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html) 。 在电子邮件中包含Adobe目标的动态图像时，您现在可以指定目标属性（at_property代码）。
* 具有指向用户档案资源的下载链接的自定义资源现在由GDPR隐私访问／删除请求考虑。 对于1个基数简单链接和N个基数集合链接，您需要在自定义资源中选择“删除／复制目标记录意味着删除／复制链接引用的记录”。 对于0或1基数简单链接，选择“删除／复制记录意味着删除／复制链接引用的目标记录”。

**其他更改**

* 报告共享超时时间已从1分钟增加到4分钟，以避免任何超时错误。
* 编辑电子邮件内容时，默认情况下会打开新的Creative Designer。 如果需要，您仍可以在保存更改后随时返回默认内容编辑器。 有关详细信息，请参阅详细 [文档](../../designing/using/designing-content-in-adobe-campaign.md)。
* 在Creative Designer中，现在可以向电子邮件中添加新内容组件：轮盘。 有关详细信息，请参阅详细 [文档](../../designing/using/designing-from-scratch.md#about-content-components)。
* 在事务性消息热点单击报告中，单击“ **Change用户档案** ”按钮时，现在仅列出链接到您为事务性消息定义的事件的测试用户档案。

**修补程序**

* 修复了byEmail查询过滤器无法返回任何结果的问题。 (CAMP-23420)
* 修复了允许标准用户访问受限于管理员的特定功能或屏幕(/rest/head/*端点、交易消息屏幕、用户档案和受众导入屏幕)的问题。
* 修复了在GDPR隐私删除请求的名称以数字开头时，该请求无法处理自定义资源的问题。
* 修复了“保存受众”活动无法在Adobe Experience Cloud中共享应用程序订阅者的错误。
* 修复了文件名包含空格时可能出现的“文件传输活动”问题。 (CAMP-25936)
* 修复了在会话过期后使用重新连接按钮时可能发生的问题。 (CAMP-25560)
* 修复了在发送与疲劳规则关联的时区优化投放时，可能导致排除的问题。 (CAMP-25425)
* 修复了使用API GDPR功能时，可能无法使用0-1类型链接删除数据的问题。
* 修复了在取消疲劳类型规则版本时可能导致错误消息的问题。
* 修复了在编辑投放内容后预览该内容时可能发生的问题。
* 修复了在使用解压缩选项处理CSV zip文件时可能发生的问题。
* 修复了Creative Designer中的一个问题，该问题导致使用内置样式将某些文本更改为链接或编辑该链接时，出现不需要的颜色字体和格式。 (CAMP-26001)
* 修复了导致热点单击报告无法在包含动态内容的投放中显示每个条件的百分比的问题。 以前，只显示对默认变体的单击。

## 18.6版- 2018年6月 {#release-18-6---june-2018}

**改进**

* 该 **[!UICONTROL History]** API已添加到Adobe.IO。 它允许您访问与用户档案营销历史相关的信息：接触点数、已发送投放、镜像页面URL等。 有关详细信息，请参阅专 [用用例](../../api/using/interacting-with-marketing-history.md) 。
* 为了 **[!UICONTROL Database cleanup]** 确保数据库备份的更好性能，已优化了技术工作流程。
* Creative Designer for Email现在也提供法语和德语版。

**其他更改**

* 已 **[!UICONTROL Compute stats]** 在已发送投放的窗 **[!UICONTROL Deployment]** 口中添加按钮。 它允许您检索最新的KPI，例如，如果发送结果的更新时间过长或未考虑到这些结果。 For more on this, refer to this [section](../../sending/using/confirming-the-send.md).
* 在开箱 **即用的技术工作流程中** ，功能管理员现在可以定义更新规则javascript活动中要忽略的连续错误数 **** 。 默认情况下，字段值设置为0，这意味着将忽略所有错误。
* 在管理单元访问限制条件时生成的SQL已得到优化。
* 该 **[!UICONTROL Update]** 活动现在允许您添加、更新或删除与订阅相关的数据（nms:appSubscriptionRcp表）。
* 为了 **[!UICONTROL Update delivery execution]** 优化性能，将技术工作流分为两个工作流:- **[!UICONTROL Update delivery execution]**:更新投放的跟踪。 默认情况下，每10分钟启动一次。 **[!UICONTROL Update delivery indicators]**:更新投放的KPI，默认情况下每小时启动一次。 For more on technical workflows, refer to this [section](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* 当投放发送消息时，部分中的状 **[!UICONTROL Deployment]** 态现在可以具有两个值： **[!UICONTROL Sending]**:正在发送消息。 **[!UICONTROL Sending (retry)]**:重试通过正在进行中。
* 具有该角 **[!UICONTROL Delivery preparation]** 色的用户现在可以发送验证。 (CAMP-24313)
* 通过 **SMPP路由** , SMPP外部帐户中已添加了“通过SMPP启用TLS **** ”选项。 For more on this refer to this [section](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

**修补程序**

* 修复了在包含来自Adobe目标的动态图像时，可能无法发送电子邮件的问题(CAMP-24848)。
* 修复了技术工作流的 **[!UICONTROL Privacy Access/Delete Request]** 问题，如果任何请求失败，则该问题将未完成。
* 修复了隐私核心服务无法接收请求状态更新的活动问题。
* Fixed an issue which could prevent the **[!UICONTROL Import shared audience]** technical workflow from working properly (CAMP-25465).
* 修复了在核心隐私服务中无法将活动隐私请求标记为已完成的问题。
* 修复了在Adobe ID过长时，某些用户无法通过IMS身份验证登录Campaign Standard的问题。 (CAMP-24095)
* 修复了Creative Designer中删除内容模块时可能出现的问题。 (CAMP-25242)
* 修复了在数据库中没有用户档案的订阅者使用推送通知疲劳规则的问题。 (CAMP-25344)
* 修复了在访问投放排除日志时可能显示错误消息的问题。 (CAMP-24724)
* 修复了在具有扩展发送日志的实例中阻止准备验证的问题。
* 修复了在激活扩展的情况下发布自定义资源时可能发生 **[!UICONTROL Sending log]** 的两个问题。
* 修复了在重复投放中未考虑投放持续时间时可能发生的问题。
* 修复了对具有100K以上记录的自定义资源在菜 **[!UICONTROL Client data]** 单中对数据排序时可能发生的问题。 (CAMP-24308)
* 修复了在动态报表中使用搜索功能时未考虑的自定义用户档案维度问题。
* 修复了在动态报表中显示帐户级别的国际数据的问题。
* 现在，无需订阅或退订确认消息即可创建服务。

## 版本18.5 - 2018年5月 {#release-18-5---may-2018}

**新增内容?**

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
   <td> 隐私核心服务集成允许您通过单个JSON API调用在多解决方案环境中自动执行GDPR请求。 <br /> 从隐私核心服务推送到所有Experience Cloud解决方案的GDPR请求现在由活动自动处理。 <br /> 有关详细信息，请参阅详 <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送改进——详细的投放反馈<br /> </td> 
   <td> Adobe Campaign现在提供通过MCPNS从提供商(APNS/GCM)接收推送消息的详细反馈（发送日志和排除日志）的功能。<br /> 有关详细信息，请参阅详 <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放日志扩展<br /> </td> 
   <td> 投放日志扩展允许您扩展发送日志，其中包含来自工作流的用户档案数据和段代码。 此信息随后可用于动态报表，并允许您在投放发送时保留某些信息的快照。<br /> 还有2个用例：<br /> 
    <ul> 
     <li> 导出包含“冻结”数据的扩展广播：作为营销人员，我希望导出段代码等于“A”的所有用户档案(来自工作流引擎)。 </li> 
     <li> 对“冻结”数据进行细分：作为营销人员，我希望重新定 <strong>位</strong> ，自上次发送以来或段代码等于“A”时已赢得1000个忠诚度积分的所有用户档案。 </li> 
    </ul> 有关详细信息，请参阅详 <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 使用自定义报告数据进行动态用户档案<br /> </td> 
   <td> 此功能允许您根据在用户档案资源扩展期间创建的自定义用户档案数据创建和管理报告。 您可以按用户档案属性(如忠诚度项目、首选渠道等)划分报表。<br /> 有关详细信息，请参阅详 <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**改进**

* 应用程序的总内存和CPU使用已得到增强

**其他更改**

* 阅读受众工作流活动现在可以阅读Experience Cloud受众。 以前，本活动只能阅读查询和列表受众。 请参阅详细 [文档](../../automating/using/read-audience.md)。 (CAMP-23623)
* 默认共享数据源的标识符现在处于只读模式，不再可以更改。 在与Experience Cloud共享受众时，更改此标识符可能会导致一些问题。
* 从受众管理器导入受众现在可以处理拆分文件。 以前，只有区段的最后一个文件是由importSharedAudience技术工作流导入的。
* AWS S3外部帐户现在支持区域和版本4身份验证机制。 请参阅详细 [文档](../../administration/using/external-accounts.md)。
* 现在，资产选择窗口的加载速度应更快，并且允许选择资产，然后退出窗口而不会出现任何问题。
* 技术工作流的属性和结构现在可由具有管理权限且属于“全部”组织和地理单位的用户修改。
* 在创建新区段时，分段活动界面中已进行了增强：现在，在添加限制后直接显示“限制”选项卡。 新区段的名称现已递增（“区段1”、“区段2”等）。
* “nextProcessingDate”字段将添加到工作流资源。 此字段仅通过REST API调用可见，它允许您可视化工作流的下一个处理日期。
* “sourceId”字段现在显示在跟踪日志资源(nms:trackingLog)中。
* “总打开次数”和“总点击次数”值现在可通过工作流在平面文件中导出。 (CAMP-24186)
* “英语- Danmark”现在在用户档案的“首选语言”列表中提供。 (CAMP-23728)
* 当将分段活动与附加数据(targetData)链接一起使用时，现在会显示一条消息，通知您该数据在工作流之外不可用。 单击分段活动中的计数或预览按钮时，将显示此消息。 (CAMP-23651)
* 已进行增强以优化工作流使用的磁盘空间：(CAMP-21979):现在，“加载文件”活动处理的文件在默认情况下被删除。 通过某个选项，您可以根据特定需求保留这些资源。 删除工作流后，其专用文件夹会自动从服务器目录中被禁止。

**修补程序**

* 修复了一些原始报告事件由于eventDate字段未正确填充而没有关联跟踪事件的问题。
* 修复了阻止个性化字段显示在推送通知投放的预览窗口中的问题。
* 修复了阻止文本在预览窗口中自动换行推送通知的消息正文的问题。
* 修复了主投放为空时从工作流发送重新固定目标的问题。
* 修复了当目标映射链接到不存在的模式时，无法访问该的问题。
* 修复了通过文件加载活动导入zip文件时可能出现的问题。 (CAMP-24309)
* 修复了在发送循环投放时导致PostgreSQL错误的问题。 (CAMP-23613)
* 修复了在发送REST API请求时显示错误消息的空JSON属性的问题。 (CAMP-23506)
* 修复了用户档案中设置为“ß”字符后的大写字符的问题。 (CAMP-23136)
* 修复了在发送与个性化或动态内容块的资格条件一起使用的投放时使用链接的用户档案模式的属性的问题。 (CAMP-22751)
* 修复了无法删除服务的问题。 (CAMP-22050)
* 修复了无法更改测试用户档案中的国家／地区或州值的问题。 (CAMP-20426)
* 修复了可能阻止加载Creative Designer的问题。 (CAMP-24573)
* 修复了删除了电子邮件主题中个性化字段后添加的字符的问题。 (CAMP-24113)

## 18.4版- 2018年4月 {#release-18-4---april-2018}

**修补程序**

_平台_

* 修复了一个错误，该错误可能会阻止正确处理GDPR访问或删除请求。 在提取的数据包含以下字符的某些罕见情况下，会观察到此行为：&amp; &lt; > &quot; &#39;。

_电子邮件、短信和直邮_

* 修复了在广播同步时间超过一小时后，可能导致KPI被错误值覆盖的问题。

_工作流_

* 改进了内存管理并优化了工作流中的性能。

_报告_

* KPI共享工作流现在检索最近2个月而不是过去6个月的投放值。 修复了KPI共享外部帐户显示截断日期的问题。
* 修复了一个问题，该问题可能导致“已发送”、“已交付”和“弹 **回量度**”中未 **考虑某** 些 ****&#x200B;消息。
* 修复了投放摘要报告中的选定时间范围过长 **时发生的错误** 。

_自定义资源_

* 修复了导致自定义资源准备失败的错误。

## 18.3版- 2018年3月 {#release-18-3---march-2018}

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
   <td> 欧盟一般数据保护规定(GDPR)<br /> </td> 
   <td> GDPR是欧洲合并(EU)的新隐私法，该法规将2018年5月25日生效的数据保护要求协调化并现代化。 GDPR 适用于所持有数据的数据主体位于欧盟的 Adobe Campaign 客户。<br /> 除了Adobe Campaign中已有的隐私权（包括同意管理、数据保留设置和用户角色）外，我们还将利用作为数据处理者的角色中的这一机会加入其他功能，以帮助您为某些GDPR请求做好数据管理者的准备：<br /> 
    <ul> 
     <li> 访问权限：允许数据主体接收由数据控制者捕获的个人数据的副本，可能包括存储在Adobe Campaign中的数据。 </li> 
     <li> 删除权：数据主体有权擦除由数据控制者捕获的个人数据，可能包括存储在Adobe Campaign中的数据。 </li> 
    </ul> 有关详细信息，请参阅详 <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Creative Designer for Email（测试版）<br /> </td> 
   <td> Adobe Campaign的新Creative Designer优惠了活动中完全集成的创作体验，无需编写任何代码即可快速轻松地创建引人入胜的个性化电子邮件。 通过其强大的拖放界面，Creative Designer可帮助用户从空白的石板中开始或利用现有内容片段或模板来缩小电子邮件创建。 <br /> 主要功能包括：<br /> 
    <ul> 
     <li> 通过拖放界面以可视方式设计和创建完全个性化的响应式电子邮件，并通过本机Creative Cloud集成加以增强 </li> 
     <li> 创建和保存电子邮件内容模板并利用保存的模板帮助扩展电子邮件创建 </li> 
     <li> 创建和保存内容片段（如页眉、页脚、文章等）简化内容创建并确保品牌一致性 </li> 
     <li> 在拖放界面中创建和单击按钮直接编辑电子邮件的HTML之间无缝切换 </li> 
    </ul> Creative Designer for Email仅提供英语版。<br /> 有关详细信息，请参阅详细 <a href="../../designing/using/designing-content-in-adobe-campaign.md">文档</a> ，并观看此 <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">视频</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 多语言推送投放<br /> </td> 
   <td> 电子邮件和SMS渠道中已经存在的同一简单多语言界面已添加到推送渠道中，帮助您与客户互动，而无论客户喜欢何种语言。<br /> 此功能为管理跨多个区域的推送活动并希望以其首选语言目标用户的客户提供了可伸缩的自动解决方案。 它允许您通过模板化电子表格将所有语言变体上传到单个推送投放，只需单击一下即可。 然后，Adobe Campaign根据用户的语言偏好执行自动细分，通过简化工作流和报告帮助减少冗余。<br /> 有关详细信息，请参阅详 <a href="../../channels/using/creating-a-multilingual-push-notification.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 自定义资源在事务性消息传递中的使用<br /> </td> 
   <td> 除了开箱即用的字段之外，交易消息传递现在还允许您使用自定义资源来丰富消息的内容。<br /> 例如：<br /> 
    <ul> 
     <li> 利用自定义字段作为协调条件，将事务性消息与用户档案匹配 </li> 
     <li> 利用完整的用户档案、服务和关联数据进一步个性化事务性消息 </li> 
    </ul> 有关详细信息，请参阅详 <a href="../../administration/using/configuring-transactional-messaging.md">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* 修复了无法从列表导出5000多条记录的问题。
* 修复了将数据导出到以个性化字段命名的文件时的问题。

_电子邮件、短信和直邮_

* 修复了由于部分大小是以字符而不是字节计算，导致多部分SMS被截断的问题。
* 添加了一个选项，允 **[!UICONTROL Delivered]** 许 **[!UICONTROL Bounces + Errors]** 在发送投放后实时更新KPI或KPI。 直接从从提供者接收的SR（状态报告）中重新计算它们。
* 修复了投放调度程序中日历构件的问题。
* 修复了在已发送的目标中再次打开投放时的显示问题。
* 修复了在创建发送日期延迟的电子邮件模板时导致请求开始日期的错误消息的问题。
* 修复了在编辑投放内容时可能导致图像渲染问题的问题。
* 修复了复制验证时的活动问题。
* 修复了在将活动模板添加到工作流后，通过导航栏访问投放时导致错误消息的问题。
* 修复了一个问题，该问题可能导致无法自动选择A/B测试电子邮件的优胜者，从而导致电子邮件不发送。 如果投放处于状态，则可能会发生此 **[!UICONTROL retryInProgress]** 行为。
* 修复了在重新打开A/B测试电子邮件的参数时，可能导致出现错误消息的问题。

_受众和查询_

* 修复了无法访问数据和为从Adobe Campaign经典到标准的复制收件人设置查询的问题。
* 修复了在使用“计数”或“查询”按钮后，在预览编辑器中使用过滤器类型字段时发 **生的****问题** 。

_工作流_

* 已优 **化投放工作** 流，以改进帐单准备延迟。
* 修复了在使用循环过渡时阻止在出站投放中显示人口数据的问题。
* 修复了在更新数据过渡后，拒绝记录无法在活动中显示的 **问题** 。
* 修复了可能导致deliverabilityUpdate技术工 **作流失败的问** 题。

_集成_

* 修复了无法将国际字符正确发送到Adobe Analytics的问题。
* 现在，当尝试在消息中插入Experience Cloud资源库中的图像时，资产的加载速度应更快。
* 修复了在某些情况下可能无法关闭资产选择窗口的问题。
* 从数据源详细信息中，您现在可以直接访问其相关工作流以检查该工作流的状态。
* 您现在可以在定义或编辑触发器模式时直接更新触发器事件。 通过此更改，您不必再取消发布触发器并创建另一个触发器。

_事务性消息_

* 修复了扩展事务性消息模板资源时投放出错的问题。
* 现在可以删除事务性消息。

## 18.2版- 2018年2月 {#release-18-2---february-2018}

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
   <td> 订阅-订阅或取消订阅列表的多项服务<br /> </td> 
   <td> 订阅服务 <strong>工作流</strong> 活动现在允许您订阅或取消订阅一列表用户档案至多项服务。 在您的工作流中，导入包含用户档案的文件，并针对每个用户档案、操作类型和服务。 订阅服务 <strong></strong> 活动将能够使用此信息并同时动态处理您的所有用户档案订阅和退订。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/subscription-services.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 扩充活动-根据以前的过渡丰富数据<br /> </td> 
   <td> 新的 <span class="uicontrol">扩充活动</span> ，您可以利用入站过渡并使用其他数据完成输出过渡。 如果您目标用户档案,扩充活动允许您使用未存储在数据库中的其他数据（例如，来自导入的文件）来丰富用户档案信息。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/enrichment.md">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* Adobe Campaign界面的顶栏已使用新的Experience Cloud菜单进行更新。
* 修复了阻止在解决方案下拉 **[!UICONTROL Offers]** 框列表中显示要链接的问题。

_电子邮件、短信和直邮_

* 投放制备阶段已经增强以改进性能。
* 修复了若干问题，这些问题可能导致跟踪日志在某些特殊情况下受损。
* 修复了在准备投放和确认之间更改联系日期时发生的联系日期更新问题。 现在，当您在准备后更改联系日期时，您必须再次准备投放，然后才能确认发送。 请参阅详 [细文档](../../sending/using/preparing-the-send.md)。

_推送通知_

* 修复了导致某些个性化字段无法在iOS推送通知中工作的错误。
* 修复了在推送通知仪表板中将单击和打开速率显示为0%的错误。

_报告_

* 修复了在某些浏览器中将报表列表显示为空的错误。
* 修复了在技术工作流达到 **[!UICONTROL Report sharing]** 到期限之前发生的错误。

_工作流_

* 修复了在拖放活动后无法访问它们的问题。
* 修复了在某些情况下可能导致活动的输出过渡 **[!UICONTROL Segmentation]** 顺序发生更改的问题。
* 修复了读取包含受众类型字段的明细列表时以前从工作流中保存的错误
* 修复了在定义在工作流 **[!UICONTROL Request confirmation before sending messages]** 中创建的投放的调度属性时，即使取消选中该选项也会保持选中状态的问题。
* 现在，可以通过选项卡中的新选项在重复中禁用自动删除活动行（DISTINCT子句） **[!UICONTROL Query]****[!UICONTROL Additional data]** 功能。 出于性能原因，在定义许多（超过100个）附加元素时，建议禁用此选项。

_集成_

* 对配置屏幕进行了 **[!UICONTROL Data sources]** 一些改进。

_已知问题_

由于可能出现显示问题，建议您不要使用Internet Explorer 11版。

使用活动界面中的上下文帮助链接时，可能会出现一些问题。 18.3中将予以修复。

## 18.1版- 2018年1月 {#release-18-1---january-2018}

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
   <td> 疲劳管理报告是一种专用的可配置报告，显示疲劳规则对电子邮件、推送、短信和直邮投放在发送前的指定日期范围内的影响。 通过增加的洞察，可以在一个视图中快速查看所有冲突活动，营销人员可以根据疲劳规则设置更有效地规划营销活动，并优先安排通信。<br /> 有关详细信息，请参阅详 <a href="../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 报告共享<br /> </td> 
   <td> “报告共享”允许您以电子邮件附件的形式与Adobe Campaign用户共享报告，包括自动重复发送。 收到重复报告的用户可以通过每封电子邮件中的专用链接取消订阅这些通信。<br /> 有关详细信息，请参阅详 <a href="../../reporting/using/reporting-interface.md#share-tab">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送新功能<br /> </td> 
   <td> 推送消息预览-在iOS和Android设备上，从推送通知内容编辑器中预览推送通知，以准确查看收件人在测试或执行投放之前将看到的内容。<br /> 有关详细信息，请参阅详 <a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">细文档</a>。<br /> 可用内容——当应用程序在较长时间内未打开时，其数据可能会过期。 这会导致数据在用户最终打开应用程序时必须进行更新或替换，这会导致应用程序使用延迟。 借助“可用内容”的新增支持，Adobe Campaign用户可以在发送推送通知时唤醒其应用程序以在后台刷新其数据，从而提高一致性并控制用户的应用程序内体验。<br /> 可变内容——借助对可变内容的新增支持，Adobe Campaign用户现在可以利用他们的移动应用程序扩展进一步修改从Adobe Campaign发送的推送通知的内容或演示。 例如，用户可以利用可变内容执行以下操作： <br /> 
    <ul> 
     <li> 解密以加密格式传送的数据 </li> 
     <li> 下载图像或其他媒体文件，并将它们作为附件添加到通知中 </li> 
     <li> 更改通知的正文或标题文本 </li> 
     <li> 向通知添加线程标识符 </li> 
    </ul> 有关“可用内容”和“可移动内容”的详细信息，请参阅详 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">细文档</a>。<br /> 警 <strong>告：</strong> 这些推送通知更新要求客户升级其移动应用程序。 Refer to <a href="https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html">this technote</a> for more information.<br /> </td> 
  </tr> 
  <tr> 
   <td> 时区优化投放<br /> </td> 
   <td> 计划重复发送电子邮件、短信和推送通知，这些通知将在每个收件人时区的特定日／时间发送，确保消息在正确的时间发送，而无需设置多个投放。 <br /> 有关详细信息，请参阅详 <a href="../../automating/using/scheduler.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> API信号活动触发<br /> </td> 
   <td> 现在可以直接从活动标准API为工作流触发信号Adobe Campaign。<br /> 有关详细信息，请参阅详 <a href="/help/api/using/triggering-a-signal-activity.md">细文档</a> 。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* 用户档案搜索已经过优化以提高性能。
* 对于标准用户，默认安全组的内部标识符现在处于只读模式。

_电子邮件、短信和直邮_

* 修复了在投放内容中插入emoji时出现的显示问题。
* 修复了在投放仍在版本中时允许用户访问发送日志的问题。
* 该 **[!UICONTROL Scheduler]** 活动现在允许您根据收件人的时区发送投放。
* SMS:数据库 **[!UICONTROL Store incoming MO]** 中的选项已添加到外部帐户。 选中后，所有传入的SMS都将存储到 **inSMS表** 中。
* SMS:服务现在附加到事件而不是事务模板。
* SMS:默认的SMTP连接超时已缩短为30秒。

_推送通知_

* 修复了阻止推送通知投放停止的错误。
* 在推送通知中添加了一个选项，用于通过推送通知唤醒应用程序。
* 为推送通知预览视频添加了暂停按钮。
* 推送通知预览现在可用于iPhone、Android和平板电脑等不同设备。

_报告_

* 修复了显示超过100%的速率的错误。
* 修复了用户无法下载CSV格式的报告的问题。
* 在主页中 **[!UICONTROL Report]** 添加了新项目。

_工作流_

* 修复了在查询中使用其他数据并添加包含空格的别名时导致错误消息的问题。 非字母数字字符现在替换为“_”。
* 修复了在某些情况下，技术工作流计算KPI时可能会默认停止的问题。

_用户档案和受众_

* 修复了在受众过滤器中添加多个查询时发生的错误。
* 修复了更改用户档案图片时出现的显示问题。
* 添加了一个工具提示，显示在计算查询的填充数后的确切结果编号。
* 修复了用户无法选择受众或关闭受众选取器窗口的问题。
* 表达式编辑器中可用函数的列表已更新。 FormatCurrency **和** ConvertCurrency **** 函数已被删除。

