---
title: 发行说明 2017
description: 本页列表了所有2017版Adobe Campaign标准版。
page-status-flag: never-activated
uuid: d73f8186-e309-441b-969d-71d0a1c33cf4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 1cfd9b3b-9b3e-4587-9c46-b6fb02131654
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c21a6fb4916430deb76d5d01b379453e398f6f25

---


# 发行说明 2017{#release-notes}

是否正在寻找特定的2017版Adobe Campaign标准？

每个版本都提供新功能和修补程序。 单击某个版本可视图其内容。

视图最新 [的Adobe Campaign](../../rn/using/documentation-updates.md) Standard文档更新。 如果要寻找较新的版本，请查阅此 [页](../../rn/using/release-notes.md)。

## 版本17.10 - 2017年10月 {#release-17-10---october-2017}

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
   <td> 疲劳管理允许您创建疲劳规则以管理与用户档案的过度沟通。 疲劳规则很容易构建，但极其灵活，包括跨多个渠道(包括事务性消息)计数消息、仅计数特定投放或将规则应用于特定用户档案等功能。<br /> 有关详细信息，请参阅详 <a href="../../sending/using/fatigue-rules.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 内容创建：从URL导入<br /> </td> 
   <td> 通过URL导入，您可以快速从网站检索您的创意内容，为任何投放构建电子邮件。 此外，您还可以通过使第三方直接通过URL共享内容来简化您的创作过程。 导入的内容可以灵活地用作单个投放的一部分或在模板级别使用，以确保所有相关活动(无论是基于工作流还是事务性消息)的品牌一致性，并包括A/B或多变量测试。 从URL导入会自动转换和跟踪所有链接，以通过动态报告监控电子邮件性能。<br /> 有关详细信息，请参阅详 <a href="../../designing/using/using-existing-content.md#importing-content-from-a-url">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* 修复了可能导致无法正确解压大文件的问题。
* 品牌管理的安全性已得到改进。 现在，Adobe技术管理员可以保留修改品牌名称和发件人地址。
* 为提高安全性，用户生成的内容(图像、镜像页面、登陆页等)不再由adobe.com域提供。 现在，您必须使用自己的域来通过使用品牌来处理这些资源。
* 修复了显示和筛选营销活动时的界面问题。
* 修复了阻止订阅日期字段用POST Rest API调用进行更新的问题。

_电子邮件、短信和直邮_

* 修复了一个问题，该问题可能会阻止将消息中的列表类型受众定位为目标，导致准备失败。
* 多语言电子邮件投放功能中新增了缺失的语言。
* 内容缩略图(显示在投放仪表板上)现在会在用户修改内容并保存时自动更新。
* 修复了阻止打开投放的时区相关问题。

_推送通知_

* 配置推送通知渠道时，iOS的推送提供者平台应为apns **** ,Android **gcm**&#x200B;的推送提供者平台。
* 修复了阻止iOS移动应用程序添加到Adobe Campaign界面中的错误。
* 推送通知现在在支持GCM和FCM的Android移动应用程序上都受支持。
* 修复了复制推送通知模板时无法保存内容的错误。
* 现在，通过协调移动应用程序用户的数据，可以从Adobe Campaign数据库创建或更新用户档案。
* Adobe Campaign现在优先处理事务推送通知而不是标准推送通知。

_报告_

* 修复了阻止热点单击百分比显示在电子邮件内容中的问题。
* 修复了黑名单指标的问题，该指标被计为硬弹跳而非弹跳。
* 修复了导致在摘要数据中显示负计数的问题。
* 修复了在错误的年龄段中计算用户档案数的问题。
* 软弹跳和硬弹跳计算公式已更改。

_工作流_

* 修复了活动中的一 **[!UICONTROL Load file]** 个问题，该问题可能导致在手动添加和删除活动中的列后出现错误。
* 技术 **[!UICONTROL deliverabilityUpdate]** 工作流程现在计划在服务器时间凌晨2点运行。
* 修复了允许在不具有导出角色的情况下执行列表导出的安全问题。
* 修复了活动的问题。 **[!UICONTROL Reconciliation]**
* 修复了活动中使用通配符的问 **[!UICONTROL File Transfer]** 题。

