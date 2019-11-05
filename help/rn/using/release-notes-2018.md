---
title: 发行说明 2018
description: 本页列出了所有2018版Adobe Campaign Standard。
page-status-flag: 从未激活
uuid: 99f92a54-4b3d-48b9-b08d-e98b24e75f62
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: 参考
topic-tags: campaign-standard-releases
discoiquuid: e54f8305-7e32-4193-8e5a-b5d87b03038c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 发行说明 2018{#release-notes}

是否正在寻找Adobe Campaign Standard的特定2018版本？

每个版本都提供新功能和修补程序。 单击某个版本可查看其内容。

查看Adobe Campaign [Standard的最新文档](../../rn/using/documentation-updates.md) 更新。 如果要寻找较新的版本，请查阅此 [页](../../rn/using/release-notes.md)。

## 18.9版- 2018年9月 {#release-18-9---september-2018}

### What's new? {#what-s-new-}

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
   <td> Adobe Launch与Adobe Campaign的集成现在可使用Mobile SDK V5简化和自动化Campaign中移动应用程序属性激活的过程。<br /> 有关详细信息，请参阅详 <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 改进 {#improvements}

* Adobe Campaign Standard现在支持Amazon S3 API的版本4。

### 其他更改 {#other-changes}

* 在广播中，现在可以区分每小时最大连接数和最大消息数。 当达到这些限制时，可以知道为什么吞吐量有限。 以前，两种情况都使用相同的消息（“配额满足”）。
* 在Campaign中配置移动应用程序时，用户现在可以知道iOS证书和Android服务器密钥是否已成功上传及其过期日期。

   有关详细信息，请参阅有关如何使用 [SDK V4和](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) SDK V5配置移动应用程序的详细文档 [](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)。

* 通过在定义营销活动属性时选择移动应用程序，定位特定移动应用程序上的用户。 此功能适用于推送和应用程序内消息传递渠道。

   有关详细信息，请参阅详 [细文档](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification)。

* 使用Creative Designer界面选择内容块时，现在将加载并显示列表中的所有内容块。 (CAMP-27311)

   有关详细信息，请参阅详细 [文档](../../designing/using/personalization.md#adding-a-content-block)。

### 修补程序 {#patches}

* 修复了电子邮件功能板和交易电子邮件的电子邮件摘要报告之间日志计数不一致的问题。 (CAMP-28237)
* 修复了工作流中的一个问题，该问题导致在通过文件传输活动导入文件时可能显示错误消息。 (CAMP-27435)
* 修复了包含超过25项服务的登录页面导致在表单中随机取消选择服务的问题。 (CAMP-26572)
* 修复了工作流中的一个问题，该问题导致在使用文件传输活动时无法使用SFTP URL配置外部帐户。 (CAMP-26475)
* 修复了无法更新服务摘要报告的问题。 (CAMP-26301)
* 修复了使用丰富化活动时工作流中的一个问题，该问题导致自定义字段无法显示正确的日期。 (CAMP-26242)
* 修复了通过文件导入导入时无法更新服务订阅日期的问题。
* 修复了加载文件活动导致工作流无法导入文件的错误(CAMP-27068)。
* 修复了在服务摘要报告中显示错误订阅数的问题(CAMP-25587)。
* 修复了Adobe Analytics与Adobe Campaign报表之间数据不一致的问题。 (CAMP-25393)
* 修复了阻止受限访问用户登录的问题。 (CAMP-27381)
* 修复了使用Creative Designer编辑电子邮件时可能无法显示Adobe Experience Manager内容列表的问题。 (CAMP-27181)
* 修复了可能阻止Creative Designer打开并导致错误的问题。 (CAMP-27304)
* 修复了在使用Internet Explorer 11时，拖放在Creative Designer中无法正确工作的问题。
* 修复了一个问题，该问题导致从相机上传的照片以及以纵向模式拍摄的照片在不需要的旋转位置显示。
* 修复了在Creative Designer中使用查询编辑器界面时显示选择信息不明确的问题。
* 修复了在Creative Designer中使用查询编辑器界面时无法正确复制元素的问题。
* 修复了即使通过自动回复取消订阅，仍然向列入黑名单的收件人发送SMS消息的问题。 (CAMP-27128)
* 修复了阻止显示导致“数据库清除”工作流失 **败的错误** 的问题。 (CAMP-26876)
* 修复了一个问题，该问题可能会阻止删除推送通知定义中的自定义字段。 (CAMP-25588)

## 18.7版- 2018年7月 {#release-18-7---july-2018}

### What's new? {#what-s-new--1}

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
   <td> Android的高优先级标志——支持为Android应用程序提供高优先级的推送通知，这会导致休眠设备唤醒并运行一些有限的处理。 请注意，默认优先级为“正常”，这可能会延迟消息传送以节省电池。 <br /> 有关详细信息，请参阅详 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 针对移动App用户的排版过滤器<br /> </td> 
   <td> 支持排版过滤器中的订阅——当为排版规则指定筛选条件时，可以选择应用程序订阅作为筛选和定位维度，从而提供对具有或没有配置文件的用户的属性进行筛选的能力。 <br /> 有关详细信息，请参阅详 <a href="../../administration/using/about-typology-rules.md#typology-rules">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 在准备消息期间从URL自动导入内容<br /> </td> 
   <td> 现在，可以在准备阶段从URL导入电子邮件内容。 对于重复发送的电子邮件，每次准备邮件时都会检索最新的HTML内容，确保该内容在发送电子邮件时始终保持最新。 此功能还允许您创建包含URL中内容的预定交付，即使该内容尚未准备好。<br /> 有关详细信息，请参阅详 <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 营销活动发布通知消息<br /> </td> 
   <td> 现在，当用户在实例升级到新版本后登录时，会显示一条弹出消息。 该消息指示版本号，并包含指向发行说明的链接。 您可以选择在下一个版本之前隐藏消息。 <br /> </td> 
  </tr> 
  <tr> 
   <td> 用户管理<br /> </td> 
   <td> 从18.7版本开始，地理单元功能现在不可用于新的Campaign standard实例以及没有创建地理单元的现有实例。<br /> 有关详细信息，请参阅本 <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">页</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 改进 {#improvements-1}

* Adobe Campaign和Adobe Target集成现在允许您利用Target的“权限” [功能](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html) 。 在电子邮件中包含Adobe Target的动态图像时，您现在可以指定目标属性（at_property代码）。
* 具有指向配置文件资源的下载链接的自定义资源现在由GDPR隐私访问／删除请求考虑。 对于1个基数简单链接和N个基数集合链接，您需要在自定义资源中选择“删除／复制目标记录意味着删除／复制链接引用的记录”。 对于0或1基数简单链接，选择“删除／复制记录意味着删除／复制链接引用的目标记录”。

### 其他更改 {#other-changes-1}

* 报告共享超时时间已从1分钟增加到4分钟，以避免任何超时错误。
* 编辑电子邮件内容时，默认情况下会打开新的Creative Designer。 如果需要，您仍可以在保存更改后随时返回默认内容编辑器。 有关详细信息，请参阅详细 [文档](../../designing/using/overview.md)。
* 在Creative Designer中，现在可以向电子邮件中添加新内容组件：轮盘。 有关详细信息，请参阅详细 [文档](../../designing/using/designing-from-scratch.md#about-content-components)。
* 在事务性消息热点单击报告中，当您单击“ **Change profile** （更改配置文件）”按钮时，现在仅列出链接到您为事务性消息定义的活动的测试配置文件。

### 修补程序 {#patches-1}

* 修复了byEmail查询筛选器无法返回任何结果的问题。 (CAMP-23420)
* 修复了允许标准用户访问受限于管理员的特定功能或屏幕（/rest/head/*端点、交易消息屏幕、配置文件和受众导入屏幕）的问题。
* 修复了在GDPR隐私删除请求的名称以数字开头时，该请求无法处理自定义资源的问题。
* 修复了阻止“保存受众”活动在Adobe Experience cloud中共享应用程序订阅者的错误。
* 修复了文件名包含空格时可能发生的文件传输活动问题。 (CAMP-25936)
* 修复了在会话过期后使用重新连接按钮时可能发生的问题。 (CAMP-25560)
* 修复了在发送具有与疲劳规则关联的时区优化的交货时可能导致排除的问题。 (CAMP-25425)
* 修复了使用API GDPR功能时，可能无法使用0-1类型链接删除数据的问题。
* 修复了在取消疲劳类型规则版本时可能导致错误消息的问题。
* 修复了在编辑分发内容后预览分发内容时可能发生的问题。
* 修复了在使用解压缩选项处理CSV zip文件时可能发生的问题。
* 修复了Creative Designer中的一个问题，该问题导致使用内置样式将某些文本更改为链接或编辑该链接时，出现不需要的颜色字体和格式。 (CAMP-26001)
* 修复了阻止热点单击报告显示包含动态内容的分发中每个条件的百分比的问题。 以前，只显示对默认变体的单击。

## 18.6版- 2018年6月 {#release-18-6---june-2018}

### 改进 {#improvements-2}

* 该 **[!UICONTROL History]** API已添加到Adobe.IO。 它允许您访问与个人资料的营销历史记录相关的信息：接触点数、已发送的交付、镜像页面URL等。 有关详细信息，请参阅专 [用用例](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#how-to-retrieve-the-mirror-page-for-a-delivery-sent-to-a-profile) 。
* 为了 **[!UICONTROL Database cleanup]** 确保数据库备份的更好性能，已优化了技术工作流程。
* Creative Designer for email现在也提供法语和德语版。

### 其他更改 {#other-changes-2}

* 已 **[!UICONTROL Compute stats]** 在已发送的提交窗口 **[!UICONTROL Deployment]** 中添加一个按钮。 它允许您检索最新的KPI，例如，如果发送结果的更新时间过长或未考虑到这些结果。 For more on this, refer to this [section](../../sending/using/confirming-the-send.md).
* 在开箱 **即用的技术工作流程中** ，功能管理员现在可以定义更新规则javascript活动中要忽略的连续错误数 **量** 。 默认情况下，字段值设置为0，这意味着将忽略所有错误。
* 在管理单元访问限制条件时生成的SQL已得到优化。
* 该 **[!UICONTROL Update]** 活动现在允许您添加、更新或删除与订阅相关的数据（nms:appSubscriptionRcp表）。
* 为了 **[!UICONTROL Update delivery execution]** 优化性能，技术工作流分为两个工作流：- **[!UICONTROL Update delivery execution]**:更新交付的跟踪。 默认情况下，每10分钟启动一次。 **[!UICONTROL Update delivery indicators]**:更新交付的KPI，默认情况下每小时开始一次。 For more on technical workflows, refer to this [section](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* 发送消息时，部分中的状态现 **[!UICONTROL Deployment]** 在可以有两个值： **[!UICONTROL Sending]**:正在发送消息。 **[!UICONTROL Sending (retry)]**:重试通过正在进行中。
* 具有该角色 **[!UICONTROL Delivery preparation]** 的用户现在可以发送校样。 (CAMP-24313)
* 通过 **SMPP** , SMPP上的启用TLS选项已经通过SMPP外部帐户 **添加到SMS路由中** 。 For more on this refer to this [section](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

### 修补程序 {#patches-2}

* 修复了在包含来自Adobe Target的动态图像时，可能无法发送电子邮件的问题(CAMP-24848)。
* 修复了技术工作 **[!UICONTROL Privacy Access/Delete Request]** 流程的一个问题，如果任何请求失败，该问题将未完成。
* 修复了隐私核心服务无法从营销活动接收请求状态更新的问题。
* Fixed an issue which could prevent the **[!UICONTROL Import shared audience]** technical workflow from working properly (CAMP-25465).
* 修复了阻止在核心隐私服务中将营销活动隐私请求标记为已完成的问题。
* 修复了在Adobe ID过长时，某些用户无法通过IMS身份验证登录到Campaign Standard的问题。 (CAMP-24095)
* 修复了Creative Designer中删除内容模块时可能出现的问题。 (CAMP-25242)
* 修复了在数据库中没有配置文件的用户使用推送通知疲劳规则的问题。 (CAMP-25344)
* 修复了在访问交付排除日志时可能显示错误消息的问题。 (CAMP-24724)
* 修复了在具有扩展发送日志的实例中无法准备校样的问题。
* 修复了在激活扩展的情况下发布自定义资源时可能发生 **[!UICONTROL Sending log]** 的两个问题。
* 修复了在重复交付时可能考虑交付持续时间的问题。
* 修复了对具有100K以上记录的自定义资源在菜 **[!UICONTROL Client data]** 单中对数据排序时可能发生的问题。 (CAMP-24308)
* 修复了在动态报表中使用搜索功能时未考虑的自定义配置文件维度问题。
* 修复了在动态报表中显示帐户级别的国际数据的问题。
* 现在，无需订阅或取消订阅确认消息即可创建服务。

## 版本18.5 - 2018年5月 {#release-18-5---may-2018}

### What's new? {#what-s-new--2}

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
   <td> 隐私核心服务集成允许您通过单个JSON API调用在多解决方案环境中自动执行GDPR请求。 <br /> 从隐私核心服务推送到所有Experience cloud解决方案的GDPR请求现在由Campaign自动处理。 <br /> 有关详细信息，请参阅详 <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送改进——详细的交付反馈<br /> </td> 
   <td> Adobe Campaign现在提供通过MCPNS从提供商(APNS/GCM)接收推送消息的详细反馈（发送日志和排除日志）的功能。<br /> 有关详细信息，请参阅详 <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付日志扩展<br /> </td> 
   <td> 交付日志扩展允许您扩展发送日志，其中包含来自工作流的配置文件数据和区段代码。 此信息随后可用于动态报表，并允许您在发送时保留某些信息的快照。<br /> 还有2个用例：<br /> 
    <ul> 
     <li> 导出包含“冻结”数据的扩展广播：作为营销人员，我希望导出区段代码等于“A”的所有配置文件（来自工作流引擎）。 </li> 
     <li> 对“冻结”数据进行细分：作为营销人员，我希望重新定 <strong>位自上次发送</strong> 1000个忠诚度积分或区段代码等于“A”的所有档案。 </li> 
    </ul> 有关详细信息，请参阅详 <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 使用自定义配置文件数据进行动态报告<br /> </td> 
   <td> 此功能允许您根据在配置文件资源扩展期间创建的自定义配置文件数据创建和管理报告。 您可以按忠诚度计划、首选渠道等个人资料属性细分报告。<br /> 有关详细信息，请参阅详 <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 改进 {#improvements-3}

* 应用程序的总内存和CPU使用已得到增强

### 其他更改 {#other-changes-3}

* “阅读受众”工作流活动现在可以阅读Experience cloud受众。 以前，此活动只能读取查询和列表受众。 请参阅详细 [文档](../../automating/using/read-audience.md)。 (CAMP-23623)
* 默认共享数据源的标识符现在处于只读模式，不再可以更改。 在与Experience cloud共享受众时，更改此标识符可能会导致一些问题。
* 从Audience Manager导入受众现在可处理拆分文件。 以前，只有区段的最后一个文件是由importSharedAudience技术工作流导入的。
* AWS S3外部帐户现在支持区域和版本4身份验证机制。 请参阅详细 [文档](../../administration/using/external-accounts.md)。
* 现在，资产选择窗口的加载速度应更快，并且允许选择资产，然后退出窗口而不会出现任何问题。
* 技术工作流的属性和结构现在可由具有管理权限且属于“全部”组织和地理单元的用户修改。
* 在创建新区段时，分段活动界面中进行了增强：现在，在添加限制后直接显示“限制”选项卡。 新区段的名称现已递增（“区段1”、“区段2”等）。
* “nextProcessingDate”字段将添加到工作流资源。 此字段仅通过REST API调用可见，它允许您可视化下一个处理日期的工作流。
* “sourceId”字段现在显示在跟踪日志资源(nms:trackingLog)中。
* “总打开次数”和“总点击次数”值现在可通过工作流在平面文件中导出。 (CAMP-24186)
* “英语- Danmark”现在在配置文件的“首选语言”列表中可用。 (CAMP-23728)
* 当将分段活动与附加数据(targetData)链接一起使用时，现在会显示一条消息，通知您该数据在工作流之外不可用。 单击分段活动中的计数或预览按钮时，将显示此消息。 (CAMP-23651)
* 已进行增强以优化工作流使用的磁盘空间：(CAMP-21979):“加载文件”活动处理的文件现在默认情况下被删除。 通过某个选项，您可以根据特定需求保留这些资源。 删除工作流后，其专用文件夹会自动从服务器目录中被禁止。

### 修补程序 {#patches-3}

* 修复了一些原始报告事件由于eventDate字段未正确填充而没有关联跟踪事件的问题。
* 修复了阻止个性化字段显示在推送通知交付的预览窗口中的问题。
* 修复了阻止文本在预览窗口中自动换行推送通知的消息正文的问题。
* 修复了在主目标为空时从工作流发送重新固化交付时的问题。
* 修复了当目标映射链接到不存在的架构时，无法访问该映射的问题。
* 修复了通过文件加载活动导入zip文件时可能发生的问题。 (CAMP-24309)
* 修复了在发送重复交付时导致PostgreSQL错误的问题。 (CAMP-23613)
* 修复了在发送REST API请求时显示错误消息的空JSON属性的问题。 (CAMP-23506)
* 修复了配置文件中的问题，该问题将“ß”字符后面的字符设置为大写。 (CAMP-23136)
* 修复了在发送与个性化或动态内容块的资格条件一起使用的分发时使用关联的配置文件架构的属性的问题。 (CAMP-22751)
* 修复了无法删除服务的问题。 (CAMP-22050)
* 修复了无法更改测试配置文件中的国家／地区或州值的问题。 (CAMP-20426)
* 修复了可能阻止加载Creative Designer的问题。 (CAMP-24573)
* 修复了删除了电子邮件主题中个性化字段后添加的字符的问题。 (CAMP-24113)

## 18.4版- 2018年4月 {#release-18-4---april-2018}

### 修补程序 {#patches-4}

#### 平台 {#platform}

* 修复了一个错误，该错误可能会阻止正确处理GDPR访问或删除请求。 在提取的数据包含以下字符的某些罕见情况下，会观察到此行为：&amp; &lt; &gt; " '。

#### 电子邮件、短信和直邮 {#emails--sms-messages-and-direct-mail}

* 修复了在广播同步时间超过一小时后，可能导致KPI被错误值覆盖的问题。

#### 工作流 {#workflows}

* 改进了内存管理并优化了工作流中的性能。

#### 报告 {#reporting}

* KPI共享工作流现在检索最近2个月而不是过去6个月的交付值。 修复了KPI共享外部帐户显示截断日期的问题。
* 修复了一个问题，该问题可能导致“已发送”、“已交付”和“弹 **回量度**”中未 **考虑某** 些 ****&#x200B;消息。
* 修复了在“交付摘要”报表中的选定时 **间范围过长时** ，发生的错误。

#### 自定义资源 {#custom-resources}

* 修复了导致自定义资源准备失败的错误。

## 18.3版- 2018年3月 {#release-18-3---march-2018}

### 新功能 {#new-capabilities}

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
   <td> GDPR是欧盟(EU)的新隐私法，该法规将2018年5月25日生效的数据保护要求协调化并现代化。 GDPR 适用于所持有数据的数据主体位于欧盟的 Adobe Campaign 客户。<br /> 除了Adobe Campaign中已有的隐私权（包括同意管理、数据保留设置和用户角色）外，我们还将作为数据处理者的角色利用此机会加入其他功能，以帮助您为某些GDPR请求做好数据管理者的准备：<br /> 
    <ul> 
     <li> 访问权限：允许数据主体接收由数据管理者捕获的个人数据的副本，可能包括Adobe Campaign中存储的数据。 </li> 
     <li> 删除权：使数据主体能够擦除由数据管理者捕获的个人数据，可能包括存储在Adobe Campaign中的数据。 </li> 
    </ul> 有关详细信息，请参阅详 <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Creative Designer for Email（测试版）<br /> </td> 
   <td> Adobe Campaign的新Creative Designer在Campaign中提供完全集成的创作体验，无需编写任何代码即可快速轻松地创建引人入胜的个性化电子邮件。 通过其强大的拖放界面，无论用户是从空白的石板开始还是利用现有内容片段或模板，Creative Designer都能帮助缩放电子邮件创建。 <br /> 主要功能包括：<br /> 
    <ul> 
     <li> 通过拖放界面以可视方式设计和创建完全个性化的响应式电子邮件，并通过本机Creative cloud集成加以增强 </li> 
     <li> 创建和保存电子邮件内容模板并利用保存的模板帮助扩展电子邮件创建 </li> 
     <li> 创建和保存内容片段（如页眉、页脚、文章等）简化内容创建并确保品牌一致性 </li> 
     <li> 在拖放界面中创建和单击按钮直接编辑电子邮件的HTML之间无缝切换 </li> 
    </ul> Creative Designer for email仅提供英语版。<br /> 有关详细信息，请参阅详细 <a href="../../designing/using/overview.md">文档</a> ，并观看此 <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">视频</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 多语言推送交付<br /> </td> 
   <td> 电子邮件和短信渠道中已经存在的同一简单多语言界面，现已添加到推送渠道中，无论客户喜欢使用何种语言，都能帮助您吸引客户。<br /> 此功能为管理跨多个区域的推送营销活动并希望以其首选语言定位用户的客户提供了可伸缩的自动解决方案。 它允许您通过模板化电子表格将所有语言变体上传到单个推送交付，只需单击一下即可。 然后，Adobe Campaign会根据用户的语言偏好执行自动细分，通过简化工作流和报告帮助减少冗余。<br /> 有关详细信息，请参阅详 <a href="../../channels/using/creating-a-multilingual-push-notification.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 自定义资源在事务性消息传递中的使用<br /> </td> 
   <td> 除了开箱即用的字段之外，交易消息传递现在还允许您使用自定义资源来丰富消息的内容。<br /> 例如：<br /> 
    <ul> 
     <li> 利用自定义字段作为协调标准，将交易消息与配置文件匹配 </li> 
     <li> 利用完整档案、服务和链接数据进一步个性化交易信息 </li> 
    </ul> 有关详细信息，请参阅详 <a href="../../administration/using/configuring-transactional-messaging.md">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-5}

#### 平台 {#platform-1}

* 修复了无法从列表导出5000多条记录的问题。
* 修复了将数据导出到使用个性化字段命名的文件时的问题。

#### 电子邮件、短信和直邮 {#emails--sms-messages-and-direct-mail-1}

* 修复了由于部分大小是以字符而不是字节计算，导致多部分SMS被截断的问题。
* 添加了一个选项，允 **[!UICONTROL Delivered]** 许 **[!UICONTROL Bounces + Errors]** 在发送交付后实时更新KPI或KPI。 直接从从提供者收到的SR（状态报告）中重新计算这些值。
* 修复了分发调度程序中日历构件的问题。
* 修复了在已发送的分发中再次打开目标时的显示问题。
* 修复了在创建发送日期延迟的电子邮件模板时导致请求开始日期的错误消息的问题。
* 修复了在编辑分发的内容时可能导致图像渲染问题的问题。
* 修复了复制营销活动时的校样问题。
* 修复了在向工作流中添加分发后，通过导航栏访问营销活动模板时导致错误消息的问题。
* 修复了一个问题，该问题可能导致无法自动选择A/B测试电子邮件的优胜者，从而导致电子邮件不发送。 如果交付处于状态，则可能会发生此 **[!UICONTROL retryInProgress]** 行为。
* 修复了在重新打开A/B测试电子邮件的参数时可能导致显示错误消息的问题。

#### 受众和查询 {#audiences-e-queries}

* 修复了无法访问数据和为从Adobe Campaign Classic复制到Standard的收件人设置查询的问题。
* 修复了在使用“计数”或“预览”按钮后在查询编辑器中使用过滤器类型字段时 **发生** 的 **问题** 。

#### 工作流 {#workflows-1}

* 开 **单工作流已经过优化** ，可改善交付准备延迟。
* 修复了在使用循环交付活动时阻止在出站转换中显示人口数据的问题。
* 修复了在“更新”数据活动后，拒绝记录在转换中无法显示 **的问题** 。
* 修复了可能导致deliverabilityUpdate技术工 **作流失败的问** 题。

#### 集成 {#integrations}

* 修复了无法将国际字符正确发送到Adobe Analytics的问题。
* 现在，当尝试在消息中插入Experience Cloud资源库中的图像时，资产的加载速度应更快。
* 修复了在某些情况下可能无法关闭资产选择窗口的问题。
* 从数据源详细信息中，您现在可以直接访问其相关工作流以检查该工作流的状态。
* 现在，您可以在定义或编辑触发器事件时直接更新触发器架构。 通过此更改，您不必再取消发布触发器并创建另一个触发器。

#### 交易消息 {#transactional-messages}

* 修复了延长交付资源时事务消息模板的错误。
* 现在可以删除交易消息。

## 18.2版- 2018年2月 {#release-18-2---february-2018}

### 新功能 {#new-capabilities-1}

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 说明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 订阅——订阅或取消订阅多项服务的配置文件列表<br /> </td> 
   <td> 订阅 <strong>服务工作流程</strong> ，现在允许您将配置文件列表订阅或取消订阅到多个服务。 在您的工作流程中，导入一个包含配置文件的文件，并针对每个配置文件、操作类型和服务进行导入。 订阅 <strong>服务活动将能够使用此信息</strong> ，并同时动态处理您的所有配置文件订阅和取消订阅。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/subscription-services.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 丰富化活动——根据以前的过渡来丰富数据<br /> </td> 
   <td> 新的丰 <span class="uicontrol">富化工作流</span> ，允许您利用入站过渡和使用其他数据完成输出过渡。 如果以配置文件为目标，则丰富化活动允许您使用数据库中未存储的其他数据（例如，来自导入的文件）来丰富配置文件信息。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/enrichment.md">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-6}

#### 平台 {#platform-2}

* Adobe Campaign界面的顶栏已使用新的Experience cloud菜单进行更新。
* 修复了阻止要在解决方案下拉 **[!UICONTROL Offers]** 列表中显示的链接的问题。

#### 电子邮件、短信和直邮 {#emails--sms-messages-and-direct-mail-2}

* 该递送准备阶段已被增强以改进性能。
* 修复了若干问题，这些问题可能导致跟踪日志在某些特殊情况下损坏。
* 修复了在交付准备和确认之间更改联系日期时发生的联系日期更新问题。 现在，当您在准备后更改联系日期时，您必须再次准备交付，然后才能确认发送。 请参阅详 [细文档](../../sending/using/preparing-the-send.md)。

#### 推送通知 {#push-notifications}

* 修复了导致某些个性化字段无法在iOS推送通知中工作的错误。
* 修复了在推送通知功能板中将单击和打开率显示为0%的错误。

#### 报告 {#reports}

* 修复了在某些浏览器中将报表列表显示为空的错误。
* 修复了在技术工作流达到 **[!UICONTROL Report sharing]** 到期限之前发生的错误。

#### 工作流 {#workflows-2}

* 修复了在拖放活动后无法访问的问题。
* 修复了在某些情况下可能导致活动的输出过渡 **[!UICONTROL Segmentation]** 顺序发生更改的问题。
* 修复了在读取包含枚举类型字段的受众时发生的错误，该错误之前已从工作流中保存
* 修复了在定义在工作流 **[!UICONTROL Request confirmation before sending messages]** 中创建的交付的调度属性时，即使取消选中该选项也会保持选中状态的问题。
* 现在，可通过选项卡中的新选项，在活动中禁 **[!UICONTROL Query]** 用自动删除重复行（DISTINCT子句）的 **[!UICONTROL Additional data]** 功能。 出于性能原因，在定义许多（超过100个）附加元素时，建议禁用此选项。

#### 集成 {#integrations-1}

* 对配置屏幕进行了 **[!UICONTROL Data sources]** 一些改进。

### 已知问题 {#known-issues}

由于可能出现显示问题，建议您不要使用Internet Explorer 11版。

使用营销活动界面中的上下文帮助链接时，可能会出现一些问题。 18.3中修复。

## 18.1版- 2018年1月 {#release-18-1---january-2018}

### 新功能 {#new-capabilities-2}

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
   <td> 疲劳管理报告是一种专用的可配置报告，显示疲劳规则对发送前指定日期范围内电子邮件、推送、短信和直邮渠道的发送的影响。 通过增加的洞察，可以在单一视图中快速查看所有冲突的营销活动，营销人员可以根据疲劳规则设置更有效的营销活动计划，并优先安排通信。<br /> 有关详细信息，请参阅详 <a href="../../administration/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 报告共享<br /> </td> 
   <td> “报告共享”允许您以电子邮件附件的形式与Adobe Campaign用户共享报告，包括自动重复使用。 收到重复报告的用户可以通过每封电子邮件中的专用链接取消订阅这些通信。<br /> 有关详细信息，请参阅详 <a href="../../reporting/using/reporting-interface.md#share-tab">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送新功能<br /> </td> 
   <td> 推送消息预览——在iOS和Android设备上，从推送通知内容编辑器中预览推送通知，以准确查看收件人在测试或执行交付之前将看到的内容。<br /> 有关详细信息，请参阅详 <a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">细文档</a>。<br /> 可用内容——当应用程序在较长时间内未打开时，其数据可能会过期。 这会导致数据在用户最终打开应用程序时必须进行更新或替换，这会导致应用程序使用延迟。 借助“可用内容”的新增支持，Adobe Campaign用户可以在发送推送通知时唤醒其应用程序以在后台刷新其数据，从而提高用户应用程序内体验的一致性和控制度。<br /> 可变内容——借助对可变内容的新增支持，Adobe Campaign用户现在可以利用他们的移动应用程序扩展进一步修改从Adobe Campaign发送的推送通知的内容或演示。 例如，用户可以利用可变内容执行以下操作： <br /> 
    <ul> 
     <li> 解密以加密格式传送的数据 </li> 
     <li> 下载图像或其他媒体文件，并将它们作为附件添加到通知中 </li> 
     <li> 更改通知的正文或标题文本 </li> 
     <li> 向通知添加线程标识符 </li> 
    </ul> 有关“可用内容”和“可移动内容”的详细信息，请参阅详 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">细文档</a>。<br /><strong> 警 </strong>告：这些推送通知更新要求客户升级其移动应用程序。 Refer to <a href="https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html">this technote</a> for more information.<br /> </td> 
  </tr> 
  <tr> 
   <td> 时区优化交付<br /> </td> 
   <td> 计划在每个收件人时区的特定日／时间发送重复的电子邮件、短信和推送通知，确保在正确的时间发送您的消息，而无需设置多次发送。 <br /> 有关详细信息，请参阅详 <a href="../../automating/using/scheduler.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> API信号活动触发<br /> </td> 
   <td> 现在可以直接从Adobe Campaign Standard API触发工作流的信号活动。<br /> 有关详细信息，请参阅详 <a class="anchorLink" href="https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity" target="_blank">细文档</a> 。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-7}

#### 平台 {#platform-3}

* 已优化配置文件搜索以提高性能。
* 对于标准用户，默认安全组的内部标识符现在处于只读模式。

#### 电子邮件、短信和直邮 {#emails--sms-messages-and-direct-mail-3}

* 修复了在分发内容中插入emoji时出现的显示问题。
* 修复了在交付仍在版本中时允许用户访问发送日志的问题。
* 活动 **[!UICONTROL Scheduler]** 现在允许您根据收件人的时区发送交货。
* SMS:数据库 **[!UICONTROL Store incoming MO]** 中的选项已添加到外部帐户。 选中后，所有传入的SMS都将存储到 **inSMS表** 中。
* SMS:服务现在附加到活动而不是事务模板。
* SMS:默认的SMTP连接超时已缩短为30秒。

#### 推送通知 {#push-notifications-1}

* 修复了阻止推送通知发送停止的错误。
* 在推送通知中添加了一个选项，用于通过推送通知唤醒应用程序。
* 为推送通知预览视频添加了暂停按钮。
* 推送通知预览现在可用于iPhone、Android和平板电脑等不同设备。

   所有渠道

#### 报告 {#reports-1}

* 修复了显示超过100%的速率的错误。
* 修复了用户无法下载CSV格式的报告的问题。
* 在主页中 **[!UICONTROL Report]** 添加了新项目。

#### 工作流 {#workflows-3}

* 修复了在查询中使用其他数据并添加包含空格的别名时导致错误消息的问题。 非字母数字字符现在替换为“_”。
* 修复了在某些情况下，技术工作流计算KPI时可能会默认停止的问题。

#### 用户档案和受众 {#profiles-and-audiences}

* 修复了在受众的查询中添加多个过滤器时出现的错误。
* 修复了更改配置文件图片时出现的显示问题。
* 添加了一个工具提示，其中显示了在计算查询的填充数后的确切结果编号。
* 修复了用户无法选择受众或关闭受众选取器窗口的问题。
* 表达式编辑器中的可用函数列表已更新。 FormatCurrency **和** ConvertCurrency **** 函数已被删除。

