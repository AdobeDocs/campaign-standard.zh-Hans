---
title: 2017发行说明
seo-title: 2017发行说明
description: 2017发行说明
seo-description: 本页列出了Adobe Campaign Standard的所有2017版。
page-status-flag: 从未激活
uuid: d73f8186-e309-441b-969d-71d0 a1 c33 cf4
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: paign-standard-release
discoiquuid: CFD9b3b-3b3e-4587-9c46-b6 fb02131654
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Release Notes 2017{#release-notes}

正在寻找Adobe Campaign Standard的特定2017版？

每个版本都附带新增功能和修补程序。单击某个版本可查看其内容。

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a newer release, consult this [page](../../rn/using/release-notes.md).

## Release 17.10 - October 2017 {#release-17-10---october-2017}

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
   <td> Fatigue Management<br /> </td> 
   <td> 疲劳管理允许您创建疲劳规则，用档案管理过度沟通。疲劳规则很容易构建，但非常灵活，如在多个渠道中对消息计数(包括交易消息)、只计数特定交付，或将规则应用于特定档案。<br /> 有关详细信息，请参阅 <a href="../../administration/using/fatigue-rules.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Content creation: Import from a URL<br /> </td> 
   <td> 通过URL导入，您可以快速从网站检索创意内容，以便为任何交付构建电子邮件。此外，您还可以通过使第三方直接通过URL共享内容简化创意流程。导入的内容可以灵活地用作单次交付的一部分或在模板级别确保所有相关营销活动的品牌一致性，无论这些营销活动是基于工作流程的还是交易消息，并包括A/B或多变量测试。从URL导入可自动转换和跟踪通过动态报告监视电子邮件性能的所有链接。<br /> 有关详细信息，请参阅 <a href="../../designing/using/importing-content-from-a-url.md">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches}

#### Platform {#platform}

* 修复了可防止大压缩文件被正确解压缩的问题。
* 提高了品牌管理的安全性。现在，可以为Adobe技术管理员保留品牌名称和发送者地址。
* 为提高安全性，用户生成的内容(图像、镜像页面、着陆页面等)不再由adobe.com域提供。现在必须使用自己的域，通过使用品牌来处理这些资源。
* 修复了显示和筛选营销活动时的界面问题。
* 修复了使用POST Rest API调用更新订阅日期字段的问题。

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail}

* 修复了一个问题，该问题可能会阻止在消息中定位列表类型受众，从而导致准备失败。
* 多语言电子邮件交付功能中添加了缺少的语言。
* 在用户修改内容和保存内容时，现在会自动更新交付功能板上显示的内容缩略图。
* 修复了一个时区相关问题，该问题导致无法打开分发。

#### Push notifications {#push-notifications}

* When configuring the push notification channel, the push provider platform for iOS should be **apns** and for Android **gcm**.
* 修复了阻止在Adobe Campaign界面中添加iOS移动应用程序的错误。
* 现在，支持GCM和FCM的Android移动应用程序均支持推送通知。
* 修复了复制推送通知模板时无法保存内容的错误。
* 现在，可以通过协调移动应用程序用户的数据，从Adobe Campaign数据库创建或更新配置文件。
* Adobe Campaign现在优先处理通过标准推送通知处理交易推送通知。

#### Reports {#reports}

* 修复了阻止热点点击百分比显示在电子邮件内容中的问题。
* 修复了黑名单量度的问题，该问题计为硬退回而非退回。
* 修复了导致汇总数据中显示负值的问题。
* 修复了在错误年龄区段中计数档案的问题。
* 软和硬弹跳计算公式已更改。

#### Workflows {#workflows}

* Fixed an issue in the **[!UICONTROL Load file]** activity that could lead to errors after manually adding and removing columns in the activity.
* **[!UICONTROL deliverabilityUpdate]** 技术工作流现在计划在2am、服务器时间运行。
* 修复了一个安全问题，该问题允许在不使用导出角色的情况下执行列表导出。
* Fixed an issue with the **[!UICONTROL Reconciliation]** activity.
* Fixed an issue with the use of wildcard characters in the **[!UICONTROL File Transfer]** activity.

#### Profiles and audiences {#profiles-and-audiences}

* 修复了在某些特定情况下无法正确考虑查询条件的问题，从而导致错误结果。
* 修复了一个问题，该问题导致如果在准备好但从未发送和过期的消息中定位配置文件，则会阻止访问配置文件。