_用户档案和受众_

* 修复了在某些特定情况下可能无法正确考虑查询条件导致错误结果的问题。
* 修复了在已准备但从未发送和过期的消息中定位用户档案时，可能会阻止访问它们的问题。

_集成_

* 修复了一个问题，该问题可能会阻止为触发器创建的某些数据源正确显示和被选择。

_自定义资源_

* 修复了在列表屏幕中出现的一个问题，该问题导致自定义资源行可能在没有任何数据的情况下显示。
* 修复了阻止具有“False”值的布尔类型字段在自定义资源中显示的问题。

## 17.9版- 2017年9月 {#release-17-9---september-2017}

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
   <td> 推出了18个全新的响应式模板，它们采用两个美丽的主题- Astro和Feather设计。 这些可自定义的模板与行业无关，并且随时可用。 模板包含多种用例内容，可让电子邮件营销活动比以往更快、更高效、更美观地设计和交付。<br /> 有关详细信息，请参阅详 <a href="../../designing/using/using-reusable-content.md#content-templates">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 动态报告用户档案数据<br /> </td> 
   <td> 动态报告提供完全可自定义的实时业务报告。 在此版本中，动态报告的强大增强功能增加了对用户档案数据的访问，使得除了功能性电子邮件活动数据（如打开和点击）之外，还能够按用户档案维度（如性别、城市、邮政编码和年龄）进行人口统计分析。 借助相同的易于使用的拖放界面，确定电子邮件活动对于最重要的客户细分的执行方式比以往更容易。<br /> 有关详细信息，请参阅详 <a href="../../reporting/using/about-dynamic-reports.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 具有来源和日期的成批订阅<br /> </td> 
   <td> 通过此批量订阅增强功能，您现在可以通过工作流中的订阅活动直接在Adobe Campaign标准数据库中存储订阅服务信息(来源和日期)。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/subscription-services.md">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* 一些客户需要能够利用来自Adobe Campaign标准版的ID，因为他们没有管理唯一的密钥来识别自己的记录。 此ID(**ACS ID**)可在更新数据时导出并用作合并关键项。 有关详细信息，请参阅详 [细文档](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)。
* FTP协议已弃用。 您现在应改用SFTP。 为了不阻止现有实施，FTP上的现有配置仍将像以前一样工作，但新活动的选项将不显示。

_电子邮件、短信和直邮_

* 现在，可以创建新的警报标准，以便在投放警报通知中使用它们。 有关详细信息，请参阅详 [细文档](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion)。
* 投放警报通知具有新设计，投放警报仪表板用户体验已得到改进。
* 现在，当路由外部帐户被禁用时，受影响的投放（电子邮件、SMS和推送）中会显示一条警告消息，并且 **** 预览按钮隐藏在这些投放中。
* 修复了在主题行中启用动态文本时，电子邮件内容的A/B测试预览出错的问题。

_事务性消息_

* 现在可以定义何时发送后续消息，例如，在发送事务性消息后3天。 有关详细信息，请参阅详 [细文档](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)。
* 现在，可以定义应发送链接到事务性消息的事件的日期。
* 修复了在删除链接到已接收和已处理用户档案的事件后，执行包含后续消息的工作流时导致SQL错误的问题。
* 修复了无法删除链接到用户档案的事件的错误。
* 修复了一个问题，该问题可能会阻止跟踪链接的重定向工作。
* 修复了阻止您对电子邮件或SMS消息中的特定链接进行跟踪的问题。

_报告_

* 热点 **单击** (Hot clicks)报告已得到改进。 此外，现在可以根据在投放中定义的每个条件内容显示热点单击，并可以显示重复投放或事务性消息的每次执行的热点单击。 有关详细信息，请参阅详 [细文档](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion)。
* 修复了导致隔离度量无法检索正确数据的问题。
* 新的预设时间范围已添加到日历构件。
* 动 [态报告指标](../../reporting/using/indicator-calculation.md) , [](../../sending/using/confirming-the-send.md) 活动的KPI(显示在已发送消息的仪表板上)已保持一致，以便更加一致。
* 修复了可能导致流水线在debian 7上崩溃的问题。

_工作流_

* 修复了导入的文件保留无法正常工作的问题。

