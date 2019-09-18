---
title: 发行说明2017
seo-title: 发行说明2017
description: 发行说明2017
seo-description: 本页列出了所有2017版Adobe Campaign Standard。
page-status-flag: 从未激活
uuid: d73f8186-e309-441b-969d-71d0a1c33cf4
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: 参考
topic-tags: campaign-standard-releases
discoiquuid: 1cfd9b3b-9b3e-4587-9c46-b6fb02131654
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7a091f0fd4b191a9f81dfe3a8c74e1624de72f12

---


# 发行说明2017{#release-notes}

是否正在寻找Adobe Campaign Standard的特定2017版本？

每个版本都提供新功能和修补程序。 单击某个版本可查看其内容。

查看Adobe Campaign [Standard的最新文档](../../rn/using/documentation-updates.md) 更新。 如果要寻找较新的版本，请查阅此 [页](../../rn/using/release-notes.md)。

## 版本17.10 - 2017年10月 {#release-17-10---october-2017}

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
   <td> 疲劳管理<br /> </td> 
   <td> 疲劳管理允许您创建疲劳规则以管理与配置文件的过度通信。 疲劳规则的构建很容易，但是具有非常灵活的功能，如跨多个渠道（包括交易消息）计数消息、仅计数特定交付或将规则应用于特定配置文件。<br /> 有关详细信息，请参阅详 <a href="../../administration/using/fatigue-rules.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 内容创建：从URL导入<br /> </td> 
   <td> 通过URL导入，您可以快速从网站中检索您的创意内容，为任何分发构建电子邮件。 此外，您还可以通过使第三方直接通过URL共享内容来简化您的创作过程。 导入的内容可以灵活地用作单个交付的一部分或在模板级别使用，以确保所有相关营销活动的品牌一致性（无论这些活动是基于工作流的消息还是交易消息），并包括A/B或多变量测试。 从URL导入会自动转换和跟踪所有链接，以通过Dynamic Reporting监控电子邮件性能。<br /> 有关详细信息，请参阅详 <a href="../../designing/using/using-existing-content.md#importing-content-from-a-url">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches}

#### 平台 {#platform}

* 修复了可能导致无法正确解压大文件的问题。
* 品牌管理的安全性已得到改进。 现在，Adobe技术管理员可以保留修改品牌名称和发件人地址。
* 为提高安全性，用户生成的内容（图像、镜像页面、登录页面等）不再由adobe.com域提供。 现在，您必须使用自己的域来通过使用品牌来处理这些资源。
* 修复了显示和筛选营销活动时的界面问题。
* 修复了阻止使用POST Rest API调用更新订阅日期字段的问题。

#### 电子邮件、短信和直邮 {#emails--sms-messages-and-direct-mail}

* 修复了一个问题，该问题可能导致无法定位消息中的列表类型受众，从而导致准备失败。
* 多语言电子邮件交付功能中新增了缺失的语言。
* 内容缩略图（显示在交付功能板上）现在会在用户修改内容并保存时自动更新。
* 修复了阻止打开交付的时区相关问题。

#### 推送通知 {#push-notifications}

* 在配置推送通知通道时，iOS的推送提供者平台应为apns **** ,Android **gcm**&#x200B;的推送提供者平台。
* 修复了阻止iOS移动应用程序添加到Adobe Campaign界面中的错误。
* 推送通知现在在支持GCM和FCM的Android移动应用程序上都受支持。
* 修复了复制推送通知模板时无法保存内容的错误。
* 现在，通过协调移动应用程序用户的数据，可以从Adobe Campaign数据库创建或更新配置文件。
* Adobe Campaign现在优先处理事务推送通知而不是标准推送通知。

#### 报告 {#reports}

* 修复了阻止热点单击百分比显示在电子邮件内容中的问题。
* 修复了黑名单指标的问题，该指标被计为硬弹跳而非弹跳。
* 修复了导致在摘要数据中显示负计数的问题。
* 修复了在错误的年龄区段中计算配置文件的问题。
* 软弹跳和硬弹跳计算公式已更改。

