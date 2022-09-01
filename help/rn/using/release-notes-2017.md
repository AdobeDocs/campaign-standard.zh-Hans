---
title: 发行说明 2017
description: 本页列出了所有 2017 版的 Adobe Campaign Standard。
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 73a1ec49-fcbc-406b-9590-1ad20da9e73b
source-git-commit: 177d9e0f8d61c000f01ac5e148dbd98fef0538ff
workflow-type: tm+mt
source-wordcount: '4613'
ht-degree: 5%

---

# 发行说明 2017{#release-notes}

是否正在寻找2017版的Adobe Campaign Standard?

每个版本都提供新功能和修补程序。 单击某个版本以查看其内容。

查看最新 [文档更新](../../rn/using/documentation-updates.md) Adobe Campaign Standard。 如果您正在查找较新版本，请参阅 [页面](../../rn/using/release-notes.md).

## 17.10 版 - 2017 年 10 月 {#release-17-10---october-2017}

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
   <td> 疲劳管理<br /> </td> 
   <td> 疲劳管理允许您创建疲劳规则以管理与用户档案的过度通信。 疲劳规则的构建非常容易，但其功能非常灵活，例如对跨多个渠道（包括事务型消息）的消息进行计数、仅对特定投放进行计数或将规则应用于特定用户档案。<br /> 有关更多信息，请参阅 <a href="../../sending/using/fatigue-rules.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 内容创建：从URL导入<br /> </td> 
   <td> 通过URL导入，您可以快速从网站中检索创意内容，以构建任何投放的电子邮件。 此外，您还可以通过允许第三方直接通过URL共享内容来简化您的创作流程。 导入的内容可以灵活地用作单次投放的一部分，或在模板级别用于确保所有相关营销活动（无论是基于工作流还是事务型消息）的品牌一致性，并包括A/B或多变量测试。 从URL导入会自动转换并跟踪所有链接，以通过动态报告监控电子邮件的性能。<br /> 有关更多信息，请参阅 <a href="../../designing/using/using-existing-content.md">详细文档</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* 修复了可能阻止正确解压缩大型压缩文件的问题。
* 品牌管理的安全性已得到改进。 现在，为Adobe技术管理员保留了修改品牌名称和发件人地址的权限。
* 为了提高安全性，用户生成的内容（图像、镜像页面、登陆页面等） 不再由adobe.com域提供。 现在，您必须通过使用品牌策略，使用自己的域来处理这些资源。
* 修复了显示和过滤营销活动时的界面问题。
* 修复了阻止使用POST剩余API调用更新订阅日期字段的问题。

_电子邮件、短信和直邮_

* 修复了可能阻止定向消息中的列表类型受众，从而导致准备失败的问题。
* 多语言电子邮件投放功能中添加了缺失的语言。
* 现在，当用户修改内容并进行保存时，投放仪表板中显示的内容缩略图会自动更新。
* 修复了阻止打开投放的时区相关问题。

_推送通知_

* 配置推送通知渠道时，iOS的推送提供程序平台应为 **apns** 和（对于Android） **gcm**.
* 修复了阻止在iOS界面中添加Adobe Campaign移动应用程序的错误。
* 现在， GCM和启用了FCM的Android移动应用程序都支持推送通知。
* 修复了在复制推送通知模板时阻止保存内容的错误。
* 现在，可以通过协调移动应用程序用户的数据，从Adobe Campaign数据库创建或更新用户档案。
* Adobe Campaign现在将处理事务推送通知优先于标准推送通知。

_报告_

* 修复了热点单击百分比无法在电子邮件内容中显示的问题。
* 修复了量阻止列表度被计为硬跳出而非跳出的问题。
* 修复了导致在摘要数据中显示负数的问题。
* 修复了将用户档案计入错误年龄区段的问题。
* 软退回和硬退回计算公式已更改。

_工作流_

* 修复了 **[!UICONTROL Load file]** 活动，在手动添加和删除活动中的列后可能会导致错误。
* 的 **[!UICONTROL deliverabilityUpdate]** 技术工作流现在计划在服务器时间凌晨2点运行。
* 修复了允许在没有导出角色的情况下执行列表导出的安全问题。
* 修复了 **[!UICONTROL Reconciliation]** 活动。
* 修复了在 **[!UICONTROL File Transfer]** 活动。