_集成_

* eVar和事件现在支持Analytics和活动集成。
* 发送包含放弃购物车内容的电子邮件时，从购物车中删除的元素的有效负荷参数现在是可选的。

_用户档案和受众_

* Adobe Campaign现在提供一个报告，其中显示活动用户档案的数量。 此报告仅提供信息，对计费没有直接影响。 有关详细信息，请参阅详 [细文档](../../audiences/using/active-profiles.md)。
* 修复了在使用用户档案和服务API时阻止用户档案订阅服务的问题。

## 17.7版- 2017年7月 {#release-17-7---july-2017}

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
   <td> 根据自动细分的客户首选语言，通过单一投放定义并执行多语言电子邮件和短信投放。 报告每个投放的性能，包括语言和各个级别。<br /> 随着内容在国内外的发展，越来越多的公司面临以多种语言提供内容的挑战。 因此，简化本地化消息投放是跨国公司有效客户沟通策略的关键部分；公司语国家／地区；以及希望在语言级别进一步个性化其内容的公司，无论客户位于何处。 有关详细信息，请参阅详 <a href="../../channels/using/creating-a-multilingual-email.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Campaign通知<br /> </td> 
   <td> 直接在Adobe Campaign标准中接收有关重要系统活动的通知。 例如，您将收到持续投放进度通知或当工作流出错时通知。<br /> 实时通知可让相关利益相关方及时获得通知，并使用户能够立即直接在应用程序内对活动通知采取行动。 团队的成果是先进的敏捷性、效率和更顺畅的活动执行。 有关详细信息，请参阅详 <a href="../../administration/using/sending-internal-notifications.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放警报<br /> </td> 
   <td> 除了直接在Adobe Campaign标准中查看通知外，Adobe Campaign现在还提供电子邮件警报系统，以向用户或重要系统活动的外部利益相关方发送电子邮件警报。 创建、管理和接收可自定义的警报和仪表板，以跟踪投放成功或失败。<br /> Adobe Campaign投放警报通过电子邮件和仪表板让所有相关Adobe Campaign用户在一个公司中自动获知投放执行状态，从而提高了效率。 有关详细信息，请参阅详 <a href="../../sending/using/receiving-alerts-when-failures-happen.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 数据源中的加密Declared ID<br /> </td> 
   <td> 使用加密的联系信息（电子邮件地址或电话号码）作为Declared ID，发送电子邮件和SMS触发器，无需活动中的现有用户档案。 由于加密的Declared ID可以通过Adobe Campaign标准进行解码，因此，从包含先前未知联系人的其他Experience Cloud解决方案接收受众时，活动现在可以创建新的可销售用户档案。<br /> 通过电子邮件和短信实时目标客户和未知潜在客户，分别提高现有客户群的忠诚度和赢取新客户。 在潜在客户进行身份验证并利用Adobe Campaign中的洞察后，充分利用第一方Cookie数据(来自Adobe受众管理器*)。 <br /> *需要Adobe受众经理。 有关详细信息，请参阅详 <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 从活动到分析的KPI共享<br /> </td> 
   <td> 与Adobe Analytics共享活动数据，通过转化、统一点击前和点击后行为，衡量来自活动和其他营销和广告工作的电子邮件营销指标。<br /> 在Analytics中直接跟踪整体绩效并发现与外部项目的协同效应。 将您从这一整合视图中学到的知识应用到您的活动中；最终改进开放、点进和转化率，提高收入和整体活动表现。 <br /> 需要Adobe Analytics。 有关详细信息，请参阅详 <a href="../../integrating/using/about-campaign-analytics-integration.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 直邮渠道-返回发件人<br /> </td> 
   <td> 现在支持与直接邮件提供商进行包含“返回给发送者”信息的平面文件交换。 直邮渠道的这一增强功能允许将相应的邮政地址排除在将来的通信之外。<br /> 这使营销人员能够收到错误地址的通知，并通过其他渠道与客户联系，或鼓励他更新其邮政地址。 这还可以减少营销人员避免将邮件发送到错误地址时浪费的营销资金。 <br /> “直邮”可作为附加渠道提供。 有关详细信息，请参阅详 <a href="../../channels/using/return-to-sender.md">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_常规_