#### Integrations {#integrations}

* 修复了一个问题，该问题可能会阻止为触发器创建的某些Data Sources正确显示和被选中。

#### Custom resources {#custom-resources}

* 修复了在列表屏幕中出现自定义资源行而不显示任何数据的问题。
* 修复了阻止具有“False”值的布尔型字段在自定义资源中显示的问题。

## Release 17.9 - September 2017 {#release-17-9---september-2017}

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
   <td> Library of Email templates<br /> </td> 
   <td> 推出18个全新的、响应式模板，它们采用两个漂亮的主题- Astro和羽化。这些可自定义的模板具有行业敏感性，随时可供使用。模板包括各种使用案例，可让您更快、更高效、更漂亮地设计和交付您的电子邮件营销活动。<br /> 有关详细信息，请参阅 <a href="../../start/using/about-templates.md#content-templates">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamic Reporting with Profile Data<br /> </td> 
   <td> 动态报告可提供完全可自定义和实时的业务报表。在此版本中，强大的动态报告增强功能可增加对配置文件数据的访问权限，通过性别、城市、邮政编码和年龄等配置文件维度实现人口统计分析，除了功能电子邮件营销活动数据，如打开和点击。通过相同易用的拖放界面，确定针对最重要客户细分执行的电子邮件营销活动比以往更容易。<br /> 有关详细信息，请参阅 <a href="../../reporting/using/about-dynamic-reports.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Mass Subscription with Origin &amp; Date<br /> </td> 
   <td> 通过此大规模订阅增强功能，您现在可以通过工作流中的订阅服务活动直接在Adobe Campaign Standard数据库中存储订阅信息(源和日期)。<br /> 有关详细信息，请参阅 <a href="../../automating/using/subscription-services.md">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-1}

#### Platform {#platform-1}

* 一些客户需要能够利用来自Adobe Campaign Standard的ID，因为他们不管理唯一的密钥来识别自己的记录。This ID (**ACS ID**) can be exported as well as used as a reconciliation key while updating the data. For more information, refer to the [detailed documentation](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).
* FTP协议已停用。现在应改用SFTP。为了避免阻止现有的实施，FTP上的现有配置仍可照常运行，但此选项将不会显示新活动。

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-1}