_用户档案和受众_

* 修复了在某些情况下可能导致错误结果而无法正确考虑查询条件的问题。
* 修复了在已准备但从未发送和过期的消息中定向用户档案时，可能会阻止访问这些用户档案的问题。

_集成_

* 修复了可能阻止为触发器创建的某些数据源正确显示和选择的问题。

_自定义资源_

* 修复了列表屏幕中出现的问题，该问题导致可以在没有任何数据的情况下显示自定义资源行。
* 修复了导致具有“False”值的布尔类型字段无法在自定义资源中显示的问题。

## 17.9 版 - 2017 年 9 月 {#release-17-9---september-2017}

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
   <td> 电子邮件模板库<br /> </td> 
   <td> 引入了18个全新的响应式模板，这些模板以两个美丽的主题 — Astro和Feather设计。 这些可自定义的模板与行业无关，可立即使用。 模板包含各种用例的内容，可让您以比以往更快、更高效、更美观地设计和投放电子邮件营销活动。<br /> 有关更多信息，请参阅 <a href="../../designing/using/using-reusable-content.md#content-templates">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 使用用户档案数据进行动态报告<br /> </td> 
   <td> 动态报告提供完全可自定义的实时业务报告。 在此版本中，动态报告的强大增强功能增加了对用户档案数据的访问权限，从而除了功能电子邮件促销活动数据（如打开数和点击数）之外，还允许按用户档案维度（如性别、城市、邮政编码和年龄）进行人口统计分析。 通过相同的易于使用的拖放界面，确定电子邮件促销活动如何针对最重要的客户区段执行比以往更轻松。<br /> 有关更多信息，请参阅 <a href="../../reporting/using/about-dynamic-reports.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 成批订阅来源和日期<br /> </td> 
   <td> 通过此批量订阅增强功能，您现在可以通过工作流中的订阅服务活动，直接在Adobe Campaign Standard数据库中存储订阅信息（来源和日期）。<br /> 有关更多信息，请参阅 <a href="../../automating/using/subscription-services.md">详细文档</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* 有些客户需要能够利用来自Adobe Campaign Standard的ID，因为他们无法管理唯一的密钥来标识自己的记录。 此ID(**ACS ID**)可在更新数据时导出以及用作协调键值。 有关更多信息，请参阅[详细文档](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)。
* FTP协议即将弃用。 现在，您应该改用SFTP。 为了不阻止现有实施，FTP上的现有配置仍将像以前一样工作，但新活动将不显示选项。

_电子邮件、短信和直邮_

* 现在，可以创建新的警报标准，以将其用于投放警报通知。 有关更多信息，请参阅[详细文档](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion)。
* 投放警报通知具有新设计，并且投放警报仪表板用户体验已得到改进。
* 现在，当路由外部帐户被禁用时，受影响的投放（电子邮件、短信和推送）以及 **预览** 按钮。
* 修复了在主题行中启用动态文本时，导致在电子邮件内容上预览A/B测试时出错的问题。

_事务性消息_

* 现在，可以定义何时发送跟进消息，例如，在发送事务型消息的3天后。 有关更多信息，请参阅[详细文档](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)。
* 现在，可以定义应发送链接到事件的事务型消息的日期。
* 修复了在删除链接到已接收和已处理事件的用户档案后执行包含跟进消息的工作流时导致SQL错误的问题。
* 修复了阻止删除链接到事件的用户档案的错误。
* 修复了可能阻止跟踪链接的重定向正常工作的问题。
* 修复了阻止对电子邮件或短信消息中的特定链接禁用跟踪的问题。

_报告_

* 的 **热点点击** 报表已得到改进。 此外，现在还可以根据投放中定义的每个条件内容显示热点点击，并针对定期投放或事务型消息的每次执行显示热点点击。 有关更多信息，请参阅[详细文档](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion)。
* 修复了隔离量度无法检索正确数据的问题。
* 日历小组件中添加了新的预设时间范围。
* 的 [动态报告量度](../../reporting/using/indicator-calculation.md) 和 [促销活动KPI](../../sending/using/confirming-the-send.md) （显示在已发送消息的仪表板上）已保持一致，以提高一致性。
* 修复了可能导致debian 7上的管道崩溃的问题。