* 修复了允许任何用户导出列表的问题。 现在，仅允许具有该角 **[!UICONTROL Export]** 色的用户访问。

_电子邮件、短信和直邮_

* 修复了updateDeliveryExecInfo **(更新DeliveryExecInfo** )工作流程中的一个问题，该问题将SMS投放的“ **To deliver** indicator”（传送指示符）设置为0。
* 在投放模板 **属性的** “高级参数”中 **** ,“路由”下拉列表现在仅显示与模板消息类型对应的外部帐户。 例如，电子邮件投放模板仅显示电子邮件外部帐户。
* 修复了为测试电子邮件格式定 **[!UICONTROL Text]** 义的首选用户档案的问题。
* 修复了在投放的计划定义屏幕中选择默认时区时导致Javascript错误的问题。
* 修复了阻止陷阱显示在发送日志中的问题。
* 在投放创建向导的模板选择屏幕中，现在默认情况下隐藏后续和A/B测试模板。 有关详细信息，请参阅详 [细文档](../../channels/using/creating-an-email.md)。
* 修复了允许任何用户发送投放的问题。 现在，仅允许具有该角 **[!UICONTROL Start deliveries]** 色的用户访问。 有关详细信息，请参阅详 [细文档](../../sending/using/confirming-the-send.md)。

_推送通知_

* 修复了活动跟踪端 **** 点URL中阻止报告的问题。
* 修复了在Android设备上无法显示推送通知标题的问题。
* 修复了当推送通知仅包含标题（消息正文中没有标题）时，在iOS设备上无法显示推送通知的问题。
* 修复了强制跟踪投放中的媒体附件URL的问题，该问题导致视频和图片无法嵌入投放中。 现在，对于推送通知，默认情况下将取消激活媒体附件URL类型的URL跟踪。

_报告_

* 更正了图表和表之间显示值不同的问题。
* 更正了将推送通知值显示为电子邮件值的问题。
* 修复了在投放之外创建活动时，将值显示为未知的问题。
* 更正了将SMS报告数据显示为移动应用程序数据的问题。

_工作流_

