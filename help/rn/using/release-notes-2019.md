---
title: 2019 年版发行说明
description: 本页列出了所有 2019 年版的 Adobe Campaign Standard。
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 6a53e6f5-9b69-4068-ab7d-10e22e266277
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '7556'
ht-degree: 8%

---

# 2019 年版发行说明{#release-notes-2019}

## 19.4版 — 2019年12月 {#release-19-4---october-2019}

**新增功能**

<table> 
 <thead> 
  <tr> 
   <th> <strong>《加州消费者隐私法案》(CCPA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>CCPA是加利福尼亚州新推行的隐私法，旨在实现数据保护要求的协调和现代化，于2020年1月1日正式生效。 CCPA适用于位于加利福尼亚州且持有数据主体数据的Adobe Campaign客户。</p>
   <p>除了Adobe Campaign中已有的可用隐私功能（包括同意管理、数据保留设置和用户角色）之外，我们还利用这个机会纳入了其他功能，以帮助您为CCPA做好准备：</p>
   <ul>
    <li>访问权利和删除权利：我们将利用为GDPR添加的功能。 <a href="https://helpx.adobe.com/content/help/zh-Hans/campaign/kb/acs-privacy.html#righttoaccess">了解详情</a> </li>
    <li><p>在创建隐私请求时，隐私核心服务中添加了法规类型（GDPR或CCPA）。 您应将此方法应用于所有访问和删除请求。将 Campaign API 和接口用于访问和删除请求的方法已被弃用。请参阅<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=zh-Hans#release-notes">已弃用和已删除的功能</a>一文。</p></li>
    <li>A <strong>CCPA选择退出</strong> “配置文件”资源中已添加字段，以允许Adobe Campaign用户跟踪消费者是否已选择退出个人信息销售。 <a href="https://helpx.adobe.com/cn/campaign/kb/acs-privacy.html#ccpa">了解详情</a>。</li>
  </ul>
    <p>请参阅<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">操作方法视频</a>。</p>
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
    <p>Adobe Campaign Standard与Microsoft Dynamics 365之间的集成现已可用。 您将能够将联系人和自定义实体记录从Dynamics 365传输到Campaign，并将电子邮件事件数据从Campaign返回到Dynamics 365，以便更好地协调销售/营销。</p>
    <p>请参阅 <a href="../../integrating/using/d365-acs-get-started.md">详细文档</a> 以设置此集成。</p>
  </td>
  </tr> 
 </tbody> 
</table>

**改进**

* 更新了动态报告的同意弹出窗口，以包含Adobe Campaign Standard和Microsoft Dynamics 365集成。 接受这些条款后，在使用Adobe Campaign Standard/Microsoft Dynamics 365集成和动态报表时，将包含配置文件数据。 [了解更多](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) (CAMP-29766)
* 修复了在接收投放警报时显示错误联系日期的问题。
* 现在，当使用未知上下文参数提交事务型消息事件时，Campaign会返回“400”错误消息，而不是“500”。 (CAMP-28632)
* 新 **排除证据** 区段已添加到动态报告中。 默认情况下，现在选择该区段以筛选报表。 [了解更多信息](../../reporting/using/list-of-components-.md#segments)
* 此 **消息过期** 选项已添加到推送通知。 它允许您指定到Apple (APNS)或Android (FCM)不再发送消息的截止日期。 [了解更多信息](../../channels/using/customizing-a-push-notification.md#add-expiration-date)
* 改进了 **加载文件** 活动：工作流日志更清晰，更详细地说明了文件加载失败时发生的错误。 激活时生成的叫客过渡 **将拒绝项保存在文件中** 选项已重命名 **拒绝**. [了解更多信息](../../automating/using/load-file.md)
* 已向发送日志添加多语言相关日志，以更好地了解由于上传的CSV文件中缺少语言导致的发送失败。

**安全性增强**

* 修复了在通过隐私请求删除隔离用户档案的信息时，会删除隔离列表中除电子邮件地址以外的所有数据的问题。
* 增强了安全性，以防止电子邮件标头中的注入。
* 增强了安全性，以防止可能使用xtk表达式(电子邮件HTML、文本内容和主题、短信和推送通知内容)的SSRF攻击。

**Email Designer 增强功能**

* 修复了在电子邮件中插入退订、订阅和登陆页面链接时，无法跟踪这些链接的问题。 (CAMP-37809)
* 修复了在创建新电子邮件并选择模板时可能导致错误的问题。 (CAMP-38000)
* 使用Email Designer编辑链接时，您现在可以使用 **为链接加下划线** 选项。 此外， **Target** 已添加属性，并将默认值设置为 **无**. [了解更多信息](../../designing/using/styles.md#about-styling-links)
* 修复了电子邮件正文中文本组件中链接的颜色问题。 (CAMP-37330)
* 修复了在删除图像时阻止删除关联链接的问题。 (CAMP-37234)
* 修复了阻止保存对的修改的问题 **订购** 条件中动态内容的设置。 (CAMP-36883)
* 修复了搜索登陆页面时出现的问题。 搜索范围从最初创建的50个扩展到了所有数据库。 (CAMP-36839)
* 修复了在中保存对电子邮件发件人的修改时出现的问题 **发件人：姓名** 字段。 (CAMP-36606)
* 已修改轮盘组件兼容性警告，以反映支持的电子邮件客户端。
* 修复了移动设备上的显示问题。 在电子邮件中添加或上传新图像时，高度属性现在始终设置为“height： auto”。 (CAMP-35497)
* 修复了从结构组件中删除片段时HTML中留下样式和元标记的问题。 (CAMP-35390)
* 修复了更新可重用内容时片段的问题。 (CAMP-35186)
* 修复了在电子邮件中仅显示移动设备条件内容时的问题。 (CAMP-35155)
* 修复了随机显示零宽度不间断空格的问题。 (CAMP-35116)
* 修复了中按钮位置的问题。 **另存为片段** 对话框。
* 修复了在图像标题和替换文本中添加HTML标记时的预览问题。
* 修复了在电子邮件设计工具中，从旧版编辑器编辑在电子邮件中创建的链接时出现的问题。
* 修复了内容中保留重复样式标记的问题。
* 修复了在电子邮件中插入个性化字段时日期格式的问题。
* 修复了从HTML模式切换到纯文本时的保存问题。
* 修复了在单击“锁定和解锁”选项时，会在内联样式属性面板中添加边距值的问题。
* 修复了移动设备预览的大小问题，以便更好地呈现。
* 修复了模板和片段中按钮大小的问题。
* 修复了在按钮组件中插入图像时图像大小的问题。

**其他变更**

* 已调整数据在投放KPI页面和动态报告页面上显示的默认时间范围，以防止报告结果不一致。 (CAMP-35148)
* 当应用程序证书过期时，在日志中添加了错误消息。
* 有效负载计算预览现在包含自定义字段大小，以防止推送通知失败。 (CAMP-35303)
* 的名称 **拒绝文件** 在 **加载文件** 活动现在可以在中的相同进行个性化 **文件导出** 活动。
* 现在可以通过API访问未链接到任何现成实体的所有自定义实体。
* 提高了大型资源的数据库性能。
* 对于发送短信消息时发生的一些错误的描述已变得更加清晰。 (CAMP-36558)
* 执行工作流时，现在会显示错误消息 **计划程序** 直接连接或通过多个活动与其自身连接的活动，因为这会导致实例的工作流服务器卡住。
* 为帮助排查事务型消息传递问题，我们进行了一些改进：“数据”链接已在事件配置屏幕中被重命名为“上次事务型事件”，它现在按降序列出接收的事件。 此外，已创建新的事务性事件状态：“targetingFailed”。 当事务型消息传递模块无法扩充用于消息定向的链接时，事务型事件现在将处于此新状态（而不是“routingFailed”状态）。
* 在限制登陆页面访问特定地理或组织单位时，已对界面进行了改进。 其目的是警告登陆页面可能受可见性条件的约束：现在，在创建登陆页面时必须选择地理和组织单位。 现在，在选择设备后，将显示包含相关信息的横幅。 测试登陆页面时显示的错误消息已变得更加清晰。
* 在Campaign StandardAPI中，如果密钥值与原始密钥不同，或者您将自己的业务密钥用作URI而不是Adobe提供的业务密钥，则无法使用PATCH操作修改自定义密钥。
* “阿尔巴尼亚语 — 马其顿”语言已添加到首选语言下拉列表。 (CAMP-35396)

**修补程序**

* 修复了阻止对计划报表进行排序或搜索的问题。
* 修复了触发器规则的一个问题，该问题导致AND和OR规则混合在一起。
* 修复了在Launch中将移动属性显示为“已删除”的问题。 (CAMP-35382)
* 修复了导致Adobe启动移动资产无法在Adobe Campaign中同步的问题。 (CAMP-35411、CAMP-35089、CAMP-35014和CAMP-35487)
* 修复了使用用户档案数据扩充事件时事务推送消息失败的问题。 (CAMP-34385)
* 修复了移动资产未在多个环境中同步的问题。 (CAMP-37060)
* 修复了在推送通知中使用联系日期公式选择模板时的问题。 (CAMP-35300)
* 修复了可能导致消息发送服务崩溃的问题。 (CAMP-35287)
* 修复了定期直邮的问题，该问题全部使用第一个事件日期定义。 (CAMP-35139)
* 修复了新扩展的问题 **配置文件** 无法用于查询的自定义资源。 (CAMP-35119)
* 修复了 **修复数据库结构** 模式。 (CAMP-35118)
* 修复了在broadlog上添加聚合数据时导致出现SQL日志错误的问题。 (CAMP-35034)
* 修复了创建时的过渡问题 **分段** 活动。 (CAMP-35033)
* 修复了中的一个问题 **查询** 活动阻止了 **encryption_aescbcDecrypt** 函数解密 **encryption_aescbcEncrypt** 函数。 (CAMP-34952)
* 修复了可能导致 **跟踪日志** 以免在投放中显示。 (CAMP-34855)
* 修复了使用的问题 **发送时间优化** 自定义日期公式，可以阻止由于工作流附加数据错误而发送推送通知。 (CAMP-30336)
* 修复了可能导致自定义资源无法发布的问题。 (CAMP-37425)
* 修复了阻止管理员用户修改导入包的问题。  (CAMP-37176)
* 修复了工作流中当投放活动连接到空时阻止发送校样的问题 **读取受众** 活动。 (CAMP-37164)
* 修复了阻止将自定义资源导入新环境的问题。 (CAMP-36506)
* 修复了热点击报表中可能导致百分比被图像隐藏的问题(CAMP-36407)
* 修复了尝试导出投放描述字段时发生的问题。 (CAMP-35467)
* 修复了在投放完成之后，投放状态仍可能为“开始挂起”的问题。 (CAMP-35355)
* 修复了在启用然后禁用SQL日志后阻止显示工作流日志的问题。

## 19.3 版 - 2019 年 7 月 {#release-19-3---july-2019}

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
   <td> 外部API活动（公共测试版）<br /> </td> 
   <td> <p>为实现更深入的个性化，外部API活动允许您通过REST API调用将外部系统中的数据引入工作流。 REST端点可以是客户管理系统、Adobe I/O Runtime或Adobe Experience Cloud REST端点（例如，Data Platform、Target、Analytics、Campaign）。</p><p>此功能当前处于公开测试阶段。</p><p>有关更多信息，请参阅<a href="../../automating/using/external-api.md">详细文档</a>和<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">操作方法视频</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 工作流区段报告<br /> </td> 
   <td> <p>此功能允许营销人员按区段代码细分其交付性能。 在创建工作流并使用分段活动将区段分配给投放群体时，这些区段现在可以进入同一投放。 这样，您就可以根据单个投放中的多个区段，显示打开/点击次数统计信息。</p><p>有关更多信息，请参阅<a href="../../reporting/using/creating-a-report-workflow-segment.md">详细文档</a>和<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">操作方法视频</a>。</p></td>
  </tr> 
 </tbody> 
</table>

**安全性增强**

* 修复了一个安全问题，以防止对获取图像的无效请求发起拒绝服务(DoS)攻击。 (CAMP-33454)

**Email Designer 增强功能**

* 修复了在每次添加组件时都向HTML模板中添加其他HTML样式标记的问题，该问题可能会显着增加模板的大小。 (CAMP-34694)
* 修复了可能阻止某些右上角工具栏菜单选项可用的问题。 (CAMP-34577)
* 修复了将镜像页面URL内容块插入电子邮件内容时发生的问题。 (CAMP-34779)
* 修复了在电子邮件中使用JSPP代码时导致难以编辑内容的问题。 (CAMP-34574)
* 修复了在向图像添加超链接时导致图像顶部截断的问题。 (CAMP-34382)
* 修复了将Email Designer与Firefox结合使用时的显示问题。 (CAMP-34364)
* 修复了在电子邮件中定义动态内容时，在高级模式下发生的几个问题。 (CAMP-34351、CAMP-34333、CAMP-34331)
* 修复了动态内容规则编辑器出现的几个问题(CAMP-34304、CAMP-34303)。
* 修复了可能导致链接字段无法在Email Designer设置窗格中显示的问题(CAMP-33749)。
* 修复了已发送电子邮件中YouTube图标过大的问题。 (CAMP-33726)
* 修复了导致镜像页面内容可编辑的安全问题。 (CAMP-33691)
* 修复了在动态内容中使用大于符号时中断HTML输出的问题。 (CAMP-33688)
* 修复了在Email Designer中编辑文本时，使用撤消选项发生的问题。 (CAMP-32565)
* 修复了在撤消样式而不是删除样式时创建额外标记的问题。 (CAMP-32359)
* 现在，您可以定义电子邮件中使用的每个组件是仅显示在桌面设备上，还是仅显示在移动设备上。
* 您现在可以设置社交内容组件的宽度和高度。
* 修复了在删除动态内容后无法删除该动态内容旧源代码的问题。
* 修复了在修改电子邮件后可能阻止更新其主题的问题。
* 修复了将n：n列结构拖放到工作区中后无法选择该结构的问题。
* 修复了导致电子邮件仪表板中消息的缩略图显示模糊的问题。
* 修复了阻止在Outlook中接收的电子邮件正确显示后台的问题。
* 修复了Email Designer主页上的某些排序问题。
* 修复了在使用动态内容时复制变量时出现的问题。
* 从Email Designer的“设置”窗格中删除了一些不需要的字段。

**其他改进**

* 通过与Adobe Experience Platform位置服务集成，Adobe Campaign现在可与兼容，以通过Experience PlatformSDK向您的移动应用程序订阅者发送基于位置的营销消息。 有关更多信息，请参阅[详细文档](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md)。
* 报告功能已得到改进，可提供更好的体验。 要使用此功能，您需要接受动态报告使用协议。 有关详细信息，请参见 [详细文档](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
* 在工作流中，添加了一个新选项来预览工作流接下来的十次执行。 有关详细信息，请参见 [详细文档](../../automating/using/scheduler.md).
* 在调度程序活动中，通过新选项可为每月投放选择一周中的特定日期。 有关详细信息，请参见 [详细文档](../../automating/using/scheduler.md).
* 现在，在创建没有聚合期的定期投放时，可通过投放仪表板在发送投放之前请求确认。 有关详细信息，请参见 [详细文档](../../sending/using/confirming-the-send.md).
* 您现在可以使用在工作流外部信号活动中声明的事件变量将投放标签个性化。 有关详细信息，请参见 [详细文档](../../automating/using/calling-a-workflow-with-external-parameters.md).
* GDPR删除查询已得到改进，以实现更好的性能。 (CAMP-33504)
* “ftp”选项已从外部帐户配置界面中删除。 (CAMP-34472)
* 现在，您可以为每个电子邮件启用和禁用SMTP测试模式选项。 有关详细信息，请参见 [详细文档](../../administration/using/configuring-email-channel.md#smtp-test-mode). (CAMP-34602)

**其他变更**

* 在投放属性界面中添加了警告。 它指定投放根据其聚合期进行准备和解冻以每天多次调用工作流，您应确保它们没有任何期限。 (CAMP-34393)
* 在自定义资源配置屏幕中添加了警告。 我们建议为自定义资源 ID 最多使用 30 个字符。这也适用于自定义资源字段、键值、索引和链接。
* 现在，在尝试删除登录页用作确认消息的事务型消息时，将显示一条消息。
* 当活动运行超过6小时时，工作流日志中现在会显示警告。 这不适用于推送通知、交付、信号、开始、结束、分支、 AND联合、计划和等待活动。
* 现在，当您达到同时运行的工作流的最大数量时，工作流日志中会显示警告。
* 处于暂停或失败状态超过7天的工作流现在已停止，以节省磁盘空间。 清理任务会显示在工作流日志中。
* 使用“传输文件”活动时，如果文件大小超过可用磁盘空间，现在会记录错误。
* 无法再为应用程序内消息中的secondary按钮选择“重定向到目标URL”操作。

**修补程序**

* 修复了可能导致GDPR访问请求失败的问题。
* 修复了在收到唯一配置文件的多个触发器时可能导致触发器被放弃的问题。
* 修复了在登录后可能导致错误的自定义资源发布错误消息的问题。
* 修复了在创建或扩展自定义资源时显示空白页面的问题。
* 修复了导致具有appSubscriptionrcp作为定向维度的受众无法在移动投放中定位的问题。
* 修复了阻止将硬退回电子邮件地址置于隔离状态的错误。 (CAMP-24587)
* 修复了在添加分类规则，然后在保存分类之前删除它时发生的问题。 (CAMP-32789)
* 修复了在禁用动态内容时可能阻止显示登陆页面内容的问题。 (CAMP-32924)
* 修复了在主要投放的属性上使用个性化时发生的定期投放问题。 (CAMP-32983)
* 修复了工作流中阻止从包含传入SMS消息数据的过渡读取结果的问题。 (CAMP-33134)
* 修复了在组合分支和排除活动以创建受众时工作流中出现的问题。 (CAMP-33401)
* 修复了可能会阻止显示镜像页面内容，以及阻止为定期投放发送校样消息的问题。 (CAMP-33413)
* 修复了在用户档案和受众之间使用合并活动时导致错误的问题。 此问题是由输入过渡中的标识键不兼容导致的。 (CAMP-33713)
* 修复了Test活动中的一个问题，该问题导致在双击“recCount”表达式时无法使用正确的语法。 (CAMP-33756)
* 修复了在打开计费技术工作流日志时可能导致出现错误消息的问题。 (CAMP-34313)
* 修复了在使用订阅配置复选框字段时登陆页面中可能发生的问题。 (CAMP-34369)
* 修复了在配置列表并向其中添加“图标”字段时发生的问题。 (CAMP-34585)
* 修复了阻止在加载文件工作流活动中使用“|”和“%”符号作为日期或时间分隔符的问题。 (CAMP-34706)
* 修复了将可见性条件与登陆页面中的复选框一起使用时发生的问题。 (CAMP-34802)
* 修复了扩充活动中的一个问题：如果已将筛选维度设置为跟踪日志，并将目标维度设置为用户档案，则该问题阻止字段在“其他数据”选项卡中显示。
* 修复了在导出“workflowTemplate”资源时导致出现错误消息的问题。
* 修复了在创建新用户档案时的问题，该问题会导致在从对话框中选择“国家/地区代码”字段时无法保存。
* 修复了使用直邮导入模板(updateQuarantinesDeliveryLogsDirectMail)时发生的几个问题。
* 修复了与按需分配资产集成相关的问题。
* 修复了在时间轴视图中放大时发生的问题。 (CAMP-33628)
* 修复了阻止对具有计划日期和时间的电子邮件即时发送校样的问题。 (CAMP-33723)
* 修复了与事务性消息相关的问题，该问题会在用户注销时生成错误日志。 (CAMP-31698)
* 修复了在计划电子邮件时特定环境中可能发生的错误。
* 修复了导致更新投放执行工作流失败的问题。
* 修复了在主题包含多行时破坏电子邮件内容的安全问题。


## 19.2.7 版 - 2019 年 7 月 {#release-19-2-7---july-2019}

**改进**

* GDPR删除查询已得到改进，以实现更好的性能。
* 修复了在19.2升级后可能导致Web崩溃的问题。 (CAMP-34862)
* 修复了可能导致非管理员用户无法保存或计划报表的问题。 (CAMP-31133)
* 修复了在加载文件工作流活动中使用“|”作为日期分隔符时的问题。 (CAMP-34706)

## 19.2.4 版 - 2019 年 6 月 {#release-19-2-4---june-2019}

**电子邮件设计工具**

* 修复了在HTML中使用空样式标记时阻止用户编辑片段的问题。 这是19.2.3中CAMP-33778的后续修复。

## 19.2.3 版 - 2019 年 6 月 {#release-19-2-3---june-2019}

**电子邮件设计工具**

在19.2版本中引入了一系列改进和修复以优化片段。 新创建的片段将无缝工作。 之前构建的片段已灰显，需要迁移到新格式。 为此，请单击每个片段并验证其是否迁移到新格式。 我们建议您在迁移所有片段之前测试一些片段。

* 修复了在解锁片段后阻止用户编辑片段的问题。 在更新到19.2时，这会影响现有片段。 (CAMP-33778)
* 修复了使用动态内容时的问题。 HTML中添加了额外的空格。

**其他改进**

* 修复了在短信连接器断开连接后可能阻止短信发送恢复的问题。
* 修复了在启用TLS时可能关闭SMPP连接的问题。
* 修复了在启用TLS时可能关闭SMPP连接的问题。
* Campaign中添加了“Launch_URL_Campaign”选项，以管理使用Adobe Experience Platform Mobile SDK创建的移动应用程序的属性。
* 修复了在上传新创建的移动属性的证书并退出移动应用程序属性页面后，导致取消选中沙盒环境选项的错误。
* 修复了阻止使用服务资源中的信息扩充事务型消息内容的问题。 (CAMP-33707)
* 修复了在尝试取消订阅服务中的用户档案时在阻止列表登陆页面中发生的问题。

## 19.2 版 - 2019 年 5 月 {#release-19-2---may-2019}

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
   <td> 控制面板<br /> </td> 
   <td> <p>为了帮助提高管理员用户的工作效率，您可以轻松监控容量和管理实例设置（从SFTP服务器管理开始）。</p><p>有关更多信息，请参阅<a href="https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hans">详细文档</a>和<a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/control-panel-overview.html?lang=zh-Hans">操作方法视频</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 本地通知<br /> </td> 
   <td> <p>本地通知消息传送允许您在移动应用程序中提供新数据时通知您的用户，即使没有连接Internet或未在前台运行移动应用程序也是如此。 本地通知由移动应用程序在特定时间根据事件触发。</p><p>有关更多信息，请参阅<a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">详细文档</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 工作流增强功能 — 将有效负载添加到外部信号活动<br /> </td> 
   <td> <p>在成功满足已定义的条件时，通过其他工作流或REST API调用启动具有有效负荷的工作流，以与外部系统集成。 这还包括新的 <strong>测试</strong> 活动，您可以从中对此功能运行测试。</p><p>有关更多信息，请参阅<a href="../../automating/using/calling-a-workflow-with-external-parameters.md">详细文档</a>和<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/execution-activities/external-signal-activity.html">操作方法视频</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 登陆页面增强功能 — Google reCAPTCHA<br /> </td> 
   <td> <p>利用Google reCAPTCHA阻止登陆页面上的垃圾邮件，无需客户采取任何操作。</p><p>有关更多信息，请参阅<a href="../../channels/using/configuring-landing-page.md#setting-google-recaptcha">详细文档</a>。</p></td> 
  </tr> 
 </tbody> 
</table>

**安全性增强**

* 修复了报告工作区中潜在的点击劫持安全问题。

**Email Designer 增强功能**

* 修复了在复制片段并尝试在Email Designer中使用它们时发生的问题。 (CAMP-33193)
* 修复了在Email Designer界面中使用内联元素时创建多余空格的问题。 (CAMP-32163)
* 修复了在Email Designer中保存电子邮件内容后删除用户添加的一些其他HTML标记属性的问题。 (CAMP-32162)
* 修复了在Email DesignerHTML模式下显示Microsoft Office标记（即使删除后也如此）的问题。 (CAMP-32141)
* 如果您使用以前版本的Email Designer创建电子邮件，则打开此电子邮件内容时，现在会有一个弹出窗口提示用户更新到最新版本。 (CAMP-31529)
* 修复了向某些消息传送客户端交付时，可能会扭曲使用Email Designer创建的电子邮件中的图像的问题。 (CAMP-31407)
* 修复了在HTML模式下创建时，阻止某些元素（如列表或按钮）以纯文本模式正确显示的问题。 （CAMP-32582 和 CAMP-32542）
* 修复了阻止在内容模板或片段属性中显示超过50个组织单位的问题。 (CAMP-32932)
* 修复了在Outlook上接收使用Email Designer创建的电子邮件时视区背景颜色出现的问题。 (CAMP-31402)
* 修复了在Outlook中打开通过Email Designer创建的电子邮件内容时无法响应的问题。 (CAMP-31400)
* 修复了在电子邮件主题中使用动态内容时无法正常工作的问题。 (CAMP-32837)
* 修复了与电子邮件主题未正确转义相关的问题。
* 修复了阻止将片段加载到Email Designer左侧面板中的问题。
* 修复了在刷新片段列表时，导致在电子邮件内容编辑期间创建的片段无法显示在Email Designer左侧面板中的问题。
* 修复了在电子邮件中使用动态内容时发生的几个问题。
* 修复了在尝试使用RGB值定义颜色时拾色器发生的问题。
* 修复了在移动设备上接收电子邮件时阻止镜像页面做出响应的问题。

**事务性消息传递增强功能**

为优化操作和性能，已对事务性消息传递渠道进行了多项改进。

* 事务性消息的持续时间已延长，以确保所有消息在过期之前发送，特别是在执行重试时。
* 通过在不同的发送线程上分配负载，提高了事务性消息传递的性能。
* 事务性消息传递过程已经过优化，以便能够并行对同一消息进行多次分析。
* 修复了可能导致事务推送通知的吞吐量和延迟不一致的问题。
* 修复了针对事务性消息执行投放显示错误目标受众的问题。
* 修复了在导入包含事件配置和关联的事务型消息的包时发生的问题。 有关详细信息，请参见 [详细文档](../../channels/using/getting-started-with-transactional-msg.md#exporting-and-importing-transactional-messages).
* 修复了从为包含产品清单的事务型消息创建的测试用户档案中删除集合数据的问题。

**其他变更**

* 短信外部帐户中添加了一个新选项。 它允许限制发送短信的MTA进程的最大数量，以便更好地控制并行连接的数量。 欲了解更多信息，请参见 [SMS连接器协议和设置](https://helpx.adobe.com/cn/campaign/kb/sms-connector-protocol-and-settings.html) 技术说明。
* 现在，使用API扩展发布资源时，如果该API已发布，那么在每次再次发布它时，都会自动更新该API。 以前，此操作是手动执行的，且未能更新API可能会破坏此API的配置文件或服务资源。 有关详细信息，请参见 [详细文档](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* 已从动态报表中删除邮政编码维度。 我们建议改用城市、国家/地区、州维度。
* 已删除应用程序内消息的“首次启动”生命周期事件触发器。
* 现在，导出具有安全组的资源包时，它包含分配给每个组的角色。 (CAMP-32960)
* 在加载文件活动中，通过新选项可检查上传文件的列是否与列定义匹配。 有关更多信息，请参阅[详细文档](../../automating/using/load-file.md)。(CAMP-32229)
* 现在可以使用有效负荷启动工作流，从而允许您在工作流中的活动中使用和共享外部参数。 有关更多信息，请参阅[详细文档](../../automating/using/calling-a-workflow-with-external-parameters.md)。(CAMP-29412和CAMP-29413)
* Campaign StandardAPI现在允许您使用有效负载更新用户档案的地理和组织单位。 有关更多信息，请参阅[详细文档](../../api/using/get-started-apis.md)。
* 无法访问数据库中的对象时的错误消息已变得更清晰、更易于理解。
* 在提取文件活动中，在定义要导出的文件名称时，更新了Javascript功能。 现在，只有formatDate函数可用于输出字段。 有关更多信息，请参阅[详细文档](../../automating/using/extract-file.md)。
* 自定义资源的自动序列ID生成已得到改进。 默认情况下，新自定义资源的主键现在为64位。
* 自定义资源发布测试模式已得到改进。 如果上次自定义资源发布失败且未修复，则现在向用户显示警告消息。 在自定义资源发布失败后，您可以回退到上一个工作版本。 有关更多信息，请参阅[详细文档](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。
* 在传输文件活动中添加了一个新选项。 它允许您在SFTP模式下使用文件下载操作对文件进行排序。 有关更多信息，请参阅[详细文档](../../automating/using/transfer-file.md)。(CAMP-33109)

**修补程序**

* 修复了在重新加载短信设置时可能导致内存泄漏到MTA的问题。
* 修复了可能导致无法在修复模式下发布数据库更新的问题。
* 修复了导致Adobe Analytics报表与Adobe Campaign动态报表不一致的问题。 (CAMP-25393)
* 修复了导致报表共享工作流失败的错误。
* 修复了阻止用户仅发送包含媒体URL的应用程序内消息的错误。
* 修复了即使未将移动应用程序的证书上传到实例，也会显示移动应用程序的问题。
* 修复了在使用时阻止个性化字段工作的错误 **定位移动应用程序的所有用户** 模板。
* 已配置新的Campaign Standard实例。 (CAMP-32635和CAMP-32344)
* 修复了导致无法在工作流中自定义日期公式的错误。 (CAMP-30336)
* 修复了在定义自定义日期公式时可能导致“Additional data”和“Segment code”字段在下拉列表中不可用的问题。 (CAMP-32383)
* 修复了可能会阻止“传输文件”和“提取文件”活动在文件加密后发现文件拒绝的问题。 (CAMP-32377)
* 修复了API中可能阻止lineCount过滤器呈现确切总计数的问题。 (CAMP-31424)
* 修复了登陆页面中修改输入字段后无法显示更新值的问题。 (CAMP-31401)
* 修复了可能导致信号活动意外激活的问题。
* 修复了在受众为空时可能阻止显示电子邮件预览的问题。
* 修复了“提取文件”活动中的问题，该问题会在激活“如果集客过渡为空，则不生成文件”选项时生成文件。
* 修复了导致可投放性工作流在未成功完成时关闭的问题。
* 修复了可能会阻止用户保存或计划报表的问题。 (CAMP-31133)

## 19.1.3 版 - 2019 年 3 月 {#release-19-1-3---march-2019}

**Email Designer 增强功能**

* 修复了在保存模板后阻止修改模板的问题。
* 修复了在电子邮件中使用之前创建的模板时出现的各种问题。
* 修复了阻止组件在导入的模板中隐藏的问题。

**其他改进**

* 修复了查看分类规则时的错误。 (CAMP-32059和CAMP-31849)
* 修复了阻止编辑分类规则的问题。 (CAMP-31750)
* 修复了inMail进程可能意外停止的问题。 (CAMP-31238)

## 19.1 版 - 2019 年 2 月 {#release-19-1---february-2019}

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
   <td> 推送渠道报告改进<br /> </td> 
   <td> <p>向推送渠道报表添加了几项增强功能，以便您更直观地衡量用户参与情况。 在此版本中，我们将推送渠道量度列表扩展到三个不同的量度：“展示次数”、“点击次数”、“打开次数”（应用程序打开），以帮助您更有效地测量和分析用户与推送通知的交互。 除此之外，我们还对这些指标的定义和实施进行了标准化。 推送通知内置报告还通过常用的可视化图表和量度进行了改进。</p><p> 有关更多信息，请参阅<a href="../../reporting/using/push-notification-report.md">详细文档</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 移动应用程序的Launch集成<br /> </td> 
   <td> <p>此发行版本包含了Adobe Campaign与Adobe Experience Platform Launch和移动SDK中适用于Adobe Campaign Standard的Android和iOS扩展的GA版本的集成。 这些扩展支持推送消息、应用程序内消息传送和移动应用程序配置文件更新。</p><p> 有关更多信息，请参阅<a href="https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdk.html">详细文档</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 移动应用程序内消息传送<br /> </td> 
   <td> <p>此发行版本包含Campaign中的应用程序内渠道的GA版本。 从功能的角度来看，Beta版中新增的最显着功能包括：应用程序内渠道动态报告，以及Mobile SDK与MCIAS(向SDK提供应用程序内规则的Marketing Cloud应用程序内消息传送服务)之间的安全握手。 安全握手可确保用户的PII数据不会落入恶意用户手中，并允许您在用户每次注销时清除消息缓存来维护用户在共享设备上的隐私。</p><p>欲了解更多信息，请参见 <a href="../../channels/using/about-in-app-messaging.md">详细文档</a> 以及全心全意的 <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/in-app/in-app-message-overview.html">应用程序内教程</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> 工作流增强功能<br /> </td> 
   <td> <p>添加了以下工作流功能：</p> 
    <ul> 
     <li> 您现在可以从同一Campaign实例复制粘贴工作流或其他工作流中的活动。 这样，您就可以轻松复制整个工作流或特定活动，并保留最初定义的设置。 有关更多信息，请参阅<a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">详细文档</a>。(CAMP-20014) </li> 
     <li> 使用时 <strong>加载文件</strong> 之后，您现在可以向包含被拒绝记录的文件名添加时间戳。 有关更多信息，请参阅<a href="../../automating/using/load-file.md#configuration">详细文档</a>。 </li> 
     <li> <strong>查询</strong> 和 <strong>分段</strong> 现在，如果活动不检索任何数据，则通过活动可启用叫客过渡。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**安全性增强**

* 更新了生成的登陆页面HTML代码，以防止搜索引擎编制索引。

**Email Designer 增强功能**

* 由Behance艺人设计的四种一流的响应式电子邮件模板现已推出。

  有关更多信息，请参阅[详细文档](../../designing/using/using-reusable-content.md#content-templates)。

* 我们新的载入体验可帮助您更快地开始创建电子邮件，并让您更轻松地访问文档和教程。

  有关更多信息，请参阅[详细文档](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page)。

* 现在，您可以根据需要灵活配置列数和宽度。

  有关更多信息，请参阅[详细文档](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

* 在移动视图中编辑时，您可以仅在移动显示中隐藏某些组件，以有效利用空间。

  有关更多信息，请参阅[详细文档](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)。

* 您现在可以在现有社交渠道的基础上，将自定义社交渠道添加到电子邮件模板。
* 修复了在使用18个以上的结构时阻止向下滚动结构菜单的问题。 (CAMP-31173)
* 修复了在转发包含与Adobe Campaign一起发送的预告的电子邮件时，在内容顶部显示预告的问题。 (CAMP-30736)
* 修复了在单击 **刷新AEM内容** Adobe Experience Manager选项。 (CAMP-29984)
* 修复了阻止使用Adobe Target中的动态图像的几个问题。
* 修复了在准备时检索内容时，如果内容先前是从URL导入的，则无法更新预览的问题。
* YouTube图标已添加到 **Social** 内容组件。
* 此 **列表** 已为Email Designer调色板中显示的内容组件和片段添加了视图。

**其他改进**

* Adobe Campaign现在完全符合FCM要求，适用于SDK V4和AEP SDK应用程序。
* Adobe Campaign支持Android的Wear OS上的推送通知以及Apple的watchOS上的推送通知。
* 在界面中导航时可能显示的警告和错误消息变得更清晰、更易于理解。
* 您现在可以向配置文件列表中添加与选择启用和选择禁用相关的列（“不再联系……”字段）。
* 用户档案创建屏幕中的时区下拉列表已从“地址”部分移至界面的上半部分。
* 现在，您可以在配置自定义资源屏幕时添加分隔符，从而使您可以将字段整理到不同类别中。

  有关更多信息，请参阅[详细文档](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration)。

**其他变更**

* 从2019年春季和Campaign Standard19.2版本开始，Adobe Campaign和Adobe Experience Cloud将停止对Microsoft Internet Explorer 11的支持。 请切换到 Microsoft Edge 或其他受支持的浏览器。请参阅 [已弃用和已删除的功能](../../rn/using/deprecated-features.md) 页面。
* 此 **国家/地区代码** 用户档案资源中的字段已重命名为 **国家/地区代码**.

**修补程序**

* 修复了在将测试用户档案添加到电子邮件事务型消息时阻止发送消息的问题。 (CAMP-29854)
* 修复了在同时触发从所有渠道发送的消息时，如果一个渠道的发送量低，则从其他渠道发送的消息速度减慢的问题。
* 修复了在尚未建立外部帐户连接时导致MTA开始发送短信消息的问题。
* 修复了调度程序活动执行频率和开始时间出现的问题。 (CAMP-30745)
* 修复了在使用扩展用户档案资源时生成PKEY时可能发生的问题。 (CAMP-30285)
* 修复了基于日历天的疲劳规则可能发生的问题。 (CAMP-30136)
* 修复了在尝试访问名称以“Base”结尾的自定义资源时可能发生的问题。 (CAMP-30109)
* 修复了阻止使用PATCH调用将用户档案订阅服务的问题。 (CAMP-29728)
* 修复了在通过加载文件活动导入XML文件时可能损坏工作流的问题。 (CAMP-29208和CAMP-28205)
* 修复了在链接自定义资源时可能导致无法生成反向基数链接的问题。 (CAMP-30476)
* 修复了在仅使用段代码时阻止扩展投放日志的问题。
* 修复了在工作流中使用文件传输活动时可能重复行的问题。
* 修复了阻止在选定时间发送计划报告的问题。
* 修复了导致工作流中应用程序内投放的“待投放”KPI与“已发送”KPI不一致的问题。
* 修复了使用自定义HTML创作的应用程序内消息无法进行跟踪的问题。
* 修复了在工作流中使用应用程序内投放内容时无法保存该内容的问题。
* 修复了阻止向管理员显示移动应用程序的问题。
* 修复了导致可投放性更新技术工作流失败的问题。 (CAMP-26387)
* 修复了在创建应用程序内投放时目标用户档案与投放仪表板中显示的用户档案不一致的问题。 (CAMP-28722)
* 修复了Campaign与Assets核心服务集成的问题，该问题可能会阻止您在电子邮件中选择共享资源。

## 19.0 版 - 2019 年 1 月 {#release-19-0---january-2019}

**新增功能**

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
   <td> Email Designer常规可用性<br /> </td> 
   <td> <p>新的直观电子邮件设计工具（以前称为Creative Designer）已迁移至GA。 它现在支持旧版内容编辑器中的所有功能，包括：</p> 
    <ul> 
     <li> 使用 <a href="../../integrating/using/adding-target-dynamic-content.md">Adobe Target中的动态图像</a> </li> 
     <li> 能够 <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">在准备期间自动从URL检索内容</a> </li> 
     <li> 完全合规 <a href="../../designing/using/using-reusable-content.md#content-templates">现成的内容模板</a>. </li> 
    </ul> 
    <p>有关更多信息，请参阅<a href="../../designing/using/designing-content-in-adobe-campaign.md">详细文档</a>和<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html">操作方法视频</a>。下面列出了改进和修复。</p><p>因此，现已弃用旧版的电子邮件内容编辑器。 有关更多信息，请参阅此 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=zh-Hans#release-notes">页面</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> 事务性电子邮件中的产品列表<br /> </td> 
   <td> <p>现在，您可以在事务型电子邮件中引用一个或多个产品集合。 例如，您可以自动发送一封有关购物车弃置的电子邮件，其中列出用户购物车中的所有产品，并附带每个产品的图像、价格和链接。</p><p>有关更多信息，请参阅<a href="../../designing/using/using-product-listings.md">详细文档</a>和<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html">操作方法视频</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> Email Designer中的移动设备视图<br /> </td> 
   <td> <p>现在，您可以在编辑电子邮件内容时切换到专用的移动视图。 借助此功能，您可以通过单独编辑移动设备显示的所有样式选项来微调电子邮件的响应式设计，例如调整边距、缩小字体大小、使用不同的背景颜色等。</p><p> 有关更多信息，请参阅<a href="../../designing/using/plain-text-html-modes.md#switching-to-mobile-view">详细文档</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内消息传送测试版改进<br /> </td> 
   <td> <p>应用程序内消息传递测试版功能已得到增强，现可提供以下功能：</p> 
    <ul> 
     <li> 应用程序内测试版渠道符合GDPR </li> 
     <li> 与Analytics API集成以填充“触发器”下拉列表 </li> 
     <li> 投放模板的直观外观和描述 </li> 
     <li> 从可用性角度增强了创作界面 </li> 
    </ul> <p>有关更多信息，请参阅<a href="../../channels/using/about-in-app-messaging.md">详细文档</a>。</p> </td> 
  </tr> 
 </tbody> 
</table>

**改进**

* 现在，加载数据活动中的新选项允许您将后处理阶段应用到包含被拒绝记录的文件(例如， Zip 格式压缩）。(CAMP-24521)
* 现在，更新数据活动中的新选项允许您配置上传数据的批次大小上限。 (CAMP-28400)
* 改进了用户档案的地址状态选择。 在选择国家/地区时，“州”下拉列表现在将自动更新相关的州值。 (CAMP-28874)
* 现在，如果集客过渡为空，则提取文件活动中的新选项将阻止生成文件。 这可避免在SFTP服务器上创建和上传空文件。
* 投放摘要报告已得到改进。
* 增加了定义用户档案地址时可用的国家/地区列表。 (CAMP-26707)
* 现在，尝试导入内置工作流时会显示错误消息。

**电子邮件设计工具**

* 修复了在电子邮件模板或使用Email Designer创建的内容片段上启用地理单位功能的问题，即使此功能在Adobe Campaign中被禁用，导致模板或片段在尝试再次访问时不可用。 (CAMP-28174)
* 修复了在使用Email Designer编辑内容时阻止保存动态内容条件的问题。 (CAMP-27905)
* 修复了在电子邮件设计工具中编辑消息的纯文本版本并中断HTML同步后，从电子邮件HTML中删除内容版本的问题。 (CAMP-28507)
* 修复了在使用Internet Explorer 11时阻止Email Designer界面打开的问题。 (CAMP-28273)
* 修复了扭曲Microsoft Outlook呈现应用于Email Designer按钮的样式设置的问题。
* 修复了Email Designer中存在的一个问题，该问题导致可编辑电子邮件中使用的内容片段的URL，在默认情况下锁定该片段时，不应出现该问题。
* 修复了导致Microsoft Office中无法显示Email Designer分隔条组件的问题。
* 修复了在使用旧版电子邮件内容编辑器查看从AEM同步的内容时，导致某些Internet浏览器页面冻结的问题。 (CAMP-29068)
* 修复了在使用旧版电子邮件内容编辑器时，单击电子邮件中的任意图像时发生的错误。 (CAMP-30424)
* 修复了在使用Email Designer编辑电子邮件时阻止显示新创建片段的问题。 (CAMP-29928)
* 修复了在使用Email Designer创建并使用Outlook Web邮件客户端接收的电子邮件中阻止正确显示按钮文本的问题。
* 现在可以使用Email Designer创建用户档案事务型消息。 (CAMP-28900)
* 修复了Email Designer中的错误，该错误会导致在准备期间从URL自动检索内容时，内容可编辑，而此错误应被锁定。

**修补程序**

* 修复了在动态报告中显示错误投放日志的问题。 (CAMP-23446)
* 修复了可能影响退回摘要报表中数字的问题(CAMP-28703)
* 修复了Campaign与Assets核心服务集成的问题，该问题可能导致在选择时无法显示资产 **[!UICONTROL Image shared from Adobe Experience Cloud]** 一封电子邮件(CAMP-28732)。
* 修复了即使已在SMPP外部帐户中授权音译，仍阻止发送包含“oe”字符的短信消息的问题。 (CAMP-29041)
* 修复了在工作流中使用分段活动时可能显示重复记录的问题。 (CAMP-28743)
* 修复了无法删除工作流活动中列的一个值映射的问题。 (CAMP-28708)
* 修复了在文件传输活动中通过“测试以查看文件是否存在”选项使用通配符时的问题。 (CAMP-28977)
* 修复了在更新外部帐户设置时文件传输活动中可能发生的问题。 (CAMP-28894)
* 修复了在使用“电子邮件不为空”条件时查询编辑器中的自定义筛选器的问题。 (CAMP-28741)
* 修复了在导出包含超过100,000条记录的自定义资源表时可能发生的问题。 (CAMP-28150)
* 修复了阻止删除链接到触发器的事务性消息的问题。 (CAMP-28385)
* 删除了在某些SMS日志中显示的不安全密码。
* 修复了由于Adobe Campaign发送的空密码而导致与SMPP模拟器的连接失败的问题。
* 修复了在短信连接不稳定时阻止发送营销活动的问题。
* 修复了在动态报告中显示已删除投放的问题。
* 修复了在工作流中使用扩充活动时，可能阻止从投放日志、跟踪日志和排除日志表中检索其他数据的问题。
* 修复了在使用“N基数收集链接”链接类型和“删除目标记录意味着通过链接删除记录引用”选项时可能发生的GDPR删除请求问题。
* 修复了报表共享的问题。
* 修复了在发送推送通知时可能导致吞吐量问题的情况。
* 修复了直邮输出文件缺少字段的问题。
* 修复了允许用户修改内置工作流的问题。
* 修复了在基于活动模板创建活动时，包括具有已配置提取活动的工作流的问题。 (CAMP-29198)
* 修复了文件提取活动阻止对多个元素使用相同表达式的问题。 (CAMP-29182)
* 修复了查询编辑器中rtEvent的broadlog和跟踪日志之间存在连接条件的问题。 (CAMP-28780)
* 修复了导致无法保存对“Specific action”登陆页面选项的修改的问题。 (CAMP-29422)
* 修复了阻止在工作流中导出事件有效负载的问题。 (CAMP-29029)
* 修复了阻止阻止列表上的短信号码在短信消息中排除的问题。 (CAMP-28898)
* 修复了在处理传入消息时，如果出现错误，可能无法通知SMPP提供商的问题。 (CAMP-29804)
* 修复了允许删除具有关联投放的外部帐户的问题。 (CAMP-29738)
* SMS消息的发送吞吐量已得到改进和稳定。
* 修复了在短信消息中无法使用“~”字符的问题。 (CAMP-29172)
* 修复了使用发送时间优化选项进行投放时出现的问题。 (CAMP-29231)