_工作流_

* 修复了可能阻止导入的文件保留正常工作的问题。

_集成_

* Analytics与Campaign集成现在支持eVar和事件。
* 发送包含放弃购物车内容的电子邮件时，从购物车中删除的元素的有效负荷参数现在是可选的。

_用户档案和受众_

* Adobe Campaign现在提供了显示活动用户档案数的报表。 此报表仅提供信息，对账单没有直接影响。 有关更多信息，请参阅[详细文档](../../audiences/using/active-profiles.md)。
* 修复了在使用Profiles and Services API时阻止用户档案订阅服务的问题。

## 17.7 版 - 2017 年 7 月 {#release-17-7---july-2017}

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
   <td> 多语言电子邮件和短信投放<br /> </td> 
   <td> 根据自动分段客户的首选语言，通过单次投放定义和执行多语言电子邮件和短信投放。 关于每次投放之绩效的报告，可以细分到语言和各个级别。<br /> 越来越多的公司面临着以多种语言提供内容的挑战，这些内容在国内外都在不断发展。 因此，简化本地化报文传送是跨国公司有效客户沟通战略的关键部分；多语言国家/地区的公司；以及无论客户位于何处，都希望在语言级别进一步个性化其内容的公司。 有关更多信息，请参阅<a href="../../channels/using/creating-a-multilingual-email.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Campaign通知<br /> </td> 
   <td> 直接在Adobe Campaign Standard中接收有关重要系统活动的通知。 例如，当正在进行的投放进度或工作流出错时，系统会向您发送通知。<br /> 实时通知可让相关利益相关方随时了解情况，并让用户能够从应用程序内立即直接对活动通知采取行动。 团队的成果是提高敏捷性、高效性并更顺畅地执行营销活动。 有关更多信息，请参阅<a href="../../administration/using/sending-internal-notifications.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放警报<br /> </td> 
   <td> 除了直接在Adobe Campaign Standard中查看通知之外，Adobe Campaign现在还提供电子邮件警报系统，用于向重要系统活动的用户或外部利益相关方触发电子邮件警报。 创建、管理和接收可自定义的警报和功能板，以跟踪投放是成功还是失败。<br /> Adobe Campaign投放警报通过电子邮件和仪表板，使公司中所有涉及的Adobe Campaign用户自动获知投放执行状态，从而提高效率。 有关更多信息，请参阅<a href="../../sending/using/receiving-alerts-when-failures-happen.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 数据源中加密的声明ID<br /> </td> 
   <td> 使用加密的联系信息（电子邮件地址或电话号码）作为声明的ID，发送电子邮件和短信触发器，而无需在Campaign中使用现有的用户档案。 由于加密的声明ID可由Adobe Campaign Standard解码，因此当从包含以前未知联系人的其他Experience Cloud解决方案接收受众时，Campaign现在可以创建新的可销售用户档案。<br /> 通过电子邮件和短信实时定位客户和未知潜在客户，以分别提高现有客户群的忠诚度和获取新客户。 潜在客户在Adobe Campaign中进行身份验证并利用这些分析后，充分利用您的第一方Cookie数据(来自Adobe Audience Manager*)。 <br /> *需要Adobe Audience Manager。 有关更多信息，请参阅<a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 将KPI从Campaign共享到Analytics<br /> </td> 
   <td> 与Adobe Analytics共享促销活动数据，以衡量Campaign中的电子邮件营销量度以及通过转化的其他营销和广告工作，从而统一点击前和点击后行为。<br /> 直接跟踪整体性能，并发现与Analytics中外部计划的协同效应。 将此整合视图中的学习内容应用到您的营销活动中；最终改善打开、点进和转化率，以提升收入和整体促销活动效果。 <br /> Adobe Analytics是必需的。 有关更多信息，请参阅<a href="../../integrating/using/about-campaign-analytics-integration.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 直邮渠道 — 退回发件人<br /> </td> 
   <td> 现在支持与直邮提供商进行平面文件交换，其中包含“退回发件人”信息。 直邮渠道的这一增强功能允许将相应的邮政地址排除在将来的通信之外。<br /> 这样，营销人员就可以收到地址不正确的通知，并通过其他渠道与客户联系，或者鼓励他们更新其邮政地址。 此外，由于营销人员避免将邮件发送到错误的地址，因此还可以减少浪费的营销资金。 <br /> 直邮可作为附加渠道提供。 有关更多信息，请参阅<a href="../../channels/using/return-to-sender.md">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_常规_

