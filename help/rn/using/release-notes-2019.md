---
title: 发行说明 2019
description: 本页列表了所有2019版Adobe Campaign标准版。
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
source-git-commit: a1bc9d23163d12517c4501a572fc92aac6aacbc6

---


# 发行说明 2019{#release-notes-2019}

[发布计划](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) |控 [制面板版本](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) |文 [档更新](../../rn/using/documentation-updates.md) |最 [新发行说明](../../rn/using/release-notes.md) |已弃 [用功能](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

## 19.4版- 2019年12月 {#release-19-4---october-2019}

**新增内容?**

<table> 
 <thead> 
  <tr> 
   <th> <strong>加利福尼亚消费者隐私法(CCPA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>CCPA是加利福尼亚州新的隐私法，它使2020年1月1日生效的数据保护要求协调并现代化。 CCPA适用于持有居住在加利福尼亚的数据主体数据的Adobe Campaign客户。</p>
   <p>除了Adobe Campaign中已有的隐私权（包括同意管理、数据保留设置和用户角色）外，我们还将利用此机会加入其他功能，以帮助您做好CCPA准备：</p>
   <ul>
    <li>访问权和删除权：我们正在利用为GDPR添加的功能。 <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#righttoaccess">了解更多</a> </li>
    <li><p>创建隐私请求时，隐私核心服务中已添加规章类型（GDPR或CCPA）。 此方法是您应用于所有访问和删除请求的方法。 不建议使用活动API和接口访问和删除请求。  请参阅已弃 <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">用和已删除功能文章</a>。</p></li>
    <li>已 <strong>向用户档案资源添加CCPA退出字段</strong> ，以允许Adobe Campaign用户跟踪消费者是否选择退出销售个人信息。 <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#ccpa">了解更多信息</a>。</li>
  </ul>
    <p>请参阅 <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">操作方法视频</a>。</p>
</td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Microsoft Dynamics 365集成(GA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 
    <p>Adobe Campaign标准版与Microsoft Dynamics 365之间的集成现已推出。 您将能够将联系人和自定义实体记录从Dynamics 365传输到活动，并将电子邮件事件数据从活动传回到Dynamics 365，以便更好地协调销售／营销。</p>
    <p>请参阅详 <a href="../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md">细文档</a> ，设置此集成并视图 <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/integrating/microsoft-dynamics365-connector/introduction.html">操作方法视频</a>。</p>
  </td>
  </tr> 
 </tbody> 
</table>

**改进**

* 动态报告的同意弹出窗口已更新，以包含Adobe Campaign标准版和Microsoft Dynamics 365集成。 接受条款后，在使用用户档案标准/Microsoft Dynamics 365集成和动态报告时，将包含Adobe Campaign数据。 [阅读更多](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) (CAMP-29766)
* 修复了在接收投放通知时显示错误联系日期的问题。
* 当事务性消息事件提交时，其上下文参数未知，活动现在会返回“400”错误消息，而不是“500”。 (CAMP-28632)
* 新的“ **排除验证** ”区段已添加到动态报告中。 现在，默认情况下已选择此区段以过滤您的报表。 [阅读更多](../../reporting/using/list-of-components-.md#segments)
* 消息 **到期选项** (Message expiration)已添加到推送通知中。 它允许您指定消息不再由Apple(APNS)或Android(FCM)发送的到期日期。 [阅读更多](../../channels/using/customizing-a-push-notification.md#add-expiration-date)
* 对加载文件活动 **进行了改进** :工作流日志已更清晰，并且更详细地介绍了在文件加载失败时发生的错误。 激活“在文件中保留拒绝” **选项时生成的出站过渡** ，已更名为“拒 **绝”**。 [阅读更多](../../automating/using/load-file.md)
* 已将多语言相关日志添加到发送日志中，以便更好地了解由于上传的CSV文件中缺少语言导致的发送失败。

**安全增强**

* 修复了通过隐私请求删除量化用户档案信息时的一个问题，该问题删除了隔离列表中除电子邮件地址之外的所有数据。
* 增强了安全性，防止在电子邮件标头中注入内容。
* 已增强安全性，以防止SSRF攻击，其中可以使用xtk表达式（电子邮件HTML、文本内容和主题、SMS和推送通知内容）。

**Email Designer增强功能**

* 修复了在电子邮件中插入退订、订阅和登陆页链接时无法跟踪的问题。 (CAMP-37809)
* 修复了在创建新电子邮件和选择模板时可能导致错误的问题。 (CAMP-38000)
* 使用电子邮件设计器编辑链接时，您现在可以使用“下划线 **”链接选项** 。 此外，还添 **加了目标** ，其默认值设置为“无” ****。 [阅读更多](../../designing/using/styles.md#about-styling-links)
* 修复了电子邮件正文中文本组件链接的颜色问题。 (CAMP-37330)
* 修复了删除图像时无法删除关联链接的问题。 (CAMP-37234)
* 修复了在某个条件下无法保存对动 **态内容** “顺序”设置的修改的问题。 (CAMP-36883)
* 修复了搜索登陆页时的问题。 搜索从最初创建的50个扩展到所有数据库。 (CAMP-36839)
* 修复了在发件人中保存电子邮件发送者的修改时 **的问题：名称** 字段。 (CAMP-36606)
* 传送组件兼容性警告已修改，以反映支持的电子邮件客户端。
* 修复了移动设备上的显示问题。 height属性现在始终设置为“height:自动”。 (CAMP-35497)
* 修复了从结构组件中删除片段时HTML中保留样式和meta标签的问题。 (CAMP-35390)
* 修复了更新可重用内容时片段的问题。 (CAMP-35186)
* 修复了在电子邮件中仅显示移动条件内容时的问题。 (CAMP-35155)
* 修复了随机显示零宽不间断空格的问题。 (CAMP-35116)
* 修复了“另存为片段”对话框中按钮 **的位置问题** 。
* 修复了在图像标题和替代文本中添加HTML标记时的预览问题。
* 修复了在电子邮件设计器中编辑在旧版编辑器的电子邮件中创建的链接时出现的问题。
* 修复了在内容中留下重复样式标记的问题。
* 修复了在电子邮件中插入个性化字段时日期格式的问题。
* 修复了从HTML模式切换为纯文本时的保存问题。
* 修复了单击“锁定并解锁”选项时在内联样式属性面板中添加边距值的问题。
* 修复了移动预览的大小问题，以便更好地进行渲染。
* 修复了模板和片段中按钮的大小问题。
* 修复了在按钮组件中插入图像时图像大小的问题。

**其他更改**

* 在投放KPI页面和动态报告页面上显示数据的默认时间范围已对齐，以防止报告结果出现差异。 (CAMP-35148)
* 应用程序证书过期时，日志中已添加一条错误消息。
* 有效负荷计算预览现在包括自定义字段大小以防止推送通知失败。 (CAMP-35303)
* 现在，可以 **像“文件导出** ”活动一样，个性化“加载文件 **”活动中的“拒绝”文件** 的名称 **** 。
* 所有未链接到任何现成实体的自定义实体现在都可以通过API进行访问。
* 改进了大型资源上的数据库性能。
* 对发送SMS消息时出现的一些错误的描述已更清晰。 (CAMP-36558)
* 现在，在执行直接或通过多个调度程序连接到自身的工作流的 **活动** 活动时，会显示一条错误消息，因为这可能导致实例的工作流服务器卡住。
* 已做出改进，以帮助对事务性消息进行疑难解答：“数据”链接在事件配置屏幕中已更名为“最后一个交易事件”，它现在按降序列表接收的事件。 此外，还创建了新的交易事件状态：“targetingFailed”。 当事务消息传递模块无法扩充用于消息定位的链接时，事务事件现在将处于此新状态（而不是“routingFailed”状态）。
* 在限制登陆页访问特定地理或组织单位时，界面已得到改进。 其目的是警告登陆页可能受可见性条件的影响：现在，在创建登陆页时必须选择地理和组织单位。 选择设备后，现在会显示包含相关信息的横幅。 测试登陆页时显示的错误消息已更清晰。
* 在Campaign StandardAPI中，如果键值与来源键不同，或者您使用自己的业务键作为URI而不是Adobe提供的业务键，则无法使用PATCH操作修改自定义键。
* &quot;阿尔巴尼亚语——马其顿语&quot;已加入首选语言下拉列表。 (CAMP-35396)

**修补程序**

* 修复了阻止对计划报表进行排序或搜索的问题。
* 修复了触发器规则导致AND和OR规则混淆的问题。
* 修复了在启动项中将“移动”属性显示为“已删除”的问题。 (CAMP-35382)
* 修复了阻止Adobe Launch移动属性在Adobe Campaign中同步的问题。 (CAMP-35411、CAMP-35089、CAMP-35014、CAMP-35487)
* 修复了当事件丰富了用户档案数据时，事务推送消息失败的问题。 (CAMP-34385)
* 修复了移动属性无法在多个环境上同步的问题。 (CAMP-37060)
* 修复了在推送通知中使用联系人日期公式选择模板时的问题。 (CAMP-35300)
* 修复了可能导致消息发送服务崩溃的问题。 (CAMP-35287)
* 修复了循环直接电子邮件的问题，这些问题都是在第一个事件日期定义的。 (CAMP-35139)
* 修复了新扩展的 **用户档案** 自定义资源不适用于查询的问题。 (CAMP-35119)
* 修复了激 **活了共享配置的实例的** “修复”数据库结构模式。 (CAMP-35118)
* 修复了在广播上添加聚合数据时导致SQL日志错误的问题。 (CAMP-35034)
* 修复了创建分段过渡时的 **活动问** 题。 (CAMP-35033)
* 修复了 **查询** 活动中的一个问题，该问题导致 **encryption_aescbcDecrypt函数无法解密** encryption_aescbcEncrypt函数 **** 。 (CAMP-34952)
* 修复了一个问题，该问题可能会阻 **止跟踪日志** 在投放中显示。 (CAMP-34855)
* 修复了使用发送时间优化自定义日期公式时的一个问题，该问题可能会防止由于工作流的其他数据出现错误而发送推送通知。 **** (CAMP-30336)
* 修复了可能阻止发布自定义资源的问题。 (CAMP-37425)
* 修复了管理员用户无法修改导入包的问题。  (CAMP-37176)
* 修复了工作流中的一个问题，该问题导致当投放活动连接到空的读取受众活动时，该验证无法 **发送** 。 (CAMP-37164)
* 修复了自定义资源无法导入到新环境的问题。 (CAMP-36506)
* 修复了热点单击报告中可能导致百分比被图像隐藏的问题(CAMP-36407)
* 修复了尝试导出投放描述字段时出现的问题。 (CAMP-35467)
* 修复了在投放完成后可能将开始状态保留为“待处理”的问题。 (CAMP-35355)
* 修复了在启用SQL日志后再禁用SQL日志后无法显示工作流日志的问题。

## 19.3版- 2019年7月 {#release-19-3---july-2019}

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
   <td> 外部API活动（公共测试版）<br /> </td> 
   <td> <p>为了实现更深入的个性化，外部API活动允许您通过REST API调用将外部系统的数据引入工作流中。 REST端点可以是客户管理系统、Adobe I/O Runtime或Adobe Experience Cloud REST端点(例如，数据平台、目标、分析、活动)。</p><p>此功能当前为公共测试版。</p><p>有关详细信息，请参 <a href="../../automating/using/external-api.md">阅详细文档</a><a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">和操作方法视频</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 关于工作流区段的报告<br /> </td> 
   <td> <p>此功能允许营销人员按投放细分其段代码绩效。 当您创建工作流并使用分段活动将区段分配给投放群时，这些区段现在可以进入相同的投放。 这允许您根据单个投放中的多个区段显示打开／单击统计信息。</p><p>有关详细信息，请参 <a href="../../reporting/using/creating-a-report-workflow-segment.md">阅详细文档</a><a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">和操作方法视频</a>。</p></td>
  </tr> 
 </tbody> 
</table>

**安全增强**

* 修复了一个安全问题，以防止拒绝服务(DoS)攻击获取图像的无效请求。 (CAMP-33454)

**Email Designer增强功能**

* 修复了每次添加组件时都会向HTML模板添加其他HTML样式标记的问题，该问题可能会大大增加模板的大小。 (CAMP-34694)
* 修复了阻止某些右上方工具栏菜单选项可用的问题。 (CAMP-34577)
* 修复了将镜像页面URL内容块插入电子邮件内容时发生的问题。 (CAMP-34779)
* 修复了在电子邮件中使用JSPP代码时出现的问题，使内容难以编辑。 (CAMP-34574)
* 修复了在向图像添加超链接时导致图像顶部截断的问题。 (CAMP-34382)
* 修复了在Firefox中使用电子邮件设计器时的显示问题。 (CAMP-34364)
* 修复了在电子邮件中定义动态内容时“高级”模式出现的几个问题。 (CAMP-34351, CAMP-34333, CAMP-34331)
* 修复了动态内容规则编辑器(CAMP-34304、CAMP-34303)出现的几个问题。
* 修复了“电子邮件设计器设置”窗格中无法显示“链接”字段的问题(CAMP-33749)。
* 修复了已发送电子邮件中超大的YouTube图标问题。 (CAMP-33726)
* 修复了使镜像页面内容可编辑的安全问题。 (CAMP-33691)
* 修复了在动态内容中使用大于符号时中断HTML输出的问题。 (CAMP-33688)
* 修复了在电子邮件设计器中编辑文本时使用“撤消”选项时出现的问题。 (CAMP-32565)
* 修复了在撤消样式而不是删除样式时创建额外标记的问题。 (CAMP-32359)
* 您现在可以定义电子邮件中使用的每个组件是否只显示在桌面设备上或仅在移动设备上显示。
* 您现在可以设置社交内容组件的宽度和高度。
* 修复了删除动态内容后无法删除动态内容旧源代码的问题。
* 修复了在电子邮件主题被修改后无法更新的问题。
* 修复了将n:n列结构放入工作区后无法选择的问题。
* 修复了导致邮件缩略图在电子邮件仪表板中显示模糊的问题。
* 修复了一个问题，该问题导致Outlook中收到的电子邮件无法正确显示背景。
* 修复了电子邮件设计器主页上的某些排序问题。
* 修复了在使用动态内容时复制变体时出现的问题。
* 从“电子邮件设计器设置”窗格中删除了一些不需要的字段。

**其他改进**

* 通过与Adobe Experience Platform Location Services的集成，Adobe Campaign现在兼容，可通过Experience Platform SDK向移动应用程序的订户发送基于位置的营销消息。 有关详细信息，请参阅详 [细文档](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md)。
* 报告功能已得到改进，以获得更好的体验。 要使用此功能，您需要接受动态报告使用协议。 有关详细信息，请参阅详细 [文档](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。
* 在工作流中，新增了一个选项以预览工作流的接下来十个执行。 有关详细信息，请参阅详细 [文档](../../automating/using/scheduler.md)。
* 在调度程序活动中，新选项允许您为月度投放选择特定周的特定日期。 有关详细信息，请参阅详细 [文档](../../automating/using/scheduler.md)。
* 在创建没有聚合期的重复投放时，投放仪表板现在允许您在发送投放之前请求确认。 有关详细信息，请参阅详细 [文档](../../sending/using/confirming-the-send.md)。
* 您现在可以使用已在工作流的外部信号投放中声明的事件变量个性化活动的标签。 有关详细信息，请参阅详细 [文档](../../automating/using/calling-a-workflow-with-external-parameters.md)。
* GDPR删除查询已得到改进，以获得更好的性能。 (CAMP-33504)
* “ftp”选项已从外部帐户配置界面中删除。 (CAMP-34472)
* 您现在可以为每封电子邮件启用或禁用SMTP测试模式选项。 有关详细信息，请参阅详细 [文档](../../administration/using/configuring-email-channel.md#smtp-test-mode)。 (CAMP-34602)

**其他更改**

* 在投放属性界面中添加了警告。 它指定投放根据其聚合期准备，并解冻以每天多次调用工作流，您应确保它们没有任何期间。 (CAMP-34393)
* 自定义资源配置屏幕中已添加警告。 我们建议对自定义资源ID使用最多30个字符。 这也适用于自定义资源字段、键、索引和链接。
* 现在，在尝试删除事务性消息时，登陆页会将其用作确认消息。
* 当工作流运行超过6小时时，活动日志中现在显示警告。 这不适用于推送通知、投放、信号、开始、结束、分叉、AND-joint、计划和等待活动。
* 当您达到同时运行的最大工作流数时，工作流日志中现在会显示一条警告消息。
* 已暂停或失败状态超过7天的工作流现在将停止，以消耗较少的磁盘空间。 清理任务显示在工作流日志中。
* 当使用“传输文件”活动时，如果文件大小超过可用磁盘空间，则现在会记录错误。
* 无法再为应用程序内消息中的辅助按钮选择重定向到目标URL操作。

**修补程序**

* 修复了可能导致GDPR访问请求失败的问题。
* 修复了在为唯一用户档案接收多个触发器时可能导致触发器被丢弃的问题。
* 修复了在登录后可能导致错误的自定义资源发布错误消息的问题。
* 修复了在创建或扩展自定义资源时显示空白页面的问题。
* 修复了阻止将appSubscriptionrcp作为受众的定位维度在移动投放中用于定位的问题。
* 修复了阻止将电子邮件地址硬弹回的错误。 (CAMP-24587)
* 修复了在添加类型规则，然后在保存排版之前删除该字体时出现的问题。 (CAMP-32789)
* 修复了在禁用动态内容时可能无法显示登陆页内容的问题。 (CAMP-32924)
* 修复了在主投放属性上使用个性化时出现的重复投放问题。 (CAMP-32983)
* 修复了工作流中的一个问题，该问题导致无法从包含传入SMS消息数据的过渡读取结果。 (CAMP-33134)
* 修复了在组合分叉和排除工作流以创建受众时出现的活动问题。 (CAMP-33401)
* 修复了一个问题，该问题可能会阻止显示镜像页面内容，并阻止为重复投放发送验证消息。 (CAMP-33413)
* 修复了在合并和受众之间使用活动时导致错误的问题。 此问题是由于输入过渡中标识键不兼容造成的。 (CAMP-33713)
* 修复了测试活动中的一个问题，该问题导致“recCount”表达式在多次单击时无法使用正确的语法。 (CAMP-33756)
* 修复了在打开付费技术工作流日志时可能导致错误消息的问题。 (CAMP-34313)
* 修复了在登陆页中配置复选框字段时可能出现的问题。 (CAMP-34369)
* 修复了在配置列表并向其添加“图标”字段时发生的问题。 (CAMP-34585)
* 修复了在加载文件工作流活动中无法将“|”和“%”符号用作日期或时间分隔符的问题。 (CAMP-34706)
* 修复了在登陆页中将可见性条件与复选框结合使用时出现的问题。 (CAMP-34802)
* 修复了扩充活动中的一个问题，该问题导致将过滤维度设置为跟踪日志，将目标维设置为用户档案时，字段无法显示在“附加数据”选项卡中。
* 修复了导出“workflowTemplate”资源时导致错误消息的问题。
* 修复了创建新用户档案时，如果从对话框中选择“国家／地区代码”字段，则无法保存该字段的问题。
* 修复了使用“直邮”导入模板(updateQuarinesDeliveryLogsDirectMail)时发生的几个问题。
* 修复了与资产（按需）集成相关的问题。
* 修复了在时间轴视图上放大时出现的问题。 (CAMP-33628)
* 修复了阻止验证在预定日期和时间即时发送电子邮件的问题。 (CAMP-33723)
* 修复了与用户注销时生成错误日志的事务性消息传递相关的问题。 (CAMP-31698)
* 修复了计划电子邮件时可能在特定环境上发生的错误。
* 修复了导致更新投放执行工作流失败的问题。
* 修复了主题包含多行时导致电子邮件内容中断的安全问题。


## 19.2.7版- 2019年7月 {#release-19-2-7---july-2019}

**改进**

* GDPR删除查询已得到改进，以获得更好的性能。
* 修复了在19.2升级后可能导致Web崩溃的问题。 (CAMP-34862)
* 修复了可能阻止非管理员用户保存或计划报告的问题。 (CAMP-31133)
* 修复了在加载文件工作流活动中将“|”用作日期分隔符时的问题。 (CAMP-34706)

## 19.2.4版- 2019年6月 {#release-19-2-4---june-2019}

**电子邮件设计人员**

* 修复了在HTML中使用空样式标签时用户无法编辑片段的问题。 这是19.2.3中CAMP-33778的后续修复。

## 19.2.3版- 2019年6月 {#release-19-2-3---june-2019}

**电子邮件设计人员**

为优化19.2版本中的片段引入了一系列改进和修复。 新创建的片段将无缝工作。 先前构建的片段已灰显，需要迁移到新格式。 为此，请单击每个片段并验证其迁移到新格式。 我们建议您先测试几个片段，然后再迁移所有片段。

* 修复了在解锁片段后阻止用户编辑片段的问题。 在更新到19.2时，这会影响现有片段。 (CAMP-33778)
* 修复了使用动态内容时的问题。 HTML中增加了额外的空格。

**其他改进**

* 修复了在SMS连接器断开后，SMS发送无法恢复的问题。
* 修复了启用TLS时可能关闭SMPP连接的问题。
* 修复了启用TLS时可能关闭SMPP连接的问题。
* 在活动中添加了“Launch_URL_活动”选项，以管理使用Adobe Experience Platform Mobile SDK创建的移动应用程序的属性。
* 修复了在上传新创建的移动属性的证书并退出移动应用程序属性页面后导致“沙箱环境”选项未选中的错误。
* 修复了一个问题，该问题导致您无法使用来自服务资源的信息丰富事务性消息内容。 (CAMP-33707)
* 修复了在试图从服务中取消订阅登陆页时黑名单用户档案中出现的问题。

## 版本19.2 - 2019年5月 {#release-19-2---may-2019}

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
   <td> 控制面板<br /> </td> 
   <td> <p>为了帮助提高管理员用户的工作效率，您可以轻松监控容量并管理实例的设置（从SFTP服务器管理开始）。</p><p>有关详细信息，请参 <a href="https://docs.adobe.com/content/help/en/control-panel/using/control-panel-home.html">阅详细文档</a><a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/control-panel/control-panel-overview.html">和操作方法视频</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 本地通知<br /> </td> 
   <td> <p>本地通知消息允许您在用户的移动应用程序中有新数据可用时通知用户，即使没有访问Internet或前台运行的移动应用程序的权限。 本地通知由移动应用程序在特定时间触发，具体取决于事件。</p><p>有关详细信息，请参阅详 <a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">细文档</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 工作流增强——向外部信号活动添加有效负荷<br /> </td> 
   <td> <p>当从另一个工作流或REST API调用成功满足定义的条件时，将工作流与有效负荷开始，以与外部系统集成。 此外，还包含一个新的 <strong>测试活动</strong> ，您可以在该环境中对此功能运行测试。</p><p>有关详细信息，请参 <a href="../../automating/using/calling-a-workflow-with-external-parameters.md">阅详细文档</a><a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/execution-activities/external-signal-activity.html">和操作方法视频</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 登陆页增强- Google reCAPTCHA<br /> </td> 
   <td> <p>利用Google reCAPTCHA防止您的登陆页上的垃圾邮件，无需客户采取任何操作。</p><p>有关详细信息，请参阅详 <a href="../../channels/using/configuring-landing-page.md#setting-google-recaptcha">细文档</a>。</p></td> 
  </tr> 
 </tbody> 
</table>

**安全增强**

* 修复了报告工作区中的潜在Clickjacking安全问题。

**Email Designer增强功能**

* 修复了复制片段并尝试在电子邮件设计器中使用它们时出现的问题。 (CAMP-33193)
* 修复了在电子邮件设计器界面中使用内联元素时创建多余空格的问题。 (CAMP-32163)
* 修复了在电子邮件设计器中保存电子邮件内容后，删除了用户添加的一些其他HTML标记属性的问题。 (CAMP-32162)
* 修复了即使在删除Microsoft Office标签后仍在“电子邮件设计器”HTML模式中显示该标签的问题。 (CAMP-32141)
* 如果您使用电子邮件设计器的先前版本创建了电子邮件，则打开此电子邮件内容时，现在会出现一个弹出窗口，提示用户更新至最新版本。 (CAMP-31529)
* 修复了在发送给某些消息客户端时，会扭曲使用电子邮件设计器创建的电子邮件中的图像的问题。 (CAMP-31407)
* 修复了在HTML模式下创建时，列表或按钮等某些元素无法在纯文本模式下正确显示的问题。 (CAMP-32582, CAMP-32542)
* 修复了阻止在内容模板或片段属性中显示50个以上组织单位的问题。 (CAMP-32932)
* 修复了在Outlook上接收使用电子邮件设计器创建的电子邮件时，视区背景颜色的问题。 (CAMP-31402)
* 修复了在Outlook中打开使用电子邮件设计器创建的电子邮件内容时无法响应的问题。 (CAMP-31400)
* 修复了在电子邮件主题中使用动态内容时无法正常工作的问题。 (CAMP-32837)
* 修复了与未正确转义的电子邮件主题相关的问题。
* 修复了阻止片段加载到电子邮件设计器左调板中的问题。
* 修复了在刷新片段列表时，电子邮件内容版本中创建的片段无法显示在电子邮件设计器左侧调色板中的问题。
* 修复了在电子邮件中使用动态内容时发生的几个问题。
* 修复了在尝试使用RGB值定义颜色时拾色器出现的问题。
* 修复了在移动设备上接收电子邮件时镜像页面无法响应的问题。

**Transactional Messaging增强功能**

为了优化操作和性能，在事务消息渠道中增加了若干改进。

* 事务性消息持续时间已延长，以确保所有消息在过期之前发送，尤其是在执行重试时。
* 通过在不同的发送线程上分配负载，提高了事务消息传递性能。
* 该事务消息传递过程已经优化，以能够以同一消息的并行多分析开始。
* 修复了可能导致事务推送通知的吞吐量和延迟不一致的问题。
* 修复了对于目标执行受众显示错误的事务性消息投放的问题。
* 修复了导入包时使用事件配置和关联的事务性消息所发生的问题。 有关详细信息，请参阅详细 [文档](../../channels/using/about-transactional-messaging.md#exporting-and-importing-transactional-messages)。
* 修复了从为包含产品列表的事务性消息创建的测试用户档案中删除收集数据的问题。

**其他更改**

* SMS外部帐户中新增了一个选项。 它能够限制发送SMS的MTA进程的最大数量，以便更好地控制并行连接的数量。 有关详细信息，请参阅 [SMS连接器协议和设置技术](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html) 。
* 在发布具有API扩展的资源时，如果该API已发布，则现在每次重新发布该资源时，它都会自动更新。 以前，此操作是手动操作，无法更新API可能会破坏此API的用户档案或服务资源。 有关详细信息，请参阅详细 [文档](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension)。
* Zip代码维度已从动态报告中删除。 我们建议改用“城市”、“国家”和“州”维度。
* 已删除应用程序内消息的“首次启动”生命周期事件触发器。
* 导出包含安全组的包时，它现在包含分配给每个组的角色。 (CAMP-32960)
* 在“加载文件”活动中，新选项允许您检查要上传的文件的列是否与列定义匹配。 有关详细信息，请参阅详 [细文档](../../automating/using/load-file.md)。 (CAMP-32229)
* 工作流现在可以从有效负荷开始，允许您在工作流中的活动之间使用和共享外部参数。 有关详细信息，请参阅详 [细文档](../../automating/using/calling-a-workflow-with-external-parameters.md)。 （CAMP-29412和CAMP-29413）
* Campaign StandardAPI现在允许您使用有效负荷更新用户档案的地理和组织单位。 有关详细信息，请参阅详 [细文档](../../api/using/about-campaign-standard-apis.md)。
* 当数据库中的对象无法访问时，会有更清楚的错误消息。
* 在“提取文件”活动中，在定义要导出的文件的名称时，已更新Javascript功能。 “输出”字段中现在只能使用formatDate函数。 有关详细信息，请参阅详 [细文档](../../automating/using/extract-file.md)。
* 自定义资源的自动序列ID生成已得到改进。 新自定义资源的主键现在默认为64位。
* 自定义资源发布测试模式已得到改进。 如果上次自定义资源发布失败且未修复，则现在将向用户显示一条警告消息。 自定义资源发布失败后，您可以回滚到上一个工作版本。 有关详细信息，请参阅详 [细文档](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。
* 在“传输文件”活动中添加了新选项。 它允许您在SFTP模式下使用“文件下载”动作对文件进行排序。 有关详细信息，请参阅详 [细文档](../../automating/using/transfer-file.md)。 (CAMP-33109)

**修补程序**

* 修复了在重新加载SMS设置时可能导致MTA内存泄漏的问题。
* 修复了可能阻止在修复模式下发布数据库更新的问题。
* 修复了导致Adobe Analytics报告与Adobe Campaign动态报告不一致的问题。 (CAMP-25393)
* 修复了导致报告共享工作流失败的错误。
* 修复了阻止用户仅通过媒体URL发送应用程序内消息的错误。
* 修复了即使移动应用程序的证书未上载到实例也会显示该应用程序的问题。
* 修复了在使用移动应用程序模板的所有用户的 **目标时，个性化字段无法工作的错误** 。
* 新的Campaign Standard实例已配置。 （CAMP-32635和CAMP-32344）
* 修复了阻止自定义工作流中的日期公式的错误。 (CAMP-30336)
* 修复了定义自定义日期公式时的一个问题，该问题会阻止“附加数据”和“段代码”字段在下拉列表中可用。 (CAMP-32383)
* 修复了一个问题，该问题可能会阻止“传输文件”和“提取文件”活动在加密后发现文件被拒绝。 (CAMP-32377)
* 修复了API中的一个问题，该问题可能会阻止lineCount过滤器呈现确切的总计数。 (CAMP-31424)
* 修复了登陆页中的一个问题，该问题可能会阻止输入字段在修改后显示更新的值。 (CAMP-31401)
* 修复了可能导致信号活动意外激活的问题。
* 修复了一个问题，该问题会阻止电子邮件预览在受众为空时显示。
* 修复了“提取文件”活动中的一个问题，该问题在激活“如果入站过渡为空，则不生成文件”选项时可能生成文件。
* 修复了在交付性工作流未完成时导致其关闭的问题。
* 修复了可能阻止用户保存或计划报告的问题。 (CAMP-31133)

## 19.1.3版- 2019年3月 {#release-19-1-3---march-2019}

**Email Designer增强功能**

* 修复了在保存模板后无法对其进行修改的问题。
* 修复了在电子邮件中使用以前创建的模板时的各种问题。
* 修复了导入的模板中无法隐藏组件的问题。

**其他改进**

* 修复了查看类型规则时的错误。 （CAMP-32059和CAMP-31849）
* 修复了阻止编辑类型规则的问题。 (CAMP-31750)
* 修复了inMail进程中可能意外停止的问题。 (CAMP-31238)

## 19.1版- 2019年2月 {#release-19-1---february-2019}

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
   <td> 推送渠道报告改进<br /> </td> 
   <td> <p>推送渠道报告中已添加了多项增强功能，可让您更直观地衡量用户参与度。 在此版本中，我们将推送渠道指标的列表扩展到三个不同的指标：展示次数、点击次数、打开次数（应用程序打开次数）可帮助您更有效地衡量和分析用户与推送通知的交互情况。 与此同时，我们也在规范这些指标的定义和实施。 推送通知内置报告也已改进，其中包含常用的可视化和指标。</p><p> 有关详细信息，请参阅详 <a href="../../reporting/using/push-notification-report.md">细文档</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 移动应用程序的启动集成<br /> </td> 
   <td> <p>此版本包含将Adobe Campaign与Adobe Experience Platform Launch和Mobile SDK中针对Adobe Campaign标准的Android和iOS扩展的GA版本集成。 这些扩展支持推送消息、应用程序内消息和移动应用程序用户档案更新。</p><p> 有关详细信息，请参阅详 <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">细文档</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 移动应用程序内消息传递<br /> </td> 
   <td> <p>此版本包含活动中GA版本的应用程序内渠道。 从功能角度看，测试版中最显着的附加功能是Mobile SDK与MCIAS（为SDK提供应用程序内规则的Marketing Cloud应用程序内消息传递服务）之间的应用程序内渠道和安全握手的动态报告。 安全握手可确保用户的PII数据不会落入恶意的之手，并且允许您在用户每次注销时清除消息缓存，从而在共享设备上维护用户的隐私。</p><p>有关详细信息，请参阅详细 <a href="../../channels/using/about-in-app-messaging.md">文档</a> 和专用的 <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/in-app/in-app-message-overview.html">应用程序内教程</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 工作流增强功能<br /> </td> 
   <td> <p>已添加以下工作流功能：</p> 
    <ul> 
     <li> 您现在可以从同一活动实例在工作流或其他工作流中复制粘贴活动。 这样，您便可以轻松重复整个工作流或特定活动，并保留最初定义的设置。 有关详细信息，请参阅详 <a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">细文档</a>。 (CAMP-20014) </li> 
     <li> 使用“加 <strong>载文件</strong> ”活动时，您现在可以向包含拒绝记录的文件的名称中添加时间戳。 有关详细信息，请参阅详 <a href="../../automating/using/load-file.md#configuration">细文档</a>。 </li> 
     <li> <strong>查询</strong> 和 <strong></strong> 分段活动现在允许您启用出站过渡(如果活动没有检索数据)。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**安全增强**

* 生成的登陆页HTML代码已更新，以防止搜索引擎索引。

**Email Designer增强功能**

* 由Behance艺术家设计的一套四种一流的响应式电子邮件模板现已推出。

   有关详细信息，请参阅详 [细文档](../../designing/using/using-reusable-content.md#content-templates)。

* 我们新的入门培训体验将帮助您更快地开始电子邮件创建，并让您更轻松地访问文档和教程。

   有关详细信息，请参阅详 [细文档](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page)。

* 您现在可以根据需要灵活配置列数和宽度。

   有关详细信息，请参阅详 [细文档](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

* 在移动视图中编辑时，您可以仅在移动显示屏中隐藏某些组件，以有效利用空间。

   有关详细信息，请参阅详 [细文档](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)。

* 您现在可以在现有电子邮件模板之上添加自定义社交渠道。
* 修复了在使用18个以上结构时无法向下滚动结构菜单的问题。 (CAMP-31173)
* 修复了在转发包含随Adobe Campaign发送的预头的电子邮件时，在内容顶部显示预头的问题。 (CAMP-30736)
* 修复了在Adobe Experience Manager中修改主题后单击“刷新 **** AEM内容”选项时，主题行无法更新的问题。 (CAMP-29984)
* 修复了阻止从Adobe目标使用动态图像的几个问题。
* 修复了在准备时检索内容时，如果预览之前是从URL导入的，则无法更新该内容的问题。
* YouTube图标已添加到 **Social内容组件** 。
* 已 **为“电子邮件设计** ”调板中显示的内容组件和片段添加列表视图。

**其他改进**

* Adobe Campaign现在完全符合FCM对SDK V4和AEP SDK应用程序的要求。
* Adobe Campaign支持Android在Wear OS上推送通知以及Apple的watchOS。
* 在界面中导航时可能显示的警告和错误消息变得清晰易懂。
* 您现在可以添加到与选择加入和选择退出相关的用户档案列表列（“不再联系……”字段）。
* 用户档案创建屏幕中的时区下拉列表已从“地址”部分移到界面的上部。
* 您现在可以在配置自定义资源屏幕时添加分隔符，从而将字段组织到类别中。

   有关详细信息，请参阅详 [细文档](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration)。

**其他更改**

* Adobe Campaign和Adobe Experience Cloud将从2019年春季起停止对Microsoft Internet Explorer 11和Campaign Standard19.2版本的支持。 请切换到Microsoft Edge或其他支持的浏览器。 请参 [阅已弃用和已删除的功能](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html) 页。
* 用户档案 **资源中的国家／地区代码字段已更** 名为国家／地区代码 ****。

**修补程序**

* 修复了在向电子邮件用户档案添加测试事务性消息时无法发送消息的问题。 (CAMP-29854)
* 修复了在同时触发所有渠道的消息发送时，一个渠道的消息发送量较低时，会减慢其他渠道发送消息的速度的问题。
* 修复了在开始连接尚未建立时，MTA外部帐户发送SMS消息的问题。
* 修复了调度程序活动执行频率和开始时间出现的问题。 (CAMP-30745)
* 修复了在使用扩展用户档案资源时，PKEY生成可能发生的问题。 (CAMP-30285)
* 修复了基于日历日的疲劳规则可能出现的问题。 (CAMP-30136)
* 修复了在尝试访问名称以“Base”结尾的自定义资源时可能发生的问题。 (CAMP-30109)
* 修复了无法使用PATCH调用订阅服务用户档案的问题。 (CAMP-29728)
* 修复了通过“加载文件”活动导入XML文件时可能损坏工作流的问题。 （CAMP-29208和CAMP-28205）
* 修复了链接自定义资源时可能阻止生成反向基数链接的问题。 (CAMP-30476)
* 修复了仅使用投放日志时无法扩展段代码的问题。
* 修复了在工作流中使用文件传输活动时可能重复行的问题。
* 修复了阻止在所选时间发送计划报告的问题。
* 修复了在工作流中导致应用程序内投放的“要交付”和“已发送”KPI之间出现差异的问题。
* 修复了导致跟踪无法处理使用自定义HTML创作的应用程序内消息的问题。
* 修复了在工作流中使用应用程序内投放内容时无法保存的问题。
* 修复了阻止管理员显示手机应用程序的问题。
* 修复了导致“可交付性更新”技术工作流失败的问题。 (CAMP-26387)
* 修复了在创建应用程序内投放时导致目标用户档案与投放仪表板中显示的之间不一致的问题。 (CAMP-28722)
* 修复了活动和资产核心服务集成的一个问题，该问题可能会妨碍您在电子邮件中选择共享资产。

## 19.0版- 2019年1月 {#release-19-0---january-2019}

**新增内容?**

<table> 
 <colgroup><col style="width: 30%"><col style="width: 70%"></colgroup>
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 说明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 电子邮件设计人员的一般可用性<br /> </td> 
   <td> <p>新的直观的电子邮件设计器（以前称为Creative Designer）已转向GA。 它现在支持旧版内容编辑器的所有功能，包括：</p> 
    <ul> 
     <li> 使用Adobe <a href="../../integrating/using/adding-target-dynamic-content.md">目标中的动态图像</a> </li> 
     <li> 能够在准 <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">备时自动从URL检索内容</a> </li> 
     <li> 完全 <a href="../../designing/using/using-reusable-content.md#content-templates">兼容的现成内容模板</a>。 </li> 
    </ul> 
    <p>有关详细信息，请参 <a href="../../designing/using/designing-content-in-adobe-campaign.md">阅详细文档</a><a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html">和操作方法视频</a>。 以下列出了改进和修复。</p><p>因此，现在已弃用旧版电子邮件内容编辑器。 For more information, refer to this <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">page</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> 交易电子邮件中的产品列表<br /> </td> 
   <td> <p>您现在可以在交易电子邮件中引用一个或多个产品集合。 例如，您可以自动发送购物车放弃电子邮件，其中列出用户购物车中的所有产品，并包含图像、价格和指向每个产品的链接。</p><p>有关详细信息，请参 <a href="../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message">阅详细文档</a><a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html">和操作方法视频</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 电子邮件设计人员中的移动视图<br /> </td> 
   <td> <p>您现在可以在编辑电子邮件内容时切换到专用的移动视图。 这允许您通过单独编辑移动显示的所有样式选项（如调整边距、较小的字体大小、不同的背景颜色等）来微调电子邮件的响应式设计。</p><p> 有关详细信息，请参阅详 <a href="../../designing/using/plain-text-html-modes.md#switching-to-mobile-view">细文档</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内消息传递测试版改进<br /> </td> 
   <td> <p>应用程序内消息传递测试版功能已通过以下功能得到增强：</p> 
    <ul> 
     <li> 应用程序内测试版渠道符合GDPR要求 </li> 
     <li> 与Analytics API集成以填充触发器下拉列表 </li> 
     <li> 直观的外观和投放模板描述 </li> 
     <li> 从可用性角度对创作界面的增强 </li> 
    </ul> <p>有关详细信息，请参阅详 <a href="../../channels/using/about-in-app-messaging.md">细文档</a>。</p> </td> 
  </tr> 
 </tbody> 
</table>

**改进**

* 现在，通过“加载数据”活动中的新选项，您可以将后处理阶段应用到包含拒绝记录的文件(例如， Zip格式压缩)。 (CAMP-24521)
* “更新数据”活动中的新选项现在允许您为要上传的数据配置最大批量大小。 (CAMP-28400)
* 改进了用户档案的地址状态选择。 选择国家／地区时，“状态”下拉列表现在会自动更新为相关的状态值。 (CAMP-28874)
* 如果入站活动为空，“提取”文件过渡中的新选项现在可阻止生成文件。 这可避免在SFTP服务器上创建和上传空文件。
* 投放摘要报告已得到改进。
* 现有国家在定义用户档案地址时的列表已得到丰富。 (CAMP-26707)
* 现在，在尝试导入内置工作流时显示错误消息。

**电子邮件设计人员**

* 修复了在电子邮件模板或使用电子邮件设计器创建的内容片段上启用地理单元功能的问题，即使该功能在Adobe Campaign中被禁用，这使得在再次尝试访问该模板或片段时该模板或片段不可用。 (CAMP-28174)
* 修复了在使用电子邮件设计器编辑内容时无法保存动态内容条件的问题。 (CAMP-27905)
* 修复了在编辑邮件的纯文本版本并在电子邮件设计器中中断HTML同步后，从电子邮件内容中删除HTML版本的问题。 (CAMP-28507)
* 修复了使用Internet Explorer 11时无法打开电子邮件设计器界面的问题。 (CAMP-28273)
* 修复了使用电子邮件设计器对按钮应用的样式设置的Microsoft Outlook呈现失真的问题。
* 修复了电子邮件设计器中的一个问题，该问题使电子邮件中使用的内容片段的URL可编辑，但该URL不是预期的，因为该片段在默认情况下处于锁定状态。
* 修复了阻止在Microsoft Office中显示“电子邮件设计器”分隔器组件的问题。
* 修复了在使用旧版电子邮件内容编辑器查看从AEM同步的内容时，导致某些Internet浏览器上的页面冻结的问题。 (CAMP-29068)
* 修复了在使用旧版电子邮件内容编辑器时单击电子邮件中的任何图像时出现的错误。 (CAMP-30424)
* 修复了在使用电子邮件设计器编辑电子邮件时无法显示新创建的片段的问题。 (CAMP-29928)
* 修复了阻止按钮文本在使用电子邮件设计器创建并使用Outlook电子邮件客户端接收的电子邮件中正确显示的问题。
* 现在，可以使用电子邮件设计器创建用户档案事务性消息。 (CAMP-28900)
* 修复了电子邮件设计器中的一个错误，该错误使内容在准备时从URL自动检索内容时可编辑，而内容应被锁定。

**修补程序**

* 修复了在动态报告中显示错误投放日志的问题。 (CAMP-23446)
* 修复了影响弹回摘要报告数字的问题(CAMP-28703)
* 修复了活动和资产核心服务集成的一个问题，该问题可能会阻止在电子邮件中选择资产时 **[!UICONTROL Image shared from Adobe Experience Cloud]** 显示资产(CAMP-28732)。
* 修复了即使在SMPP外部帐户中授权音译，包含“oe”字符的SMS消息仍无法发送的问题。 (CAMP-29041)
* 修复了在重复中使用分段活动时可能显示工作流记录的问题。 (CAMP-28743)
* 修复了无法删除工作流活动中某列上的值映射之一的问题。 (CAMP-28708)
* 修复了在文件传输活动中使用通配符时“测试以查看文件是否存在”选项的问题。 (CAMP-28977)
* 修复了文件传输活动中在更新外部帐户设置时可能发生的问题。 (CAMP-28894)
* 修复了在使用“电子邮件不为空”条件时查询编辑器中的自定义过滤器的问题。 (CAMP-28741)
* 修复了导出具有100k以上记录的自定义资源表时可能发生的问题。 (CAMP-28150)
* 修复了无法删除与触发器链接的事务性消息的问题。 (CAMP-28385)
* 删除了某些SMS日志中不安全显示的密码。
* 修复了由于Adobe Campaign发送的空密码，导致与SMPP模拟器的连接失败的问题。
* 修复了在SMS连接不稳定时无法发送活动的问题。
* 修复了在动态报告中显示已删除投放的问题。
* 修复了在工作流中使用投放日志活动时，可能无法从跟踪日志、扩充和排除日志表检索其他数据的问题。
* 修复了GDPR删除请求的一个问题，该问题在使用“N基数收集链接”链接类型和“删除目标记录意味着通过链接删除记录引用”选项时可能发生。
* 修复了报告共享的问题。
* 修复了在发送推送通知时可能导致吞吐量问题的问题。
* 修复了直接邮件输出文件缺少字段的问题。
* 修复了允许用户修改内置工作流的问题。
* 修复了在创建基于活动(包括具有已配置提取活动的工作流)的活动模板时的问题。 (CAMP-29198)
* 修复了文件提取活动的一个问题，该问题导致无法对多个元素使用相同表达式。 (CAMP-29182)
* 修复了在查询编辑器中rtEvent的broadlog和跟踪日志之间存在连接条件的问题。 (CAMP-28780)
* 修复了无法保存对“特定操作”登陆页选项的修改的问题。 (CAMP-29422)
* 修复了在工作流中无法导出事件的有效负荷的问题。 (CAMP-29029)
* 修复了阻止已列入黑名单SMS号码在SMS消息中被排除的问题。 (CAMP-28898)
* 修复了在处理传入消息时出错时，可能会阻止SMPP提供商收到通知的问题。 (CAMP-29804)
* 修复了允许删除与关联外部帐户相关的投放的问题。 (CAMP-29738)
* SMS消息的发送吞吐量已得到改进和稳定。
* 修复了阻止在SMS消息中使用“~”字符的问题。 (CAMP-29172)
* 修复了“发送时间优化”选项在投放中的问题。 (CAMP-29231)