#### 工作流 {#workflows}

* 修复了活动中 **[!UICONTROL Load file]** 在手动添加和删除活动中的列后可能导致错误的问题。
* 技术 **[!UICONTROL deliverabilityUpdate]** 工作流程现在计划在服务器时间凌晨2点运行。
* 修复了允许在不具有导出角色的情况下执行列表导出的安全问题。
* 修复了活动的问 **[!UICONTROL Reconciliation]** 题。
* 修复了在活动中使用通配符的问 **[!UICONTROL File Transfer]** 题。

#### 档案和受众 {#profiles-and-audiences}

* 修复了一个问题，该问题可能导致在某些情况下无法正确考虑查询条件，从而导致错误结果。
* 修复了在已准备但从未发送和过期的消息中定位配置文件时，可能会阻止访问配置文件的问题。

#### 集成 {#integrations}

* 修复了一个问题，该问题可能会阻止为触发器创建的某些数据源正确显示和被选择。

#### 自定义资源 {#custom-resources}

* 修复了在列表屏幕中出现的一个问题，该问题导致自定义资源行可能在不显示任何数据的情况下显示。
* 修复了阻止具有“False”值的布尔类型字段在自定义资源中显示的问题。

## 17.9版- 2017年9月 {#release-17-9---september-2017}

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
   <td> 电子邮件模板库<br /> </td> 
   <td> 隆重推出采用两种精美主题设计的十八款全新响应式模板：Astro和Feather。 这些可自定义的模板与行业无关，并且随时可用。 模板包含多种用例内容，可让您的电子邮件营销活动比以往更快、更高效、更美观地设计和投放。<br /> 有关详细信息，请参阅详 <a href="../../designing/using/using-reusable-content.md#content-templates">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 使用配置文件数据的动态报告<br /> </td> 
   <td> 动态报告提供完全可自定义的实时业务报告。 在此版本中，动态报告的强大增强功能增加了对个人资料数据的访问，使用户能够按个人资料维度（如性别、城市、邮政编码和年龄）以及功能性电子邮件营销活动数据（如打开和点击）进行人口统计分析。 借助相同的易用拖放界面，确定电子邮件营销活动如何针对最重要的客户细分执行比以往更容易。<br /> 有关详细信息，请参阅详 <a href="../../reporting/using/about-dynamic-reports.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 具有来源和日期的批量订阅<br /> </td> 
   <td> 通过此批量订阅增强功能，您现在可以通过工作流中的订阅服务活动直接在Adobe Campaign standard数据库中存储订阅信息（源和日期）。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/subscription-services.md">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-1}

#### 平台 {#platform-1}

* 一些客户需要能够利用Adobe Campaign Standard提供的ID，因为他们没有管理唯一的密钥来识别自己的记录。 此ID(**ACS ID**)可在更新数据时导出并用作对帐密钥。  有关详细信息，请参阅详 [细文档](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)。
* FTP协议已弃用。 您现在应改用SFTP。 为了不阻止现有实施，FTP上的现有配置仍将像以前一样工作，但新活动不会显示此选项。

#### 电子邮件、短信和直邮 {#emails--sms-messages-and-direct-mail-1}

* 现在，可以创建新的警报标准，以将其用于发送警报通知。  有关详细信息，请参阅详 [细文档](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion)。
* 交付警报通知具有新设计，并且交付警报功能板用户体验已得到改进。
* 现在，当路由外部帐户被禁用时，受影响的分发（电子邮件、SMS和推送）中会显示一条警告消息，并且 **Preview** （预览）按钮隐藏在这些分发中。
* 修复了在主题行中启用动态文本时，电子邮件内容的A/B测试预览出现错误的问题。

#### 交易消息 {#transactional-messages}

