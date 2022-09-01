---
title: 2019 年版发行说明
description: 本页列出了所有 2019 版的 Adobe Campaign Standard。
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 6a53e6f5-9b69-4068-ab7d-10e22e266277
source-git-commit: 177d9e0f8d61c000f01ac5e148dbd98fef0538ff
workflow-type: tm+mt
source-wordcount: '7588'
ht-degree: 8%

---

# 2019 年版发行说明{#release-notes-2019}

[发行计划](https://helpx.adobe.com/cn/campaign/kb/acs-release-planning.html) | [控制面板版本](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=zh-Hans) | [文档更新](../../rn/using/documentation-updates.md) | [最新发行说明](../../rn/using/release-notes.md) | [已弃用的功能](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=zh-Hans#release-notes)

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
   <td> <p>CCPA是加利福尼亚州新推出的隐私法，旨在协调数据保护要求并使之现代化，于2020年1月1日正式生效。 CCPA适用于为居住在加利福尼亚州的数据主体持有数据的Adobe Campaign客户。</p>
   <p>除了Adobe Campaign中已有的可用隐私功能（包括同意管理、数据保留设置和用户角色）之外，我们还利用这个机会纳入了其他功能，以帮助您为CCPA做好准备：</p>
   <ul>
    <li>访问权和删除权：我们将利用为GDPR添加的功能。 <a href="https://helpx.adobe.com/content/help/zh-Hans/campaign/kb/acs-privacy.html#righttoaccess">了解详情</a> </li>
    <li><p>创建隐私请求时，隐私核心服务中已添加法规类型（GDPR或CCPA）。 您应将此方法应用于所有访问和删除请求。将 Campaign API 和接口用于访问和删除请求的方法已被弃用。请参阅<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html">已弃用和已删除的功能</a>一文。</p></li>
    <li>A <strong>CCPA选择退出</strong> 字段，以便Adobe Campaign用户跟踪消费者是否选择退出了出售个人信息。 <a href="https://helpx.adobe.com/cn/campaign/kb/acs-privacy.html#ccpa">了解详情</a>。</li>
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
    <p>Adobe Campaign Standard与Microsoft Dynamics 365之间的集成现已可用。 您将能够将联系人和自定义实体记录从Dynamics 365传输到Campaign，并将电子邮件事件数据从Campaign返回Dynamics 365，以更好地协调销售/营销。</p>
    <p>请参阅 <a href="../../integrating/using/d365-acs-get-started.md">详细文档</a> 以设置此集成。</p>
  </td>
  </tr> 
 </tbody> 
</table>

**改进**

* 更新了动态报告的同意弹出窗口，以包含Adobe Campaign Standard和Microsoft Dynamics 365集成。 接受条款后，在使用Adobe Campaign Standard/Microsoft Dynamics 365集成和动态报告时，将包含用户档案数据。 [了解更多](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) (CAMP-29766)
* 修复了在接收投放警报时显示错误联系日期的问题。
* 现在，在使用未知上下文参数提交事务型消息事件时，Campaign会返回“400”错误消息，而不是“500”。 (CAMP-28632)
* 新 **排除校样** 区段已添加到动态报告中。 现在，默认情况下会选择此区段来过滤您的报表。 [了解更多信息](../../reporting/using/list-of-components-.md#segments)
* 的 **消息过期** 选项。 利用此选项，可指定Apple(APNS)或Android(FCM)将不再发送消息的过期日期。 [了解更多信息](../../channels/using/customizing-a-push-notification.md#add-expiration-date)
* 已对 **加载文件** 活动：工作流日志已变得更清晰，并更详细地说明了在文件加载失败时发生的错误。 激活 **在文件中保留rejects** 选项已重命名 **拒绝**. [了解更多信息](../../automating/using/load-file.md)
* 已在发送日志中添加多语言相关日志，以便更好地了解由于上传的CSV文件中缺少语言而导致的发送失败。

**安全性增强**

* 修复了通过隐私请求删除量化用户档案信息的问题，该问题会删除隔离列表中除电子邮件地址之外的所有数据。
* 增强了安全性，以防止在电子邮件标头中注入。
* 增强了针对可使用xtk表达式(电子邮件HTML、文本内容和主题、短信和推送通知内容)的SSRF攻击的安全性。

**Email Designer 增强功能**

* 修复了在电子邮件中插入退订、订阅和登陆页面链接时无法跟踪的问题。 (CAMP-37809)
* 修复了在创建新电子邮件和选择模板时可能导致错误的问题。 (CAMP-38000)
* 现在，使用Email Designer编辑链接时，您可以使用 **下划线链接** 选项。 此外， **Target** 属性已添加，其默认值设置为 **无**. [了解更多信息](../../designing/using/styles.md#about-styling-links)
* 修复了电子邮件正文文本组件中的链接的颜色问题。 (CAMP-37330)
* 修复了删除图像时无法删除关联链接的问题。 (CAMP-37234)
* 修复了阻止在 **订购** 条件中动态内容的设置。 (CAMP-36883)
* 修复了搜索登陆页面时的问题。 搜索已从最初创建的50个扩展到所有数据库。 (CAMP-36839)
* 修复了在 **从：名称** 字段。 (CAMP-36606)
* 已修改轮播组件兼容性警告，以反映支持的电子邮件客户端。
* 修复了移动设备上的显示问题。 现在，高度属性始终设置为“高度：自动”。 (CAMP-35497)
* 修复了从结构组件中删除片段时HTML中存在的左侧样式和元标记问题。 (CAMP-35390)
* 修复了更新可重用内容时片段存在的问题。 (CAMP-35186)
* 修复了在电子邮件中仅显示移动设备条件内容时的问题。 (CAMP-35155)
* 修复了随机显示零宽度不间断空格的问题。 (CAMP-35116)
* 修复了 **另存为片段** 对话框。
* 修复了在图像标题和替换文本中添加HTML标记时的预览问题。
* 修复了在Email designer中编辑在旧版编辑器的电子邮件中创建的链接时的问题。
* 修复了在内容中保留重复的样式标记的问题。
* 修复了在电子邮件中插入个性化字段时日期格式存在的问题。
* 修复了从HTML模式切换到纯文本时的保存问题。
* 修复了在内联样式属性面板中单击锁定和解锁选项时添加边距值的问题。
* 修复了移动预览大小以便更好地呈现的问题。
* 修复了模板和片段中按钮的大小问题。
* 修复了在按钮组件中插入图像时图像大小的问题。

**其他变更**

* 在投放KPI页面和动态报告页面上显示数据的默认时间范围已保持一致，以防止报告结果出现差异。 (CAMP-35148)
* 应用程序证书过期后，日志中已添加错误消息。
* 负载计算预览现在包含自定义字段大小，以防止推送通知失败。 (CAMP-35303)
* 的名称 **拒绝文件** 在 **加载文件** 活动现在可以与中的相同进行个性化 **文件导出** 活动。
* 现在，可以通过API访问所有未链接到任何现成实体的自定义实体。
* 提高了大型资源上的数据库性能。
* 更清晰地描述了发送短信消息时出现的一些错误。 (CAMP-36558)
* 现在，在执行工作流的 **调度程序** 直接或通过多个活动连接到其自身的活动，因为这可能会导致实例的工作流服务器卡住。
* 已做出改进，以帮助对事务型消息传递进行故障诊断：“数据”链接在事件配置屏幕中已更名为“最后一个事务性事件”，现在它以降序方式列出接收的事件。 此外，还创建了新的事务型事件状态：&quot;targetingFailed&quot;。 当事务型消息传递模块未能扩充用于消息定位的链接时，事务型事件现在将处于此新状态（而不是“routingFailed”状态）。
* 改进了将登陆页面访问权限限制为特定地理或组织单位时的界面。 其目的是警告登陆页面可能受可见性条件的影响：现在，在创建登陆页面时必须选择地理和组织单位。 现在，在选择设备后，会显示包含相关信息的横幅。 测试登陆页面时显示的错误消息已变得更清晰。
* 在Campaign StandardAPI中，如果键值与原始键不同，或者您使用自己的业务键作为URI而不是Adobe提供的业务键，则无法使用PATCH操作修改自定义键。
* “阿尔巴尼亚语 — 马其顿语”语言已添加到首选语言下拉列表中。 (CAMP-35396)

**修补程序**

* 修复了阻止对计划报表进行排序或搜索的问题。
* 修复了触发器规则中导致AND和OR规则混合的问题。
* 修复了在Launch中将移动属性显示为已删除的问题。 (CAMP-35382)
* 修复了导致AdobeLaunch移动属性无法在Adobe Campaign中同步的问题。 (CAMP-35411、CAMP-35089、CAMP-35014、CAMP-35487)
* 修复了使用用户档案数据扩充事件时事务推送消息失败的问题。 (CAMP-34385)
* 修复了移动资产无法在多个环境中同步的问题。 (CAMP-37060)
* 修复了在推送通知中使用联系日期公式选择模板时的问题。 (CAMP-35300)
* 修复了可能导致消息发送服务崩溃的问题。 (CAMP-35287)
* 修复了所有都是使用第一个事件日期定义的定期直邮的问题。 (CAMP-35139)
* 修复了新扩展的问题 **用户档案** 无法用于查询的自定义资源。 (CAMP-35119)
* 修复了 **修复数据库结构** 模式。 (CAMP-35118)
* 修复了在broadlogs中添加聚合数据时导致SQL日志错误的问题。 (CAMP-35034)
* 修复了在创建 **分段** 活动。 (CAMP-35033)
* 修复了 **查询** 阻止 **encryption_aescbcDecrypt** 函数 **encryption_aescbcEncrypt** 函数。 (CAMP-34952)
* 修复了可能阻止 **跟踪日志** 从显示在投放中。 (CAMP-34855)
* 修复了在使用 **发送时间优化** 自定义日期公式，该公式可阻止由于工作流的其他数据出错而发送推送通知。 (CAMP-30336)
* 修复了可能阻止发布自定义资源的问题。 (CAMP-37425)
* 修复了阻止管理员用户修改导入包的问题。  (CAMP-37176)
* 修复了在投放活动连接到空时，工作流中阻止发送校样的问题 **读取受众** 活动。 (CAMP-37164)
* 修复了自定义资源无法导入新环境的问题。 (CAMP-36506)
* 修复了热点单击报表中可能导致图像隐藏百分比的问题(CAMP-36407)
* 修复了尝试导出投放描述字段时发生的问题。 (CAMP-35467)
* 修复了在投放完成后，可能会将投放状态保留为“开始挂起”的问题。 (CAMP-35355)
* 修复了在启用后，禁用SQL日志后，工作流日志无法显示的问题。

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
   <td> <p>为了实现更深入的个性化，外部API活动允许您通过REST API调用将外部系统中的数据引入工作流。 REST端点可以是客户管理系统、Adobe I/O Runtime或Adobe Experience Cloud REST端点（例如Data Platform、Target、Analytics、Campaign）。</p><p>此功能目前处于公共测试阶段。</p><p>有关更多信息，请参阅<a href="../../automating/using/external-api.md">详细文档</a>和<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">操作方法视频</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 工作流区段报告<br /> </td> 
   <td> <p>此功能允许营销人员按区段代码划分其交付性能。 当您创建工作流并使用分段活动将区段分配给投放群体时，这些区段现在可以进入相同的投放。 这样，您就可以在一个投放中根据多个区段显示打开/点击量统计信息。</p><p>有关更多信息，请参阅<a href="../../reporting/using/creating-a-report-workflow-segment.md">详细文档</a>和<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">操作方法视频</a>。</p></td>
  </tr> 
 </tbody> 
</table>

**安全性增强**

* 修复了一个安全问题，以防止对获取图像的无效请求进行拒绝服务(DoS)攻击。 (CAMP-33454)

**Email Designer 增强功能**

* 修复了每次添加组件时向HTML模板添加其他HTML样式标记的问题，该问题可能会显着增加模板的大小。 (CAMP-34694)
* 修复了可能阻止某些右上方工具栏菜单选项可用的问题。 (CAMP-34577)
* 修复了将镜像页面URL内容块插入到电子邮件内容中时发生的问题。 (CAMP-34779)
* 修复了在电子邮件中使用JSPP代码时，难以编辑内容的问题。 (CAMP-34574)
* 修复了在向图像添加超链接时，导致图像顶部截断的问题。 (CAMP-34382)
* 修复了在Firefox中使用Email Designer时的显示问题。 (CAMP-34364)
* 修复了在电子邮件中定义动态内容时高级模式出现的几个问题。 (CAMP-34351、CAMP-34333、CAMP-34331)
* 修复了动态内容规则编辑器(CAMP-34304、CAMP-34303)出现的几个问题。
* 修复了可能阻止链接字段显示在电子邮件设计器设置窗格中的问题(CAMP-33749)。
* 修复了已发送电子邮件中YouTube图标超大的问题。 (CAMP-33726)
* 修复了使镜像页面内容可编辑的安全问题。 (CAMP-33691)
* 修复了在动态内容中使用大于符号时中断HTML输出的问题。 (CAMP-33688)
* 修复了在Email Designer中编辑文本时使用撤消选项时发生的问题。 (CAMP-32565)
* 修复了在撤消样式而不是删除样式时创建额外标记的问题。 (CAMP-32359)
* 现在，您可以定义电子邮件中使用的每个组件是否将仅在桌面设备上显示，或仅在移动设备上显示。
* 您现在可以设置社交内容组件的宽度和高度。
* 修复了删除动态内容后无法删除动态内容旧源代码的问题。
* 修复了在修改电子邮件主题后可能阻止更新该主题的问题。
* 修复了将n:n列结构放入工作区后无法选择的问题。
* 修复了导致电子邮件仪表板中消息的缩略图模糊的问题。
* 修复了Outlook中收到的电子邮件无法正确显示背景的问题。
* 修复了Email Designer主页上的一些排序问题。
* 修复了使用动态内容复制变体时发生的问题。
* 从“Email Designer设置”窗格中删除了一些不需要的字段。

**其他改进**

* 通过与Adobe Experience Platform位置服务的集成，Adobe Campaign现在可以兼容，通过Experience PlatformSDK向移动应用程序的订阅者发送基于位置的营销消息。 有关更多信息，请参阅[详细文档](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md)。
* 报表功能已得到改进，可提供更好的体验。 要使用此功能，您需要接受动态报告使用协议。 有关更多信息，请参阅 [详细文档](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
* 在工作流中，新增了一个选项，用于预览工作流接下来的十次执行。 有关更多信息，请参阅 [详细文档](../../automating/using/scheduler.md).
* 在调度程序活动中，新选项允许您为每月投放选择特定一周中的特定日期。 有关更多信息，请参阅 [详细文档](../../automating/using/scheduler.md).
* 现在，在创建无聚合期的定期投放时，利用投放仪表板，可在发送投放之前请求确认。 有关更多信息，请参阅 [详细文档](../../sending/using/confirming-the-send.md).
* 现在，您可以使用在工作流外部信号活动中声明的事件变量对投放的标签进行个性化。 有关更多信息，请参阅 [详细文档](../../automating/using/calling-a-workflow-with-external-parameters.md).
* GDPR删除查询已得到改进，以提高性能。 (CAMP-33504)
* “ftp”选项已从外部帐户配置界面中删除。 (CAMP-34472)
* 现在，您可以为每封电子邮件启用或禁用SMTP测试模式选项。 有关更多信息，请参阅 [详细文档](../../administration/using/configuring-email-channel.md#smtp-test-mode). (CAMP-34602)

**其他变更**

* 在投放属性界面中添加了警告。 它指定根据投放的聚合期和解冻期准备投放，以便每天多次调用工作流，您应确保它们没有任何期限。 (CAMP-34393)
* 在自定义资源配置屏幕中添加了警告。 我们建议为自定义资源 ID 最多使用 30 个字符。这也适用于自定义资源字段、键值、索引和链接。
* 现在，在尝试删除登陆页面用作确认消息的事务型消息时，会显示一条消息。
* 当活动运行时间超过6小时时，工作流日志中现在会显示警告。 这不适用于推送通知、投放、信号、开始、结束、分支、AND-joint、计划和等待活动。
* 现在，当您达到同时运行的最大工作流数时，工作流日志中会显示警告。
* 处于暂停或失败状态超过7天的工作流现在将停止，以节省磁盘空间。 清理任务会显示在工作流日志中。
* 现在，使用“传输文件”活动时，如果文件大小超过可用磁盘空间，则会记录错误。
* 不能再为应用程序内消息中的辅助按钮选择重定向到目标URL操作。

**修补程序**

* 修复了可能导致GDPR访问请求失败的问题。
* 修复了在收到唯一用户档案的多个触发器时，可能导致触发器丢弃的问题。
* 修复了可能导致登录后出现错误的自定义资源发布错误消息的问题。
* 修复了在创建或扩展自定义资源时显示空白页面的问题。
* 修复了将appSubscriptionrcp作为定向维度的受众无法在移动投放中进行定向的问题。
* 修复了阻止将硬退回的电子邮件地址添加到隔离的错误。 (CAMP-24587)
* 修复了在添加分类规则后在保存分类之前将其删除时发生的问题。 (CAMP-32789)
* 修复了在禁用动态内容时可能阻止显示登陆页面内容的问题。 (CAMP-32924)
* 修复了对主投放属性使用个性化时发生的定期投放问题。 (CAMP-32983)
* 修复了工作流中阻止从包含传入短信消息数据的过渡读取结果的问题。 (CAMP-33134)
* 修复了将分支和排除活动组合在一起以创建受众时工作流中发生的问题。 (CAMP-33401)
* 修复了可能阻止显示镜像页面内容以及为定期投放发送校样消息的问题。 (CAMP-33413)
* 修复了在用户档案和受众之间使用并集活动时导致错误的问题。 此问题是由于输入转换中的标识键不兼容所致。 (CAMP-33713)
* 修复了测试活动中阻止“recCount”表达式在双击时使用正确语法的问题。 (CAMP-33756)
* 修复了在打开账单技术工作流日志时可能导致错误消息的问题。 (CAMP-34313)
* 修复了在通过订阅配置复选框字段时可能出现的登陆页面中的问题。 (CAMP-34369)
* 修复了配置列表并向其添加“图标”字段时发生的问题。 (CAMP-34585)
* 修复了在加载文件工作流活动中无法使用“|”和“%”符号作为日期或时间分隔符的问题。 (CAMP-34706)
* 修复了在登陆页面中将可见性条件与复选框结合使用时出现的问题。 (CAMP-34802)
* 修复了当过滤维度设置为跟踪日志，而目标维度设置为用户档案时，扩充活动中阻止字段在“附加数据”选项卡中显示的问题。
* 修复了导致导出“workflowTemplate”资源时显示错误消息的问题。
* 修复了创建新用户档案时，如果从对话框中选择了“国家/地区代码”字段，则无法保存该字段的问题。
* 修复了使用直邮导入模板(updateQuarinesDeliveryLogsDirectMail)时发生的几个问题。
* 修复了与资产（按需）集成相关的问题。
* 修复了放大时间轴视图时出现的问题。 (CAMP-33628)
* 修复了阻止针对具有计划日期和时间的电子邮件立即发送校样的问题。 (CAMP-33723)
* 修复了与用户注销时生成错误日志的事务型消息传递相关的问题。 (CAMP-31698)
* 修复了计划电子邮件时在特定环境中可能发生的错误。
* 修复了导致更新投放执行工作流失败的问题。
* 修复了在主题包含多行时损坏电子邮件内容的安全问题。


## 19.2.7 版 - 2019 年 7 月 {#release-19-2-7---july-2019}

**改进**

* GDPR删除查询已得到改进，以提高性能。
* 修复了在19.2升级后可能导致Web崩溃的问题。 (CAMP-34862)
* 修复了可能阻止非管理员用户保存或计划报表的问题。 (CAMP-31133)
* 修复了在加载文件工作流活动中使用“|”作为日期分隔符时的问题。 (CAMP-34706)

## 19.2.4 版 - 2019 年 6 月 {#release-19-2-4---june-2019}

**电子邮件设计工具**

* 修复了在HTML中使用空样式标记时阻止用户编辑片段的问题。 这是19.2.3中CAMP-33778的后续修复。

## 19.2.3 版 - 2019 年 6 月 {#release-19-2-3---june-2019}

**电子邮件设计工具**

在19.2版本中引入了一系列改进和修复，以优化片段。 新创建的片段将可以无缝工作。 之前构建的片段呈灰显状态，需要迁移到新格式。 为此，请单击每个片段并验证其迁移到新格式。 我们建议您在迁移一些片段之前先测试这些片段。

* 修复了在解锁片段后阻止用户编辑片段的问题。 这会在更新到19.2时影响现有片段。 (CAMP-33778)
* 修复了使用动态内容时的问题。 在HTML中添加了额外的空格。

**其他改进**

* 修复了在短信连接器断开后，短信发送无法恢复的问题。
* 修复了在启用TLS时可能关闭SMPP连接的问题。
* 修复了在启用TLS时可能关闭SMPP连接的问题。
* 在Campaign中添加了“Launch_URL_Campaign”选项，以管理使用Adobe Experience Platform Mobile SDK创建的移动应用程序的属性。
* 修复了在上传新创建移动资产的证书并退出移动应用程序资产页面后，导致“沙盒”环境选项未选中的错误。
* 修复了阻止使用服务资源中的信息扩充事务型消息内容的问题。 (CAMP-33707)
* 修复了在尝试使用阻止列表户档案从服务取消订阅时，“订阅”登陆页面中发生的问题。

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
   <td> <p>为了帮助提高管理员用户的工作效率，您可以轻松监控容量并管理实例的设置（从SFTP服务器管理开始）。</p><p>有关更多信息，请参阅<a href="https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hans">详细文档</a>和<a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/control-panel-overview.html?lang=zh-Hans">操作方法视频</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 本地通知<br /> </td> 
   <td> <p>本地通知消息传送允许您在移动应用程序中提供新数据时通知您的用户，即使没有访问互联网或未在前台运行移动应用程序的权限。 本地通知由移动设备应用程序在特定时间根据事件触发。</p><p>有关更多信息，请参阅<a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">详细文档</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 工作流增强 — 向外部信号活动添加有效负载<br /> </td> 
   <td> <p>在成功满足定义的条件时，通过另一个工作流中的有效负载或REST API调用启动工作流，以与外部系统集成。 此外，还包含一个 <strong>测试</strong> 活动中，您可以在此功能上运行测试。</p><p>有关更多信息，请参阅<a href="../../automating/using/calling-a-workflow-with-external-parameters.md">详细文档</a>和<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/execution-activities/external-signal-activity.html">操作方法视频</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 登陆页面增强 — Google reCAPTCHA<br /> </td> 
   <td> <p>利用Google reCAPTCHA防止登陆页面上的垃圾邮件，无需客户采取任何措施。</p><p>有关更多信息，请参阅<a href="../../channels/using/configuring-landing-page.md#setting-google-recaptcha">详细文档</a>。</p></td> 
  </tr> 
 </tbody> 
</table>

**安全性增强**

* 修复了报表工作区中潜在的Clickjacking安全问题。

**Email Designer 增强功能**

* 修复了复制片段并尝试在Email Designer中使用它们时发生的问题。 (CAMP-33193)
* 修复了在Email Designer界面中使用内联元素时创建多余空格的问题。 (CAMP-32163)
* 修复了在Email Designer中保存电子邮件内容后删除用户添加的一些其他HTML标记属性的问题。 (CAMP-32162)
* 修复了在Email DesignerHTML模式下即使删除Microsoft Office标记后仍显示该标记的问题。 (CAMP-32141)
* 如果您使用Email Designer的早期版本创建了电子邮件，则打开此电子邮件内容时，会出现一个弹出窗口，提示用户更新到最新版本。 (CAMP-31529)
* 修复了在将图像发送到某些消息传送客户端时，可能会扭曲使用Email Designer创建的电子邮件中图像的问题。 (CAMP-31407)
* 修复了在HTML模式下创建列表或按钮等某些元素时，无法在纯文本模式下正确显示的问题。 （CAMP-32582 和 CAMP-32542）
* 修复了阻止在内容模板或片段属性中显示50个以上组织单位的问题。 (CAMP-32932)
* 修复了当收到通过Email Designer on Outlook创建的电子邮件时，视区背景颜色出现的问题。 (CAMP-31402)
* 修复了在Outlook中打开使用Email Designer创建的电子邮件内容时无法响应的问题。 (CAMP-31400)
* 修复了在电子邮件主题中使用动态内容时无法正常工作的问题。 (CAMP-32837)
* 修复了与未正确转义的电子邮件主题相关的问题。
* 修复了阻止在Email Designer左侧面板中加载片段的问题。
* 修复了在刷新片段列表时，电子邮件内容编辑期间创建的片段无法在Email Designer左侧面板中显示的问题。
* 修复了在电子邮件中使用动态内容时出现的几个问题。
* 修复了在尝试使用RGB值定义颜色时拾色器出现的问题。
* 修复了在移动设备上收到电子邮件时镜像页面无法响应的问题。

**事务型消息传递增强功能**

为优化操作和性能，已向事务性消息传递渠道添加了多项改进。

* 事务型消息持续时间已延长，可确保所有消息在过期之前发送，尤其是在执行重试时。
* 通过在不同发送线程上分配负载，提高了事务性消息传递性能。
* 事务性消息传递流程已进行优化，以便能够同时开始对同一消息进行多次分析。
* 修复了可能导致事务推送通知的吞吐量和延迟不一致的问题。
* 修复了事务性消息执行投放的目标受众显示错误的问题。
* 修复了导入具有事件配置和关联事务型消息的包时发生的问题。 有关更多信息，请参阅 [详细文档](../../channels/using/getting-started-with-transactional-msg.md#exporting-and-importing-transactional-messages).
* 修复了从为包含产品清单的事务型消息创建的测试用户档案中删除收集数据的问题。

**其他变更**

* 短信外部帐户中添加了新选项。 它允许限制发送短信的MTA进程的最大数量，以便更好地控制并行连接的数量。 有关更多信息，请参阅 [SMS连接器协议和设置](https://helpx.adobe.com/cn/campaign/kb/sms-connector-protocol-and-settings.html) 技术说明。
* 现在，在发布带有API扩展的资源时，如果API已发布，则每当再次发布时，都会自动更新该API。 以前，此操作是手动执行的，如果未能更新API，则可能会损坏此API的用户档案或服务资源。 有关更多信息，请参阅 [详细文档](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* 邮政编码维度已从动态报告中删除。 我们建议改用“城市”、“国家/地区”和“州”维度。
* 应用程序内消息的“首次启动”生命周期事件触发器已删除。
* 现在，在导出包含安全组的资源包时，它包含分配给每个组的角色。 (CAMP-32960)
* 在加载文件活动中，您可以使用新选项检查上传文件的列是否与列定义匹配。 有关更多信息，请参阅[详细文档](../../automating/using/load-file.md)。(CAMP-32229)
* 现在，工作流可以通过有效负载启动，从而允许您在工作流中的活动之间使用和共享外部参数。 有关更多信息，请参阅[详细文档](../../automating/using/calling-a-workflow-with-external-parameters.md)。(CAMP-29412和CAMP-29413)
* Campaign StandardAPI现在允许您使用有效负载更新用户档案的地理和组织单位。 有关更多信息，请参阅[详细文档](../../api/using/get-started-apis.md)。
* 无法访问数据库中的对象时的错误消息已变得清晰易懂。
* 在提取文件活动中，更新了定义要导出的文件名称时的Javascript功能。 现在，只有formatDate函数可在“输出”字段中使用。 有关更多信息，请参阅[详细文档](../../automating/using/extract-file.md)。
* 自定义资源的自动序列ID生成已得到改进。 默认情况下，新自定义资源的主键位为64位。
* 自定义资源发布测试模式已得到改进。 现在，如果上次自定义资源发布失败且未修复，则会向用户显示警告消息。 自定义资源发布失败后，您可以回滚到上一个工作版本。 有关更多信息，请参阅[详细文档](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。
* 在传输文件活动中添加了新选项。 利用此功能，可在SFTP模式下使用“文件下载”操作时对文件进行排序。 有关更多信息，请参阅[详细文档](../../automating/using/transfer-file.md)。(CAMP-33109)

**修补程序**

* 修复了在重新加载短信设置时可能导致MTA内存泄漏的问题。
* 修复了可能阻止在修复模式下发布数据库更新的问题。
* 修复了导致Adobe Analytics报表与Adobe Campaign动态报表不一致的问题。 (CAMP-25393)
* 修复了导致报表共享工作流失败的错误。
* 修复了阻止用户仅使用媒体URL发送应用程序内消息的错误。
* 修复了即使移动设备应用程序的证书未上传到实例，仍会显示该应用程序的问题。
* 修复了在使用 **定位移动设备应用程序的所有用户** 模板。
* 已配置新的Campaign Standard实例。 (CAMP-32635和CAMP-32344)
* 修复了阻止在工作流中自定义日期公式的错误。 (CAMP-30336)
* 修复了定义自定义日期公式时的问题，该公式可能会阻止下拉列表中的“附加数据”和“段码”字段可用。 (CAMP-32383)
* 修复了“传输文件”和“提取文件”活动在加密后无法查找文件拒绝的问题。 (CAMP-32377)
* 修复了API中可能阻止lineCount过滤器呈现确切总计数的问题。 (CAMP-31424)
* 修复了登陆页面中的一个问题，该问题可能会在修改输入字段后阻止显示更新的值。 (CAMP-31401)
* 修复了可能导致信号活动意外激活的问题。
* 修复了受众为空时可能无法显示电子邮件预览的问题。
* 修复了激活“集客过渡为空时，不生成文件”选项时“提取文件”活动可能生成文件的问题。
* 修复了在投放能力工作流未成功完成时导致其关闭的问题。
* 修复了可能阻止用户保存或计划报表的问题。 (CAMP-31133)

## 19.1.3 版 - 2019 年 3 月 {#release-19-1-3---march-2019}

**Email Designer 增强功能**

* 修复了在保存模板后阻止修改模板的问题。
* 修复了在电子邮件中使用之前创建的模板时的各种问题。
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
   <td> 推送渠道报表改进<br /> </td> 
   <td> <p>推送渠道报表中添加了多项增强功能，使您能够更直观地衡量用户参与度。 在此版本中，我们将推送渠道量度列表扩展为三个不同的量度：展示次数、点击次数、打开次数（应用程序打开次数），可帮助您更有效地测量和分析用户与推送通知的交互情况。 除此之外，我们还在对这些量度的定义和实施进行标准化。 推送通知内置报表还通过常用的可视化图表和量度进行了改进。</p><p> 有关更多信息，请参阅<a href="../../reporting/using/push-notification-report.md">详细文档</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 适用于移动设备应用程序的Launch集成<br /> </td> 
   <td> <p>此版本包含将Adobe Campaign与Adobe Experience Platform Launch和Mobile SDK中适用于Adobe Campaign Standard的Android和iOS扩展的GA版本集成。 这些扩展支持推送消息、应用程序内消息传送和移动应用程序配置文件更新。</p><p> 有关更多信息，请参阅<a href="https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdk.html">详细文档</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 移动设备应用程序内消息传送<br /> </td> 
   <td> <p>此版本包含Campaign中应用程序内渠道的GA版本。 从功能角度来看，测试版中最引人注目的新增内容是：应用程序内渠道的动态报表以及Mobile SDK与MCIAS之间的安全握手(Marketing Cloud应用程序内消息传送服务，为SDK提供应用程序内规则)。 安全握手可确保用户PII数据不会落入恶意人手中，并且通过在用户每次注销时清除消息缓存，使您能够在共享设备上维护用户的隐私。</p><p>有关更多信息，请参阅 <a href="../../channels/using/about-in-app-messaging.md">详细文档</a> 和 <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/in-app/in-app-message-overview.html">应用程序内教程</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> 工作流增强功能<br /> </td> 
   <td> <p>添加了以下工作流功能：</p> 
    <ul> 
     <li> 现在，您可以从同一Campaign实例复制粘贴工作流或其他工作流中的活动。 这样，您就可以轻松复制整个工作流或特定活动，并保留最初定义的设置。 有关更多信息，请参阅<a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">详细文档</a>。(CAMP-20014) </li> 
     <li> 使用 <strong>加载文件</strong> 活动时，您现在可以向包含被拒绝记录的文件名中添加时间戳。 有关更多信息，请参阅<a href="../../automating/using/load-file.md#configuration">详细文档</a>。 </li> 
     <li> <strong>查询</strong> 和 <strong>分段</strong> 现在，如果活动未检索任何数据，则允许您启用叫客过渡。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**安全性增强**

* 生成的登陆页面HTML代码已更新，以防止索引搜索引擎。

**Email Designer 增强功能**

* 由Behance艺术家设计的一套四款一流的响应式电子邮件模板现已推出。

   有关更多信息，请参阅[详细文档](../../designing/using/using-reusable-content.md#content-templates)。

* 我们新的入门体验可帮助您更快地开始创建电子邮件，并让您更轻松地访问文档和教程。

   有关更多信息，请参阅[详细文档](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page)。

* 现在，您可以根据需要灵活地配置列数和宽度。

   有关更多信息，请参阅[详细文档](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

* 在移动设备视图中编辑时，您可以隐藏仅在移动设备显示屏中的某些组件，以便有效地使用空间。

   有关更多信息，请参阅[详细文档](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)。

* 现在，您可以在现有的渠道之上，将自定义社交渠道添加到电子邮件模板。
* 修复了在使用18个以上结构时阻止向下滚动结构菜单的问题。 (CAMP-31173)
* 修复了在转发包含随Adobe Campaign一起发送的预标头的电子邮件时，内容顶部显示预标头的问题。 (CAMP-30736)
* 修复了在单击 **刷新AEM内容** 选项。 (CAMP-29984)
* 修复了阻止从Adobe Target使用动态图像的几个问题。
* 修复了在准备时检索内容时，如果先前从URL导入了内容，则预览无法更新的问题。
* YouTube图标已添加到 **社交** 内容组件。
* 的 **列表** 为Email Designer面板中显示的内容组件和片段添加了视图。

**其他改进**

* Adobe Campaign现在完全兼容SDK V4和AEP SDK应用程序。
* Adobe Campaign支持Wear OS by Android上的推送通知以及watchOS by Apple。
* 在界面中导航时可能显示的警告和错误消息变得更加清晰易懂。
* 现在，您可以向与选择启用和选择禁用相关的用户档案列表列（“不再联系……”字段）进行添加。
* “配置文件创建”屏幕中的“时区”下拉列表已从“地址”部分移至界面的上部。
* 现在，您可以在配置自定义资源屏幕时添加分隔符，从而将字段组织为不同的类别。

   有关更多信息，请参阅[详细文档](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration)。

**其他变更**

* Adobe Campaign和Adobe Experience Cloud将从2019年春季开始停止对Microsoft Internet Explorer 11和Campaign Standard19.2版本的支持。 请切换到 Microsoft Edge 或其他受支持的浏览器。请参阅 [已弃用和已删除的功能](../../rn/using/deprecated-features.md) 页面。
* 的 **国家/地区代码** 字段已重命名为 **国家/地区代码**.

**修补程序**

* 修复了在向电子邮件事务型消息添加测试用户档案时阻止发送消息的问题。 (CAMP-29854)
* 修复了在同时触发从所有渠道发送消息时，如果一个渠道的发送量较低，则会减慢从其他渠道发送消息的问题。
* 修复了在尚未建立外部帐户连接时导致MTA开始发送短信消息的问题。
* 修复了调度程序活动执行频率和开始时间出现的问题。 (CAMP-30745)
* 修复了使用扩展配置文件资源生成PKEY时可能发生的问题。 (CAMP-30285)
* 修复了基于日历日的疲劳规则可能发生的问题。 (CAMP-30136)
* 修复了在尝试访问名称以“Base”结尾的自定义资源时可能发生的问题。 (CAMP-30109)
* 修复了阻止使用PATCH调用将用户档案订阅服务的问题。 (CAMP-29728)
* 修复了通过加载文件活动导入XML文件时可能损坏工作流的问题。 (CAMP-29208和CAMP-28205)
* 修复了链接自定义资源时可能阻止生成反向基数链接的问题。 (CAMP-30476)
* 修复了仅使用段码时无法扩展投放日志的问题。
* 修复了在工作流中使用文件传输活动时可能会复制行的问题。
* 修复了阻止在选定时间发送计划报表的问题。
* 修复了导致工作流中应用程序内投放的“待交付”KPI与“已发送”KPI不一致的问题。
* 修复了跟踪无法用于使用自定义HTML创作的应用程序内消息的问题。
* 修复了在工作流中使用应用程序内投放内容时无法保存的问题。
* 修复了阻止向管理员显示移动应用程序的问题。
* 修复了导致可投放性更新技术工作流失败的问题。 (CAMP-26387)
* 修复了在创建应用程序内投放时定向的用户档案与投放仪表板中显示的用户档案不一致的问题。 (CAMP-28722)
* 修复了营销活动和资产核心服务集成可能阻止您在电子邮件中选择共享资产的问题。

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
   <td> Email Designer一般可用性<br /> </td> 
   <td> <p>新的直观Email Designer（以前称为Creative Designer）已移至GA。 现在，它支持旧版内容编辑器中的所有功能，包括：</p> 
    <ul> 
     <li> 的使用 <a href="../../integrating/using/adding-target-dynamic-content.md">来自Adobe Target的动态图像</a> </li> 
     <li> 能够 <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">在准备时自动从URL检索内容</a> </li> 
     <li> 完全兼容 <a href="../../designing/using/using-reusable-content.md#content-templates">现成内容模板</a>. </li> 
    </ul> 
    <p>有关更多信息，请参阅<a href="../../designing/using/designing-content-in-adobe-campaign.md">详细文档</a>和<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html">操作方法视频</a>。下面列出了改进和修复。</p><p>因此，现已弃用旧版电子邮件内容编辑器。 有关更多信息，请参阅 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html">页面</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> 事务型电子邮件中的产品清单<br /> </td> 
   <td> <p>现在，您可以在事务型电子邮件中引用一个或多个产品收藏集。 例如，您可以自动发送一封购物车放弃电子邮件，其中列出用户购物车中的所有产品，以及指向每个产品的图像、价格和链接。</p><p>有关更多信息，请参阅<a href="../../designing/using/using-product-listings.md">详细文档</a>和<a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html">操作方法视频</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> Email Designer中的移动设备视图<br /> </td> 
   <td> <p>现在，您可以在编辑电子邮件内容时切换到专用的移动设备视图。 这允许您通过单独编辑移动设备显示的所有样式选项来微调电子邮件的响应式设计，例如调整边距、缩小字体大小、使用不同的背景颜色等。</p><p> 有关更多信息，请参阅<a href="../../designing/using/plain-text-html-modes.md#switching-to-mobile-view">详细文档</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内消息传递测试版改进<br /> </td> 
   <td> <p>应用程序内消息传递测试版功能已通过以下功能得到增强：</p> 
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

* 现在，通过加载数据活动中的新选项，您可以将后处理阶段应用到包含拒绝记录的文件(例如， Zip 格式压缩）。(CAMP-24521)
* 现在，更新数据活动中的新选项允许您配置上传数据的批次大小上限。 (CAMP-28400)
* 改进了用户档案的地址状态选择。 现在，在选择国家/地区时，“状态”下拉列表会自动更新为相关的状态值。 (CAMP-28874)
* 现在，如果集客过渡为空，则提取文件活动中的新选项可阻止生成文件。 这样可避免在SFTP服务器上创建和上传空文件。
* 投放摘要报告已得到改进。
* 扩充了定义用户档案地址时可用国家/地区的列表。 (CAMP-26707)
* 现在，在尝试导入内置工作流时，会显示错误消息。

**电子邮件设计工具**

* 修复了在电子邮件模板或通过Email Designer创建的内容片段上启用地理单位功能的问题，即使在Adobe Campaign中禁用了此功能，这使得模板或片段在再次尝试访问时不可用。 (CAMP-28174)
* 修复了使用Email Designer编辑内容时无法保存动态内容条件的问题。 (CAMP-27905)
* 修复了在编辑消息的纯文本版本并中断Email Designer中的HTML同步后，从电子邮件内容中删除HTML版本的问题。 (CAMP-28507)
* 修复了使用Internet Explorer 11时Email Designer界面无法打开的问题。 (CAMP-28273)
* 修复了使用Email Designer扭曲了应用于按钮的样式设置的Microsoft Outlook呈现的问题。
* 修复了Email Designer中的一个问题，该问题导致可以从电子邮件中使用的内容片段中编辑URL，该问题不是预期的，因为该片段默认处于锁定状态。
* 修复了导致Email Designer分隔器组件无法在Microsoft Office中显示的问题。
* 修复了在使用旧版电子邮件内容编辑器查看从AEM同步的内容时，某些Internet浏览器上导致页面冻结的问题。 (CAMP-29068)
* 修复了使用旧版电子邮件内容编辑器单击电子邮件中的任何图像时发生的错误。 (CAMP-30424)
* 修复了使用Email Designer编辑电子邮件时，新创建的片段无法显示的问题。 (CAMP-29928)
* 修复了按钮文本无法在与Email Designer一起创建并使用Outlook Webmail客户端接收的电子邮件中正确显示的问题。
* 现在，可以使用Email Designer创建用户档案事务型消息。 (CAMP-28900)
* 修复了Email Designer中的一个错误，该错误在准备时从URL自动检索内容时使内容可编辑，而该错误应被锁定。

**修补程序**

* 修复了动态报告中显示错误投放日志的问题。 (CAMP-23446)
* 修复了可能影响退回摘要报表数字的问题(CAMP-28703)
* 修复了营销活动和资产核心服务集成可能会阻止在选择 **[!UICONTROL Image shared from Adobe Experience Cloud]** (CAMP-28732)。
* 修复了即使在SMPP外部帐户中授权了音译，仍无法发送包含“oe”字符的短信消息的问题。 (CAMP-29041)
* 修复了在工作流中使用分段活动时可能显示重复记录的问题。 (CAMP-28743)
* 修复了阻止删除工作流活动中某列上的某个值映射的问题。 (CAMP-28708)
* 修复了在“测试以查看文件是否存在”选项中使用通配符时，文件传输活动中的问题。 (CAMP-28977)
* 修复了在更新外部帐户设置时可能发生的文件传输活动问题。 (CAMP-28894)
* 修复了使用“电子邮件不为空”条件时查询编辑器中自定义过滤器的问题。 (CAMP-28741)
* 修复了导出具有10万条以上记录的自定义资源表时可能发生的问题。 (CAMP-28150)
* 修复了无法删除链接到触发器的事务型消息的问题。 (CAMP-28385)
* 删除了某些短信日志中不安全显示的密码。
* 修复了由于Adobe Campaign发送的空密码，导致与SMPP模拟器的连接失败的问题。
* 修复了短信连接不稳定时无法发送营销活动的问题。
* 修复了在动态报告中显示已删除投放的问题。
* 修复了在工作流中使用扩充活动时，可能会阻止从投放日志、跟踪日志和排除日志表检索其他数据的问题。
* 修复了GDPR删除请求的问题，该问题在使用“N基数收集链接”链接类型和“删除目标记录意味着通过链接删除记录引用”选项时可能发生。
* 修复了报表共享的问题。
* 修复了在发送推送通知时可能导致吞吐量问题的问题。
* 修复了直邮输出文件缺少字段的问题。
* 修复了允许用户修改内置工作流的问题。
* 修复了基于包含已配置提取活动的工作流的促销活动模板创建促销活动时的问题。 (CAMP-29198)
* 修复了文件提取活动中阻止对多个元素使用相同表达式的问题。 (CAMP-29182)
* 修复了查询编辑器中rtEvent的broadlog和跟踪日志之间存在连接条件的问题。 (CAMP-28780)
* 修复了无法保存对“特定操作”登陆页面选项的修改的问题。 (CAMP-29422)
* 修复了阻止在工作流中导出事件有效负载的问题。 (CAMP-29029)
* 修复了阻止在短信消息中排阻止列表除上的短信号码的问题。 (CAMP-28898)
* 修复了在处理传入消息时出错时可能阻止SMPP提供程序收到通知的问题。 (CAMP-29804)
* 修复了允许删除具有关联投放的外部帐户的问题。 (CAMP-29738)
* 已改进并稳定了短信消息的发送吞吐量。
* 修复了短信消息中无法使用“~”字符的问题。 (CAMP-29172)
* 修复了使用发送时间优化选项进行投放时的问题。 (CAMP-29231)