* 现在，可以创建新的警报条件以将其用于发送通知通知。For more information, refer to the [detailed documentation](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* 交付通知通知具有新的设计，并且交付通知仪表板用户体验已得到改进。
* Now when a routing external account is disabled, a warning is displayed in the impacted deliveries (email, SMS and push) and the **Preview** button is hidden in these deliveries.
* 修复了在主题行中启用动态文本时对电子邮件内容进行A/B测试预览的问题。

#### Transactional messages {#transactional-messages}

* 现在可以定义要发送后续消息的时间，例如发送交易消息后的天。For more information, refer to the [detailed documentation](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).
* 现在可以定义链接到活动的事务消息的发送日期。
* 修复了在删除与接收和处理的事件链接的配置文件之后执行工作流时导致SQL错误的问题。
* 修复了一个错误，该错误导致无法删除链接到活动的配置文件。
* 修复了可防止跟踪链接重定向的问题。
* 修复了一个问题，该问题导致您无法禁用电子邮件或SMS消息中某些链接的跟踪。

#### Reports {#reports-1}

* **热门点击** 报告已得到改进。此外，现在可以根据在交付中定义的每个条件内容显示热点击，并为每次执行循环传输或事务消息显示热点击。For more information, refer to the [detailed documentation](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* 修复了阻止隔离指标检索正确数据的问题。
* 新的预设时间帧已添加到日历构件。
* [动态报告指标](../../reporting/using/indicator-calculation.md) 和 [营销活动的KPI](../../sending/using/confirming-the-send.md) (在发送消息的仪表板上显示)已进行对齐，以实现更高的一致性。
* 修复了可能导致在debian上崩溃的问题。

#### Workflows {#workflows-1}

* 修复了可防止导入的文件保留工作的问题。

#### Integrations {#integrations-1}

* 现在，Analytics和Campaign集成支持eVar和事件。
* 当发送包含已放弃购物车内容的电子邮件时，从购物车中删除的元素的有效负荷参数现在为可选。

#### Profiles and audiences {#profiles-and-audiences-1}

* Adobe Campaign现在提供一个报告，其中显示活动配置文件的数量。此报告仅具有信息性，不会直接影响计费。For more information, refer to the [detailed documentation](../../audiences/using/active-profiles.md).
* 修复了在使用配置文件和服务API时阻止配置文件订阅服务的问题。

## Release 17.7 - July 2017 {#release-17-7---july-2017}

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
   <td> Multilingual email and SMS deliveries<br /> </td> 
   <td> 根据自动细分客户的首选语言，通过单次交付定义和执行多语言电子邮件和SMS交付。报告每个分发的效果，涵盖语言和各个级别。<br /> 越来越多的公司面临着在国内和国外提供多种语言内容的挑战。因此，简化本地化消息交付是跨国公司有效的客户沟通战略的重要组成部分；多语言国家/地区的公司；那些希望在客户所在之处进一步个性化内容的公司。For more information, refer to the <a href="../../channels/using/creating-a-multilingual-email.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Campaign Notifications<br /> </td> 
   <td> 直接在Adobe Campaign Standard内接收有关重要系统活动的通知。例如，将通知您持续分发的进度，或者当工作流出错时。<br /> 实时通知可让相关利益相关者知晓并为用户提供即时、直接在应用程序中采取活动通知的能力。团队的结果是灵活性、效率和更顺畅地执行营销活动。For more information, refer to the <a href="../../administration/using/sending-internal-notifications.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery Alerting<br /> </td> 
   <td> 除了在Adobe Campaign Standard中直接查看通知外，Adobe Campaign现在还提供电子邮件警报系统，以向用户或外部相关人员触发重要系统活动的电子邮件警报。创建、管理和接收可自定义的警报和仪表板，以跟踪交付成功或失败。<br /> Adobe Campaign交付通知可使公司内所有相关Adobe Campaign用户能够通过电子邮件和仪表板自动获知投放执行状态，从而提高效率。For more information, refer to the <a href="../../sending/using/receiving-alerts-when-failures-happen.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Encrypted Declared ID in Datasources<br /> </td> 
   <td> 通过使用加密联系人信息(电子邮件地址或电话号码)作为声明ID，发送电子邮件和SMS触发器，无需在Campaign中使用现有配置文件。由于加密Declared ID可由Adobe Campaign Standard解码，因此，当从包含以前未知的联系人的其他Experience Cloud解决方案收到受众时，Campaign现在可创建新的可营销档案。<br /> 通过电子邮件和短信实时定位客户和未知的潜在客户，提高现有客户群中的忠诚度并分别赢取新客户。在潜在客户身份验证后充分利用第一方cookie数据(来自Adobe Audience Manager*)，并利用Adobe Campaign中的洞察。<br /> *需要Adobe Audience Manager。For more information, refer to the <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> KPI sharing from Campaign to Analytics<br /> </td> 
   <td> 通过Adobe Analytics共享营销活动数据，通过转化、统一前后和点击后行为，衡量Campaign中的电子邮件营销指标以及其他营销和广告工作。<br /> 在Analytics中直接跟踪整体绩效并揭示与外部项目的协同作用。将您的学习从整合视图应用回营销活动；最终提高打开率、点击率和转化率，提升收入和整体营销活动绩效。<br /> 需要Adobe Analytics。For more information, refer to the <a href="../../integrating/using/about-campaign-analytics-integration.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Direct Mail Channel - Return To Sender<br /> </td> 
   <td> 现在支持与发送方信息的直接邮件提供商进行平面文件交换。通过此增强的直邮渠道，可以将相应的邮寄地址排除在将来的通信中。<br /> 这使营销人员能够收到不正确地址的通知并通过其他渠道与客户互动，或鼓励他更新其邮寄地址。这也减少了营销人员浪费的营销资金，因为营销人员避免发送邮件至错误地址。<br /> 直邮可作为附加渠道提供。For more information, refer to the <a href="../../channels/using/return-to-sender.md">detailed documentation</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-2}

#### General {#general}

* 修复了允许任何用户导出列表的问题。Now only users with the **[!UICONTROL Export]** role are allowed to.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-2}