* 现在可以定义何时发送后续消息，例如，在发送交易消息后3天。  有关详细信息，请参阅详 [细文档](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)。
* 现在，可以定义应从何时发送链接到活动的交易消息开始的日期。
* 修复了在删除链接到已接收和已处理事件的配置文件后，执行包含后续消息的工作流时导致SQL错误的问题。
* 修复了无法删除链接到事件的配置文件的错误。
* 修复了一个问题，该问题可能会阻止跟踪链接的重定向工作。
* 修复了阻止您对电子邮件或SMS消息中的特定链接进行跟踪的问题。

#### 报告 {#reports-1}

* 热点 **单击** (Hot clicks)报告已得到改进。 此外，现在可以根据在分发中定义的每个条件内容显示热点点击，并且可以显示重复分发或交易消息的每次执行的热点点击。  有关详细信息，请参阅详 [细文档](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion)。
* 修复了导致隔离度量无法检索正确数据的问题。
* 新的预设时间范围已添加到日历构件。
* 动态 [报告指标](../../reporting/using/indicator-calculation.md) ，营销 [](../../sending/using/confirming-the-send.md) 活动的KPI（显示在已发送消息的仪表板上）已保持一致，以便更加一致。
* 修复了可能导致流水线在debian 7上崩溃的问题。

#### 工作流 {#workflows-1}

* 修复了导入的文件保留无法正常工作的问题。

#### 集成 {#integrations-1}

* 现在，Analytics &amp; Campaign集成支持eVar和事件。
* 发送包含放弃购物车内容的电子邮件时，从购物车中删除的元素的有效负荷参数现在是可选的。

#### 档案和受众 {#profiles-and-audiences-1}

* Adobe Campaign现在提供一个报告，其中显示活动配置文件的数量。 此报告仅提供信息，对计费没有直接影响。  有关详细信息，请参阅详 [细文档](../../audiences/using/active-profiles.md)。
* 修复了在使用Profiles and Services API时，配置文件无法订阅服务的问题。

## 17.7版- 2017年7月 {#release-17-7---july-2017}

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
   <td> 多语种电子邮件和短信发送<br /> </td> 
   <td> 根据自动细分的客户首选语言，通过单次分发来定义和执行多语言电子邮件和短信发送。 向下报告每次交付的效果，包括语言和各个级别。<br /> 随着内外内容的不断增长，越来越多的公司面临着以多种语言提供内容的挑战。 因此，简化本地化消息传送是跨国公司有效客户沟通战略的关键部分；多语言国家／地区的公司；以及希望在语言级别进一步个性化其内容的公司，无论客户位于何处。  有关详细信息，请参阅详 <a href="../../channels/using/creating-a-multilingual-email.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Campaign通知<br /> </td> 
   <td> 直接在Adobe Campaign standard中接收有关重要系统活动的通知。 例如，您将收到持续分发进度或工作流出错时的通知。<br /> 实时通知可让相关利益相关方及时获得通知，并使用户能够立即直接从应用程序内对活动通知采取行动。 团队的成果是高级敏捷性、效率和更顺畅的营销活动执行。  有关详细信息，请参阅详 <a href="../../administration/using/sending-internal-notifications.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付警报<br /> </td> 
   <td> 除了直接在Adobe Campaign Standard中查看通知外，Adobe Campaign现在还提供电子邮件警报系统，可向用户或外部利益相关方触发重要系统活动的电子邮件警报。 创建、管理和接收可自定义的警报和仪表板，以跟踪交付成功或失败。<br /> Adobe Campaign交付警报通过电子邮件和仪表板自动告知公司内所有相关的Adobe Campaign用户交付执行状态，从而提高了效率。  有关详细信息，请参阅详 <a href="../../sending/using/receiving-alerts-when-failures-happen.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 数据源中的加密Declared ID<br /> </td> 
   <td> 使用加密的联系信息（电子邮件地址或电话号码）作为Declared ID发送电子邮件和SMS触发器，而无需在Campaign中存在配置文件。 由于加密的Declared ID可以由Adobe Campaign Standard解码，因此，从包含先前未知联系人的其他Experience cloud解决方案接收受众时，Campaign现在可以创建新的可销售档案。<br /> 通过电子邮件和短信实时定位客户和未知的潜在客户，分别提高现有客户群的忠诚度和赢取新客户。 在潜在客户进行身份验证并在Adobe Campaign中利用这些洞察后，充分利用您的第一方Cookie数据（来自Adobe Audience Manager*）。 <br /> *需要Adobe Audience Manager。  有关详细信息，请参阅详 <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 从营销活动到分析的KPI共享<br /> </td> 
   <td> 与Adobe Analytics共享营销活动数据，通过转化、统一点击前和点击后行为，衡量Campaign中的电子邮件营销指标以及其他营销和广告工作。<br /> 在Analytics中直接跟踪整体绩效并发现与外部计划的协同作用。 将您从此整合视图中的学习内容应用回营销活动中；最终提高开放、点进率和转化率，提高收入和整体营销活动效果。 <br /> 需要Adobe Analytics。  有关详细信息，请参阅详 <a href="../../integrating/using/about-campaign-analytics-integration.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 直邮渠道——返回发件人<br /> </td> 
   <td> 现在支持与直接邮件提供商进行包含“返回给发送者”信息的平面文件交换。 对“直邮”渠道的这一增强功能允许将相应的邮政地址排除在将来的通信之外。<br /> 这使营销人员能够收到错误地址的通知并通过其他渠道与客户互动或鼓励他更新其邮寄地址。 这还可以减少营销人员避免将邮件发送到错误地址时浪费的营销资金。 <br /> “直邮”可作为附加渠道提供。  有关详细信息，请参阅详 <a href="../../channels/using/return-to-sender.md">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-2}

