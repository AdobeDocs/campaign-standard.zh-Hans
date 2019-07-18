---
title: 发行说明
seo-title: 发行说明
description: 发行说明
seo-description: 本页列出了Adobe Campaign Standard的所有近期发行版。
page-status-flag: 从未激活
uuid: cf2e40c-beca-43db-8261-a1820 ee86 ad3
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: paign-standard-release
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41 d34 b41
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 830292bd6f5bbd143ad0c674aaac67b67abc5665

---


# Release Notes{#release-notes}

正在寻找特定版本的Adobe Campaign Standard？

每个版本都附带新增功能和修补程序。单击某个版本可查看其内容。Consult the [Release Planning](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) to find out when the next release will happen.

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a previous release, consult these pages: [2018 Release Notes](../../rn/using/release-notes-2018.md), [2017 Release Notes](../../rn/using/release-notes-2017.md), [2015-2016 Release Notes](../../rn/using/release-notes-2015-2016.md). Also consult the list of [Deprecated and Removed Features](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html).

## Release 19.2.7 - July 2019 {#release-19-2-7---july-2019}

### Improvements {#improvements-2}

* GDPR删除查询已得到改进，可提高性能。
* 修复了在19.2升级后Web崩溃的问题。(AMP-34862)
* 修复了一个问题，该问题可能会阻止非管理员用户保存或安排报告。(AMP-31133)
* 修复了使用“||“作为加载文件工作流活动中的日期分隔符。(AMP-34706)

## Release 19.2.4 - June 2019 {#release-19-2-4---june-2019}

### Email Designer {#email-designer-2}

* 修复了在HTML中使用空样式标签时阻止用户编辑片段的问题。这是AMP-33778在19.2.3中的后续修复。

## Release 19.2.3 - June 2019 {#release-19-2-3---june-2019}

### Email Designer {#email-designer-1}

引入了在19.2版本中优化片段的一系列改进和修复。新创建的片段将无缝工作。以前构建的片段已灰显，需要迁移到新格式。为此，请单击每个片段并验证其迁移到新格式。我们建议您先测试几个片段，然后再迁移它们。

* 修复了阻止用户在解锁片段后编辑片段的问题。更新到19.2时，这会影响现有片段。(AMP-33778)
* 修复了使用动态内容时出现的问题。HTML中增加了额外的空格。

### Other improvements {#other-improvements-2}

* 修复了SMS连接器断开连接后无法发送SMS发送的问题。
* 修复了启用TLS时可能关闭SMTP连接的问题。
* 修复了启用TLS时可能关闭SMTP连接的问题。
* Campaign中添加了“Launch_ URL_ Campaign”选项，用于管理使用Adobe Experience Platform Mobile SDK创建的移动应用程序的属性。
* 修复了在上传新创建的移动属性的证书并退出移动应用程序属性页面后导致“沙箱环境”选项被取消选中的错误。
* 修复了一个问题，该问题导致您无法使用来自服务资源的信息丰富交易消息内容。(AMP-33707)
* 修复了在尝试取消订阅服务配置文件时出现的黑名单登陆页面中存在的问题。

## Release 19.2 - May 2019 {#release-19-2---may-2019}

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
   <td> Control Panel<br /> </td> 
   <td> <p>为了帮助您以管理员用户的身份提高工作效率，您可以轻松监控容量和管理实例设置(从SFTP服务器管理开始)。</p><p>For more information, refer to the <a href="https://helpx.adobe.com/campaign/kb/control-panel.html">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-control-panel-video-use.html">how-to video</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Local notifications<br /> </td> 
   <td> <p>本地通知消息允许您在移动应用程序中提供新数据时通知用户，即使没有访问Internet或在前台运行的移动应用程序时也是如此。本地通知由移动应用程序在特定时间触发，具体取决于活动。</p><p>For more information, refer to the <a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">detailed documentation</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Workflow enhancement - Add a payload to external signal activity<br /> </td> 
   <td> <p>在从另一个工作流成功满足定义条件或REST API调用与外部系统集成时，开始使用有效负荷启动工作流。This also includes a new <strong>test</strong> activity where you can run tests on this functionality.</p><p>For more information, refer to the <a href="../../automating/using/calling-a-workflow-with-external-parameters.md">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-external-signal-activity-feature-video-use.html">how-to video</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Landing Pages enhancement - Google reCAPTCHA<br /> </td> 
   <td> <p>利用Google ReCAPTCHA防止登录页面上垃圾邮件，无需客户采取任何行动。</p><p>For more information, refer to the <a href="../../channels/using/designing-a-landing-page.md#setting-google-recaptcha">detailed documentation</a>.</p></td> 
  </tr> 
 </tbody> 