* Fixed an issue with the **updateDeliveryExecInfo** workflow that set the **To deliver** indicator to 0 for SMS deliveries.
* In the **Advanced parameters** of the delivery template’s properties, the **Routing** drop-down list now only displays external accounts corresponding to the template message type. 例如，电子邮件分发模板仅显示电子邮件外部帐户。
* Fixed an issue with the **[!UICONTROL Text]** preferred email format defined for test profiles.
* 修复了在交付的计划定义屏幕中选择默认时区时导致Javascript错误的问题。
* 修复了阻止陷印在发送日志中显示的问题。
* 在交付创建向导的模板选择屏幕中，默认情况下会隐藏后续和A/B测试模板。For more information, refer to the [detailed documention](../../channels/using/creating-an-email.md).
* 修复了允许任何用户发送分发的问题。Now only users with the **[!UICONTROL Start deliveries]** role are allowed to. For more information, refer to the [detailed documention](../../sending/using/confirming-the-send.md).

#### Push notifications {#push-notifications-1}

* Fixed an issue with the **Campaign Tracking Endpoint** URL that prevented reporting.
* 修复了阻止在Android设备上显示推送通知标题的问题。
* 修复了一个问题，该问题导致推送通知仅包含标题(并且邮件正文中不包含任何内容)，从而阻止在iOS设备上显示推送通知。
* 修复了一个问题，该问题导致在要跟踪的交付中强制媒体附件URL，这会阻止视频和图片嵌入到交付中。现在，推送通知默认取消激活type MediaAttachMurl类型的URL。

#### Reports {#reports-2}

* 更正了图表和表之间值显示不同的问题。
* 更正了将推送通知值作为电子邮件值显示的问题。
* 修复了在营销活动外部创建分发时显示未知值的问题。
* 更正了将SMS报告数据作为移动应用程序数据显示的问题。

#### Workflows {#workflows-2}

* 您现在可以过滤工作流日志(时间和文本搜索期间)。For more information, refer to the [detailed documention](../../automating/using/executing-a-workflow.md#monitoring).
* 现在，工作流交付中提供了一个选项，用于在发送之前取消激活确认。
* 修复了一个问题，该问题导致您无法在重复交付的创建向导中设置出站过渡。
* 修复了在使用包含大量值的枚举的自定义资源字段时，使用工作流查询活动的问题

## Release 17.5 - May 2017 {#release-17-5---may-2017}

### New capabilities {#new-capabilities-3}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Direct mail<br /> </td> 
   <td> 通过Adobe Campaign Standard的第一个线下渠道Direct Mail突破数字化壁垒并连接到实体世界。此功能允许您个性化并生成直接邮件提供商所需的文件，作为跨渠道营销活动的一部分。利用直接邮件重新吸引客户或通过引人注目的触觉接触点推动客户体验，将客户带到您的App、网站或商店。<br /> 有关详细信息，请参阅 <a href="../../channels/using/about-direct-mail.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Email BCC<br /> </td> 
   <td> 通过电子邮件密送，可以保存发送给个别收件人的唯一电子邮件，因此品牌可以存档这些消息。通过向所有电子邮件中添加密送电子邮件地址，Adobe Campaign Standard客户可以使用此功能保留每封电子邮件的精确副本。这是金融服务行业的一个常见法律要求，有助于客户服务中心实时解决冲突。<br /> 有关详细信息，请参阅 <a href="../../administration/using/configuring-email-channel.md#archiving-emails">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-3}

#### Interface updates {#interface-updates}

* In the top bar, the **[!UICONTROL Timeline]** link has been removed and replaced with a link to **[!UICONTROL Programs & Campaigns]** .

#### Emails and SMS messages {#emails-and-sms-messages}

* Fixed an issue which displayed the wrong color for the **[!UICONTROL Retry in progress]** delivery status. 颜色为灰色而不是蓝色。

#### Workflows {#workflows-3}

* Fixed an issue that occurred when changing the action to perform in a **[!UICONTROL Transfer file]** activity.

#### Reports {#reports-3}

* The **[!UICONTROL Spam]** and **[!UICONTROL Spam rate]** indicator calculations have been changed.
* **[!UICONTROL Bounce]** 指标已得到改进，结果更准确。

#### Push notifications {#push-notifications-2}

* 修复了一个问题，该问题导致您无法单击配置文件营销历史记录中的推送事件。
* 改进了工作流程中推送通知的使用。

## Release 17.4 - April 2017 {#release-17-4---april-2017}

