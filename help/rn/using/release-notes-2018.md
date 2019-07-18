---
title: 2018发行说明
seo-title: 2018发行说明
description: 2018发行说明
seo-description: 本页列出了Adobe Campaign Standard的所有2018版。
page-status-flag: 从未激活
uuid: 99f92a54-4b3d-48b9-b08 d-e98 b24 f62 f62
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: paign-standard-release
discoiquuid: e54f8305-7e32-4193-8e5a-b5 d87 b03038 c
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Release Notes 2018{#release-notes}

正在寻找Adobe Campaign Standard的特定2018版？

每个版本都附带新增功能和修补程序。单击某个版本可查看其内容。

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a newer release, consult this [page](../../rn/using/release-notes.md).

## Release 18.9 - September 2018 {#release-18-9---september-2018}

### What's new? {#what-s-new-}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> In-App messaging (beta)<br /> </td> 
   <td> 应用程序内消息传递允许您通过提供上下文交互并使您能够触及可能退出推送通知的用户，从而更有效地吸引移动应用程序用户。将应用程序内消息传递与推送通知结合使用，创建高度个性化、相关的体验。这有助于更好地转换和保留App用户。<br /> 有关详细信息，请参阅 <a href="../../channels/using/about-in-app-messaging.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Launch integration for mobile apps (beta)<br /> </td> 
   <td> Adobe Campaign与Adobe Campaign的集成现在可使用Mobile SDK V简化和自动化Campaign中移动App属性激活的过程。<br /> 有关详细信息，请参阅 <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements}

* Adobe Campaign Standard现在支持Amazon S API的版本4。

### Other changes {#other-changes}

