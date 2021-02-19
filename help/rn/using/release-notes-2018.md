---
solution: Campaign Standard
product: campaign
title: 发行说明 2018
description: 本页列出了所有 2018 版的 Adobe Campaign Standard。
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
translation-type: tm+mt
source-git-commit: a51943e4da04f5d19aaecdfcf956f5c4f3d804c8
workflow-type: tm+mt
source-wordcount: '5402'
ht-degree: 4%

---


# 发行说明 2018{#release-notes}

是否正在寻找Adobe Campaign Standard的特定2018版？

每个版本都提供新功能和修补程序。 单击某个版本可视图其内容。

视图Adobe Campaign Standard的最新[文档更新](../../rn/using/documentation-updates.md)。 如果要查找较新的版本，请查阅此[页面](../../rn/using/release-notes.md)。

## 18.9 版 - 2018 年 9 月{#release-18-9---september-2018}

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
   <td> 应用程序内消息传递使您能够通过提供上下文交互和触及已选择退出推送通知的用户，更有效地吸引移动App用户。 将应用程序内消息传递与推送通知结合使用，创建高度个性化的相关体验。 这样可提高App用户的转化率和保留率。<br /> 有关详细信息，请参阅 <a href="../../channels/using/about-in-app-messaging.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Launch集成（适用于移动应用程序）<br /> </td> 
   <td> Adobe Launch与Adobe Campaign的集成现在使用Mobile SDK V5简化了活动中移动应用程序属性激活的过程并实现了自动化。<br /> 有关详细信息，请参阅 <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**改进**

* Adobe Campaign Standard现在支持Amazon S3 API的版本4。

**其他变更**

* 在广播中，现在在每小时的最大连接数和最大消息数之间有所区别。 当达到这些限制时，就可以知道为什么吞吐量受到限制。 以前，同一消息（“配额满足”）适用于两种情况。
* 在活动中配置移动应用程序时，用户现在可以知道iOS证书和Android服务器密钥是否已成功上载及其过期日期。

   有关详细信息，请参阅有关如何使用[SDK V4](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdkv4.html)和[SDK V5](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdk.html)配置移动应用程序的详细文档。

* 在定义目标属性时，通过选择移动应用程序，在特定移动应用程序上活动用户。 此功能适用于推送和应用程序内消息传递渠道。

   有关详细信息，请参阅[详细文档](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification)。