### New capabilities {#new-capabilities-4}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Enhanced Image edition capabilities with the Creative SDK<br /> </td> 
   <td> 您现在可以访问由Creative SDK支持的一整套功能，以便在编辑电子邮件或登录页面时直接在内容编辑器中增强图像。<br /> 此功能不需要获取其他Creative Cloud解决方案。<br /> 有关详细信息，请参阅 <a href="../../designing/using/modifying-images-with-the-adobe-creative-sdk.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional push notifications<br /> </td> 
   <td> 移动应用程序频道已添加到Adobe Campaign的交易消息功能。交易消息现在支持三个通道：电子邮件、SMS和推送通知。<br /> 有关详细信息，请参阅 <a href="../../channels/using/transactional-push-notifications.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Recurring push notifications<br /> </td> 
   <td> 您现在可以在工作流中配置递归推送通知。在客户期望定期更新(如每周提醒新内容或促销)时，您可以使用循环推送通知。<br /> 有关详细信息，请参阅 <a href="../../automating/using/push-notification-delivery.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Amazon Simple Storage Service (S3) connector<br /> </td> 
   <td> 现在，Amazon Simple Storage Service(S3)连接器可用于将数据导入或导出到Adobe Campaign。它可以在工作流活动中进行设置。配置在外部帐户中完成。<br /> 有关详细信息，请参阅 <a href="../../administration/using/external-accounts.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver integration live<br /> </td> 
   <td> Adobe Campaign与Dreamweaver之间的集成现已上线。它现在可与Dreamweaver的官方官方版本(17.0.2)一起使用。<br /> 这需要从此处安装Adobe Campaign集成扩展： <a href="http://adobe.ly/acdw_addon">http://adobe.ly/acdw_addon</a><br /> 有关更多信息，请参阅此 <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">视频</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-4}

#### Platform {#platform-2}

* 修复了内存消耗问题。

#### Emails and SMS messages {#emails-and-sms-messages-1}

* 修复了在预览消息时内容无法与最新更改正确同步的问题。
* 修复了导致MX或域电子邮件处理规则无法创建或删除的问题。
* 修复了可能导致您无法发送多个别名电子邮件的问题。
* 修复了阻止陷印交付日志出现在发送日志中的问题。
* 修复了一个问题，该问题导致在显示内容的跟踪URL时出现错误，其中不含URL中的URL。
* 修复了一个问题，该问题导致图像的大小属性无法正确应用于发送的消息中。

#### Transactional messages {#transactional-messages-1}

* RTVenthIstog字段不再作为交易消息模板中的个性化字段暴露。

#### Landing pages {#landing-pages}

* We have optimized the **[!UICONTROL by email]** filter used in landing pages to reconcile new subscribers with database profiles.
* 修复了在表单配置中使用布尔字段时显示免费文本输入而不是复选框的问题。
* 修复了导致登录页面缩略图无法生成的问题。

#### Workflows {#workflows-4}

* Fixed a display error when editing an **[!UICONTROL End]** or **[!UICONTROL External Signal]** activity (on Safari only).
* Improved the error message displayed when editing a **[!UICONTROL Read Audience]** activity containing an erroneous audience.
* 修复了执行订阅活动时可能导致SQL错误的问题。

#### Integrations {#integrations-2}

* 兴趣点数据：修复了计数位置订阅者时出现的错误。

#### Audiences and queries {#audiences-and-queries}

* 修复了阻止在查询编辑器中的集合上使用总和和平均分配的问题。
* 修复了在更改过滤器的资源后重新加载查询编辑器的问题。

#### Reports {#reports-4}

* 修复了在表中选择多行时，无法正确计算打开速率指标的问题。
* 修复了仅将度量显示为整数值的错误。现在可以使用小数显示指标。

#### Push notifications {#push-notifications-3}

* 修复了在创建与在MCNS上创建的移动应用程序链接的Android应用程序时未显示错误消息的问题。
* 修复了允许用户向无声通知添加声音的问题。

## Release 17.2 - March 2017 {#release-17-2---march-2017}