</table>

### Security enhancements {#security-enhancements}

* 修复了报告工作区中潜在的点击劫持安全问题。

### Email Designer enhancements {#email-designer-enhancements}

* 修复了复制片段并尝试在电子邮件设计器中使用它们时出现的问题。(AMP-33193)
* 修复了在电子邮件设计器界面中使用内嵌元素时创建多余空格的问题。(AMP-32163)
* 修复了在电子邮件设计器中保存电子邮件内容后，用户添加了一些其他HTML标记属性的问题。(AMP-32162)
* 修复了在电子邮件设计器HTML模式下即使删除它也会显示Microsoft Office标记的问题。(AMP-32141)
* 如果您使用电子邮件设计器的早期版本创建了电子邮件，在打开此电子邮件内容时，弹出窗口现在会提示用户更新到最新版本。(AMP-31529)
* 修复了一个问题，该问题可能会导致在发送给某些消息传递客户端时使用电子邮件设计器创建的电子邮件中扭曲图像。(AMP-31407)
* 修复了在HTML模式下创建时，阻止某些元素在纯文本模式下正确显示等元素的问题。(AMP-32582，Camp-32542)
* 修复了一个问题，该问题导致在内容模板或片段属性中显示50多个组织单位。(AMP-32932)
* 修复了接收使用Outlook上的电子邮件设计器创建的电子邮件时视图端口背景颜色的问题。(AMP-31402)
* 修复了在Outlook中打开电子邮件设计器时，使用电子邮件设计器创建的电子邮件内容的问题。(AMP-31400)
* 修复了一个问题，该问题导致动态内容在电子邮件主题中使用时无法正常工作。(AMP-32837)
* 修复了与未正确转义的电子邮件主题相关的问题。
* 修复了阻止在电子邮件设计器左调板中加载片段的问题。
* 修复了电子邮件内容版本中创建的片段在刷新片段列表时无法显示在电子邮件设计器左调板中的问题。
* 修复了在电子邮件中使用动态内容时出现的几个问题。
* 修复了在尝试使用RGB值定义颜色时出现的拾色器问题。
* 修复了在手机上接收电子邮件时，镜像页面无法响应的问题。

### Transactional Messaging enhancements {#transactional-messaging-enhancements}

为了优化操作和性能，已向Transactional Messaging通道添加了若干改进。