#### 常规 {#general}

* 修复了允许任何用户导出列表的问题。 现在，仅允许具有该角 **[!UICONTROL Export]** 色的用户访问。

#### 电子邮件、短信和直邮 {#emails--sms-messages-and-direct-mail-2}

* 修复了updateDeliveryExecInfo **（更新交付执行信息）** 工作流程中将SMS发送的“ **To deliver** indicator”（发送指示符）设置为0的问题。
* 在交 **付模板属性的** “高级参数”中，“路由选择 **** ”下拉列表现在仅显示与模板消息类型对应的外部帐户。 例如，电子邮件分发模板仅显示电子邮件外部帐户。
* 修复了为测试配置文件定 **[!UICONTROL Text]** 义的首选电子邮件格式的问题。
* 修复了在分发的计划定义屏幕中选择默认时区时导致Javascript错误的问题。
* 修复了阻止陷阱显示在发送日志中的问题。
* 现在，在交付创建向导的模板选择屏幕中，默认情况下隐藏跟进和A/B测试模板。 有关详细信息，请参阅详 [细文档](../../channels/using/creating-an-email.md)。
* 修复了允许任何用户发送分发的问题。 现在，仅允许具有该角 **[!UICONTROL Start deliveries]** 色的用户访问。 有关详细信息，请参阅详 [细文档](../../sending/using/confirming-the-send.md)。

#### 推送通知 {#push-notifications-1}

* 修复了营销活动跟 **踪端点URL中阻止报告的问题** 。
* 修复了在Android设备上无法显示推送通知标题的问题。
* 修复了当推送通知仅包含标题（消息正文中没有标题）时，在iOS设备上无法显示推送通知的问题。
* 修复了在要跟踪的分发中强制使用媒体附件URL的问题，该问题导致视频和图片无法嵌入到分发中。 现在，对于推送通知，默认情况下将取消激活媒体附件URL类型的URL跟踪。

#### 报告 {#reports-2}

* 更正了图表和表之间显示值不同的问题。
* 更正了将推送通知值显示为电子邮件值的问题。
* 修复了在营销活动之外创建分发时，将值显示为未知的问题。
* 更正了将SMS报告数据显示为移动应用程序数据的问题。

#### 工作流 {#workflows-2}