* 在日志中，现在最大连接数和每小时最大消息数之间有区别。达到限制后，可以了解为什么吞吐量有限。以前，应用于这两种情况的消息('配额')相同。
* 在Campaign中配置手机应用程序时，用户现在可以了解是否已成功上传iOS证书和Android服务器密钥及其到期日期。

   For more on this, refer to the detailed documentation on how to configure a mobile application using [SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) and [SDK V5](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

* 在定义营销活动属性时选择移动App，定位特定移动应用程序中的用户。此功能适用于推送和应用程序内消息传递通道。

   For more information, refer to the [detailed documentation](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification).

* 使用Creative Designer界面选择内容块时，现在加载和显示列表中的所有内容块。(AMP-27311)

   For more on this, refer to the [detailed documentation](../../designing/using/adding-a-content-block.md).

### Patches {#patches}

* 修复了电子邮件功能板与交易电子邮件的电子邮件摘要报告之间存在差异的问题。(CMS-28237
* 修复了在通过文件传输活动导入文件时可能显示错误消息的工作流中的问题。(AMP-27435)
* 修复了一个问题，该问题导致包含更多服务的登陆页面更多地包含在表单中随机取消选择的服务。(AMP-26572)
* 修复了在使用文件传输活动时阻止在SFTP URL中配置外部帐户的工作流中存在的问题。(AMP-26475)
* 修复了阻止更新服务摘要报告的问题。(AMP-26301)
* 修复了使用丰富化活动时工作流中的某个问题，这会阻止自定义字段显示正确的日期。(CMS-26242)
* 修复了在通过文件导入导入服务订阅日期时无法更新服务订阅日期的问题。
* 修复了一个错误，该错误导致加载文件活动无法导入文件(AMP-27068)。
* 修复了在服务摘要报告中显示订阅数量错误的问题(Camp-25587)。
* 修复了Adobe Analytics和Adobe Campaign报告之间数据不一致的问题。(AMP-25393)
* 修复了可阻止受限访问用户登录的问题。(AMP-27381)
* 修复了使用Creative Designer编辑电子邮件时，可能会阻止Adobe Experience Manager内容列表显示的问题。(AMP-27181)
* 修复了可能阻止Creative Designer打开导致错误的问题。(AMP-27304)
* 修复了在使用Internet Explorer11时无法在Creative Designer中正确工作的问题。
* 修复了一个问题，该问题导致从相机上上传的照片和以纵向模式拍摄的照片以不想要的旋转位置显示。
* 修复了在Creative Designer中使用查询编辑器界面时显示不清楚的选择信息的问题。
* 修复了在Creative Designer中使用查询编辑器界面时无法正确复制元素的问题。
* 修复了一个问题，该问题导致即使通过自动回复取消订阅，仍向黑名单收件人发送SMS消息。(AMP-27128)
* Fixed an issue that prevented displaying the errors that caused the **Database Cleanup** workflow to fail. (AMP-26876)
* 修复了一个问题，该问题可能会阻止在推送通知定义中删除自定义字段。(AMP-25588)

## Release 18.7 - July 2018 {#release-18-7---july-2018}

### What's new? {#what-s-new--1}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> High priority flag for Android push notifications<br /> </td> 
   <td> Android的高优先级标志-支持交付Android应用程序优先级高的推送通知，这使得睡眠设备醒来并运行某些有限的处理。请注意，默认优先级为正常优先级，这会延迟消息传送以节省电池。<br /> 有关详细信息，请参阅 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Typology filter for mobile app subscribers<br /> </td> 
   <td> 支持字型过滤器中的订阅-为字型规则指定筛选条件时，可以选择应用程序订阅作为过滤和定位维度，提供对具有或没有配置文件的用户进行属性筛选的能力。<br /> 有关详细信息，请参阅 <a href="../../administration/using/about-typology-rules.md#typology-rules">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Automated content import from a URL during message preparation<br /> </td> 
   <td> 现在可以在准备阶段从URL导入电子邮件内容。对于重复的电子邮件发送，每次准备消息时都会检索最新的HTML内容，确保在发送电子邮件时始终保持内容始终处于最新状态。此功能还允许您通过URL中的内容创建计划交付，即使内容尚未准备就绪也是如此。<br /> 有关详细信息，请参阅 <a href="../../designing/using/importing-content-from-a-url.md#retrieving-content-from-a-url-automatically-at-preparation-time">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Campaign release notification message<br /> </td> 
   <td> 现在，当用户在实例升级到新版本后登录时，会显示弹出消息。此消息指示版本号并包含指向发行说明的链接。You can choose to hide the message until the next release. <br /> </td> 
  </tr> 
  <tr> 
   <td> User management<br /> </td> 
   <td> 新的Campaign Standard实例以及未创建的地理单位(开始18.7版本)的现有实例不可使用地理单位功能。<br /> 有关详细信息，请参阅此 <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">页面</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements-1}

* The Adobe Campaign and Adobe Target integration now allows you to leverage Target’s [Permissions](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html) feature. 在电子邮件中包含来自Adobe Target的动态图像时，您现在可以指定目标属性(_属性代码)。
* GDPR隐私权访问/删除请求现在会考虑具有指向配置文件资源的副本链接的自定义资源。对于基数简单链接和N基数集合链接，您需要选择“删除/复制目标记录”，以便在自定义资源中删除/复制链接引用的记录。对于或基数简单的链接，选择“删除/复制记录意味着删除/复制链接引用的目标记录”。

### Other changes {#other-changes-1}

* 报告共享超时从一到四分钟增加，以避免出现超时错误。
* 编辑电子邮件内容时，默认情况下会打开新的Creative Designer。您可以在保存更改后随时返回默认内容编辑器。For more on this, refer to the [detailed documentation](../../designing/using/about-email-content-design.md).
* 在Creative Designer中，现在可以将新内容组件添加到电子邮件中：传送。For more on this, refer to the [detailed documentation](../../designing/using/defining-the-email-structure.md#about-content-components).
* In a transactional message hot click report, when you click the **Change profile** button, now only the test profiles linked to the event that you defined for your transactional message are listed.

### Patches {#patches-1}

* 修复了ByEmail查询过滤器无法返回任何结果的问题。(AMP-23420)
* 修复了一个问题，该问题导致标准用户能够访问受限于管理员的特定功能或屏幕(/rest/head/*端点、事务消息屏幕、配置文件和受众导入屏幕)。
* 修复了在由数字开始的情况下，阻止GDPR隐私删除请求处理自定义资源的问题。
* 修复了阻止在Adobe Experience Cloud中共享应用程序用户活动的错误。
* 修复了文件名称包含空白空格时可能发生的文件传输活动的问题。(AMP-25936)
* 修复了在会话到期后使用重新连接按钮时可能发生的问题。(AMP-25560)
* 修复了在发送与传真规则相关的时区优化时可能导致排除的问题。(CMS-25425)
* 修复了使用API GDPR功能时可能无法删除具有0-1类型链接的数据的问题。
* 修复了在取消疲劳字型规则的版本时可能导致错误消息的问题。
* 修复了在编辑交付内容后预览交付内容可能出现的问题。
* 修复了在使用“解压缩”选项处理CSV zip文件时可能出现的问题。
* 修复了Creative Designer中的一个问题，该问题导致在将某些具有内置样式的文本更改为链接或编辑链接时，会导致不需要的颜色字体和格式。(AMP-26001)
* 修复了阻止热单击报告显示包含动态内容的交付中每个条件的百分比的问题。以前，只显示默认变体上的单击。

## Release 18.6 - June 2018 {#release-18-6---june-2018}

### Improvements {#improvements-2}

* **[!UICONTROL History]** API已添加到Adobe. IO。它允许您访问与配置文件营销历史记录相关的信息：接触点、发送的递送、镜像页面URL等。For more on this, refer to the [dedicated use case](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#how-to-retrieve-the-mirror-page-for-a-delivery-sent-to-a-profile) .
* **[!UICONTROL Database cleanup]** 为确保数据库备份更好的性能，已优化了技术工作流程。
* Creative Designer for Email现在还提供法语和德语版。

### Other changes {#other-changes-2}

* **[!UICONTROL Compute stats]** 已在发送的分发 **[!UICONTROL Deployment]** 窗口中添加一个按钮。它允许您检索最新KPI，例如，如果发送结果过长，无法更新或尚未考虑。For more on this, refer to this [section](../../sending/using/confirming-the-send.md).
* In the **Update for deliverability** out-of-the-box technical workflow, functional administrators can now define the number of consecutive errors to ignore in the **Update rules** javascript activity. 默认情况下，字段值设置为0，这意味着所有错误都将被忽略。
* 管理单元访问限制条件时生成的SQL已进行优化。
* **[!UICONTROL Update]** 现在，活动允许您添加、更新或删除与订阅相关的数据(nms：appsubscriptionRCP表)。
* **[!UICONTROL Update delivery execution]** 为了优化性能，技术工作流分为两个工作流：- **[!UICONTROL Update delivery execution]**：更新交付的跟踪。默认情况下，每10分钟开始一次。**[!UICONTROL Update delivery indicators]**：更新交付的KPI，默认情况下，它会每小时启动一次。For more on technical workflows, refer to this [section](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* When a delivery is sending messages, the status in the **[!UICONTROL Deployment]** section can now have two values: **[!UICONTROL Sending]**: the messages are being sent. **[!UICONTROL Sending (retry)]**：重试。
* Users with the **[!UICONTROL Delivery preparation]** role are now able to send proofs. (AMP-24313)
* The **Enable TLS over SMPP** option has been added to the **SMS routing via SMPP** external account. For more on this refer to this [section](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

### Patches {#patches-2}

* 修复了在包含来自Adobe Target的动态图像(AMP-24848)时，可防止发送电子邮件的问题。
* Fixed an issue with the **[!UICONTROL Privacy Access/Delete Request]** technical workflows, which did not complete if any of the requests failed.
* 修复了阻止隐私核心服务从Campaign接收请求状态更新的问题。
* Fixed an issue which could prevent the **[!UICONTROL Import shared audience]** technical workflow from working properly (CAMP-25465).
* 修复了在核心隐私服务中将Campaign隐私请求标记为完成的问题。
* 修复了一个问题，该问题可能导致某些用户在Adobe ID过长时无法通过IMS身份验证登录Campaign Standard。(AMP-2095)
* 修复了Creative Designer中删除内容模块时可能出现的问题。(AMP-25242)
* 修复了在数据库中对没有配置文件的订阅者使用推送通知疲劳规则时出现的问题。(AMP-25344)
* 修复了访问提交排除日志时可能显示错误消息的问题。(AMP-24724)
* 修复了阻止在具有延长发送日志的实例中准备校样的问题。
* Fixed two issues that could occur when publishing custom resources with the **[!UICONTROL Sending log]** extension activated.
* 修复了在重复分发期间未考虑到交付持续时间的问题。
* Fixed an issue that could occur when sorting data in the **[!UICONTROL Client data]** menu, for custom resources with more than 100K records. (AMP-24308)
* 修复了在动态报告中使用搜索功能时未考虑到自定义配置文件尺寸的问题。
* 修复了在动态报告中显示帐户级别国际数据的问题。
* 现在，无需订阅或取消订阅确认消息即可创建服务。

## Release 18.5 - May 2018 {#release-18-5---may-2018}

### What's new? {#what-s-new--2}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> GDPR: Core Service Integration<br /> </td> 
   <td> 隐私核心服务集成允许您通过单个JSON API调用在多解决方案上下文中自动执行GDPR请求。<br /> 从隐私核心服务推送到所有Experience Cloud解决方案的GDPR请求现在由Campaign自动处理。<br /> 有关详细信息，请参阅 <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Push improvements - detailed delivery feedback<br /> </td> 
   <td> Adobe Campaign现在可通过MCNS接收提供商(APNS/GCM)推送消息上的详细反馈(发送日志集排除日志)。<br /> 有关详细信息，请参阅 <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery logs extension<br /> </td> 
   <td> 通过提供日志扩展，您可以通过配置文件数据和来自工作流的区段代码扩展发送日志。然后，此信息可在动态报告中使用，并允许您在发送发送时保留一些信息的快照。<br /> 有个使用案例：<br /> 
    <ul> 
     <li> 使用“冻结”数据导出扩展的大会议室：作为营销人员，我希望导出区段代码等于“A”(来自工作流程引擎)的所有配置文件。 </li> 
     <li> Segmentation on "frozen" data: As a marketer, I would like to <strong>retarget</strong> all profiles who have won 1000 loyalty points since the last sending or where segment code was equal to "A". </li> 
    </ul> For more information, refer to the <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamic reporting with Custom profile data<br /> </td> 
   <td> 此功能允许您基于在配置文件资源扩展过程中创建的自定义配置文件数据创建和管理报表。您可以按客户资料属性划分报告，例如忠诚度计划、首选渠道等。<br /> 有关详细信息，请参阅 <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements-3}

* 应用程序的总体内存和CPU使用已得到增强

### Other changes {#other-changes-3}

* 阅读受众工作流程活动现在可以阅读Experience Cloud受众。以前，此活动只能读取查询和列表受众。Refer to the [detailed documentation](../../automating/using/read-audience.md). (AMP-23623)
* 默认共享数据源的标识符现在处于只读模式，无法再更改。在使用Experience Cloud共享受众时，更改此标识符可能会导致某些问题。
* 从Audience Manager导入受众现在可与拆分文件配合使用。以前，只有导入程序的最后一个文件是由ImportSharedAudience技术工作流导入的。
* AWS S外部帐户现在支持区域和第版身份验证机制。Refer to the [detailed documentation](../../administration/using/external-accounts.md).
* 此时，资产选择窗口应更快加载，并允许选择一个资产，然后退出窗口而不会出现任何问题。
* 技术工作流程的属性和结构现在可由具有管理权限且属于“所有”组织和地理单位的用户修改。
* 在创建新区段时，已在分段活动界面中进行了增强：“限制”选项卡现在可在添加限制后直接显示。新区段的名称现已增加(“区段1”、“区段2”等)。
* “nextProcessingDate”字段添加到工作流资源。此字段仅通过REST API调用可见，它允许您在下一个处理日期可视化工作流。
* “sourceID”字段现在跟踪日志资源中公开(nms：trackingLog)。
* “总打开次数”和“总点击次数”值现在可通过工作流导出到平面文件中。(CMS-24186)
* “英语-丹麦语”现在配置文件的首选语言列表中可用。(AMP-23728)
* 将分段活动与其他数据(targetData)链接一起使用时，现在会有一条消息告知您该数据在工作流之外不可用。单击分段活动中的计数或预览按钮时，将显示此消息。(AMP-23651)
* 对工作流使用的磁盘空间进行了增强：(AMP-21979)：默认情况下，“加载文件”活动所处理的文件已被删除。选项允许您将其保留为特定需求。删除工作流后，会自动禁止服务器目录中的专用文件夹。

### Patches {#patches-3}

* 修复了某些原始数据报告事件没有关联的跟踪事件，因为eventDate字段未正确填充的问题。
* 修复了一个问题，该问题导致在推送通知交付的预览窗口中显示个性化字段。
* 修复了一个问题，该问题导致文本无法在预览窗口中将推送通知的消息正文添加为单词。
* 修复了在主目标为空时从工作流发送重新组织分发的问题。
* 修复了如果链接到未存在的架构，阻止访问目标映射的问题。
* 修复了通过文件加载活动导入zip文件时可能发生的问题。(AMP-24309)
* 修复了发送定期分发时导致PostGreQL错误的问题。(AMP-23613)
* 修复了使用空JSON属性发送REST API请求时显示错误消息的问题。(AMP-23506)
* 修复了配置文件中设置为大写字符之后的字符的问题。(AMP-23136)
* 修复了在使用个性化或动态内容块的资格条件时，使用关联的配置文件架构中的属性发送传送的问题。(AMP-22751)
* 修复了阻止删除服务的问题。(AMP-205050)
* 修复了阻止在测试配置文件中更改国家/地区值或状态值的问题。(CMS-20426)
* 修复了可能阻止Creative Designer加载的问题。(AMP-24573)
* 修复了一个问题，该问题导致删除了电子邮件主题中个性化字段后添加的字符。(AMP-24113)

## Release 18.4 - April 2018 {#release-18-4---april-2018}

### Patches {#patches-4}

#### Platform {#platform}

* 修复了可能无法正确处理GDPR访问或删除请求的错误。在某些情况下，提取的数据包含下列字符之一，在某些情况下观察到此行为：&amp;&lt;&gt;”。

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail}

* 修复了如果Broadlog同步用时超过一小时，则会导致KPI被错误值覆盖的问题。

#### Workflows {#workflows}

* 改进了工作流中的内存管理和优化性能。

#### Reporting {#reporting}

* KPI共享工作流现在检索过去个月的交付值，而不是过去个月的发货值。修复了KPI共享外部帐户显示截断日期的问题。
* Fixed an issue which could lead to certain messages not being taken into account in **Sent**, **Delivered** and **Bounce** metrics.
* Fixed an error which occurred when the chosen time range in the **Delivery Summary Report** was too long.

#### Custom resources {#custom-resources}

* 修复了导致自定义资源准备失败的错误。

## Release 18.3 - March 2018 {#release-18-3---march-2018}

### New capabilities {#new-capabilities}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> EU General Data Protection Regulation (GDPR)<br /> </td> 
   <td> GDPR是欧盟(EU)新的隐私法规，旨在协调数据保护要求并在2018年月25日生效。GDPR适用于持有在欧盟存放数据主体数据的Adobe Campaign客户。<br /> 除了Adobe Campaign中已经提供的隐私权功能(包括同意管理、数据保留设置和用户角色)之外，我们还将利用我们作为数据处理者的机会作为数据处理者，以帮助您为特定GDPR请求的数据管理者做好准备：<br /> 
    <ul> 
     <li> 访问权限：允许数据主体接收由数据管理者捕获的其个人数据副本，包括Adobe Campaign中存储的数据。 </li> 
     <li> 删除权利：授权数据主体删除由数据管理者捕获的其个人数据，包括存储在Adobe Campaign中的数据。 </li> 
    </ul> For more information, refer to the <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creative Designer for Email (Beta)<br /> </td> 
   <td> Adobe Campaign的新Creative Designer在Campaign中提供完全集成的创建体验，使您能够快速轻松地创建引人注目的个性化电子邮件，而无需编写任何代码。通过强大的拖放界面，Creative Designer可帮助用户根据空白的幻灯片或模板，帮助扩展电子邮件创建。<br /> 主要功能包括：<br /> 
    <ul> 
     <li> 通过拖放界面以可视方式设计和创建完全个性化的响应式电子邮件，该界面由本机Creative Cloud集成增强 </li> 
     <li> 创建并保存电子邮件内容模板并利用保存的模板来帮助扩展电子邮件创建 </li> 
     <li> 创建和保存内容片段(例如标题、页脚、文章等)简化内容创建过程并确保品牌一致性 </li> 
     <li> 在拖放界面中进行创建并单击按钮的HTML直接编辑电子邮件HTML </li> 
    </ul> Creative Designer for Email仅提供英文版。<br /> 有关详细信息，请参阅 <a href="../../designing/using/about-email-content-design.md#about-the-email-designer">详细文档</a> 并观看此 <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">视频</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Multilingual Push Deliveries<br /> </td> 
   <td> 电子邮件和SMS渠道中已经存在的同一个简单的多语言界面已添加到推送渠道中，帮助您吸引客户不管他们喜欢的语言。<br /> 此功能为管理跨多个区域的推送活动并希望以首选语言定位用户的客户提供可扩展的自动解决方案。它允许您通过一次点击将所有语言变体通过模板电子表格上载到单个推送交付。Adobe Campaign随后根据用户的语言偏好执行自动细分，从而简化工作流程和报告，从而减少冗余。<br /> 有关详细信息，请参阅 <a href="../../channels/using/creating-a-multilingual-push-notification.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Use of Custom Resources in Transactional Messaging<br /> </td> 
   <td> 除了开箱即用字段之外，交易消息现在还允许您使用自定义资源丰富消息内容。<br /> 例如：<br /> 
    <ul> 
     <li> 利用自定义字段作为一个匹配条件，将交易消息与个人资料相匹配 </li> 
     <li> 利用完整的档案、服务和链接数据进一步个性化信息传递信息 </li> 
    </ul> For more information, refer to the <a href="../../administration/using/configuring-transactional-messaging.md">detailed documentation</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-5}

#### Platform {#platform-1}

* 修复了阻止从列表中导出超过5000条记录的问题。
* 修复了将数据导出到使用个性化字段命名的文件时出现的问题。

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-1}

* 修复了导致多部分SMS被截断的问题，因为部分大小以字符而非字节计算。
* Added an option which allows the **[!UICONTROL Delivered]** or **[!UICONTROL Bounces + Errors]** KPIs to be updated in real time after sending your delivery. 从提供商收到的SR(状态报告)中直接重新计算它们。
* 修复了交付调度程序中日历构件的问题。
* 修复了在发送的交付中再次打开目标时显示问题。
* 修复了创建具有延迟发送日期的电子邮件模板时导致请求开始日期的问题。
* 修复了在编辑交付内容时可能导致图像渲染问题的问题。
* 修复了复制营销活动时校样的问题。
* 修复了在向工作流添加分发之后通过导航栏访问系列活动模板时导致错误消息的问题。
* 修复了一个问题，该问题可能会阻止自动选择A/B测试电子邮件的入选方，导致电子邮件无法发送。This behavior could occur if the delivery was in **[!UICONTROL retryInProgress]** state.
* 修复了在重新打开A/B测试电子邮件的参数时出现错误消息的问题。

#### Audiences &amp; queries {#audiences-e-queries}

* 修复了一个问题，该问题导致无法访问数据并为从Adobe Campaign Classic到Standard复制的收件人设置查询。
* Fixed an issue that occurred when using a filter type field in the query editor, after using the **Count** or **Preview** buttons.

#### Workflows {#workflows-1}

* **结帐** 工作流程已经过优化，可缩短交付准备延迟。
* 修复了在使用持续分发活动时阻止在出站过渡中显示人口数据的问题。
* Fixed an issue that prevented reject records from being displayed in a transition after an **Update data** activity.
* Fixed an issue which could cause the **deliverabilityUpdate** technical workflow to fail.

#### Integrations {#integrations}

* 修复了阻止国际字符正确发送到Adobe Analytics的问题。
* 在邮件中尝试插入Experience Cloud资产库中的图像时，资产现在应更快加载。
* 修复了在某些情况下无法关闭资产选择窗口的问题。
* 在数据源详细信息中，您现在可以直接访问其相关工作流以检查工作流的状态。
* 现在，您可以在定义或编辑触发器事件时直接更新触发器架构。在此更改中，您不再必须取消发布触发器并创建另一个触发器。

#### Transactional messages {#transactional-messages}

* 修复了传送资源时带事务消息模板的错误。
* 现在可以删除交易消息。

## Release 18.2 - February 2018 {#release-18-2---february-2018}

### New capabilities {#new-capabilities-1}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Subscription - subscribe or unsubscribe a list of profiles to multiple services<br /> </td> 
   <td> <strong>订阅服务</strong> 工作流活动现在允许您订阅或取消订阅配置文件到多个服务。在工作流中，导入包含配置文件的文件，以及每个配置文件、操作类型和服务。<strong>订阅服务</strong> 活动将能够使用此信息并同时处理所有配置文件订阅和取消订阅。<br /> 有关详细信息，请参阅 <a href="../../automating/using/subscription-services.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Enrichment activity - enrich data based on previous transitions<br /> </td> 
   <td> <span class="uicontrol">新的丰富化</span> 工作流程活动允许您利用入站过渡并利用额外数据完成输出过渡。如果您定位档案，丰富化活动允许您丰富档案信息，这些数据不会存储在数据库中(例如来自导入的文件)中。<br /> 有关详细信息，请参阅 <a href="../../automating/using/enrichment.md">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-6}

#### Platform {#platform-2}

* Adobe Campaign界面的顶栏已使用新的Experience Cloud菜单进行更新。
* Fixed an issue which prevented the link to **[!UICONTROL Offers]** from being displayed in the solution dropdown list.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-2}

* 交付准备阶段已得到增强，可提高性能。
* 修复了若干可能导致跟踪日志损坏的问题。
* 修复了在交付准备和确认之间更改联系日期时发生的联系日期更新问题。现在，当您在准备完成后更改联系人日期时，必须先准备分发，然后才能确认发送。See the [detailed documentation](../../sending/using/preparing-the-send.md).

#### Push notifications {#push-notifications}

* 修复了阻止某些个性化字段在iOS推送通知中工作的错误。
* 修复了在推送通知仪表板中显示点击率和打开率为0%的错误。

#### Reports {#reports}

* 修复了在某些浏览器中将报告列表显示为空的错误。
* Fixed an error that occurred in the **[!UICONTROL Report sharing]** technical workflow just before its expiration limit was reached.

#### Workflows {#workflows-2}

* 修复了在拖放操作后无法访问活动的问题。
* Fixed an issue that could cause the order of output transitions of a **[!UICONTROL Segmentation]** activity to change in some situations.
* 修复了在读取包含枚举类型字段且之前从工作流保存的受众时发生的错误
* Fixed an issue causing the **[!UICONTROL Request confirmation before sending messages]** option to remain checked even after unchecking it when defining the scheduling properties of a delivery created in a workflow.
* Automatic removal of duplicate rows (DISTINCT clause) can now be disabled in **[!UICONTROL Query]** activities, via a new option located in the **[!UICONTROL Additional data]** tab. 出于性能原因定义许多(超过100个)附加元素时，建议禁用此选项。

#### Integrations {#integrations-1}

* **[!UICONTROL Data sources]** 对配置屏幕进行了一些改进。

### Known issues {#known-issues}

我们建议您由于可能出现显示问题而使用Internet Explorer版本11。

在使用Campaign界面中的上下文帮助链接时可能会出现一些问题。它们将在18.3中修复。

## Release 18.1 - January 2018 {#release-18-1---january-2018}

### New capabilities {#new-capabilities-2}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Reporting for Fatigue Management<br /> </td> 
   <td> 疲劳管理报告是专用的、可配置的报告，可显示疲劳规则在发送之前在指定的日期范围内对电子邮件、推送、SMS和直邮渠道提供的影响。通过新增的洞察，可以在一个视图中快速查看所有冲突的营销活动，营销人员可以根据更有效地制定疲劳规则并优先排序来规划营销活动。<br /> 有关详细信息，请参阅 <a href="../../administration/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Report sharing<br /> </td> 
   <td> 通过“报告共享”，您可以将报告与Adobe Campaign用户共享为电子邮件附件，其中包括自动循环。收到重复报告的用户可以通过每封电子邮件中的专用链接取消订阅这些通信。<br /> 有关详细信息，请参阅 <a href="../../reporting/using/reporting-interface.md#share-tab">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Push New capabilities<br /> </td> 
   <td> 推送消息预览-在推送通知内容编辑器中预览iOS和Android设备上的推送通知，以准确查看收件人在测试或执行交付之前将看到的内容。<br /> 有关详细信息，请参阅 <a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">详细文档</a>。<br /> 可用内容-当应用程序未在长时间内打开时，其数据可能会过期。这将在用户最终打开应用程序时更新或替换数据，这会导致使用应用程序延迟。添加了对内容的支持后，Adobe Campaign用户可以在交付推送通知时唤醒其应用程序在后台刷新数据，从而实现更高的一致性和对用户应用程序内体验的控制。<br /> 可自由链接内容-通过新增的Mutable Content支持，Adobe Campaign用户现在可以利用其移动应用程序扩展进一步修改从Adobe Campaign发送的推送通知的内容或演示。For example, users can leverage Mutable Content to: <br /> 
    <ul> 
     <li> 解密以加密格式传送的数据 </li> 
     <li> 下载图像或其他媒体文件，并将其作为附件添加到通知 </li> 
     <li> 更改通知的正文或标题文本 </li> 
     <li> 向通知中添加线程标识符 </li> 
    </ul> For more information on Content Available and Mutable Content, refer to the <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">detailed documentation</a>.<br /><strong>警告：</strong> 这些推送通知的更新要求客户升级其移动应用程序。Refer to <a href="https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html">this technote</a> for more information.<br /> </td> 
  </tr> 
  <tr> 
   <td> Time-zone optimized deliveries<br /> </td> 
   <td> 计划循环电子邮件、SMS和推送通知以在每个收件人的时区的特定天/时间发送，确保在适当的时间发送消息而无需设置多次交付。<br /> 有关详细信息，请参阅 <a href="../../automating/using/scheduler.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> API Signal activity triggering<br /> </td> 
   <td> 现在可以直接从Adobe Campaign Standard API触发工作流程的信号活动。<br /> 有关详细信息，请参阅 <a class="anchorLink" href="https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity" target="_blank">详细文档</a> 。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-7}

#### Platform {#platform-3}

* 配置文件搜索已经过优化，可提高性能。
* 默认安全组的内部标识符现在为标准用户处于只读模式。

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-3}

* 修复了在传送内容中插入表情符号时出现的显示问题。
* 修复了一个问题，该问题允许用户在分发仍处于版本状态时访问发送日志。
* **[!UICONTROL Scheduler]** 活动现在允许您根据收件人的时区发送分发。
* SMS: The option **[!UICONTROL Store incoming MO]** in the database has been added to external accounts. When checked, all incoming SMS will be stored into the **inSMS** table.
* SMS：服务现在附加到活动而不是交易模板。
* SMS：默认的SMTP连接超时减少到30秒。

#### Push notifications {#push-notifications-1}

* 修复了阻止推送通知传送停止的错误。
* 在推送通知高级选项中添加了一个选项，以使用推送通知唤醒应用程序。
* 为推送通知预览视频添加了暂停按钮。
* 推送通知预览现在可用于iPhone、Android、Tablet等不同设备。

   所有渠道

#### Reports {#reports-1}

* 修复了显示率超过100%的错误。
* 修复了阻止用户以CSV下载报告的问题。
* Added a new **[!UICONTROL Report]** item in the homepage.

#### Workflows {#workflows-3}

* 修复了在查询中使用其他数据并添加包含空格的别名时导致错误消息的问题。非字母数字字符现在替换为“_”。
* 修复了在某些情况下可能会停止计算KPI技术工作流的问题。

#### Profiles and audiences {#profiles-and-audiences}

* 修复了在受众查询中添加多个过滤器时出现的错误。
* 修复了更改配置文件图片时出现的显示问题。
* 添加了一个工具提示，它在计数查询的人口后显示准确的结果编号。
* 修复了一个问题，该问题可能导致用户无法选择受众或关闭受众选取器窗口。
* 表达式编辑器中可用函数的列表已更新。**FormatCurrency** 和 **ConvertCurrency** 函数已被删除。