* 您现在可以过滤工作流日志（时间段和文本搜索）。 有关详细信息，请参阅详 [细文档](../../automating/using/executing-a-workflow.md#monitoring)。
* 现在，工作流投放中有一个选项可用于在发送之前取消激活确认。
* 修复了在循环过渡的创建向导中无法设置出站投放的问题。
* 修复了在基于具有大量值的查询的自定义资源字段使用工作流活动时发生的问题

## 17.5版- 2017年5月 {#release-17-5---may-2017}

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
   <td> 借助Adobe Campaign标准版的第一个脱机渠道“直邮”，突破数字障碍并与现实世界互联。 此功能允许您将直邮提供商所需的文件个性化并生成为跨渠道活动的一部分。 利用直邮，通过引人入胜的触觉接触点将客户引导到您的应用程序、网站或商店，重新吸引客户或增强客户体验。<br /> 有关详细信息，请参阅详 <a href="../../channels/using/about-direct-mail.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 密件抄送<br /> </td> 
   <td> 密件抄送电子邮件可保存发送给各个收件人的唯一电子邮件，因此品牌可以存档这些邮件。 通过向所有电子邮件添加密送电子邮件地址，Adobe Campaign标准版客户可以使用此功能保留每封电子邮件的精确副本。 这是金融服务业的常见法律要求，有助于客户服务中心实时解决冲突。<br /> 有关详细信息，请参阅详 <a href="../../sending/using/archiving.md">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_界面更新_

* 在顶部栏中，已删 **[!UICONTROL Timeline]** 除链接，并替换为指向的链接 **[!UICONTROL Programs & Campaigns]** 。

_电子邮件和SMS消息_

* 修复了投放状态显示错误颜色的问 **[!UICONTROL Retry in progress]** 题。 颜色是灰色而不是蓝色。

_工作流_

* 修复了将操作更改为在活动中执行时发生的问 **[!UICONTROL Transfer file]** 题。

_报告_

* 已 **[!UICONTROL Spam]** 更改 **[!UICONTROL Spam rate]** 了计算和指示符。
* 改进 **[!UICONTROL Bounce]** 了指标，以获得更准确的结果。

_推送通知_

* 修复了阻止您单击用户档案事件中的推送营销历史的问题。
* 改进了在工作流中使用推送通知。

## 17.4版- 2017年4月 {#release-17-4---april-2017}

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
   <td> 借助Creative SDK增强的图像编辑功能<br /> </td> 
   <td> 您现在可以访问由Creative SDK提供支持的一整套功能，在编辑电子邮件或登陆页时直接在内容编辑器中增强图像。<br /> 此功能不需要获取其他Creative Cloud解决方案。<br /> 有关详细信息，请参阅详 <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交易推送通知<br /> </td> 
   <td> 移动应用程序渠道已经添加到Adobe Campaign的交易消息传递功能中。 现在支持三个渠道事务性消息:电子邮件、短信和推送通知。<br /> 有关详细信息，请参阅详 <a href="../../channels/using/transactional-push-notifications.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 循环推送通知<br /> </td> 
   <td> 您现在可以在工作流中配置循环推送通知。 在客户期望定期更新（如每周提醒以查看新内容或促销）的情况下，您可以使用循环推送通知。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/push-notification-delivery.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Amazon Simple存储服务(S3)连接器<br /> </td> 
   <td> Amazon Simple存储服务(S3)连接器现在可用于将数据导入或导出到Adobe Campaign。 可以在工作流活动中设置它。 配置在外部帐户中完成。<br /> 有关详细信息，请参阅详 <a href="../../administration/using/external-accounts.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver实时集成<br /> </td> 
   <td> Adobe Campaign与Dreamweaver之间的集成现已实现。 它现在可与Dreamweaver的最新正式发布版本(17.0.2)配合使用。<br /> 这需要从此处安装Adobe Campaign集成扩展：https://adobe.ly/acdw_addon <a href="https://adobe.ly/acdw_addon">有关详细信息，请参阅此</a><br /> 视频 <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html"></a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* 修复了内存消耗问题。

_电子邮件和SMS消息_

* 修复了在预览消息时内容无法与最新更改正确同步的问题。
* 修复了阻止创建或删除MX或域电子邮件处理规则的问题。
* 修复了可能阻止您发送具有多个别名的电子邮件的问题。
* 修复了阻止陷印投放日志显示在投放发送日志中的问题。
* 修复了在显示内容中没有URL的投放的跟踪URL时导致错误的问题。
* 修复了在发送的消息中无法正确应用图像的大小属性的问题。

_事务性消息_

* rtEventHistoId字段不再作为事务性消息模板中的个性化字段显示。

_登陆页面_

* 我们优化了登陆页中 **[!UICONTROL by email]** 使用的过滤器，以协调新订阅者与数据库用户档案。
* 修复了在表单配置中使用布尔字段时显示自由文本输入而非复选框的问题。
* 修复了无法生成登陆页缩略图的问题。

_工作流_

* 修复了编辑或活动(仅 **[!UICONTROL End]** 在Safari上) **[!UICONTROL External Signal]** 时的显示错误。
* 改进了编辑包含错误活动的 **[!UICONTROL Read Audience]** 受众时显示的错误消息。
* 修复了在执行订阅活动时可能导致SQL错误的问题。

_集成_

* 兴趣点数据：修复了在计算位置订阅者时发生的错误。

_受众和查询_

* 修复了阻止在聚合编辑器中对集合使用和和平均查询的问题。
* 修复了在更改查询器资源后，可能会阻止重新加载过滤器编辑器的问题。

_报告_

* 修复了在表中选择多行时无法正确计算开放率度量的问题。
* 修复了仅将度量显示为整数值的错误。 现在可以使用小数显示度量。

_推送通知_

* 修复了在创建链接到在MCPNS上创建失败的移动应用程序的Android应用程序时，不显示错误消息的问题。
* 修复了允许用户向无提示通知添加声音的问题。

## 17.2版- 2017年3月 {#release-17-2---march-2017}

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
   <td> 动态报告提供新一代完全可自定义的实时业务报表。 此功能基于可视的动态透视表和图形，允许您拖放变量和尺寸以分析营销活动的效率和有效性。 动态报告还允许您从头开始创建自己的业务报表并保存以供以后使用。<br /> 有关详细信息，请参阅详 <a href="../../reporting/using/about-dynamic-reports.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver集成（实验室）<br /> </td> 
   <td> 通过Adobe Campaign和Dreamweaver集成，您现在可以通过Adobe解决方案创建电子邮件活动。<br /> 您可以在Dreamweaver中编辑Adobe Campaign电子邮件，并使内容在两个解决方案之间无缝同步。<br /> 对于初始版本，该集成可作为“实验室”功能提供，并且仅与Dreamweaver预发行版测试版一起使用。 如果要激活它，请联系AC-DW-integration@adobe.com。<br /> 有关详细信息，请参阅此视 <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">频</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 手动发送时间优化<br /> </td> 
   <td> 您现在可以在收件人级别或使用工作流手动定义每个投放的自定义发送时间。 <br /> 有两个新选项可用： <br /> 
    <ul> 
     <li> 所有收件人都会收到消息，并考虑其时区。 </li> 
     <li> 每个收件人在由公式定义的计算日期和时间接收消息。 </li> 
    </ul> 有关详细信息，请参阅详 <a href="../../sending/using/optimizing-the-sending-time.md">细文档</a>。<br /> </td> 
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
    </ul> 有关详细信息，请参阅详 <a href="../../channels/using/about-push-notifications.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流:新信号活动<br /> </td> 
   <td> 使用新的Signal活动从另一个工作流触发 <span class="uicontrol">工作流</span> 。<br /> 利用从一个工作流到另一个工作流的开始能力，您现在可以支持更复杂的客户旅程。 您可以更好地监控客户旅程，并在出现问题时做出反应。<br /> 已更新多个工作流活动:<br /> 
    <ul> 
     <li> <span class="uicontrol">结束活动</span> :新选项卡允许您指定要在执行此活动后触发的工作流。 </li> 
     <li> <span class="uicontrol">更新数据</span> 活动:使用新的空出站过渡添加一个触 <strong>发另一个工作流的End</strong> 活动。 空的出站过渡不会携带任何数据，也不会占用系统上不必要的空间 </li> 
    </ul> 有关详细信息，请参阅详 <a href="../../automating/using/external-signal.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流:新阅读受众活动<br /> </td> 
   <td> 将定位过程与现有受众开始，您可以在一个活动中轻松选择和调整。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/read-audience.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 兴趣点数据<br /> </td> 
   <td> 兴趣点数据将Adobe Campaign与Adobe Analytics for Mobile集成在一起。 当用户打开品牌的应用程序时，品牌可以从用 <strong>户的移动位置(称为兴趣点</strong> )收集数据。 这使品牌能够利用Adobe Campaign工作流，以便根据用户的位置发送个性化消息。 此渠道利用移动核心服务的SDK。<br /> 请注意，使用此功能需要Analytics for Mobile（一种付费解决方案）。<br /> 有关详细信息，请参阅详 <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> REST API<br /> </td> 
   <td> API中现在提供与用户档案或服务资源链接的任何级别的资源。<br /> 有关详细信息，请参阅详 <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_常规_

* 现在，在导出用户档案时可以添加投放日志数据。

_电子邮件和SMS消息_

* 修复了即使取消选 **[!UICONTROL Request confirmation before sending messages]** 中并保存投放后仍然选中该选项的问题。
* 修复了可能阻止取消发布交易电子邮件的问题。
* 修复了在预览投放之前，内容无法与最新更改正确同步的问题。

_登陆页面_

* 修复了用户在单击登陆页内容时无法编辑的错误。

_工作流_

* 修复了可能无法阅读活动拒绝过渡内容的问 **[!UICONTROL Load file]** 题。
* 修复了在配置活动时无法正确考虑已交换列的问题。 **[!UICONTROL Load file]**

## 17.1版- 2017年1月 {#release-17-1---january-2017}

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
   <td> 为外部报告导出日志<br /> </td> 
   <td> 导出投放和跟踪日志等日志，以在您喜欢的报告或BI工具中处理它们。 您可以使用简单的工作流和增量查询自动定期导出新日志。<br /> 除了资源选取器中的日志资源可用性外，还对 <a href="../../automating/using/incremental-query.md">增量查询</a> 和 <a href="../../automating/using/extract-file.md">Extract文件活动进行了增强</a> :<br /> 
    <ul> 
     <li> <span class="uicontrol">增量查询</span> 现在允许您使用日期字段检索新数据或更新的数据。 以前，即使自上次执行以来更新了先前执行的所有结果，也会自动排除这些结果。 </li> 
     <li> <span class="uicontrol">提取文件</span> ，现在可以导出明细列表值的标签，而不是ID。 </li> 
    </ul> 这些活动对拥有所有地理和组织单位访问权限的管理员可用。<br /> 有关导出日志的详细信息，请参阅详细 <a href="../../automating/using/exporting-logs.md">文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 针对事务性消息的营销功能<br /> </td> 
   <td> 营销人员现在可以根据客户营销用户档案发送事务性消息。 这允许他们：<br /> 
    <ul> 
     <li> 应用营销类型规则，如 <span class="uicontrol">已列入黑名单地址</span> 。 </li> 
     <li> 在消息中包含退订链接。 </li> 
     <li> 将事务性消息添加到全球投放报告。 </li> 
     <li> 利用客户旅程中的事务性消息。 </li> 
    </ul> 有关详细信息，请参阅详 <a href="../../channels/using/profile-transactional-messages.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional Messaging API<br /> </td> 
   <td> Transactional Messaging API现已通过 <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io提供</a>，从而更便于使用和监控：<br /> 
    <ul> 
     <li> 您可以从adobe.io平台报告和监视功能中受益。 </li> 
     <li> 身份验证现在使用基于adobe.io令牌的身份验证而不是IP白名单来执行，从而简化了安全过程。 </li> 
     <li> 所有API现在都集成在一个平台上，因此，如果您已经支持用户档案和服务API，则为集成添加交易消息功能将变得前所未有的简单。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_常规_

* 选 **[!UICONTROL Access authorization]** 项已返回到登陆页属性。
* 修复了可能导致旧图像而不是正确图像呈现的问题。 如果源图像在投放或登陆页的内容定义中已更新，则会发生这种情况。
* 修复了阻止用户编辑现有SFTP外部帐户中的某些字段的问题。
* 修复了多个UI问题。 例如，用户现在可以编辑用户档案属性并保存修改，而不会遇到UI问题。

_电子邮件和SMS消息_

* 修复了与包含HTML内容的投放模板相关的问题

_推送通知_

* 修复了可能阻止从应用程序回传到Adobe Campaign服务器的问题。
* 修复了可能已阻止并 **[!UICONTROL Play a sound]** 需要 **[!UICONTROL Custom fields]** 考虑Android的问题。
* 修复了可能导致向用于Emoji的Unicode字符添加额外转义字符的问题。
* 当用户的注册令牌变得已列入黑名单时，相应的状态现在在Adobe Campaign的用户的列表中立即更新。

_工作流_

* 修复了可能阻止预览查询事件资源（例如rtEvent）的问题。
* 现在，可以在活动的出站过渡中检索由生成的拒绝文件，并在下一个活动中进行处理。 **[!UICONTROL Load file]** 例如，使用通过SFTP服务器上传拒绝文件 **[!UICONTROL Transfer file]** 。
* 修复了在的选项卡中选择时，用户可能无法限制区段 **[!UICONTROL Temporary resource]** 人口的 **[!UICONTROL General]** 问题 **[!UICONTROL Segmentation]** 。
* **[!UICONTROL Scheduler]** 活动不能再设置为每10分钟多触发一次工作流。
* 修复了可能导致活动无 **[!UICONTROL Use common columns]** 法正常工作的问 **[!UICONTROL Union]** 题。

_集成_

* 修复了在Adobe Campaign中部署事件触发器时可能导致错误的问题。 当“30天后返回的可能性”元数据添加到Adobe Marketing Cloud中的“放弃”触发器时，会发生此错误。
* 修复了从People核心服务导入目标时，技术工作流可能会清除受众维字段的问题。 后续查询无法检索导入的受众。
* 修复了选中该选项时可 **[!UICONTROL Save audience]** 能导致工作流活动失败 **[!UICONTROL Share in Adobe Marketing Cloud]** 的问题。