* 您现在可以过滤工作流日志（时间段和文本搜索）。 有关详细信息，请参阅详 [细文档](../../automating/using/executing-a-workflow.md#monitoring)。
* 工作流提交中现在提供了一个选项，用于在发送之前取消激活确认。
* 修复了在重复交付的创建向导中无法设置出站过渡的问题。
* 修复了在使用具有大量值的枚举的自定义资源字段时，基于该自定义资源字段使用工作流查询活动时出现的问题

## 17.5版- 2017年5月 {#release-17-5---may-2017}

### 新功能 {#new-capabilities-3}

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
   <td> 借助Adobe Campaign Standard的第一个线下渠道“直邮”，打破数字壁垒并与现实世界建立联系。 此功能允许您将直接邮件提供商所需的文件个性化并生成为跨渠道营销活动的一部分。 利用直邮，通过引人入胜的触觉接触点将客户引导到您的应用程序、网站或商店，重新吸引客户或增强客户体验。<br /> 有关详细信息，请参阅详 <a href="../../channels/using/about-direct-mail.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 密件抄送<br /> </td> 
   <td> 密件抄送电子邮件可保存发送给各个收件人的唯一电子邮件，因此品牌可以存档这些邮件。 通过向所有电子邮件添加密送电子邮件地址，Adobe Campaign Standard客户可以使用此功能保留每封电子邮件的准确副本。 这是金融服务业的常见法律要求，有助于客户服务中心实时解决冲突。<br /> 有关详细信息，请参阅详 <a href="../../administration/using/configuring-email-channel.md#archiving-emails">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-3}

#### 界面更新 {#interface-updates}

* 在顶部栏中，已删 **[!UICONTROL Timeline]** 除链接，并替换为指向的链接 **[!UICONTROL Programs & Campaigns]** 。

#### 电子邮件和SMS消息 {#emails-and-sms-messages}

* 修复了传送状态显示错误颜色 **[!UICONTROL Retry in progress]** 的问题。 颜色是灰色而不是蓝色。

#### 工作流 {#workflows-3}

* 修复了将操作更改为在活动中执行时发生的问 **[!UICONTROL Transfer file]** 题。

#### 报告 {#reports-3}

* 已 **[!UICONTROL Spam]** 更改 **[!UICONTROL Spam rate]** 了计算和指示符。
* 改进 **[!UICONTROL Bounce]** 了指标，以获得更准确的结果。

#### 推送通知 {#push-notifications-2}

* 修复了导致您无法在个人资料的营销历史记录中单击推送事件的问题。
* 工作流中推送通知的使用已得到改进。

## 17.4版- 2017年4月 {#release-17-4---april-2017}

### 新功能 {#new-capabilities-4}

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 说明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 借助Creative SDK增强的图像编辑功能<br /> </td> 
   <td> 现在，您可以访问由Creative SDK提供支持的一整套功能，在编辑电子邮件或登录页面时直接在内容编辑器中增强您的图像。<br /> 此功能不需要获取其他Creative cloud解决方案。<br /> 有关详细信息，请参阅详 <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交易推送通知<br /> </td> 
   <td> 移动应用程序渠道已添加到Adobe Campaign的交易消息传递功能中。 交易消息现在支持三个渠道：电子邮件、短信和推送通知。<br /> 有关详细信息，请参阅详 <a href="../../channels/using/transactional-push-notifications.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 循环推送通知<br /> </td> 
   <td> 您现在可以在工作流中配置循环推送通知。 在客户期望定期更新（如每周提醒以查看新内容或促销）的情况下，您可以使用循环推送通知。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/push-notification-delivery.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Amazon Simple Storage Service(S3)连接器<br /> </td> 
   <td> Amazon Simple Storage Service(S3)连接器现在可用于将数据导入或导出到Adobe Campaign。 可以在工作流活动中设置它。 配置在外部帐户中完成。<br /> 有关详细信息，请参阅详 <a href="../../administration/using/external-accounts.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver实时集成<br /> </td> 
   <td> Adobe Campaign与Dreamweaver之间的集成现已实现。 它现在可与Dreamweaver的最新正式发布版本(17.0.2)配合使用。<br /> 这需要从以下位置安装Adobe Campaign集成扩展：http://adobe.ly/acdw_addon <a href="http://adobe.ly/acdw_addon">有关详细信息，请参阅此</a><br /> 视频 <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html"></a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-4}

