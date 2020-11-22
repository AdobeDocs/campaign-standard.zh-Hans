---
solution: Campaign Standard
product: campaign
title: 发行说明 2019
description: 本页列出了所有 2019 版的 Adobe Campaign Standard。
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '7624'
ht-degree: 8%

---


# 发行说明 2019{#release-notes-2019}

[发布计划](https://helpx.adobe.com/cn/campaign/kb/acs-release-planning.html) | [控制面板版](https://docs.adobe.com/content/help/zh-Hans/control-panel/using/release-notes.html) |文 [档更新](../../rn/using/documentation-updates.md) |最 [新发行说明](../../rn/using/release-notes.md) |已弃 [用功能](https://helpx.adobe.com/cn/campaign/kb/acs-deprecated-and-removed-features.html)

## 版本19.4 - 2019年12月 {#release-19-4---october-2019}

**新增功能**

<table> 
 <thead> 
  <tr> 
   <th> <strong>加利福尼亚消费者隐私法(CCPA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>CCPA是加利福尼亚州新的隐私法，它协调2020年1月1日起生效的数据保护要求并使其现代化。 CCPA适用于持有居住在加利福尼亚的数据主体数据的Adobe Campaign客户。</p>
   <p>除了Adobe Campaign中已有的隐私功能（包括同意管理、数据保留设置和用户角色）之外，我们还将利用此机会加入其他功能，以帮助您为CCPA做好准备：</p>
   <ul>
    <li>访问权和删除权：我们正在利用为GDPR增加的功能。 <a href="https://helpx.adobe.com/content/help/zh-Hans/campaign/kb/acs-privacy.html#righttoaccess">了解详情</a> </li>
    <li><p>创建隐私请求时，隐私核心服务中已添加规章类型（GDPR或CCPA）。 您应将此方法应用于所有访问和删除请求。将 Campaign API 和接口用于访问和删除请求的方法已被弃用。请参阅<a href="https://helpx.adobe.com/cn/campaign/kb/acs-deprecated-and-removed-features.html">已弃用和已删除的功能</a>一文。</p></li>
    <li>已 <strong>在用户档案资源中添加</strong> “CCPA选择退出”字段，以允许Adobe Campaign用户跟踪消费者是否选择退出个人信息的销售。 <a href="https://helpx.adobe.com/content/help/zh-Hans/campaign/kb/acs-privacy.html#ccpa">了解详情</a>。</li>
  </ul>
    <p>请参阅<a href="https://docs.adobe.com/content/help/zh-Hans/campaign-standard-learn/tutorials/privacy/privacy-overview.translate.html">操作方法视频</a>。</p>
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
    <p>Adobe Campaign Standard与Microsoft Dynamics 365之间的集成现已可用。 您将能够将联系人和自定义实体记录从Dynamics 365传输到活动，并将电子邮件事件数据从活动传回到Dynamics 365，以便更好地协调销售／营销。</p>
    <p>请参阅详 <a href="../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md">细文档</a> ，设置此集成并视图 <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/integrating-with-adobe-cloud/campaign-and-microsoft-dynamics-365/working-with-campaign-standard-and-microsoft-dynamics-365.html">操作方法视频</a>。</p>
  </td>
  </tr> 
 </tbody> 
</table>

**改进**

* 动态报告的同意弹出窗口已更新，其中包括Adobe Campaign Standard和Microsoft Dynamics 365集成。 接受条款后，在使用Adobe Campaign Standard/Microsoft Dynamics 365集成和动态用户档案时，将包含报告数据。 [阅读更多](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) (CAMP-29766)
* 修复了在接收投放通知时显示错误联系日期的问题。
* 当事务性消息事件提交时，活动现在返回“400”错误消息而不是“500”。 (CAMP-28632)
* 在动态 **验证中** ，新增了一个“排除”报告段。 现在，默认情况下已选择此区段来筛选您的报表。 [阅读更多](../../reporting/using/list-of-components-.md#segments)
* 消息 **过期** 选项已添加到推送通知中。 它允许您指定消息不再由Apple(APNS)或Android(FCM)发送的过期日期。 [阅读更多](../../channels/using/customizing-a-push-notification.md#add-expiration-date)
* 已对加载文件 **活动进行了** :工作流日志已变得更清晰，并且更详细地说明了在文件无法加载时发生的错误。 激活“在文件中保 **留拒绝”选项时生成的** “出站过渡”已 **更名为Rejects**。 [阅读更多](../../automating/using/load-file.md)
* 已将多语言相关日志添加到发送日志中，以便更好地了解由于上传的CSV文件中缺少语言而导致的发送失败。

**安全性增强**

* 修复了通过隐私请求删除量化用户档案信息时的一个问题，该问题删除了隔离列表中除电子邮件地址以外的所有数据。
* 增强了安全性，防止在电子邮件标头中注入。
* 已增强安全性，以防止SSRF攻击，这些攻击中可以使用xtk表达式（电子邮件HTML、文本内容和主题、SMS和推送通知内容）。

**Email Designer 增强功能**

* 修复了在电子邮件中插入退订、订阅和登陆页链接时无法跟踪的问题。 (CAMP-37809)
* 修复了在创建新电子邮件和选择模板时可能导致错误的问题。 (CAMP-38000)
* 使用电子邮件设计器编辑链接时，您现在可以使用“下划线 **”链接选** 项。 此外，还 **添加了** 目标 **属性，并将默认值设置为** None。 [阅读更多](../../designing/using/styles.md#about-styling-links)
* 修复了电子邮件正文文本组件中链接的颜色问题。 (CAMP-37330)
* 修复了删除图像时无法删除关联链接的问题。 (CAMP-37234)
* 修复了在某个条件下无法保存对 **动态内容** “顺序”设置的修改的问题。 (CAMP-36883)
* 修复了搜索登陆页时的问题。 搜索已从最初创建的50个扩展到所有数据库。 (CAMP-36839)
* 修复了在发件人中保存电子邮件发件人的修改 **时的问题：名称** 字段。 (CAMP-36606)
* 传送组件兼容性警告已修改以反映支持的电子邮件客户端。
* 修复了移动设备上的显示问题。 高度属性现在始终设置为“高度：自动”。 (CAMP-35497)
* 修复了从结构组件删除片段时HTML中保留样式和meta标签的问题。 (CAMP-35390)
* 修复了更新可重用内容时片段的问题。 (CAMP-35186)
* 修复了在电子邮件中仅显示移动条件内容时的问题。 (CAMP-35155)
* 修复了随机显示零宽不间断空格的问题。 (CAMP-35116)
* 修复了“另存为片段”对话框中 **按钮的位置** 问题。
* 修复了在图像标题和替换文本中添加HTML标记时的预览问题。
* 修复了在电子邮件设计器中编辑在旧版编辑器的电子邮件中创建的链接时的问题。
* 修复了在内容中留下重复的样式标记的问题。
* 修复了在电子邮件中插入个性化字段时日期格式的问题。
* 修复了从HTML模式切换为纯文本时的保存问题。
* 修复了单击在内联样式属性面板中添加边距值的锁定和解锁选项时的问题。
* 修复了移动预览的大小问题，以便更好地进行渲染。
* 修复了模板和片段中按钮的大小问题。
* 修复了在按钮组件中插入图像时图像大小的问题。

**其他变更**

* 投放KPI页面和动态报告页面上显示数据的默认时间范围已对齐，以防止报告结果出现差异。 (CAMP-35148)
* 应用程序证书过期时，日志中已添加一条错误消息。
* 有效负荷计算预览现在包括自定义字段大小以防止推送通知失败。 (CAMP-35303)
* 现在，可以 **像“文件** ”导出 **活动一样** ，个性化“加载文件 **”活动中的“拒绝”** 文件的名称。
* 所有未链接到任何现成实体的自定义实体现在都可以通过API进行访问。
* 提高了大型资源上的数据库性能。
* 发送SMS消息时出现的一些错误的描述已经更清晰。 (CAMP-36558)
* 现在，在执行直接或通过多个调度程序连接的工 **作流的活动** 活动时，会显示一条错误消息，因为这可能会导致实例的工作流服务器卡住。
* 已做出改进，以帮助解决事务性消息传递问题：“事件”链接在事件配置屏幕中已更名为“最后一个事务性列表”，它现在按降序排序接收的事件。 此外，还创建了新的事务事件状态：“定位失败”。 当事务消息传递模块无法扩充用于消息定位的链接时，事务事件现在将处于此新状态（而不是“routingFailed”状态）。
* 在限制登陆页访问特定地理或组织单位时，界面已得到改进。 其目的是警告登陆页可能受可见性条件的影响：创建登陆页时必须选择地理和组织单位。 选择设备后，现在会显示包含相关信息的横幅。 测试登陆页时显示的错误消息已更清晰。
* 在Campaign StandardAPI中，如果密钥值与PATCH密钥不同，或者您使用自己的业务密钥作为URI而不是Adobe提供的业务密钥，则无法使用来源操作修改自定义密钥。
* &quot;阿尔巴尼亚语——马其顿语&quot;已加入首选语言下拉列表。 (CAMP-35396)

**修补程序**

* 修复了阻止对计划报告进行排序或搜索的问题。
* 修复了触发器规则导致AND和OR规则混合的问题。
* 修复了在启动项中将移动属性显示为“已删除”的问题。 (CAMP-35382)
* 修复了阻止Adobe启动移动属性在Adobe Campaign中同步的问题。 （35411营，35089营，35014营，35487营）
* 修复了在事件丰富用户档案数据时事务推送消息失败的问题。 (CAMP-34385)
* 修复了移动属性无法在多个环境上同步的问题。 (CAMP-37060)
* 修复了在推送通知中使用联系人日期公式选择模板时的问题。 (CAMP-35300)
* 修复了可能导致消息发送服务崩溃的问题。 (CAMP-35287)
* 修复了循环直接邮件的问题，这些问题都是在第一个事件日期定义的。 (CAMP-35139)
* 修复了新扩展的 **用户档案** 自定义资源不适用于查询的问题。 (CAMP-35119)
* 修复了激 **活了共享配置** 的实例的修复数据库结构模式。 (CAMP-35118)
* 修复了在广播上添加聚合数据时导致SQL日志错误的问题。 (CAMP-35034)
* 修复了创建分段过渡时活动 **的问** 题。 (CAMP-35033)
* 修复了查询 **活动中的一个** 问题 **，该问题导致** encryption_aescbcDecrypt函数无法对 **encryption_aescbcEncrypt函数进行解密** 。 (CAMP-34952)
* 修复了一个问题，该问题可 **能会阻止** 跟踪日志在投放中显示。 (CAMP-34855)
* 修复了在使用发送时间优 **化自定义日期公式** 时，由于工作流的其他数据出现错误，推送通知无法发送的问题。 (CAMP-30336)
* 修复了可能阻止发布自定义资源的问题。 (CAMP-37425)
* 修复了管理员用户无法修改导入包的问题。  (CAMP-37176)
* 修复了工作流中的一个问题，该问题导致当投放活动连接到空的读取受众活动时，验证 **无法发送** 。 (CAMP-37164)
* 修复了阻止将自定义资源导入新环境的问题。 (CAMP-36506)
* 修复了热点单击报告中可能导致图像隐藏百分比的问题(CAMP-36407)
* 修复了尝试导出投放描述字段时发生的问题。 (CAMP-35467)
* 修复了在投放完成后可能将开始状态保留为“待处理”的问题。 (CAMP-35355)
* 修复了在启用后再禁用SQL日志后无法显示工作流日志的问题。

## 19.3 版 - 2019 年 7 月{#release-19-3---july-2019}

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
   <td> <p>为了实现更深入的个性化，外部API活动允许您通过REST API调用将外部系统的数据引入工作流中。 REST端点可以是客户管理系统、Adobe I/O Runtime或Adobe Experience CloudREST端点(例如数据平台、目标、分析、活动)。</p><p>此功能当前为公共测试版。</p><p>有关更多信息，请参阅<a href="../../automating/using/external-api.md">详细文档</a>和<a href="https://docs.adobe.com/content/help/zh-Hans/campaign-standard-learn/tutorials/managing-processes-and-data/data-management-activities/external-api-activity.translate.html">操作方法视频</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 报告工作流区段<br /> </td> 
   <td> <p>此功能允许营销人员按投放细分其段代码效果。 当您创建工作流并使用分段活动将区段分配给投放群时，这些区段现在可以进入同一投放。 这允许您根据单个投放中的多个区段显示打开／单击统计信息。</p><p>有关更多信息，请参阅<a href="../../reporting/using/creating-a-report-workflow-segment.md">详细文档</a>和<a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">操作方法视频</a>。</p></td>
  </tr> 
 </tbody> 
</table>

**安全性增强**

* 修复了一个安全问题，以防止拒绝服务(DoS)攻击获取映像的无效请求。 (CAMP-33454)

**Email Designer 增强功能**

* 修复了每次添加组件时向HTML模板添加其他HTML样式标记的问题，该问题可能会显着增加模板的大小。 (CAMP-34694)
* 修复了可能阻止某些右上工具栏菜单选项可用的问题。 (CAMP-34577)
* 修复了在将镜像页面URL内容块插入电子邮件内容时发生的问题。 (CAMP-34779)
* 修复了在电子邮件中使用JSPP代码时出现的问题，使内容难以编辑。 (CAMP-34574)
* 修复了在向图像添加超链接时导致图像顶部截断的问题。 (CAMP-34382)
* 修复了在Firefox中使用电子邮件设计器时的显示问题。 (CAMP-34364)
* 修复了在电子邮件中定义动态内容时“高级”模式出现的几个问题。 （34351营，34333营，34331营）
* 修复了动态内容规则编辑器(CAMP-34304、CAMP-34303)出现的几个问题。
* 修复了一个问题，该问题可能会阻止“电子邮件设计器设置”窗格中显示“链接”字段(CAMP-33749)。
* 修复了已发送电子邮件中超大的YouTube图标问题。 (CAMP-33726)
* 修复了使镜像页面内容可编辑的安全问题。 (CAMP-33691)
* 修复了在动态内容中使用大于符号时中断HTML输出的问题。 (CAMP-33688)
* 修复了在电子邮件设计器中编辑文本时使用“撤消”选项时出现的问题。 (CAMP-32565)
* 修复了在撤消样式而不是删除样式时创建额外标记的问题。 (CAMP-32359)
* 您现在可以定义电子邮件中使用的每个组件是否仅在桌面设备上显示，或仅在移动设备上显示。
* 您现在可以设置社交内容组件的宽度和高度。
* 修复了删除动态内容后无法删除动态内容旧源代码的问题。
* 修复了在修改电子邮件主题后可能无法更新该电子邮件主题的问题。
* 修复了在将n:n列结构放入工作区后无法选择的问题。
* 修复了邮件缩略图在电子邮件仪表板中显示模糊的问题。
* 修复了一个问题，该问题导致Outlook中收到的电子邮件无法正确显示背景。
* 修复了电子邮件设计器主页上的一些排序问题。
* 修复了在使用动态内容时复制变体时出现的问题。
* 已从“电子邮件设计器设置”窗格中删除一些不需要的字段。

**其他改进**

* 通过与Adobe Experience Platform位置服务的集成，Adobe Campaign现在可兼容，通过Experience PlatformSDK向移动应用程序的订户发送基于位置的营销消息。 有关详细信息，请参阅[详细文档](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md)。
* 报告功能已得到改进，以获得更好的体验。 要使用此功能，您需要接受动态报告使用协议。 For more on this, refer to the [detailed documentation](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
* 在工作流中，已添加一个新选项来预览下一个十个工作流执行。 For more on this, refer to the [detailed documentation](../../automating/using/scheduler.md).
* 在调度程序活动中，新选项允许您为月度投放选择特定周的特定日期。 For more on this, refer to the [detailed documentation](../../automating/using/scheduler.md).
* 创建没有聚合期的重复投放时，投放仪表板现在允许您在发送投放之前请求确认。 For more on this, refer to the [detailed documentation](../../sending/using/confirming-the-send.md).
* 您现在可以使用已在工作流的外部信号投放中声明的事件变量个性化活动的标签。 For more on this, refer to the [detailed documentation](../../automating/using/calling-a-workflow-with-external-parameters.md).
* GDPR删除查询已得到改进，以获得更好的性能。 (CAMP-33504)
* “ftp”选项已从外部帐户配置界面中删除。 (CAMP-34472)
* 您现在可以为每封电子邮件启用或禁用SMTP测试模式选项。 For more on this, refer to the [detailed documentation](../../administration/using/configuring-email-channel.md#smtp-test-mode). (CAMP-34602)

**其他变更**

* 在投放属性界面中添加了警告。 它指定投放根据其聚合期准备，并解冻以每天多次调用工作流，您应确保他们没有任何期。 (CAMP-34393)
* 自定义资源配置屏幕中已添加警告。 我们建议为自定义资源 ID 最多使用 30 个字符。这也适用于自定义资源字段、键值、索引和链接。
* 现在，当尝试删除事务性消息时，登陆页会将其用作确认消息。
* 当工作流运行超过6小时时，活动日志中现在显示警告。 这不适用于推送通知、投放、信号、开始、结束、分叉、AND-joint、计划和等待活动。
* 当达到同时运行的最大工作流数时，工作流日志中现在会显示警告。
* 已暂停或失败状态超过7天的工作流现在将停止，以减少磁盘空间。 清理任务会显示在工作流日志中。
* 当使用“传输文件”活动时，如果文件大小超过可用磁盘空间，则现在会记录错误。
* 无法再为应用程序内消息中的辅助按钮选择重定向到目标URL操作。

**修补程序**

* 修复了可能导致GDPR访问请求失败的问题。
* 修复了一个问题，该问题可能导致在为唯一用户档案接收多个触发器时丢弃触发器。
* 修复了在登录后可能导致错误的自定义资源发布错误消息的问题。
* 修复了在创建或扩展自定义资源时显示空白页面的问题。
* 修复了阻止将appSubscriptionrcp作为受众的定位维度在移动投放中用于定位的问题。
* 修复了阻止将电子邮件地址硬弹回的错误放入隔离。 (CAMP-24587)
* 修复了在添加类型规则，然后在保存字体之前将其删除时出现的问题。 (CAMP-32789)
* 修复了在禁用动态内容时可能阻止显示登陆页内容的问题。 (CAMP-32924)
* 修复了在主投放属性上使用个性化时出现的重复投放问题。 (CAMP-32983)
* 修复了工作流中的一个问题，该问题导致无法从包含传入SMS消息数据的过渡读取结果。 (CAMP-33134)
* 修复了在组合叉和排除工作流以创建受众时发生的活动问题。 (CAMP-33401)
* 修复了一个问题，该问题可能会阻止显示镜像页面内容，以及为重复投放发送验证消息。 (CAMP-33413)
* 修复了在合并和活动之间使用用户档案时导致错误的问题。 此问题是由于输入过渡中标识键不兼容引起的。 (CAMP-33713)
* 修复了测试活动中的一个问题，该问题导致“recCount”表达式在多次单击时无法使用正确的语法。 (CAMP-33756)
* 修复了在打开付费技术工作流日志时可能导致错误消息的问题。 (CAMP-34313)
* 修复了在登陆页中配置复选框字段时可能出现的问题。 (CAMP-34369)
* 修复了配置列表并向其添加“图标”字段时发生的问题。 (CAMP-34585)
* 修复了在加载文件工作流活动中无法将“|”和“%”符号用作日期或时间分隔符的问题。 (CAMP-34706)
* 修复了在登陆页中将可见性条件与复选框结合使用时出现的问题。 (CAMP-34802)
* 修复了扩充活动中的一个问题，该问题导致将过滤维度设置为跟踪日志，将目标维设置为用户档案时，字段无法显示在“附加数据”选项卡中。
* 修复了导致导出“workflowTemplate”资源时出现错误消息的问题。
* 修复了创建新用户档案时的问题，该问题导致从对话框中选择“国家／地区代码”字段时无法保存该字段。
* 修复了使用“直接邮件”导入模板(updateQuaninesDeliveryLogsDirectMail)时发生的几个问题。
* 修复了与资产（按需）集成相关的问题。
* 修复了在放大时间轴视图时发生的问题。 (CAMP-33628)
* 修复了阻止验证在预定日期和时间即时发送电子邮件的问题。 (CAMP-33723)
* 修复了与用户注销时生成错误日志的事务消息相关的问题。 (CAMP-31698)
* 修复了计划电子邮件消息时可能在特定环境上发生的错误。
* 修复了导致更新投放执行工作流失败的问题。
* 修复了在主题包含多行时导致电子邮件内容中断的安全问题。


## 19.2.7 版 - 2019 年 7 月{#release-19-2-7---july-2019}

**改进**

* GDPR删除查询已得到改进，以获得更好的性能。
* 修复了在19.2升级后可能导致Web崩溃的问题。 (CAMP-34862)
* 修复了可能阻止非管理员用户保存或计划报告的问题。 (CAMP-31133)
* 修复了在加载文件工作流活动中将“|”用作日期分隔符时的问题。 (CAMP-34706)

## 19.2.4 版 - 2019 年 6 月{#release-19-2-4---june-2019}

**电子邮件设计工具**

* 修复了在HTML中使用空样式标记时阻止用户编辑片段的问题。 这是19.2.3中CAMP-33778的后续修复。

## 19.2.3 版 - 2019 年 6 月{#release-19-2-3---june-2019}

**电子邮件设计工具**

在19.2版本中引入了一系列改进和修复功能来优化片段。 新创建的片段将无缝工作。 以前构建的片段已灰显，需要迁移到新格式。 为此，请单击每个片段并验证其迁移到新格式。 我们建议您先测试几个片段，然后再迁移所有片段。

* 修复了在解锁片段后阻止用户编辑片段的问题。 这在更新到19.2时影响了现有片段。 (CAMP-33778)
* 修复了使用动态内容时的问题。 在HTML中添加了额外的空格。

**其他改进**

* 修复了在SMS连接器断开连接后，SMS发送无法恢复的问题。
* 修复了启用TLS时可能关闭SMPP连接的问题。
* 修复了启用TLS时可能关闭SMPP连接的问题。
* 已在活动中添加“Launch_URL_活动”选项，以管理使用Adobe Experience Platform移动SDK创建的移动应用程序的属性。
* 修复了在上传新创建的移动属性的证书并退出移动应用程序属性页面后导致“沙箱环境”选项未选中的错误。
* 修复了一个问题，该问题导致您无法用服务资源中的信息丰富事务性消息内容。 (CAMP-33707)
* 修复了在试阻止列表图取消订阅服务用户档案时发生的登陆页问题。

## 19.2 版 - 2019 年 5 月{#release-19-2---may-2019}

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
   <td> <p>为了提高管理员用户的工作效率，您可以轻松监控容量并管理实例的设置（从SFTP服务器管理开始）。</p><p>有关更多信息，请参阅<a href="https://docs.adobe.com/content/help/zh-Hans/control-panel/using/control-panel-home.html">详细文档</a>和<a href="https://docs.adobe.com/content/help/zh-Hans/campaign-standard-learn/control-panel/control-panel-overview.html">操作方法视频</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 本地通知<br /> </td> 
   <td> <p>本地通知消息允许您在用户的移动应用程序中有新数据可用时通知用户，即使您无法访问Internet或前台运行的移动应用程序。 本地通知由移动应用程序在特定时间触发，具体取决于事件。</p><p>有关详细信息，请参阅<a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">详细文档</a>。</p></td> 
  </tr> 
  <tr> 
   <td> Workflow enhancement - Add a payload to external signal activity<br /> </td> 
   <td> <p>当从另一个工作流或REST API调用成功满足定义的条件并与外部系统集成时，将工作流与有效负荷开始。 此外，还包含一个新 <strong>的测试活动</strong> ，您可以在该中对此功能运行测试。</p><p>有关更多信息，请参阅<a href="../../automating/using/calling-a-workflow-with-external-parameters.md">详细文档</a>和<a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/execution-activities/external-signal-activity.html">操作方法视频</a>。</p></td> 
  </tr> 
  <tr> 
   <td> 登陆页增强- Google reCAPTCHA<br /> </td> 
   <td> <p>利用Google reCAPTCHA防止登陆页上的垃圾邮件，无需客户采取任何操作。</p><p>有关详细信息，请参阅<a href="../../channels/using/configuring-landing-page.md#setting-google-recaptcha">详细文档</a>。</p></td> 
  </tr> 
 </tbody> 
</table>

**安全性增强**

* 修复了报告工作区中潜在的点击劫持安全问题。

**Email Designer 增强功能**

* 修复了复制片段并尝试在电子邮件设计器中使用它们时发生的问题。 (CAMP-33193)
* 修复了在电子邮件设计器界面中使用内联元素时，创建不需要的空格的问题。 (CAMP-32163)
* 修复了在电子邮件设计器中保存电子邮件内容后删除用户添加的一些其他HTML标记属性的问题。 (CAMP-32162)
* 修复了在删除Microsoft Office标签后仍在电子邮件设计器HTML模式下显示该标签的问题。 (CAMP-32141)
* 如果您使用电子邮件设计器的先前版本创建了电子邮件，则打开此电子邮件内容时，现在会出现一个弹出窗口，提示用户更新至最新版本。 (CAMP-31529)
* 修复了在发送给某些消息客户端时，会扭曲使用电子邮件设计器创建的电子邮件中的图像的问题。 (CAMP-31407)
* 修复了在HTML模式下创建列表或按钮等元素时无法在纯文本模式下正确显示的问题。 （CAMP-32582 和 CAMP-32542）
* 修复了无法在内容模板或片段属性中显示50个以上组织单位的问题。 (CAMP-32932)
* 修复了在Outlook上接收使用电子邮件设计器创建的电子邮件时，视区背景颜色的问题。 (CAMP-31402)
* 修复了在Outlook中打开使用电子邮件设计器创建的电子邮件内容时无法响应的问题。 (CAMP-31400)
* 修复了在电子邮件主题中使用动态内容时无法正常工作的问题。 (CAMP-32837)
* 修复了与未正确转义的电子邮件主题相关的问题。
* 修复了阻止片段加载到电子邮件设计器左侧调色板中的问题。
* 修复了在电子邮件内容编辑期间创建的片段在刷新片段列表时无法在电子邮件设计器左侧调色板中显示的问题。
* 修复了在电子邮件中使用动态内容时发生的几个问题。
* 修复了尝试使用RGB值定义颜色时拾色器出现的问题。
* 修复了在移动设备上接收电子邮件时镜像页面无法响应的问题。

**Transactional Messaging增强功能**

为了优化操作和性能，已在事务消息渠道中添加了多项改进。

* 事务性消息持续时间已延长，以确保所有消息在过期之前发送，尤其是在执行重试时。
* 通过在不同的发送线程上分配负载，提高了事务消息传递性能。
* 事务消息传递过程已经优化，能够以同一消息的多个开始并行进行。
* 修复了可能导致事务推送通知的吞吐量和延迟不一致的问题。
* 修复了对于目标执行受众显示错误的事务性消息投放的问题。
* 修复了导入包时使用事件配置和关联事务性消息的问题。 For more on this, refer to the [detailed documentation](../../channels/using/getting-started-with-transactional-msg.md#exporting-and-importing-transactional-messages).
* 修复了从为包含产品列表的用户档案创建的测试事务性消息中删除收集数据的问题。

**其他变更**

* 新选项已添加到SMS外部帐户。 它能够限制发送SMS的MTA进程的最大数量，以便更好地控制并行连接的数量。 有关详细信息，请参 [阅SMS连接器协议和设置技术](https://helpx.adobe.com/cn/campaign/kb/sms-connector-protocol-and-settings.html) 说明。
* 在发布具有API扩展的资源时，如果API已经发布，则现在每次重新发布该资源时，它都会自动更新。 以前，此操作是手动操作，无法更新API可能会中断此API的用户档案或服务资源。 For more on this, refer to the [detailed documentation](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* 邮政编码维度已从动态报告中删除。 我们建议改用“城市”、“国家”、“州”维度。
* 已删除应用程序内消息的“首次启动”生命周期事件触发器。
* 导出包含安全组时，它现在包含分配给每个组的角色。 (CAMP-32960)
* 在“加载文件”活动中，新选项允许您检查正在上传的文件的列是否与列定义匹配。 有关详细信息，请参阅[详细文档](../../automating/using/load-file.md)。(CAMP-32229)
* 工作流现在可以从有效负荷开始，这样您就可以在工作流中的活动之间使用和共享外部参数。 有关详细信息，请参阅[详细文档](../../automating/using/calling-a-workflow-with-external-parameters.md)。（CAMP-29412和CAMP-29413）
* Campaign StandardAPI现在允许您使用有效负荷更新用户档案的地理和组织单位。 有关详细信息，请参阅[详细文档](../../api/using/get-started-apis.md)。
* 当数据库中的对象无法访问时，错误消息已变得清晰明了。
* 在“提取文件”活动中，在定义要导出的文件名称时更新了Javascript功能。 现在，“输出”字段中只能使用formatDate函数。 有关详细信息，请参阅[详细文档](../../automating/using/extract-file.md)。
* 自定义资源的自动序列ID生成已得到改进。 默认情况下，新自定义资源的主键为64位。
* 自定义资源发布测试模式已得到改进。 如果上次自定义资源发布失败且未修复，则现在将向用户显示一条警告消息。 在自定义资源发布失败后，您可以回滚到上一个工作版本。 有关详细信息，请参阅[详细文档](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。
* 在“传输文件”活动中添加了新选项。 它允许您在SFTP模式下使用文件下载操作对文件进行排序。 有关详细信息，请参阅[详细文档](../../automating/using/transfer-file.md)。(CAMP-33109)

**修补程序**

* 修复了在重新加载SMS设置时可能导致MTA内存泄漏的问题。
* 修复了可能阻止在修复模式下发布数据库更新的问题。
* 修复了导致Adobe Analytics报表与Adobe Campaign动态报告不一致的问题。 (CAMP-25393)
* 修复了导致报告共享工作流失败的错误。
* 修复了阻止用户仅使用媒体URL发送应用程序内消息的错误。
* 修复了即使移动应用程序的证书未上载到实例也会显示该应用程序的问题。
* 修复了在使用移动应用程序模板的个性化字段所 **有用户时目标无法工作** 的错误。
* 已设置新的Campaign Standard实例。 （CAMP-32635和CAMP-32344）
* 修复了阻止在工作流中自定义日期公式的错误。 (CAMP-30336)
* 修复了定义自定义日期公式时的问题，该公式可能会阻止“附加数据”和“段代码”字段在下拉列表中可用。 (CAMP-32383)
* 修复了一个问题，该问题可能会阻止“传输文件”和“提取文件”活动在加密后发现文件被拒绝。 (CAMP-32377)
* 修复了API中的一个问题，该问题可能会阻止lineCount过滤器呈现确切的总计数。 (CAMP-31424)
* 修复了登陆页中的一个问题，该问题可能会阻止输入字段在修改后显示更新的值。 (CAMP-31401)
* 修复了可能导致信号活动意外激活的问题。
* 修复了一个问题，该问题会阻止电子邮件预览在受众为空时显示。
* 修复了“提取文件”活动中的一个问题，该问题在激活“如果入站过渡为空，则不生成文件”选项时可能生成文件。
* 修复了导致交付性工作流在未完成时关闭的问题。
* 修复了可能阻止用户保存或计划报告的问题。 (CAMP-31133)

## 19.1.3 版 - 2019 年 3 月{#release-19-1-3---march-2019}

**Email Designer 增强功能**

* 修复了在保存模板后无法修改模板的问题。
* 修复了在电子邮件中使用先前创建的模板时的各种问题。
* 修复了阻止组件在导入的模板中隐藏的问题。

**其他改进**

* 修复了查看类型规则时出错的问题。 （CAMP-32059和CAMP-31849）
* 修复了阻止编辑类型规则的问题。 (CAMP-31750)
* 修复了inMail进程可能意外停止的问题。 (CAMP-31238)

## 19.1 版 - 2019 年 2 月{#release-19-1---february-2019}

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
   <td> <p>推送渠道报告中添加了多项增强功能，使您能够更直观地衡量用户参与度。 在此版本中，我们将推送渠道指标的列表扩展为三种不同的指标：展示次数、点击次数、打开次数（应用程序打开次数）可帮助您更有效地衡量和分析用户与推送通知的交互情况。 与此同时，我们也在规范这些指标的定义和实施。 推送通知内置报表还通过常用可视化和指标进行了改进。</p><p> 有关详细信息，请参阅<a href="../../reporting/using/push-notification-report.md">详细文档</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 针对移动应用程序的Launch集成<br /> </td> 
   <td> <p>此版本包含将Adobe Campaign与Adobe Experience Platform LaunchAdobe Campaign Standard的GA版Android和iOS扩展以及移动SDK集成。 这些扩展支持推送消息、应用程序内消息和移动应用用户档案更新。</p><p> 有关详细信息，请参阅<a href="https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdk.html">详细文档</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 移动应用内消息传递<br /> </td> 
   <td> <p>此版本包含GA版本的活动应用程序内渠道。 从功能角度看，测试版中最引人注目的新增功能是Mobile SDK与MCIAS(Marketing Cloud应用程序内消息传递服务，为SDK提供应用程序内规则)的应用程序内渠道和安全握手的动态报告。 安全握手可确保用户的PII数据不会落入恶意之手，并使您能够在用户每次注销时清除消息缓存，从而在共享设备上保持用户的隐私。</p><p>For more information, refer to the <a href="../../channels/using/about-in-app-messaging.md">detailed documentation</a> and the dedicated <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/in-app/in-app-message-overview.html">In-App tutorial</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> 工作流增强<br /> </td> 
   <td> <p>已添加以下工作流功能：</p> 
    <ul> 
     <li> 您现在可以从同一活动实例复制粘贴工作流或其他工作流中的活动。 这样，您可以轻松重复整个工作流或特定活动，并保留最初定义的设置。 有关详细信息，请参阅<a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">详细文档</a>。(CAMP-20014) </li> 
     <li> 使用“加 <strong>载文件</strong> ”活动时，您现在可以向包含拒绝记录的文件名称添加时间戳。 有关详细信息，请参阅<a href="../../automating/using/load-file.md#configuration">详细文档</a>。 </li> 
     <li> <strong>查询</strong> 和 <strong>分段活动现在允</strong> 许您启用出站过渡(如果活动未检索任何数据)。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**安全性增强**

* 生成的登陆页HTML代码已更新，以防止搜索引擎索引。

**Email Designer 增强功能**

* Behance艺术家设计的一套四款一流的响应式电子邮件模板现已推出。

   有关详细信息，请参阅[详细文档](../../designing/using/using-reusable-content.md#content-templates)。

* 我们新增的入门培训体验将帮助您更快地开始电子邮件创建，并让您更轻松地访问文档和教程。

   有关详细信息，请参阅[详细文档](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page)。

* 您现在可以根据需要灵活配置列数和宽度。

   有关详细信息，请参阅[详细文档](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

* 在移动视图中进行编辑时，您可以仅在移动显示屏中隐藏某些组件，以有效利用空间。

   有关详细信息，请参阅[详细文档](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)。

* 您现在可以在已有电子邮件模板的顶部添加自定义社交渠道。
* 修复了在使用18个以上结构时无法向下滚动结构菜单的问题。 (CAMP-31173)
* 修复了转发包含随Adobe Campaign发送的预头的电子邮件时在内容顶部显示预头的问题。 (CAMP-30736)
* 修复了在Adobe Experience Manager修改主题后单击“刷新AEM内容”选 **项时主题行无** 法更新的问题。 (CAMP-29984)
* 修复了阻止使用Adobe Target动态图像的几个问题。
* 修复了在准备时检索内容时，如果预览之前是从URL导入的，则该问题会阻止更新该内容。
* YouTube图标已添加到社交 **内容** 组件。
* 已 **为“电子邮件** ”设计器”调色板中显示的内容组件和片段添加列表视图。

**其他改进**

* Adobe Campaign现在完全符合FCM对SDK V4和AEP SDK应用程序的要求。
* Adobe Campaign支持Android的Wear OS和Apple的watchOS上的推送通知。
* 在界面中导航时可能显示的警告和错误消息变得清晰易懂。
* 您现在可以添加到与加入和退出相关的用户档案列表列（“不再联系……”字段）。
* 用户档案创建屏幕中的时区下拉列表已从地址部分移动到接口的上部部分。
* 您现在可以在配置自定义资源屏幕时添加分隔符，从而将字段组织为类别。

   有关详细信息，请参阅[详细文档](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration)。

**其他变更**

* Adobe Campaign和Adobe Experience Cloud将从2019年春季开始停止对Microsoft Internet Explorer 11和Campaign Standard19.2版本的支持。 请切换到Microsoft Edge或其他受支持的浏览器。 See [Deprecated and removed features](https://helpx.adobe.com/cn/campaign/kb/acs-deprecated-and-removed-features.html) page.
* 用户档案 **资源中的** “国家／地区代码”字段已更 **名为“国家／地区代码”**。

**修补程序**

* 修复了在向电子邮件用户档案添加测试事务性消息时无法发送邮件的问题。 (CAMP-29854)
* 修复了在同时触发所有渠道的消息发送时，如果一个渠道的消息发送率较低，则会减慢其他渠道发送消息的速度的问题。
* 修复了在开始连接尚未建立时导致MTA外部帐户发送SMS消息的问题。
* 修复了调度程序活动执行频率和开始时间出现的问题。 (CAMP-30745)
* 修复了在使用扩展用户档案资源时，PKEY生成可能发生的问题。 (CAMP-30285)
* 修复了基于日历日的疲劳规则可能出现的问题。 (CAMP-30136)
* 修复了在尝试访问名称以“Base”结尾的自定义资源时可能发生的问题。 (CAMP-30109)
* 修复了无法使用PATCH调用将用户档案订阅到服务的问题。 (CAMP-29728)
* 修复了通过“加载文件”活动导入XML文件时可能损坏工作流的问题。 （29208号营地和28205号营地）
* 修复了链接自定义资源时可能阻止生成反向基数链接的问题。 (CAMP-30476)
* 修复了仅使用投放日志时无法扩展段代码的问题。
* 修复了在工作流中使用文件传输活动时可能重复行的问题。
* 修复了在所选时间无法发送计划报告的问题。
* 修复了在工作流中导致应用程序内投放的“要交付”和“已发送”KPI之间不一致的问题。
* 修复了导致跟踪无法处理使用自定义HTML创作的应用程序内消息的问题。
* 修复了在工作流中使用时无法保存应用程序内投放内容的问题。
* 修复了阻止管理员显示移动应用程序的问题。
* 修复了导致“可交付性更新”技术工作流失败的问题。 (CAMP-26387)
* 修复了在创建应用程序内投放时导致目标用户档案与在投放仪表板中显示的之间出现差异的问题。 (CAMP-28722)
* 修复了活动和资产核心服务集成的一个问题，该问题可能会妨碍您在电子邮件中选择共享资产。

## 19.0 版 - 2019 年 1 月{#release-19-0---january-2019}

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
   <td> 电子邮件设计人员常规可用性<br /> </td> 
   <td> <p>新的直观的电子邮件设计器（以前称为Creative Designer）已转向GA。 它现在支持旧版内容编辑器的所有功能，包括：</p> 
    <ul> 
     <li> Adobe Target动 <a href="../../integrating/using/adding-target-dynamic-content.md">态图像的使用</a> </li> 
     <li> 能够在准 <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">备时自动从URL检索内容</a> </li> 
     <li> 完全 <a href="../../designing/using/using-reusable-content.md#content-templates">兼容的现成内容模板</a>。 </li> 
    </ul> 
    <p>有关更多信息，请参阅<a href="../../designing/using/designing-content-in-adobe-campaign.md">详细文档</a>和<a href="https://docs.adobe.com/content/help/zh-Hans/campaign-standard-learn/tutorials/designing-content/email-designer/email-designer-overview.html">操作方法视频</a>。以下列出了改进和修复。</p><p>因此，现在已弃用传统电子邮件内容编辑器。 For more information, refer to this <a href="https://helpx.adobe.com/cn/campaign/kb/acs-deprecated-and-removed-features.html">page</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Product Listings in Transactional Emails<br /> </td> 
   <td> <p>您现在可以在交易电子邮件中引用一个或多个产品集合。 例如，您可以自动发送购物车放弃电子邮件，其中列出用户购物车中的所有产品，以及图像、价格和指向每个产品的链接。</p><p>有关更多信息，请参阅<a href="../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message">详细文档</a>和<a href="https://docs.adobe.com/content/help/zh-Hans/campaign-standard-learn/tutorials/designing-content/product-listings-in-transactional-email.translate.html">操作方法视频</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> Mobile View in the Email Designer<br /> </td> 
   <td> <p>现在，您可以在编辑电子邮件内容时切换到专用的移动视图。 这允许您通过单独编辑移动显示的所有样式选项（如调整边距、较小的字体大小、不同的背景颜色等）来微调电子邮件的响应式设计。</p><p> 有关详细信息，请参阅<a href="../../designing/using/plain-text-html-modes.md#switching-to-mobile-view">详细文档</a>。</p> </td> 
  </tr> 
  <tr> 
   <td> 应用程序内消息传递测试版改进<br /> </td> 
   <td> <p>应用程序内消息传递测试版功能已通过以下功能得到增强：</p> 
    <ul> 
     <li> 应用程序内测试渠道符合GDPR要求 </li> 
     <li> 与Analytics API集成以填充触发器下拉列表 </li> 
     <li> 直观的外观和投放模板描述 </li> 
     <li> 从可用性角度增强创作界面 </li> 
    </ul> <p>有关详细信息，请参阅<a href="../../channels/using/about-in-app-messaging.md">详细文档</a>。</p> </td> 
  </tr> 
 </tbody> 
</table>

**改进**

* 现在，通过“加载数据”活动中的新选项，您可以将后处理阶段应用到包含拒绝记录的文件(例如， Zip 格式压缩）。(CAMP-24521)
* 现在，在“更新数据”活动中新增了一个选项，可让您为要上传的数据配置最大批处理大小。 (CAMP-28400)
* 改进了用户档案的地址状态选择。 选择国家／地区时，“状态”下拉列表现在会自动更新为相关的状态值。 (CAMP-28874)
* 如果入站活动为空，“提取文件”过渡中的新选项现在禁止生成文件。 这可避免在SFTP服务器上创建和上传空文件。
* 投放摘要报告已得到改进。
* 现有国家在定义用户档案地址时的列表已得到丰富。 (CAMP-26707)
* 现在，在尝试导入内置工作流时显示错误消息。

**电子邮件设计工具**

* 修复了在电子邮件模板或使用电子邮件设计器创建的内容片段上启用地理单元功能的问题，即使在Adobe Campaign中禁用了此功能，这使得在再次尝试访问该模板或片段时该模板或片段不可用。 (CAMP-28174)
* 修复了在使用电子邮件设计器编辑内容时无法保存动态内容条件的问题。 (CAMP-27905)
* 修复了在编辑邮件的纯文本版本并在电子邮件设计器中中断HTML同步后，从电子邮件内容中删除HTML版本的问题。 (CAMP-28507)
* 修复了使用Internet Explorer 11时无法打开电子邮件设计器界面的问题。 (CAMP-28273)
* 修复了使用电子邮件设计器应用于按钮的样式设置的Microsoft Outlook呈现失真的问题。
* 修复了电子邮件设计器中的一个问题，该问题导致可以从电子邮件中使用的内容片段编辑URL，但该URL不是预期的，因为该片段默认处于锁定状态。
* 修复了阻止在Microsoft Office中显示电子邮件设计器分隔器组件的问题。
* 修复了在使用旧版电子邮件内容编辑器查看从AEM同步的内容时导致某些Internet浏览器页面冻结的问题。 (CAMP-29068)
* 修复了在使用旧版电子邮件内容编辑器时单击电子邮件中的任何图像时出现的错误。 (CAMP-30424)
* 修复了在通过电子邮件设计器编辑电子邮件时无法显示新创建的片段的问题。 (CAMP-29928)
* 修复了阻止按钮文本在使用电子邮件设计器创建并使用Outlook电子邮件客户端接收的电子邮件中正确显示的问题。
* 现在，可以使用电子邮件设计器创建用户档案事务性消息。 (CAMP-28900)
* 修复了电子邮件设计器中的一个错误，该错误使内容在准备时从URL自动检索内容时变得可编辑，而应将其锁定。

**修补程序**

* 修复了在动态投放日志中显示错误报告的问题。 (CAMP-23446)
* 修复了影响退回摘要报告中数字的问题(CAMP-28703)
* 修复了活动和资产核心服务集成的一个问题，该问题可能会阻止在电子邮件中 **[!UICONTROL Image shared from Adobe Experience Cloud]** 选择时显示资产(CAMP-28732)。
* 修复了一个问题，该问题导致即使在SMPP外部帐户中授权音译，也无法发送包含“oe”字符的SMS消息。 (CAMP-29041)
* 修复了在重复中使用分段活动时可能显示工作流记录的问题。 (CAMP-28743)
* 修复了在工作流活动中无法删除列上的某个值映射的问题。 (CAMP-28708)
* 修复了在“文件传输”活动中使用通配符时“测试以查看文件是否存在”选项的问题。 (CAMP-28977)
* 修复了文件传输活动中在更新外部帐户设置时可能发生的问题。 (CAMP-28894)
* 修复了在使用“电子邮件不为空”条件时查询编辑器中自定义过滤器的问题。 (CAMP-28741)
* 修复了导出包含100k以上记录的自定义资源表时可能发生的问题。 (CAMP-28150)
* 修复了无法删除链接到触发器的事务性消息的问题。 (CAMP-28385)
* 删除了某些SMS日志中不安全显示的密码。
* 修复了由于Adobe Campaign发送的空密码，导致与SMPP模拟器的连接失败的问题。
* 修复了在SMS连接不稳定时无法发送活动的问题。
* 修复了在动态投放中显示已删除报告的问题。
* 修复了在工作流中使用投放日志活动时，可能无法从跟踪日志、扩充和排除日志表检索其他数据的问题。
* 修复了GDPR删除请求的问题，该问题在使用“N基数收集链接”链接类型和“删除目标记录意味着删除链接引用的记录”选项时可能发生。
* 修复了报告共享问题。
* 修复了在发送推送通知时可能导致吞吐量问题的问题。
* 修复了直接邮件输出文件缺少字段的问题。
* 修复了允许用户修改内置工作流的问题。
* 修复了在基于包含已配置提取活动的工作流的活动模板创建活动时的问题。 (CAMP-29198)
* 修复了文件提取活动的问题，该问题导致无法对多个元素使用相同表达式。 (CAMP-29182)
* 修复了在查询编辑器中rtEvent的broadlog和跟踪日志之间存在连接条件的问题。 (CAMP-28780)
* 修复了无法保存对“特定操作”登陆页选项的修改的问题。 (CAMP-29422)
* 修复了在工作流中无法导出事件的有效负荷的问题。 (CAMP-29029)
* 修复了阻止上的SMS号阻止列表码在SMS消息中被排除的问题。 (CAMP-28898)
* 修复了在处理传入消息时出现错误时，可能会阻止SMPP提供者收到通知的问题。 (CAMP-29804)
* 修复了允许删除具有关联外部帐户的投放的问题。 (CAMP-29738)
* SMS消息的发送吞吐量已得到改进和稳定。
* 修复了阻止在SMS消息中使用“~”字符的问题。 (CAMP-29172)
* 修复了使用发送时间优化选项的投放中的问题。 (CAMP-29231)