* 事务消息持续时间已延长，以确保所有消息都在发送之前发送，尤其是执行重试时。
* 通过在不同发送线程上分发负载，提高了交易消息性能。
* 交易消息处理过程已经过优化，能够并行多分析同一消息。
* 修复了一个问题，该问题可能导致交易推送通知的吞吐量和滞后时间不一致。
* 修复了一个问题，该问题导致目标受众的交易消息执行提交不正确。
* 修复了导入包含活动配置和关联的事务消息的包时出现的问题。For more on this, refer to the [detailed documentation](../../channels/using/about-transactional-messaging.md#exporting-and-importing-transactional-messages).
* 修复了在为包含产品列表的交易消息创建的测试配置文件中删除集合数据的问题。

### Other changes {#other-changes}

* 新选项已添加到SMS外部帐户。它允许限制发送SMS的MTA进程的最大数量，以更好地控制并行连接的数量。For more information, refer to the [SMS connector protocol and settings](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html) technote.
* 在发布带有API扩展的资源时，如果API已经发布，它现在每次再次发布时都会自动更新。以前，此操作是手动操作且未能更新API，因此API可能会破坏此API的配置文件或服务资源。For more on this, refer to the [detailed documentation](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* 已从动态报告中删除Zip代码维度。我们建议改用城市、国家/地区、州尺寸。
* 应用程序内消息的“首次启动”生命周期事件触发器已被删除。
* 在导出与安全组的包时，它现在包含分配给每个用户组的角色。(AMP-32960)
* 在加载文件活动中，新选项允许您检查上传的文件列是否匹配列定义。For more information, refer to the [detailed documentation](../../automating/using/load-file.md). (AMP-3229)
* 现在可以使用有效负荷开始工作流，以便您在工作流中的活动之间使用和共享外部参数。For more information, refer to the [detailed documentation](../../automating/using/calling-a-workflow-with-external-parameters.md). (AMP-29412&amp; AMP-29413)
* Campaign Standard API现在允许您使用有效负荷更新配置文件的地理和组织单位。For more information, refer to the [detailed documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).
* 无法访问数据库中某个对象的错误消息已得到更清晰的理解。
* 在Extract文件活动中，在定义要导出的文件名称时，Javascript功能已更新。现在只能在输出字段中使用formatDate函数。For more information, refer to the [detailed documentation](../../automating/using/extract-file.md).
* 自定义资源的自动序列ID生成已得到改进。默认情况下，新自定义资源的主键处于64位。
* 自定义资源发布测试模式已得到改进。如果上次自定义资源发布失败且未修复，则现在向用户显示警告消息。自定义资源发布失败后，您可以回滚到上一个工作版本。For more information, refer to the [detailed documentation](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
* 转移文件活动中新增了一个选项。它允许您在SFTP模式下使用文件下载操作对文件进行排序。For more information, refer to the [detailed documentation](../../automating/using/transfer-file.md). (AMP-33109)

### Patches {#patches}

* 修复了重新加载SMS设置时可能会导致MTA内存泄漏的问题。
* 修复了一个问题，该问题可能会阻止在修复模式下发布数据库更新。
* 修复了导致Adobe Analytics报告与Adobe Campaign动态报告之间存在差异的问题。(AMP-25393)
* 修复了导致报告共享工作流失败的错误。
* 修复了阻止用户仅通过媒体URL发送应用程序内消息的错误。
* 修复了显示移动应用程序的问题，即使其证书未上传到实例。
* Fixed an error that prevented personalization fields from working when using the **Target all users of a Mobile app** template.
* 提供了新的Campaign Standard实例。(AMP-32635&amp; AMP-32344)
* 修复了一个错误，该错误导致在工作流中自定义日期公式。(AMP-30336)
* 修复了定义可阻止“附加数据”和“区段代码”字段在下拉列表中可用的自定义日期公式的问题。(AMP-32383)
* 修复了一个问题，该问题导致在加密文件时，“转移文件”和“提取文件”活动无法找到这些文件。(AMP-32377)
* 修复了API中可能阻止LineCount滤镜呈现完全总数的问题。(AMP-31424)
* 修复了登陆页面中存在的一个问题，该问题可能会阻止输入字段在修改后显示更新后的值。(AMP-31401)
* 修复了可能导致信号活动意外激活的问题。
* 修复了一个问题，该问题可能导致电子邮件预览无法在受众为空时显示。
* 修复了“提取文件”活动中可能生成文件的问题，而“如果入站过渡为空”选项则“不生成文件”。
* 修复了可交付工作流在未成功完成的情况下关闭的问题。
* 修复了可能阻止用户保存或安排报表的问题。(AMP-31133)

## Release 19.1.3 - March 2019 {#release-19-1-3---march-2019}

### Email Designer enhancements {#email-designer-enhancements-1}

* 修复了保存模板后无法修改模板的问题。
* 修复了在电子邮件中使用先前创建的模板时出现的各种问题。
* 修复了阻止在导入的模板中隐藏组件的问题。

### Other improvements {#other-improvements}

* 修复了查看字型规则时出现的错误。(AMP-32059&amp; AMP-31849)
* 修复了阻止编辑规则规则的问题。(AMP-31750)
* 修复了InMail进程可能会意外停止的问题。(AMP-31238)

## Release 19.1 - February 2019 {#release-19-1---february-2019}

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
   <td> Push channel Reporting improvements<br /> </td> 
   <td> <p>推送渠道报告增加了若干增强功能，使您能够更直观地衡量用户参与度。在此版本中，我们将推送渠道指标列表扩展到三个不同的指标：印象、点击、打开(App Open)可帮助您更有效地测量和分析用户与推送通知的交互。此外，我们还要标准化这些指标的定义和实施。推送通知内置报告已通过常用可视化和指标改进。</p><p> For more information, refer to the <a href="../../reporting/using/push-notification-report.md">detailed documentation</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Launch integration for Mobile App<br /> </td> 
   <td> <p>此版本包含将Adobe Campaign与Android和iOS版的Android及iOS Adobe Campaign Standard for Adobe Campaign Platform Launch和Mobile SDK的GA版本集成。这些扩展支持推送消息、应用程序内消息传递和移动应用程序配置文件更新。</p><p> For more information, refer to the <a href="../../administration/using/about-typology-rules.md#typology-rules">detailed documentation</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Mobile In-App Messaging<br /> </td> 
   <td> <p>此版本包含Campaign中的GA应用程序内渠道的GA版本。从功能性的观点来看，Beta版最明显的新增功能是针对Mobile SDK和MCIAS(Marketing Cloud应用程序内消息服务，将应用程序内规则提供给SDK的Marketing Cloud内消息服务)的动态报告。安全握手可确保用户的PII数据不会落入恶意手中，并且可使您在每次用户注销时清除消息缓存，从而在共享设备上保持用户的隐私。</p><p>For more information, refer to the <a href="../../channels/using/about-in-app-messaging.md">detailed documentation</a> and the dedicated <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-in-app-message-tutorial.html">In-App tutorial</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Workflow enhancements<br /> </td> 
   <td> <p>添加了以下工作流功能：</p> 
    <ul> 
     <li> 您现在可以在工作流中复制粘贴活动，也可以从同一营销活动实例中复制其他工作流。这样，您就可以轻松复制整个工作流或特定活动，并保留最初定义的设置。For more information, refer to the <a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">detailed documentation</a>. (AMP-20014) </li> 
     <li> When using the <strong>Load file</strong> activity, you can now add a timestamp to the name of the file containing the rejected records. For more information, refer to the <a href="../../automating/using/load-file.md#configuration">detailed documentation</a>. </li> 
     <li> <strong>现在，查询</strong> 和 <strong>分段</strong> 活动允许您在活动检索无数据的情况下启用出站过渡。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Security enhancements {#security-enhancements-1}

* 生成的登陆页面HTML代码已更新，以防止搜索引擎索引。

### Email Designer enhancements {#email-designer-enhancements-2}

* 由Behance艺术家设计的四个一流的响应式电子邮件模板现已推出。

   For more information, refer to the [detailed documentation](../../start/using/about-templates.md#content-templates).

* 我们新的入门培训体验将帮助您更快地开始电子邮件创建，并让您更轻松地访问文档和教程。

   For more information, refer to the [detailed documentation](../../designing/using/about-email-content-design.md#email-designer-home-page).

* 现在，您可以根据需要灵活配置列数和宽度。

   For more information, refer to the [detailed documentation](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

* 在移动视图中编辑时，您可以隐藏移动显示中的某些组件，以有效使用空间。

   For more information, refer to the [detailed documentation](../../designing/using/about-email-content-design.md#switching-to-mobile-view).

* 现在，您可以在已经可用的电子邮件模板顶部添加自定义社交渠道。
* 修复了在使用超过18个结构时，阻止向下滚动结构菜单的问题。(AMP-31173)
* 修复了在转发包含Adobe Campaign发送的预标头的电子邮件时，内容顶部显示的预标头的问题。(AMP-30736)
* Fixed an issue that prevented the subject line from being updated when clicking the **Refresh AEM content** option after modifying the subject in Adobe Experience Manager. (AMP-29984)
* 修复了阻止从Adobe Target使用动态图像的若干问题。
* 修复了在准备内容之前从URL导入内容时，无法更新预览时无法更新预览的问题。
* The YouTube icon has been added to the **Social** content component.
* The **List** view has been added for content components and fragments displayed in the Email Designer palette.

### Other improvements {#other-improvements-1}

* Adobe Campaign现在完全兼容FCM V和AEP SDK应用程序。
* Adobe Campaign支持Android和Apple的“佩戴操作系统”(Apple)的推送通知。
* 在界面中导航时可能显示的警告和错误消息变得更清晰、更易于理解。
* 您现在可以添加到与选择加入和选择退出(“不再联系…”字段)相关的配置文件列表列。
* 配置文件创建屏幕中的时区下拉列表已从“地址”部分移至界面的上半部分。
* 现在，您可以在配置自定义资源屏幕时添加分隔符，以便将字段组织成类别。

   For more information, refer to the [detailed documentation](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration).

### Other changes {#other-changes-1}

* Adobe Campaign和Adobe Experience Cloud将支持Microsoft Internet Explorer11(从2019年春季开始)和Campaign Standard19.2版本。请切换到Microsoft Edge或其他支持的浏览器。See [Deprecated and removed features](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html) page.
* The **Country code** field from the Profile resource has been renamed to **Country/Region code**.

### Patches {#patches-1}

* 修复了在向电子邮件事务发送测试配置文件时阻止发送消息的问题。(AMP-29854)
* 修复了当从所有渠道发送消息时，如果同时触发来自所有渠道的消息，则会减慢从其他渠道发送的消息的问题。
* 修复了在外部帐户连接尚未建立时，MTA会开始发送SMS消息的问题。
* 修复了调度程序活动执行频率和开始时间发生的问题。(AMP-30745)
* 修复了使用扩展配置文件资源时PKEY生成可能发生的问题。(AMP-30285)
* 修复了日历天疲劳规则可能发生的问题。(AMP-30136)
* 修复了尝试访问以“基本”结尾的自定义资源时可能出现的问题。(AMP-30109)
* 修复了阻止使用修补程序调用向服务订阅配置文件的问题。(AMP-29728)
* 修复了在通过加载文件活动导入XML文件时可能会损坏工作流的问题。(AMP-29208和Camp-28205)
* 修复了链接自定义资源时可能会阻止生成基数基数链接的问题。(AMP-30476)
* 修复了仅在使用区段代码时阻止扩展交付日志的问题。
* 修复了使用工作流中的文件传输活动时可能重复行的问题。
* 修复了阻止计划报告在选定时间发送的问题。
* 修复了一个问题，该问题导致工作流中的应用程序内交付“发送”和“发送”KPI不一致。
* 修复了阻止跟踪使用自定义HTML创作应用程序内消息的问题。
* 修复了在工作流中使用应用程序内交付内容时无法保存应用程序内交付内容的问题。
* 修复了阻止向管理员显示移动应用程序的问题。
* 修复了导致可交付性更新技术工作流程失败的问题。(AMP-26387)
* 修复了在创建应用程序内分发以及显示在交付控制板中显示的配置文件之间存在不一致的问题时。(AMP-28722)
* 修复了Campaign和Assets核心服务集成导致您无法在电子邮件中选择共享资产的问题。

## Release 19.0 - January 2019 {#release-19-0---january-2019}

### What's new? {#what-s-new--2}

<table> 
 <colgroup><col style="width: 30%"><col style="width: 70%"></colgroup>
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Email Designer General Availability<br /> </td> 
   <td> <p>新的直观电子邮件设计器(以前称为Creative Designer)已移至GA。它现在支持旧版内容编辑器中的所有功能，包括：</p> 
    <ul> 
     <li> The use of <a href="../../integrating/using/adding-target-dynamic-content.md">dynamic images from Adobe Target</a> </li> 
     <li> The ability to <a href="../../designing/using/importing-content-from-a-url.md#retrieving-content-from-a-url-automatically-at-preparation-time">retrieve content from a URL automatically at preparation time</a> </li> 
     <li> Fully compliant <a href="../../start/using/about-templates.md#content-templates">out-of-the box content templates</a>. </li> 
    </ul> 
    <p>For more information, refer to the <a href="../../designing/using/about-email-content-design.md">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html">how-to video</a>. 下面列出了改进和修复。</p><p>因此，旧版电子邮件内容编辑器现已弃用。For more information, refer to this <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">page</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Product Listings in Transactional Emails<br /> </td> 
   <td> <p>您现在可以在交易电子邮件中引用一个或多个产品集合。例如，您可以自动发送废弃的电子邮件，其中列出了用户购物车中包含图像、价格和链接到每个产品的产品。</p><p>For more information, refer to the <a href="../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-product-listings-in-transactional-emails-feature-video-setup.html">how-to video</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Mobile View in the Email Designer<br /> </td> 
   <td> <p>编辑电子邮件内容时，您现在可以切换到专用的移动视图。这允许您通过单独编辑移动显示屏的所有样式选项(如调整边距、较小的字体大小、不同背景颜色等)优化电子邮件的响应式设计。</p><p> For more information, refer to the <a href="../../designing/using/about-email-content-design.md#switching-to-mobile-view">detailed documentation</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> In-App Messaging Beta Improvements<br /> </td> 
   <td> <p>应用程序内消息测试功能已通过以下功能增强：</p> 
    <ul> 
     <li> 应用程序内测试版符合GDPR规范 </li> 
     <li> 与Analytics API集成以填充触发器 </li> 
     <li> 直观的交付模板外观和说明 </li> 
     <li> 对从可用性标准进行创作界面的增强 </li> 
    </ul> <p>For more information, refer to the <a href="../../channels/using/about-in-app-messaging.md">detailed documentation</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements}

* 现在，加载数据活动中的新选项允许您将一个后期处理舞台应用到包含被拒绝记录(例如，压缩格式压缩)。(CMS-24521)
* 现在，更新数据活动中的新选项允许您配置要上传的数据的最大批次大小。(AMP-28400)
* 改进了配置文件的地址状态选择。选择国家/地区时，“状态”下拉列表现在会自动更新，并使用相关状态值进行更新。(AMP-28874)
* 现在，提取文件活动中的新选项可防止在入站过渡为空时生成文件。这避免了在SFTP服务器上创建和上传空文件。
* 提交摘要报告已得到改进。
* 定义了配置文件地址时可用国家/地区的列表。(AMP-26707)
* 现在，尝试导入内置工作流时显示错误消息。

### Email Designer {#email-designer}

* 修复了一个问题，该问题导致在电子邮件模板上启用地理单位功能或通过电子邮件设计器创建的内容片段，即使在Adobe Campaign中禁用此功能，该功能在尝试再次访问模板或片段时也不可用。(AMP-28174)
* 修复了使用电子邮件设计器编辑内容时会保存动态内容条件的问题。(AMP-27905)
* 修复了在电子邮件设计器中编辑消息的纯文本版本和中断HTML同步后，从电子邮件内容中删除HTML版本的问题。(AMP-28507)
* 修复了在使用Internet Explorer11时阻止打开电子邮件设计器界面的问题。(AMP-28273)
* 修复了通过电子邮件设计器将样式设置的Microsoft Outlook呈现应用于按钮的问题。
* 修复了电子邮件设计器中的一个问题，该问题导致电子邮件设计器中的某个URL可从电子邮件中使用的内容片段中编辑，这是因为默认情况下片段处于锁定状态。
* 修复了一个问题，该问题导致电子邮件设计器分隔条组件可在Microsoft Office中显示。
* 修复了在使用传统电子邮件内容编辑器从AEM中查看内容时，在某些Internet浏览器上冻结页面的问题。(AMP-29068)
* 修复了在使用传统电子邮件内容编辑器时单击电子邮件中的任何图像时出现的错误。(AMP-30424)
* 修复了在使用电子邮件设计器编辑电子邮件时，阻止显示新创建的片段的问题。(AMP-29928)
* 修复了一个问题，该问题导致无法在使用电子邮件设计器创建和使用Outlook Web邮件客户端接收的电子邮件中正确显示按钮文本。
* 现在可以使用电子邮件设计器创建个人资料信息消息。(AMP-28900)
* 修复了电子邮件设计器中的一个错误，该错误导致在准备时自动从URL检索内容时，内容可编辑，而应锁定。

### Patches {#patches-2}

* 修复了动态报告中显示错误提交日志的问题。(AMP-23446)
* 修复了可能影响回弹摘要报告上的数字的问题(Camp-28703)
* Fixed an issue with the Campaign and Assets Core Service integration which could prevent assets from being displayed when selecting **[!UICONTROL Image shared from Adobe Experience Cloud]** in an email (CAMP-28732).
* 修复了一个问题，该问题导致即使在SMTP外部帐户中授权翻译，也会阻止包含“œ”字符的SMS消息发送。(AMP-29041)
* 修复了在工作流中使用分段活动时可能显示重复记录的问题。(AMP-28743)
* 修复了一个问题，该问题导致阻止在工作流活动中删除列上的某个值映射。(AMP-28708)
* 修复了在使用带有“测试以查看文件是否存在”的通配符时文件传输活动中存在的问题。(AMP-28977)
* 修复了在更新外部帐户设置时可能发生的文件传输活动中存在的问题。(AMP-28894)
* 修复了使用“电子邮件不是空”条件时查询编辑器中存在自定义筛选器的问题。(AMP-28741)
* 修复了导出具有超过100k记录的自定义资源表时可能出现的问题。(AMP-28150)
* 修复了阻止删除链接到触发器的事务消息的问题。(AMP-28385)
* 删除了在某些SMS日志中安全显示的口令。
* 修复了导致指向SMTP模拟器的连接由于Adobe Campaign发送的空密码而失败的问题。
* 修复了在SMS连接不稳定时阻止发送营销活动的问题。
* 修复了在动态报告中显示已删除分发的问题。
* 修复了在工作流中使用丰富化活动时，可以防止从交付日志检索其他数据、跟踪日志和排除日志表的问题。
* 修复了在使用“N基数集合链接”链接类型时可能发生的GDPR删除请求的问题，以及“删除目标记录意味着删除链接引用”选项。
* 修复了报告共享的问题。
* 修复了发送推送通知时可能导致吞吐量问题的问题。
* 修复了直邮输出文件缺失字段的问题。
* 修复了允许用户修改内置工作流的问题。
* 修复了在基于营销活动模板创建营销活动时，包括已配置提取活动的工作流的问题。(AMP-29198)
* 修复了文件提取活动存在的一个问题，该问题阻止对多个元素使用相同的表达式。(AMP-29182)
* 修复了查询编辑器中的问题，该问题与RTEvent的Broadlog和跟踪日志之间的加入条件存在。(AMP-28780)
* 修复了阻止对“特定操作”登陆页面选项进行修改的问题。(AMP-29422)
* 修复了阻止在工作流中导出活动有效负荷的问题。(AMP-29029)
* 修复了阻止列入黑名单的SMS号码排除在SMS消息中的问题。(AMP-28898)
* 修复了一个问题，该问题可能导致SMTP提供者在处理传入消息时无法收到通知。(AMP-29804)
* 修复了允许外部帐户删除关联分发的问题。(AMP-29738)
* 改进了SMS消息的发送吞吐量。
* 修复了阻止在SMS短消息中使用“~”字符的问题。(AMP-29172)
* 修复了发送时间优化选项交付的问题。(CMS-29231)