#### 平台 {#platform-2}

* 修复了内存消耗问题。

#### 电子邮件和SMS消息 {#emails-and-sms-messages-1}

* 修复了在预览消息时内容无法与最新更改正确同步的问题。
* 修复了阻止创建或删除MX或域电子邮件处理规则的问题。
* 修复了可能阻止您发送具有多个别名的电子邮件的问题。
* 修复了阻止陷阱交付日志显示在交付的发送日志中的问题。
* 修复了在显示内容中没有URL的分发的跟踪URL时导致错误的问题。
* 修复了在发送的消息中无法正确应用图像的大小属性的问题。

#### 交易消息 {#transactional-messages-1}

* rtEventHistoId字段不再作为事务消息模板中的个性化字段公开。

#### 登陆页面 {#landing-pages}

* 我们优化了登录页 **[!UICONTROL by email]** 面中使用的过滤器，以协调新订阅者与数据库配置文件。
* 修复了在表单配置中使用布尔字段时显示自由文本输入而非复选框的问题。
* 修复了导致无法生成登录页面缩略图的问题。

#### 工作流 {#workflows-4}

* 修复了编辑活动时(仅 **[!UICONTROL End]** 限Safari) **[!UICONTROL External Signal]** 的显示错误。
* 改进了编辑包含错误受众的活 **[!UICONTROL Read Audience]** 动时显示的错误消息。
* 修复了在执行订阅活动时可能导致SQL错误的问题。

#### 集成 {#integrations-2}

* 兴趣点数据：修复了在计算位置订阅者时发生的错误。

#### 受众和查询 {#audiences-and-queries}

* 修复了阻止在查询编辑器中对集合使用总和和和平均聚合的问题。
* 修复了在更改筛选器资源后可能阻止重新加载查询编辑器的问题。

#### 报告 {#reports-4}

* 修复了在表中选择多行时无法正确计算开放率度量的问题。
* 修复了仅将度量显示为整数值的错误。 现在可以使用小数显示度量。

#### 推送通知 {#push-notifications-3}

* 修复了在创建链接到MCPNS上创建失败的移动应用程序的Android应用程序时，不显示错误消息的问题。
* 修复了允许用户向无提示通知添加声音的问题。

## 17.2版- 2017年3月 {#release-17-2---march-2017}