* 修复了允许任何用户导出列表的问题。 现在，仅具有 **[!UICONTROL Export]** 角色。

_电子邮件、短信和直邮_

* 修复了 **updateDeliveryExecInfo** 工作流 **交付** 短信投放指示器为0。
* 在 **高级参数** 的属性， **路由** 下拉列表现在仅显示与模板消息类型对应的外部帐户。 例如，电子邮件投放模板仅显示电子邮件外部帐户。
* 修复了 **[!UICONTROL Text]** 为测试用户档案定义的首选电子邮件格式。
* 修复了在投放的计划定义屏幕中选择默认时区时导致Javascript错误的问题。
* 修复了阻止陷阱在发送日志中显示的问题。
* 现在，在投放创建向导的模板选择屏幕中，默认情况下隐藏跟进和A/B测试模板。 有关更多信息，请参阅 [详细文档](../../channels/using/creating-an-email.md).
* 修复了允许任何用户发送投放的问题。 现在，仅具有 **[!UICONTROL Start deliveries]** 角色。 有关更多信息，请参阅 [详细文档](../../sending/using/confirming-the-send.md).

_推送通知_

* 修复了 **促销活动跟踪端点** 阻止报告的URL。
* 修复了在Android设备上无法显示推送通知标题的问题。
* 修复了在推送通知仅包含标题（消息正文中没有任何内容）时，推送通知无法在iOS设备上显示的问题。
* 修复了强制跟踪投放中媒体附件URL的问题，该问题会阻止视频和图片嵌入投放中。 默认情况下，推送通知将停用对mediaAttachmentURL类型URL的跟踪。

_报告_

* 更正了图表和表之间的值显示不同的问题。
* 更正了将推送通知值显示为电子邮件值的问题。
* 修复了在营销活动之外创建投放时，将值显示为未知的问题。
* 更正了将短信报表数据显示为移动应用程序数据的问题。

_工作流_

* 您现在可以过滤工作流日志（时间段和文本搜索）。 有关更多信息，请参阅 [详细文档](../../automating/using/monitoring-workflow-execution.md).
* 工作流投放中现在提供了一个选项，用于在发送前停用确认。
* 修复了阻止在定期投放的创建向导中设置叫客过渡的问题。
* 修复了在使用基于自定义资源字段的工作流查询活动时发生的问题，该活动包含具有大量值的枚举

## 17.5 版 - 2017 年 5 月 {#release-17-5---may-2017}

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
   <td> 直邮<br /> </td> 
   <td> 通过Adobe Campaign Standard的首个离线渠道直邮，突破数字屏障并连接到物理世界。 此功能允许您将直邮提供商所需的文件个性化并生成为跨渠道营销活动的一部分。 利用直邮，通过引人入胜的触点吸引客户访问您的应用程序、网站或商店，重新吸引客户或增强客户体验。<br /> 有关更多信息，请参阅 <a href="../../channels/using/about-direct-mail.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 电子邮件密件抄送<br /> </td> 
   <td> 电子邮件密件抄送允许保存发送给各个收件人的唯一电子邮件，从而让品牌可以存档这些邮件。 通过向所有电子邮件添加密件抄送电子邮件地址，Adobe Campaign Standard客户可以使用此功能保留每封电子邮件的确切副本。 这是金融服务行业的常见法律要求，有助于客户服务中心实时解决冲突。<br /> 有关更多信息，请参阅 <a href="../../sending/using/archiving.md">详细文档</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_界面更新_

* 在顶部栏中， **[!UICONTROL Timeline]** 已删除链接，并替换为指向的链接 **[!UICONTROL Programs & Campaigns]** .

_电子邮件和短信消息_

* 修复了 **[!UICONTROL Retry in progress]** 投放状态。 颜色是灰色而不是蓝色。

_工作流_

* 修复了在 **[!UICONTROL Transfer file]** 活动。

_报告_

* 的 **[!UICONTROL Spam]** 和 **[!UICONTROL Spam rate]** 指标计算已更改。
* 的 **[!UICONTROL Bounce]** 量度已得到改进，以获得更准确的结果。