* 当使用Creative Designer界面选择内容块时，现在将加载并显示来自列表的所有内容块。 (CAMP-27311)

   有关详细信息，请参阅[详细文档](../../designing/using/personalization.md#adding-a-content-block)。

**修补程序**

* 修复了电子邮件仪表板与交易电子邮件的电子邮件摘要报表之间日志计数不一致的问题。 (CAMP-28237
* 修复了工作流中的问题，该问题可能会在通过文件传输活动导入文件时显示错误消息。 (CAMP-27435)
* 修复了包含25个以上服务的登陆页在表单中随机取消选择服务的问题。 (CAMP-26572)
* 修复了在工作流中使用文件传输活动时无法使用SFTP URL配置外部帐户的问题。 (CAMP-26475)
* 修复了无法更新服务摘要报告的问题。 (CAMP-26301)
* 修复了使用工作流活动时，自定义字段无法显示正确日期的问题。 (CAMP-26242)
* 修复了通过文件导入导入时无法更新服务订阅日期的问题。
* 修复了加载文件活动错误，该错误导致工作流无法导入文件(CAMP-27068)。
* 修复了在服务摘要报告中显示错误订阅数的问题(CAMP-25587)。
* 修复了Adobe Analytics和Adobe Campaign报表之间数据不一致的问题。 (CAMP-25393)
* 修复了可能阻止受限访问用户登录的问题。 (CAMP-27381)
* 修复了使用Creative Designer编辑电子邮件时可能无法显示Adobe Experience Manager内容列表的问题。 (CAMP-27181)
* 修复了可能阻止Creative Designer打开并导致错误的问题。 (CAMP-27304)
* 修复了在使用Internet Explorer 11时，拖放功能无法在Creative Designer中正确工作的问题。
* 修复了导致从相机上传的照片以及纵向模式拍摄的照片以不需要的旋转位置显示的问题。
* 修复了在Creative Designer中使用查询编辑器界面时显示选择信息不清晰的问题。
* 修复了在使用Creative Designer中的查询编辑器界面时无法正确复制元素的问题。
* 修复了一个问题，该问题导致即使已通过自动回复取消订阅，仍阻止列表然向收件人发送SMS消息。 (CAMP-27128)
* 修复了无法显示导致&#x200B;**数据库清理**&#x200B;工作流失败的错误的问题。 (CAMP-26876)
* 修复了可能阻止删除推送通知定义中的自定义字段的问题。 (CAMP-25588)

## 18.7 版 - 2018 年 7 月{#release-18-7---july-2018}

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
   <td> Android推送通知的高优先级标志<br /> </td> 
   <td> Android的高优先级标志 — 为Android应用程序提供高优先级的推送通知，这会导致休眠设备唤醒并运行一些有限的处理。 请注意，默认优先级为“正常”，这可能会延迟消息投放以节省电池。 <br /> 有关详细信息，请参阅 <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 针对移动应用程序用户的类型学过滤器<br /> </td> 
   <td> 支持订阅的排版过滤器 — 在为类型规则指定筛选条件时，可以选择订阅作为筛选和定位维度，从而提供对具有或没有用户档案的用户的属性进行筛选的能力。 <br /> 有关详细信息，请参阅 <a href="../../sending/using/about-typology-rules.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 在准备消息<br />期间从URL自动导入内容 </td> 
   <td> 现在，在准备阶段可以从URL导入电子邮件内容。 对于循环电子邮件投放，每次准备邮件时都会检索最新的HTML内容，以确保该内容在发送电子邮件时始终保持最新。 此功能还允许您创建包含URL中内容的计划分发，即使该内容尚未准备好。<br /> 有关详细信息，请参阅 <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 活动发布通知消息<br /> </td> 
   <td> 现在，当用户在实例升级到新版本后登录时，会显示一条弹出消息。 该消息指示版本号，并包含指向发行说明的链接。 您可以选择在下一个版本之前隐藏消息。<br /> </td> 
  </tr> 
  <tr> 
   <td> 用户管理<br /> </td> 
   <td> 现在，新Campaign Standard实例以及没有创建地理单位的现有实例都无法使用地理单位功能，从18.7版本开始。<br /> 有关详细信息，请参阅 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=zh-Hans#release-notes">本页</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**改进**

* Adobe Campaign和Adobe Target集成现在允许您利用目标的[权限](https://docs.adobe.com/content/help/en/target/using/administer/manage-users/enterprise/properties-overview.html)功能。 在电子邮件中包含来自Adobe Target的动态图像时，您现在可以指定目标属性（at_property代码）。
* 具有指向用户档案资源的自定义资源的自定义资源现在由GDPR隐私访问/删除请求考虑。 对于1个基数简单链接和N个基数集合链接，您需要在自定义资源中选择“删除/复制目标记录意味着删除/复制链接引用的记录”。 对于0或1个基数简单链接，选择“删除/复制记录意味着删除/复制链接引用的目标记录”。

**其他变更**

* 报告共享超时已从1分钟增加到4分钟，以避免任何超时错误。
* 编辑电子邮件内容时，默认情况下会打开新的Creative Designer。 如果需要，您仍可以在保存更改后随时返回到默认内容编辑器。 有关详细信息，请参阅[详细文档](../../designing/using/designing-content-in-adobe-campaign.md)。
* 在Creative Designer中，现在可以将新内容组件添加到电子邮件中：旋转木马。 有关详细信息，请参阅[详细文档](../../designing/using/designing-from-scratch.md#about-content-components)。
* 在事务性消息热点单击报告中，单击&#x200B;**更改用户档案**&#x200B;按钮时，现在只列出链接到您为事务性消息定义的事件的测试用户档案。

**修补程序**

* 修复了byEmail查询过滤器无法返回任何结果的问题。 (CAMP-23420)
* 修复了允许标准用户访问受限于管理员的特定功能或屏幕(/rest/head/*终结点、事务消息屏幕、用户档案和受众导入屏幕)的问题。
* 修复了GDPR隐私删除请求在名称以数字开头时无法处理自定义资源的问题。
* 修复了“保存受众”活动无法在Adobe Experience Cloud中共享应用程序订阅者的错误。
* 修复了当文件名包含空格时，“文件传输”活动可能出现的问题。 (CAMP-25936)
* 修复了在会话过期后使用重新连接按钮时可能发生的问题。 (CAMP-25560)
* 修复了在发送具有与疲劳规则关联的时区优化的投放时可能导致排除的问题。 (CAMP-25425)
* 修复了使用API GDPR功能时可能阻止删除带0-1类型链接的数据的问题。
* 修复了在取消疲劳类型规则版本时可能导致错误消息的问题。
* 修复了在编辑投放内容后预览该内容时可能发生的问题。
* 修复了在使用解压缩选项时处理CSV zip文件时可能发生的问题。
* 修复了Creative Designer中的一个问题，该问题导致使用内置样式将某些文本更改为链接或编辑该链接时，出现不需要的颜色字体和格式。 (CAMP-26001)
* 修复了热点单击报表无法在包含动态内容的投放中显示每个条件的百分比的问题。 以前，只显示对默认变体的单击。

## 18.6 版 - 2018 年 6 月{#release-18-6---june-2018}

**改进**

* **[!UICONTROL History]** API已添加到Adobe.IO。 它允许您访问与用户档案营销历史相关的信息：接触点数、已发送投放、镜像页面URL等。 有关详细信息，请参阅[专用用例](../../api/using/interacting-with-marketing-history.md)。
* **[!UICONTROL Database cleanup]**&#x200B;技术工作流已优化，以确保数据库备份的更佳性能。
* Creative Designer for Email现在也提供法语和德语版。

**其他变更**

* 已在已发送投放的&#x200B;**[!UICONTROL Deployment]**&#x200B;窗口中添加&#x200B;**[!UICONTROL Compute stats]**&#x200B;按钮。 它允许您检索最新的KPI，例如，发送的结果需要太长时间才能更新或尚未考虑到。 有关更多信息，请参阅此](../../sending/using/confirming-the-send.md)章节[。
* 在&#x200B;**更新以获得开箱即用的技术工作流中，功能管理员现在可以定义在**&#x200B;更新规则&#x200B;**javascript活动中要忽略的连续错误数。**&#x200B;默认情况下，字段值设置为0，这意味着将忽略所有错误。
* 优化了管理单元访问限制条件时生成的SQL。
* **[!UICONTROL Update]**&#x200B;活动现在允许您添加、更新或删除与订阅相关的数据（nms:appSubscriptionRcp表）。
* 为了优化性能，**[!UICONTROL Update delivery execution]**&#x200B;技术工作流分为两个工作流:- **[!UICONTROL Update delivery execution]**:更新投放跟踪。 默认情况下，每10分钟启动一次。 **[!UICONTROL Update delivery indicators]**:更新投放的KPI，默认情况下每小时启动一次。有关技术工作流的详细信息，请参阅此[部分](../../administration/using/technical-workflows.md#list-of-technical-workflows)。
* 当投放发送消息时，**[!UICONTROL Deployment]**&#x200B;部分中的状态现在可以有两个值：**[!UICONTROL Sending]**:正在发送消息。 **[!UICONTROL Sending (retry)]**:正在进行重试通过。
* 具有&#x200B;**[!UICONTROL Delivery preparation]**&#x200B;角色的用户现在可以发送验证。 (CAMP-24313)
* **通过SMPP**&#x200B;外部帐户向&#x200B;**SMS路由添加了**&#x200B;启用TLS选项。 有关详细信息，请参阅此[部分](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)。

**修补程序**

* 修复了在包含来自Adobe Target的动态图像时，可能会阻止发送电子邮件的问题(CAMP-24848)。
* 修复了&#x200B;**[!UICONTROL Privacy Access/Delete Request]**&#x200B;技术工作流的问题，如果任何请求失败，则该问题未完成。
* 修复了隐私核心服务无法接收请求状态更新的活动问题。
* 修复了可能会阻止&#x200B;**[!UICONTROL Import shared audience]**&#x200B;技术工作流正常工作的问题(CAMP-25465)。
* 修复了阻止活动隐私请求在核心Privacy Service中标记为已完成的问题。
* 修复了在Adobe ID过长时，某些用户无法通过IMS身份验证登录Campaign Standard的问题。 (CAMP-24095)
* 修复了Creative Designer中在删除内容模块时可能出现的问题。 (CAMP-25242)
* 修复了对数据库中没有用户档案的订阅者使用推送通知疲劳规则的问题。 (CAMP-25344)
* 修复了在访问投放排除日志时可能显示错误消息的问题。 (CAMP-24724)
* 修复了在具有扩展发送日志的实例中无法准备验证的问题。
* 修复了在激活&#x200B;**[!UICONTROL Sending log]**&#x200B;扩展时发布自定义资源时可能发生的两个问题。
* 修复了在重复投放中未考虑投放持续时间时可能发生的问题。
* 修复了在&#x200B;**[!UICONTROL Client data]**&#x200B;菜单中对数据排序时，对于具有100K以上记录的自定义资源可能发生的问题。 (CAMP-24308)
* 修复了在动态报表中使用搜索功能时未考虑的自定义用户档案维度问题。
* 修复了在动态报表中显示帐户级别的国际数据的问题。
* 现在，可以创建无需订阅或退订确认消息的服务。

## 18.5 版 - 2018 年 5 月{#release-18-5---may-2018}

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
   <td> 隐私核心服务集成允许您通过单个JSON API调用在多解决方案上下文中自动执行GDPR请求。 <br /> 现在，从隐私核心服务推送到所有Experience Cloud解决方案的GDPR请求由活动自动处理。<br /> 有关详细信息，请参阅 <a href="https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=zh-Hans">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送改进 — 详细的投放反馈<br /> </td> 
   <td> Adobe Campaign现在能够通过MCPNS从提供程序(APNS/GCM)接收推送消息的详细反馈（发送日志和排除日志）。<br /> 有关详细信息，请参阅 <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放日志扩展<br /> </td> 
   <td> 投放日志扩展允许您扩展发送日志，其中包含来自工作流的用户档案数据和段代码。 此信息随后可用于动态报表，并允许您在投放发送时保留某些信息的快照。<br /> 还有2个使用案例：<br /> 
    <ul> 
     <li> 导出包含“冻结”数据的扩展广播：作为营销人员，我希望导出所有段代码等于“A”的用户档案(来自工作流引擎)。 </li> 
     <li> 对“冻结”数据的分段：作为营销人员，我希望<strong>重定位</strong>所有自上次发送以来已赢得1000个忠诚度积分或段代码等于“A”的用户档案。 </li> 
    </ul> 有关详细信息，请参阅<a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 使用自定义报告数据<br />进行动态用户档案 </td> 
   <td> 此功能允许您根据在用户档案资源扩展期间创建的自定义用户档案数据创建和管理报告。 您可以按用户档案属性(如忠诚度项目、首选渠道等)划分报表。<br /> 有关详细信息，请参阅 <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**改进**

* 应用程序的总内存和CPU使用已得到增强

**其他变更**

* “阅读受众”工作流活动现在可以阅读Experience Cloud受众。 以前，此活动只能读取查询和列表受众。 请参阅[详细文档](../../automating/using/read-audience.md)。 (CAMP-23623)
* 默认共享数据源的标识符现在处于只读模式，无法再更改。 更改此标识符可能会导致与Experience Cloud共享受众时出现一些问题。
* 现在，从Audience Manager导入受众可以处理拆分文件。 以前，只有区段的最后一个文件是由importSharedAudience技术工作流导入的。
* AWS S3外部帐户现在支持区域和版本4身份验证机制。 请参阅[详细文档](../../administration/using/external-accounts.md)。
* 现在，资产选择窗口的加载速度应更快，并且允许选择资产，然后退出窗口而不会出现任何问题。
* 拥有管理权限且属于“所有”组织和地理单位的用户现在可以修改技术工作流的属性和结构。
* 在创建新区段时，分段活动界面中已进行了增强：现在，在添加限制后直接显示限制选项卡。 新区段名称现已递增（“区段1”、“区段2”等）。
* “nextProcessingDate”字段将添加到工作流资源。 此字段仅通过REST API调用可见，它允许您可视化工作流的下一个处理日期。
* “sourceId”字段现在显示在跟踪日志资源(nms:trackingLog)中。
* “总打开次数”和“总点击次数”值现在可通过工作流在平面文件中导出。 (CAMP-24186)
* “英语 — Danmark”现在以用户档案语提供“首选语言”列表。 (CAMP-23728)
* 在将分段活动与附加数据(targetData)链接一起使用时，现在会显示一条消息，通知您该数据在工作流之外不可用。 单击分段活动中的计数或预览按钮时，将显示此消息。 (CAMP-23651)
* 已进行增强，以优化工作流使用的磁盘空间：(营21979):现在，默认情况下，“加载文件”活动处理的文件已被删除。 通过某个选项，您可以根据特定需求保留这些资源。 删除工作流后，其专用文件夹会自动从服务器目录中隐藏。

**修补程序**

* 修复了某些原始报告事件由于eventDate字段未正确填充而没有关联跟踪事件的问题。
* 修复了阻止个性化字段显示在推送通知投放的预览窗口中的问题。
* 修复了导致文本无法在预览窗口中自动换行推送通知的消息正文的问题。
* 修复了主投放为空时从工作流发送重新定义目标的问题。
* 修复了当目标映射链接到不存在的模式时无法访问该的问题。
* 修复了通过文件加载活动导入zip文件时可能发生的问题。 (CAMP-24309)
* 修复了在发送循环投放时导致PostgreSQL错误的问题。 (CAMP-23613)
* 修复了在发送REST API请求时显示错误消息的空JSON属性问题。 (CAMP-23506)
* 修复了用户档案中设置为“ß”字符后的字符的问题。 (CAMP-23136)
* 修复了在发送与个性化或动态内容块的资格条件一起使用的投放时，使用链接的用户档案模式中的属性的问题。 (CAMP-22751)
* 修复了无法删除服务的问题。 (CAMP-22050)
* 修复了无法在测试用户档案中更改国家/地区或州值的问题。 (CAMP-20426)
* 修复了可能阻止加载Creative Designer的问题。 (CAMP-24573)
* 修复了删除电子邮件主题中个性化字段后添加的字符的问题。 (CAMP-24113)

## 18.4 版 - 2018 年 4 月{#release-18-4---april-2018}

**修补程序**

_平台_

* 修复了可能无法正确处理GDPR访问或删除请求的错误。 在提取的数据包含下列字符之一的某些罕见情况下，观察到了这种行为：&amp; &lt; > &quot; &#39;。

_电子邮件、短信和直邮_

* 修复了一个问题，该问题可能导致在广播同步时间超过一小时时，KPI被错误值覆盖。

_工作流_

* 改进了内存管理并优化了工作流中的性能。

_报告_

* KPI共享工作流现在检索最近2个月而不是过去6个月的投放值。 修复了KPI共享外部帐户显示截断日期的问题。
* 修复了可能导致某些消息未在&#x200B;**已发送**、**已传送**&#x200B;和&#x200B;**弹出**&#x200B;量度中考虑的问题。
* 修复了在&#x200B;**投放摘要报告**&#x200B;中的选定时间范围过长时发生的错误。

_自定义资源_

* 修复了导致自定义资源准备失败的错误。

## 18.3 版 - 2018 年 3 月{#release-18-3---march-2018}

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
   <td> GDPR是欧洲合并(EU)的新隐私法，旨在协调将于2018年5月25日生效的数据保护要求并使之现代化。 GDPR 适用于所持有数据的数据主体位于欧盟的 Adobe Campaign 客户。<br /> 除了Adobe Campaign中已有的隐私权功能（包括同意管理、数据保留设置和用户角色）之外，我们还将利用此机会作为数据处理者加入其他功能，以帮助您为某些GDPR请求做好准备：<br /> 
    <ul> 
     <li> 访问权：允许数据主体接收由数据控制者捕获的个人数据的副本，可能包括存储在Adobe Campaign中的数据。 </li> 
     <li> 删除权：数据主体有权擦除由数据控制者捕获的个人数据，可能包括存储在Adobe Campaign中的数据。 </li> 
    </ul> 有关详细信息，请参阅<a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Creative Designer for Email（测试版）<br /> </td> 
   <td> Adobe Campaign的新款Creative Designer在活动中优惠了完全集成的创作体验，无需编写任何代码即可快速轻松地创建引人入胜的个性化电子邮件。 无论用户是从空白的石板上开始，还是利用现有内容片段或模板，Creative Designer都通过其强大的拖放界面帮助扩展电子邮件创建。 <br /> 主要功能包括：<br /> 
    <ul> 
     <li> 通过拖放界面以可视方式设计和创建完全个性化的响应式电子邮件，并辅以本机Creative Cloud集成 </li> 
     <li> 创建和保存电子邮件内容模板并利用保存的模板来帮助扩展电子邮件创建 </li> 
     <li> 创建和保存内容片段（如页眉、页脚、文章等） 简化内容创建，确保品牌一致性 </li> 
     <li> 在拖放界面中创建和单击按钮直接编辑电子邮件的HTML之间无缝切换 </li> 
    </ul> Creative Designer for Email只提供英语版。<br /> 有关详细信息，请参阅详细 <a href="../../designing/using/designing-content-in-adobe-campaign.md">文</a> 档并观看此 <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">视频</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 多语言推送投放<br /> </td> 
   <td> 电子邮件和SMS渠道中已经存在相同的简单多语种界面，现已添加到推送渠道中，无论客户喜欢什么语言，都可以帮助您吸引客户。<br /> 此功能为管理跨多个区域的推送活动并希望以其首选语言目标用户的客户优惠了可扩展的自动解决方案。它允许您通过模板化电子表格将所有语言变体上传到单个推送投放，只需单击一次。 然后，Adobe Campaign根据用户的语言偏好执行自动分段，通过简化工作流和报告帮助减少冗余。<br /> 有关详细信息，请参阅 <a href="../../channels/using/creating-a-multilingual-push-notification.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 在事务消息传递中使用自定义资源<br /> </td> 
   <td> 除了开箱即用的字段之外，transactional messaging现在还允许您使用自定义资源丰富消息的内容。<br />例如：<br /> 
    <ul> 
     <li> 利用自定义字段作为协调标准，将事务性消息与用户档案匹配 </li> 
     <li> 利用完整的用户档案、服务和链接数据，进一步个性化事务性消息 </li> 
    </ul> 有关详细信息，请参阅<a href="../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* 修复了无法从列表导出5000个以上记录的问题。
* 修复了将数据导出到使用个性化字段命名的文件时的问题。

_电子邮件、短信和直邮_

* 修复了导致多部分SMS被截断的问题，因为部分大小是以字符而不是字节计算的。
* 添加了一个选项，允许在发送投放后实时更新&#x200B;**[!UICONTROL Delivered]**&#x200B;或&#x200B;**[!UICONTROL Bounces + Errors]** KPI。 直接从从提供者接收的SR（状态报告）中重新计算这些属性。
* 修复了投放调度程序中日历小部件的问题。
* 修复了在已发送目标中再次打开投放时的显示问题。
* 修复了在创建发送日期延迟的电子邮件模板时，导致错误消息请求开始的问题。
* 修复了在编辑投放内容时可能导致图像渲染问题的问题。
* 修复了复制验证时的活动问题。
* 修复了在向工作流中添加活动模板后，通过导航栏访问投放时导致错误消息的问题。
* 修复了可能阻止自动选择A/B测试电子邮件的入选方，导致未发送该电子邮件的问题。 如果投放处于&#x200B;**[!UICONTROL retryInProgress]**&#x200B;状态，则可能发生此行为。
* 修复了在重新打开A/B测试电子邮件的参数时可能导致显示错误消息的问题。

_受众和查询_

* 修复了无法访问数据和为从Adobe Campaign Classic复制到Standard的收件人设置查询的问题。
* 修复了在使用&#x200B;**Count**&#x200B;或&#x200B;**预览**&#x200B;按钮后在查询编辑器中使用筛选器类型字段时出现的问题。

_工作流_

* **帐单**&#x200B;工作流已优化以改进投放准备延迟。
* 修复了在使用循环过渡活动时阻止在出站投放中显示人口数据的问题。
* 修复了在&#x200B;**更新数据**&#x200B;过渡后阻止拒绝记录在活动中显示的问题。
* 修复了可能导致&#x200B;**deliverabilityUpdate**&#x200B;技术工作流失败的问题。

_集成_

* 修复了无法将国际字符正确发送到Adobe Analytics的问题。
* 现在，当尝试在消息中插入Experience Cloud资源库中的图像时，资源的加载速度应更快。
* 修复了在某些情况下阻止关闭资产选择窗口的问题。
* 从数据源详细信息中，您现在可以直接访问其相关工作流以检查工作流的状态。
* 您现在可以在定义或编辑触发器模式时直接更新触发器事件。 通过此更改，您不再需要取消发布触发器并创建另一个触发器。

_事务型消息传递_

* 修复了扩展事务性消息模板资源时出现的投放错误。
* 现在可以删除事务性消息。

## 18.2 版 - 2018 年 2 月{#release-18-2---february-2018}

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
   <td> 订阅 — 订阅或取消订阅多项服务的列表用户档案<br /> </td> 
   <td> <strong>订阅服务</strong>工作流活动现在允许您订阅或取消订阅列表多项服务。 在您的工作流中，导入包含用户档案的文件，并针对每个用户档案、操作类型和服务。 <strong>订阅服务</strong>活动将能够使用此信息并同时动态处理所有用户档案订阅和退订。<br /> 有关详细信息，请参阅 <a href="../../automating/using/subscription-services.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 扩充活动 — 根据以前的过渡<br />丰富数据 </td> 
   <td> 新的<span class="uicontrol">扩充</span>工作流活动允许您利用入站过渡并使用其他数据完成输出过渡。 如果您目标用户档案，则扩充活动允许您使用未存储在数据库中的其他数据（例如，来自导入的文件）来丰富用户档案信息。<br /> 有关详细信息，请参阅 <a href="../../automating/using/enrichment.md">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* Adobe Campaign界面的顶栏已使用新的Experience Cloud菜单更新。
* 修复了阻止指向&#x200B;**[!UICONTROL Offers]**&#x200B;的链接显示在解决方案下拉列表中的问题。

_电子邮件、短信和直邮_

* 投放准备阶段已经增强以改进性能。
* 修复了在某些特殊情况下可能导致跟踪日志损坏的几个问题。
* 修复了在投放准备和确认之间更改联系日期时发生的联系日期更新问题。 现在，当您在准备后更改联系日期时，您需要重新准备投放，然后才能确认发送。 请参阅[详细文档](../../sending/using/preparing-the-send.md)。

_推送通知_

* 修复了导致某些个性化字段无法在iOS推送通知中工作的错误。
* 修复了在推送通知仪表板中将点击率显示为0%并打开率的错误。

_报告_

* 修复了在某些浏览器中显示报表列表为空的错误。
* 修复了在&#x200B;**[!UICONTROL Report sharing]**&#x200B;技术工作流达到其过期限制前发生的错误。

_工作流_

* 修复了在拖放活动后无法访问这些应用程序的问题。
* 修复了在某些情况下可能导致&#x200B;**[!UICONTROL Segmentation]**&#x200B;活动的输出过渡顺序发生更改的问题。
* 修复了读取包含明细列表类型字段且之前已从工作流中保存的受众时出现的错误
* 修复了在定义在工作流中创建的投放的调度属性时，即使取消选中&#x200B;**[!UICONTROL Request confirmation before sending messages]**&#x200B;选项后，该选项仍会保持选中的问题。
* 现在，可以通过&#x200B;**[!UICONTROL Additional data]**&#x200B;选项卡中的新选项在&#x200B;**[!UICONTROL Query]**&#x200B;活动中禁用自动删除重复行（DISTINCT子句）。 出于性能原因，在定义许多（超过100个）附加元素时，建议禁用此选项。

_集成_

* 对&#x200B;**[!UICONTROL Data sources]**&#x200B;配置屏幕进行了一些改进。

_已知问题_

由于可能存在显示问题，建议您不要使用Internet Explorer 11版。

使用活动界面中的上下文帮助链接时可能会出现一些问题。 它们将在18.3中固定。

## 18.1 版 - 2018 年 1 月{#release-18-1---january-2018}

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
   <td> 疲劳管理报告是一份专用的可配置报告，显示疲劳规则对发送前指定日期范围内的电子邮件、推送、短信和直邮渠道投放的影响。 通过增加的洞察，即能够在一个视图中快速查看所有冲突活动，营销人员可以根据疲劳规则更有效地制定营销活动计划，并排定沟通的优先级。<br /> 有关详细信息，请参阅 <a href="../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 报告共享<br /> </td> 
   <td> “报告共享”允许您以电子邮件附件的形式与Adobe Campaign用户共享报告，包括自动循环。 收到重复报告的用户可以通过每封电子邮件中的专用链接取消订阅这些通信。<br /> 有关详细信息，请参阅 <a href="../../reporting/using/reporting-interface.md#share-tab">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送新功能<br /> </td> 
   <td> 推送消息预览 — 在iOS和Android设备上，从推送通知内容编辑器中预览推送通知，以准确了解收件人在测试或执行投放之前将看到的内容。<br />有关详细信息，请参阅<a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">详细文档</a>。<br /> 可用内容 — 当应用程序在更长的时间内未打开时，其数据可能会过时。这会导致用户在最终打开应用程序时必须更新或替换数据，这可能会导致使用应用程序时出现延迟。 借助“可用内容”的额外支持，Adobe Campaign用户可以在发送推送通知时唤醒其应用程序以在后台刷新其数据，从而提高用户应用程序内体验的一致性和控制度。<br /> 可变内容 — 借助可变内容的新增支持，Adobe Campaign用户现在可以利用其移动应用程序扩展进一步修改从Adobe Campaign发送到达的推送通知的内容或演示。例如，用户可以利用可变内容执行以下操作：<br /> 
    <ul> 
     <li> 解密以加密格式传送的数据 </li> 
     <li> 下载图像或其他媒体文件，并将它们作为附件添加到通知 </li> 
     <li> 更改通知的正文或标题文本 </li> 
     <li> 向通知添加线程标识符 </li> 
    </ul> 有关“可用内容”和“可变内容”的详细信息，请参阅<a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">详细文档</a>。<br /> <strong>警告：推</strong> 送通知的这些更新要求客户升级其移动应用程序。有关详细信息，请参阅<a href="https://helpx.adobe.com/cn/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html">此技术说明</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 时区优化投放<br /> </td> 
   <td> 计划循环电子邮件、短信和推送通知将在每个收件人时区的特定日期/时间发送，确保您的消息在适当的时间发送，而无需设置多个投放。 <br /> 有关详细信息，请参阅 <a href="../../automating/using/scheduler.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> API信号活动触发<br /> </td> 
   <td> 现在可以直接从Adobe Campaign Standard API为工作流触发信号活动。<br /> 有关详细信息，请参阅 <a href="/help/api/using/triggering-a-signal-activity.md">详细文档</a> 。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* 用户档案搜索已优化，以提高性能。
* 对于标准用户，默认安全组的内部标识符现在处于只读模式。

_电子邮件、短信和直邮_

* 修复了在投放内容中插入表情符号时出现的显示问题。
* 修复了允许用户在投放仍在版本中时访问发送日志的问题。
* **[!UICONTROL Scheduler]**&#x200B;活动现在允许您根据收件人的时区发送投放。
* 短信：数据库中的选项&#x200B;**[!UICONTROL Store incoming MO]**&#x200B;已添加到外部帐户。 选中后，所有传入的SMS都将存储到&#x200B;**inSMS**&#x200B;表中。
* 短信：服务现在附加到事件而不是事务模板。
* 短信：默认SMTP连接超时已减少到30秒。

_推送通知_

* 修复了阻止推送通知投放停止的错误。
* 在推送通知中添加了一个选项，用于通过推送通知唤醒应用程序。
* 为推送通知预览视频添加了暂停按钮。
* 推送通知预览现可用于iPhone、Android、平板电脑等不同设备。

_报告_

* 修复了显示率超过100%的错误。
* 修复了用户无法以CSV格式下载报表的问题。
* 在主页中添加了新的&#x200B;**[!UICONTROL Report]**&#x200B;项。

_工作流_

* 修复了在查询中使用其他数据并添加包含空格的别名时导致错误消息的问题。 非字母数字字符现在替换为“_”。
* 修复了在某些情况下，技术工作流计算KPI在默认情况下可以停止的问题。

_用户档案和受众_

* 修复了在受众查询中添加多个过滤器时发生的错误。
* 修复了更改用户档案图片时出现的显示问题。
* 添加了一个工具提示，显示在计算查询的填充数后的确切结果编号。
* 修复了可能阻止用户选择受众或关闭受众选取器窗口的问题。
* 表达式编辑器中可用函数的列表已更新。 **FormatCurrency**&#x200B;和&#x200B;**ConvertCurrency**&#x200B;函数已被删除。