### 新功能 {#new-capabilities-5}

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
   <td> 动态报告提供新一代完全可自定义的实时业务报告。 此功能基于可视的动态枢纽表和图形，允许您拖放变量和维度以分析营销活动的效率和有效性。 动态报表还允许您从头开始创建自己的业务报表并保存以供以后使用。<br /> 有关详细信息，请参阅详 <a href="../../reporting/using/about-dynamic-reports.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver集成（实验室）<br /> </td> 
   <td> 通过Adobe Campaign和Dreamweaver的集成，您现在可以通过Adobe解决方案创建电子邮件营销活动。<br /> 您可以在Dreamweaver中编辑Adobe Campaign电子邮件，并使内容在两个解决方案之间无缝同步。<br /> 对于初始版本，该集成可作为“实验室”功能提供，并且仅与Dreamweaver预发行版测试版一起使用。 如果要激活它，请联系AC-DW-integration@adobe.com。<br /> 有关详细信息，请参阅此视 <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">频</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 手动发送时间优化<br /> </td> 
   <td> 您现在可以手动定义每个收件人的自定义发送时间——在传送级别或使用工作流。 <br /> 有两个新选项可用： <br /> 
    <ul> 
     <li> 所有收件人都会收到邮件，并考虑到其时区。 </li> 
     <li> 每个接收者在由公式定义的计算日期和时间接收消息。 </li> 
    </ul>  有关详细信息，请参阅详 <a href="../../sending/using/optimizing-the-sending-time.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送通知新功能<br /> </td> 
   <td> 推送通知渠道已通过若干新功能得到增强：<br /> 
    <ul> 
     <li> 新的创作界面 </li> 
     <li> 静默通知 </li> 
     <li> 交互式推送 </li> 
     <li> 丰富内容支持 </li> 
     <li> 有效负荷大小计算器 </li> 
    </ul>  有关详细信息，请参阅详 <a href="../../channels/using/about-push-notifications.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流：新信号活动<br /> </td> 
   <td> 使用新的Signal活动从另一个工作流触发 <span class="uicontrol">工作流</span> 。<br /> 现在，您可以从一个工作流程开始另一个工作流程，从而支持更复杂的客户旅程。 您可以更好地监控客户旅程，并在出现问题时做出反应。<br /> 已更新多个工作流活动：<br /> 
    <ul> 
     <li> <span class="uicontrol">结束活动</span> :新选项卡允许您指定在执行此活动后要触发的工作流。 </li> 
     <li> <span class="uicontrol">更新数据</span> :使用新的空出站过渡来添加一个触 <strong>发另一个工作流的</strong> “结束”活动。 空的出站过渡不会携带任何数据，也不会占用系统上不必要的空间 </li> 
    </ul>  有关详细信息，请参阅详 <a href="../../automating/using/external-signal.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流：新阅读受众活动<br /> </td> 
   <td> 从现有受众开始定位过程，您可以在一个活动中轻松选择和优化这些受众。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/read-audience.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 兴趣点数据<br /> </td> 
   <td> 兴趣点数据将Adobe Campaign与Adobe Analytics for Mobile集成在一起。 当用户打开品牌的应用程序时，品牌可以从用 <strong>户的移动位置(称为兴趣点</strong> )收集数据。 这使品牌能够利用Adobe Campaign工作流程，以便根据用户的位置发送个性化消息。 此渠道利用移动核心服务的SDK。<br /> 请注意，使用此功能需要Analytics for Mobile（一种付费解决方案）。<br /> 有关详细信息，请参阅详 <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> REST API<br /> </td> 
   <td> API中现在提供任何级别上链接到配置文件或服务资源的资源。<br /> 有关详细信息，请参阅详 <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-5}

#### 常规 {#general-1}

* 现在，在导出交付日志时可以添加配置文件数据。

#### 电子邮件和SMS消息 {#emails-and-sms-messages-2}

* 修复了即使在取消选 **[!UICONTROL Request confirmation before sending messages]** 中选项并保存交付后仍保持选中状态的问题。
* 修复了可能阻止取消发布交易电子邮件的问题。
* 修复了在预览分发之前，内容无法与最新更改正确同步的问题。

#### 登陆页面 {#landing-pages-1}

* 修复了用户在登录页面内容中单击时无法编辑的错误。

#### 工作流 {#workflows-5}

* 修复了可能无法读取活动拒绝转换内容的问 **[!UICONTROL Load file]** 题。
* 修复了在配置活动时无法正确考虑交换列的问 **[!UICONTROL Load file]** 题。

## 17.1版- 2017年1月 {#release-17-1---january-2017}