### New capabilities {#new-capabilities-5}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Dynamic reporting<br /> </td> 
   <td> 动态报告提供新一代完全可自定义和实时的业务报表。此功能基于可视动态枢轴表和图形，可让您拖放变量和维度，分析营销活动的效率和效果。动态报告还允许您从头开始创建自己的业务报表，并保存它们供以后使用。<br /> 有关详细信息，请参阅 <a href="../../reporting/using/about-dynamic-reports.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver integration (Labs)<br /> </td> 
   <td> 通过Adobe Campaign和Dreamweaver集成，您现在可以使用Adobe解决方案创建电子邮件营销活动的集成流程。<br /> 您可以在Dreamweaver中编辑Adobe Campaign电子邮件，并在两种解决方案之间无缝同步内容。<br /> 对于初始版本，集成可作为“实验室”功能提供，并且仅可用于Dreamweaver预发行版测试版。如果您要激活它，请联系AC-DW-integration@adobe.com。<br /> 有关更多信息，请参阅此 <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">视频</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Manual send time optimization<br /> </td> 
   <td> 您现在可以为每个收件人手动定义自定义发送时间-在交付级别或使用工作流。<br /> 有两个新选项可用： <br /> 
    <ul> 
     <li> 所有收件人都会收到与其时区相关的消息。 </li> 
     <li> 每个收件人以公式定义的计算日期和时间收到消息。 </li> 
    </ul> For more information, refer to the <a href="../../sending/using/optimizing-the-sending-time.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push notifications New capabilities<br /> </td> 
   <td> The push notification channel has been enhanced with several new capabilities:<br /> 
    <ul> 
     <li> 新的创作界面 </li> 
     <li> 无声通知 </li> 
     <li> 交互式推送 </li> 
     <li> 丰富内容支持 </li> 
     <li> 负载大小计算器 </li> 
    </ul> For more information, refer to the <a href="../../channels/using/about-push-notifications.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: new Signal activity<br /> </td> 
   <td> Trigger a workflow from another workflow using the new <span class="uicontrol">Signal</span> activity.<br /> 由于能够从另一个工作流程开始工作，您现在可以支持更复杂的客户旅程。您可以更好地监控客户旅程并应对问题，以防出现问题。<br /> 已更新多个工作流程活动：<br /> 
    <ul> 
     <li> <span class="uicontrol">结束</span> 活动：新选项卡允许您指定在执行此活动后触发的工作流。 </li> 
     <li> <span class="uicontrol">更新数据</span> 活动：使用新的空出站过渡添加 <strong>触发其他工作流的最终</strong> 活动。空出站过渡不会携带任何数据，而且不会占用系统中不必要的空间 </li> 
    </ul> For more information, refer to the <a href="../../automating/using/external-signal.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: new Read audience activity<br /> </td> 
   <td> 利用现有受众开始定位流程，您可以在一个活动中轻松选择和调整。<br /> 有关详细信息，请参阅 <a href="../../automating/using/read-audience.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Points of Interest data<br /> </td> 
   <td> Points of Interest数据将Adobe Campaign与Adobe Analytics相集成。A brand can collect data from users' mobile locations - called <strong>Points of Interest</strong> - when users open the brand's app. 这使品牌能够利用Adobe Campaign工作流程，根据用户的位置发送个性化消息。此渠道利用Mobile核心服务的SDK。<br /> 请注意，使用此功能需要移动版Analytics，这是付费解决方案。<br /> 有关详细信息，请参阅 <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> REST APIs<br /> </td> 
   <td> API中现在提供与配置文件或服务资源相关联的资源。<br /> 有关详细信息，请参阅 <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-5}

#### General {#general-1}

* 现在，可以在导出交付日志时添加配置文件数据。

#### Emails and SMS messages {#emails-and-sms-messages-2}

* Fixed an issue causing the **[!UICONTROL Request confirmation before sending messages]** option to remain selected even after unchecking it and saving the delivery.
* 修复了一个问题，该问题可能会阻止取消发布交易电子邮件。
* 修复了在预览交付之前内容无法与最新更改正确同步的问题。

#### Landing pages {#landing-pages-1}

* 修复了一个错误，该错误导致用户在登陆页面的内容中点击时无法编辑。

#### Workflows {#workflows-5}

* Fixed an issue that could prevent from reading the content of the reject transition of a **[!UICONTROL Load file]** activity.
* Fixed an issue that prevented swapped columns to be properly taken into account when configuring a **[!UICONTROL Load file]** activity.

## Release 17.1 - January 2017 {#release-17-1---january-2017}