_推送通知_

* 修复了阻止您在用户档案的营销历史记录中单击推送事件的问题。
* 工作流中推送通知的使用已得到改进。

## 17.4 版 - 2017 年 4 月 {#release-17-4---april-2017}

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
   <td> 利用Creative SDK增强图像编辑功能<br /> </td> 
   <td> 现在，您可以访问由Creative SDK提供支持的整套功能，以在编辑电子邮件或登陆页面时直接在内容编辑器中增强您的图像。<br /> 此功能不需要获取其他Creative Cloud解决方案。<br /> 有关更多信息，请参阅 <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 事务性推送通知<br /> </td> 
   <td> 移动应用程序渠道已添加到Adobe Campaign的事务性消息传递功能中。 事务型消息现在支持三个渠道：电子邮件、短信和推送通知。<br /> 有关更多信息，请参阅 <a href="../../channels/using/transactional-push-notifications.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 定期推送通知<br /> </td> 
   <td> 您现在可以在工作流中配置定期推送通知。 如果客户希望定期更新（如每周提醒以签出新内容或促销活动），您可以使用定期推送通知。<br /> 有关更多信息，请参阅 <a href="../../automating/using/push-notification-delivery.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Amazon Simple Storage Service(S3)连接器<br /> </td> 
   <td> Amazon Simple Storage Service(S3)连接器现在可用于将数据导入或导出到Adobe Campaign。 可以在工作流活动中进行设置。 配置在外部帐户中完成。<br /> 有关更多信息，请参阅 <a href="../../administration/using/external-accounts.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver集成上线<br /> </td> 
   <td> Adobe Campaign与Dreamweaver之间的集成现已上线。 现在，它可与官方发布的上一版Dreamweaver(17.0.2)配合使用。<br /> 这需要安装Adobe Campaign集成扩展。 有关更多信息，请参阅 <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=zh-Hans">视频</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* 修复了内存消耗问题。

_电子邮件和短信消息_

* 修复了在预览消息时内容无法与最新更改正确同步的问题。
* 修复了阻止创建或删除MX或域电子邮件处理规则的问题。
* 修复了可能阻止您发送具有多个别名的电子邮件的问题。
* 修复了陷阱投放日志无法在投放的发送日志中显示的问题。
* 修复了在显示内容中没有URL的投放的跟踪URL时导致错误的问题。
* 修复了阻止在已发送消息中正确应用图像大小属性的问题。

_事务性消息_

* rtEventHistoId字段不再作为事务型消息模板中的个性化字段显示。

_登陆页面_

* 我们优化了 **[!UICONTROL by email]** 用于在登陆页面中协调新订阅者与数据库用户档案的过滤器。
* 修复了在表单配置中使用布尔字段时显示自由文本输入而不是复选框的问题。
* 修复了导致无法生成登陆页面缩略图的问题。

_工作流_

* 修复了在编辑 **[!UICONTROL End]** 或 **[!UICONTROL External Signal]** 活动（仅在Safari上）。
* 改进了编辑 **[!UICONTROL Read Audience]** 包含错误受众的活动。
* 修复了在执行订阅活动时可能导致SQL错误的问题。

_集成_

* 目标点数据：修复了计数位置订阅者时发生的错误。

_受众和查询_

* 修复了在查询编辑器中阻止对集合使用总和和平均聚合的问题。
* 修复了在更改过滤器资源后可能阻止重新加载查询编辑器的问题。

_报告_

* 修复了在表中选择多行时，无法正确计算打开率量度的问题。
* 修复了仅将量度显示为整数值的错误。 量度现在可以显示为小数。

_推送通知_

* 修复了在创建链接到在MCPNS上创建失败的移动应用程序的Android应用程序时，未显示错误消息的问题。
* 修复了允许用户向无提示通知添加声音的问题。