### 新功能 {#new-capabilities-6}

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 说明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 外部报告的日志导出<br /> </td> 
   <td> 导出交付和跟踪日志等日志，以便在首选报告或BI工具中处理它们。 您可以使用简单的工作流和增量式查询来自动定期导出新日志。<br /> 除了资源选取器中的日志资源可用性外，还对增量查询和提取文件 <a href="../../automating/using/incremental-query.md">活动</a><a href="../../automating/using/extract-file.md">进行了增强</a> :<br /> 
    <ul> 
     <li> <span class="uicontrol">增量查询</span> 现在允许您使用日期字段检索新数据或更新的数据。 以前，即使自上次执行以来更新了先前执行的所有结果，也会自动排除这些结果。 </li> 
     <li> <span class="uicontrol">提取文件</span> 现在可以导出枚举值的标签，而不是ID。 </li> 
    </ul> 管理员可以访问所有地理和组织单位，并使用这些活动。<br /> 有关导出日志的详细信息，请参阅详细 <a href="../../automating/using/exporting-logs.md">文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交易消息的营销功能<br /> </td> 
   <td> 营销人员现在可以根据客户营销档案发送交易消息。 这允许他们：<br /> 
    <ul> 
     <li> 应用营销类型学规则，如列入黑名单 <span class="uicontrol">的地址</span> 。 </li> 
     <li> 在消息中包含取消订阅链接。 </li> 
     <li> 将事务性消息添加到全局交付报告。 </li> 
     <li> 在客户旅程中利用交易信息。 </li> 
    </ul>  有关详细信息，请参阅详 <a href="../../channels/using/profile-transactional-messages.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional Messaging API<br /> </td> 
   <td> Transactional Messaging API现已通过 <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io提供</a>，从而更便于使用和监控：<br /> 
    <ul> 
     <li> 您可以从adobe.io平台报告和监视功能中受益。 </li> 
     <li> 身份验证现在使用基于adobe.io令牌的身份验证而不是IP白名单来执行，从而简化了安全过程。 </li> 
     <li> 所有API现在都集成在一个平台上，因此，如果您已经支持Profile和Services API，则为集成添加交易消息功能变得前所未有的简单。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-6}

#### 常规 {#general-2}

* 这些 **[!UICONTROL Access authorization]** 选项已返回到登录页面属性。
* 修复了可能导致旧图像而不是正确图像呈现的问题。 如果源图像在分发或登录页面的内容定义中已更新，则会发生这种情况。
* 修复了阻止用户编辑现有SFTP外部帐户中某些字段的问题。
* 修复了多个UI问题。 例如，用户现在可以编辑配置文件属性并保存修改，而不会遇到UI问题。

#### 电子邮件和SMS消息 {#emails-and-sms-messages-3}

* 修复了与包含HTML内容的分发模板相关的问题

#### 推送通知 {#push-notifications-4}

* 修复了可能阻止从应用程序回传到Adobe Campaign服务器的问题。
* 修复了可能已阻止并 **[!UICONTROL Play a sound]** 需要 **[!UICONTROL Custom fields]** 考虑Android的问题。
* 修复了可能导致向用于Emoji的Unicode字符添加额外转义字符的问题。
* 当订阅者的注册令牌被列入黑名单时，Adobe Campaign中的订阅者列表中的相应状态现在会立即更新。

#### 工作流 {#workflows-6}

* 修复了可能阻止预览事件资源（例如rtEvent）上的查询的问题。
* 现在，可以在活动的出站过 **[!UICONTROL Load file]** 渡中检索由活动生成的拒绝文件，并在下一个活动中进行处理。 例如，使用通过SFTP服务器上传拒绝文件 **[!UICONTROL Transfer file]** 。
* 修复了在的选项卡中选择时，用户可能无法限制区段 **[!UICONTROL Temporary resource]** 人口的 **[!UICONTROL General]** 问题 **[!UICONTROL Segmentation]** 。
* **[!UICONTROL Scheduler]** 活动不能再设置为每10分钟多触发一次工作流。
* 修复了可能妨碍在活动 **[!UICONTROL Use common columns]** 中正常工作的问 **[!UICONTROL Union]** 题。

#### 集成 {#integrations-3}

* 修复了在Adobe Campaign中部署活动触发器时可能导致错误的问题。 当“30天后返回的可能性”元数据添加到Adobe Marketing cloud中的“放弃”触发器时，会发生此错误。
* 修复了在从People核心服务导入受众时，可能导致技术工作流清除Target维字段的问题。 后续查询无法检索导入的受众。
* 修复了选中选项时可 **[!UICONTROL Save audience]** 能导致工作流活动失败的 **[!UICONTROL Share in Adobe Marketing Cloud]** 问题。