### New capabilities {#new-capabilities-6}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Log export for external reporting<br /> </td> 
   <td> 导出诸如交付和跟踪日志等日志，以便在首选报告或BI工具中处理这些日志。您可以将简单的工作流与增量查询结合使用，以自动导出新日志。<br /> 除了资源选取器中的日志资源可用外， <a href="../../automating/using/incremental-query.md">对增量查询</a> 和 <a href="../../automating/using/extract-file.md">提取文件</a> 活动进行了增强：<br /> 
    <ul> 
     <li> <span class="uicontrol">增量查询</span> 现在允许您使用日期字段检索新的或更新的数据。以前，之前执行的所有结果都会自动排除，即使自上次执行以来更新的结果也是如此。 </li> 
     <li> <span class="uicontrol">提取文件</span> 现在可导出用于枚举值而非ID的标签。 </li> 
    </ul> 这些活动适用于有权访问所有地理和组织单位的管理员。<br /> 有关导出日志的详细信息，请参阅 <a href="../../automating/using/exporting-logs.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Marketing capabilities for transactional messages<br /> </td> 
   <td> 营销人员现在可以根据客户营销档案发送交易消息。This allows them to:<br /> 
    <ul> 
     <li> Apply marketing typology rules such as <span class="uicontrol">Blacklisted address</span> . </li> 
     <li> 在消息中包括取消订阅链接。 </li> 
     <li> 将交易消息添加到全局交付报告。 </li> 
     <li> 利用客户旅程中的交易消息。 </li> 
    </ul> For more information, refer to the <a href="../../channels/using/profile-transactional-messages.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional Messaging API<br /> </td> 
   <td> The Transactional Messaging API is now available through <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io</a>, making it easier to use and to monitor:<br /> 
    <ul> 
     <li> 您可以从adobe. io平台报告和监控功能中受益。 </li> 
     <li> 身份验证现在使用基于adobe. io令牌的身份验证而非IP白名单进行，从而使安全过程更简单。 </li> 
     <li> 所有API现在都集成在单一平台上，如果您已经支持Profile和Services API，则可以比以往更简单地为集成添加交易消息功能。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-6}

#### General {#general-2}

* **[!UICONTROL Access authorization]** 选项返回到登陆页面属性。
* 修复了可能导致渲染旧图像而不是正确图像的问题。如果源图像在交付或登陆页面的内容定义中已更新，则会发生这种情况。
* 修复了阻止用户编辑现有SFTP外部帐户中的某些字段的问题。
* 修复了多个UI问题。例如，用户现在可以编辑配置文件属性并保存修改，而无需在UI中遇到问题。

#### Emails and SMS messages {#emails-and-sms-messages-3}

* 修复了与包含一个

#### Push notifications {#push-notifications-4}

* 修复了可能导致从应用程序返回Adobe Campaign服务器的问题。
* Fixed an issue that may have prevented **[!UICONTROL Play a sound]** and **[!UICONTROL Custom fields]** to be taken into account for Android.
* 修复了可能导致将多余的转义字符添加到Emojis使用的Unicode字符的问题。
* 当订户的注册令牌变为黑名单时，相应的状态现在会在应用程序的用户列表中的Adobe Campaign中立即更新。

#### Workflows {#workflows-6}

* 修复了可能已阻止对事件资源(例如，RTEEvent)查询的预览的问题。
* The reject file generated by a **[!UICONTROL Load file]** activity can now be retrieved in its outbound transition and processed in the next activity. For example, upload the reject file via an SFTP server using **[!UICONTROL Transfer file]** .
* Fixed an issue that may have prevented a user from limiting the population of a segment if **[!UICONTROL Temporary resource]** was selected in the **[!UICONTROL General]** tab of **[!UICONTROL Segmentation]** .
* **[!UICONTROL Scheduler]** 不能再将活动设置为每10分钟触发一次工作流。
* Fixed an issue that may have prevented **[!UICONTROL Use common columns]** from working properly in an **[!UICONTROL Union]** activity.

#### Integrations {#integrations-3}

* 修复了在Adobe Campaign中部署事件触发器时可能导致错误的问题。在Adobe Marketing Cloud中的放弃触发器触发器添加了“30天内可能返回”元数据时出现此错误。
* 修复了在从People核心服务导入受众时，可能导致技术工作流清除“目标维度”字段的问题。随后的查询无法检索导入的受众。
* Fixed an issue that may have caused the **[!UICONTROL Save audience]** activity of a workflow to fail when the option **[!UICONTROL Share in Adobe Marketing Cloud]** was checked.