## 17.2 版 - 2017 年 3 月 {#release-17-2---march-2017}

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
   <td> 动态报告<br /> </td> 
   <td> 动态报告提供了新一代完全可自定义的实时业务报告。 此功能基于可视化的动态数据透视表和图形，允许您拖放变量和维度以分析营销活动的效率和效果。 动态报告还允许您从头开始创建自己的业务报告，并保存这些报告供以后使用。<br /> 有关更多信息，请参阅 <a href="../../reporting/using/about-dynamic-reports.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver集成(Labs)<br /> </td> 
   <td> 通过Adobe Campaign和Dreamweaver集成，您现在可以通过一个集成的流程，使用Adobe解决方案创建电子邮件促销活动。<br /> 您可以在Dreamweaver中编辑Adobe Campaign电子邮件，并在两个解决方案之间无缝同步内容。<br /> 对于初始版本，该集成将作为“Labs”功能提供，并且仅适用于Dreamweaver预发行测试版。 如果要激活它，请联系AC-DW-integration@adobe.com。<br /> 有关更多信息，请参阅 <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">视频</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 手动发送时间优化<br /> </td> 
   <td> 您现在可以在投放级别或使用工作流，手动定义每个收件人的自定义发送时间。 <br /> 提供了两个新选项： <br /> 
    <ul> 
     <li> 所有收件人都会收到考虑了所在时区时间的消息。 </li> 
     <li> 每个收件人在公式定义的计算日期和时间接收消息。 </li> 
    </ul> 有关更多信息，请参阅<a href="../../sending/using/optimizing-the-sending-time.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送通知新功能<br /> </td> 
   <td> 推送通知渠道已增强若干新功能：<br /> 
    <ul> 
     <li> 新的创作界面 </li> 
     <li> 静默通知 </li> 
     <li> 交互式推送 </li> 
     <li> 丰富的内容支持 </li> 
     <li> 负载大小计算器 </li> 
    </ul> 有关更多信息，请参阅<a href="../../channels/using/about-push-notifications.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流：新信号活动<br /> </td> 
   <td> 使用新 <span class="uicontrol">信号</span> 活动。<br /> 通过从另一个工作流启动一个工作流，您现在可以支持更复杂的客户历程。 您可以更好地监控客户历程，并在出现问题时做出反应。<br /> 更新了以下几个工作流活动：<br /> 
    <ul> 
     <li> <span class="uicontrol">结束</span> 活动：利用新选项卡，可指定要在执行此活动后触发的工作流。 </li> 
     <li> <span class="uicontrol">更新数据</span> 活动：使用新的空出站过渡添加 <strong>结束</strong> 活动来触发另一个工作流。 空出站过渡不携带任何数据，也不会占用系统上不必要的空间 </li> 
    </ul> 有关更多信息，请参阅<a href="../../automating/using/external-signal.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流：新读取受众活动<br /> </td> 
   <td> 从现有受众开始定位流程，您可以在一个活动中轻松选择和优化现有受众。<br /> 有关更多信息，请参阅 <a href="../../automating/using/read-audience.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 目标点数据<br /> </td> 
   <td> 目标点数据将Adobe Campaign与Adobe Analytics for Mobile集成在一起。 品牌可以从用户的移动位置(称为 <strong>目标点</strong>  — 用户打开品牌应用程序时。 这使品牌能够利用Adobe Campaign工作流，以便根据用户的位置发送个性化的消息。 此渠道利用Mobile核心服务的SDK。<br /> 请注意，使用此功能需要Analytics for Mobile，这是一种付费解决方案。<br /> 有关更多信息，请参阅 <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> REST API<br /> </td> 
   <td> 现在，API中提供了在任何级别链接到用户档案或服务资源的资源。<br /> 有关更多信息，请参阅 <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">详细文档</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_常规_

* 现在，可以在导出投放日志时添加用户档案数据。

_电子邮件和短信消息_

* 修复了导致 **[!UICONTROL Request confirmation before sending messages]** 选项，即使在取消选中该选项并保存投放后，仍保持选中状态。
* 修复了可能阻止取消发布事务型电子邮件的问题。
* 修复了在预览投放之前无法将内容与最新更改正确同步的问题。

_登陆页面_

* 修复了用户在单击登陆页面内容时无法编辑的错误。

_工作流_

* 修复了可能会阻止读取 **[!UICONTROL Load file]** 活动。
* 修复了在配置 **[!UICONTROL Load file]** 活动。

## 17.1 版 - 2017 年 1 月 {#release-17-1---january-2017}

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
   <td> 导出日志以进行外部报告<br /> </td> 
   <td> 导出投放和跟踪日志等日志，以便在您的首选报表或BI工具中处理它们。 您可以使用带有增量查询的简单工作流来自动定期导出新日志。<br /> 除了资源选取器中的日志资源可用性之外，还对 <a href="../../automating/using/incremental-query.md">增量查询</a> 和 <a href="../../automating/using/extract-file.md">提取文件</a> 活动：<br /> 
    <ul> 
     <li> <span class="uicontrol">增量查询</span> 现在，允许您使用日期字段检索新数据或更新的数据。 以前，即使自上次执行以来更新了之前执行的所有结果，也会自动排除这些结果。 </li> 
     <li> <span class="uicontrol">提取文件</span> 现在可以导出枚举值的标签，而不是ID。 </li> 
    </ul> 管理员可以使用这些活动来访问所有地理和组织单位。<br /> 有关导出日志的更多信息，请参阅 <a href="../../automating/using/exporting-logs.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 事务型消息的营销功能<br /> </td> 
   <td> 营销人员现在可以根据客户营销用户档案发送事务型消息。 这允许他们：<br /> 
    <ul> 
     <li> 应用营销分类规则，例如 <span class="uicontrol">阻止列表地址</span> . </li> 
     <li> 在消息中包含退订链接。 </li> 
     <li> 将事务型消息添加到全局投放报告。 </li> 
     <li> 在客户历程中使用事务型消息。 </li> 
    </ul> 有关更多信息，请参阅<a href="../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 事务型消息传递API<br /> </td> 
   <td> 事务型消息传递API现在通过 <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io</a>，从而更便于使用和监控：<br /> 
    <ul> 
     <li> 您可以从adobe.io平台报告和监控功能中受益。 </li> 
     <li> 身份验证现在使用基于adobe.io令牌的身份验证而不是IP列入允许列表来执行，从而使安全过程更简单。 </li> 
     <li> 现在，所有API都集成在一个平台上，如果您已经支持用户档案和服务API，则向集成添加事务性消息传送功能比以往更简单。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_常规_

* 的 **[!UICONTROL Access authorization]** 选项已返回到登陆页面属性。
* 修复了可能导致旧图像呈现而不是正确图像的问题。 如果在投放或登陆页面的内容定义中更新了源图像，则会发生这种情况。
* 修复了阻止用户编辑现有SFTP外部帐户中某些字段的问题。
* 修复了几个UI问题。 例如，用户现在可以编辑配置文件属性并保存修改，而不会遇到UI问题。

_电子邮件和短信消息_

* 修复了与包含HTML内容的

_推送通知_

* 修复了可能阻止从应用程序回发到Adobe Campaign服务器的问题。
* 修复了可能阻止 **[!UICONTROL Play a sound]** 和 **[!UICONTROL Custom fields]** Android中。
* 修复了可能导致向用于表情符号的Unicode字符添加额外转义字符的问题。
* 现在，在将订阅者的注册令牌添加到阻止列表后，相应的状态会立即在Adobe Campaign的应用程序订阅者列表中更新。

_工作流_

* 修复了可能阻止预览事件资源（例如rtEvent）上的查询的问题。
* 由 **[!UICONTROL Load file]** 活动现在可在其叫客过渡中进行检索，并在下一个活动中进行处理。 例如，使用 **[!UICONTROL Transfer file]** .
* 修复了在 **[!UICONTROL Temporary resource]** 在 **[!UICONTROL General]** 选项卡 **[!UICONTROL Segmentation]** .
* **[!UICONTROL Scheduler]** 不能再将活动设置为每10分钟触发一次多次工作流。
* 修复了可能阻止 **[!UICONTROL Use common columns]** 在 **[!UICONTROL Union]** 活动。

_集成_

* 修复了在Adobe Campaign中部署事件触发器时可能导致错误的问题。 在Adobe Marketing Cloud的“放弃”触发器中添加了“30天内回访的可能性”元数据后，会发生此错误。
* 修复了在从“人员”核心服务导入受众时，可能导致技术工作流清除“目标Dimension”字段的问题。 后续查询无法检索导入的受众。
* 修复了可能导致 **[!UICONTROL Save audience]** 选项时工作流的活动失败 **[!UICONTROL Share in Adobe Marketing Cloud]** 已检查。
