---
title: 发行说明 2017
description: 本页列出了所有 2017 年版的 Adobe Campaign Standard。
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 73a1ec49-fcbc-406b-9590-1ad20da9e73b
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '4572'
ht-degree: 3%

---

# 发行说明 2017{#release-notes}

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
   <td> 疲劳管理允许您创建疲劳规则来管理与用户档案的过度通信。 疲劳规则易于构建，但极其灵活，具有多种功能，例如跨多个渠道对消息进行计数（包括事务型消息）、仅对特定投放进行计数或将规则应用于特定用户档案。<br /> 欲了解更多信息，请参见 <a href="../../sending/using/fatigue-rules.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 内容创建：从URL导入<br /> </td> 
   <td> 通过URL导入，您可以从网站中快速检索创意内容，为任何投放构建电子邮件。 此外，您还可以通过使第三方直接通过URL共享内容来简化您的创作过程。 导入的内容可以灵活地用作单个投放的一部分或在模板级别使用，以确保所有相关营销活动的品牌一致性（无论是基于工作流的消息还是事务型消息），并包括A/B或多变量测试。 从URL导入会自动转换和跟踪所有链接，以通过动态报告监控电子邮件性能。<br /> 欲了解更多信息，请参见 <a href="../../designing/using/using-existing-content.md">详细文档</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* 修复了可能导致无法正确解压缩大型压缩文件的问题。
* 品牌管理的安全性已得到改进。 现在，Adobe技术管理员可以修改品牌名称和发件人地址。
* 为了提高安全性，需要用户生成内容（图像、镜像页面、登陆页面等） adobe.com域无法再提供服务。 现在，必须使用自己的域通过品牌策略处理这些资源。
* 修复了显示和筛选营销活动时的界面问题。
* 修复了订阅日期字段无法通过POSTRest API调用进行更新的问题。

_电子邮件、短信消息和直邮_

* 修复了可能导致无法在消息中定位列表类型受众，从而导致准备失败的问题。
* 多语言电子邮件投放功能中添加了缺少的语言。
* 现在，当用户修改内容并保存时，投放仪表板上显示的内容缩略图将自动更新。
* 修复了导致投放无法打开的时区相关问题。

_推送通知_

* 配置推送通知渠道时，iOS的推送提供商平台应为 **apns** 适用于Android的和 **gcm**.
* 修复了导致无法在iOS界面中添加Adobe Campaign移动设备应用程序的错误。
* 现在，启用了GCM和FCM的Android移动应用程序都支持推送通知。
* 修复了在复制推送通知模板时阻止保存内容的错误。
* 现在，可以通过协调移动应用程序用户的数据，从Adobe Campaign数据库创建或更新用户档案。
* Adobe Campaign现在优先处理事务型推送通知，而不是标准推送通知。

_报告_

* 修复了导致热门点击百分比无法在电子邮件内容中显示的问题。
* 修复了阻止列表指标被计为硬退回而非退回的问题。
* 修复了导致摘要数据中显示负数的问题。
* 修复了在错误年龄段中计数用户档案的问题。
* 软弹跳和硬弹跳的计算公式都发生了变化。

_工作流_

* 修复了中的一个问题 **[!UICONTROL Load file]** 在活动中手动添加和删除列后可能导致错误的活动。
* 此 **[!UICONTROL deliverabilityUpdate]** 技术工作流现在计划在上午2点（服务器时间）运行。
* 修复了一个安全问题，该问题允许在不使用导出角色的情况下执行列表导出。
* 修复了的问题 **[!UICONTROL Reconciliation]** 活动。
* 修复了在中使用通配符的问题 **[!UICONTROL File Transfer]** 活动。

_用户档案和受众_

* 修复了在某些特定情况下可能导致查询条件无法正确考虑并导致错误结果的问题。
* 修复了在已准备但从未发送和过期的消息中定向用户档案时可能阻止访问用户档案的问题。

_集成_

* 修复了可能导致为触发器创建的某些数据源无法正确显示和选择的问题。

_自定义资源_

* 修复了在列表屏幕中发生的问题，该问题导致可以在没有任何数据的情况下显示自定义资源行。
* 修复了阻止在自定义资源中显示值为“False”的布尔类型字段的问题。

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
   <td> 向您介绍18个全新的响应式模板，这些模板采用两个精美的主题 — Astro和Feather设计。 这些可自定义的模板与行业无关，可立即使用。 模板包括各种用例的内容，让您的电子邮件营销活动比以往任何时候都更快、更高效和更美观地设计和投放。<br /> 欲了解更多信息，请参见 <a href="../../designing/using/using-reusable-content.md#content-templates">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 使用用户档案数据进行动态报告<br /> </td> 
   <td> 动态报告提供完全可自定义的实时业务报告。 在此版本中，对动态报告的强大增强功能增加了对用户档案数据的访问，从而除了功能电子邮件促销活动数据（如打开数和点击数）之外，还支持按用户档案维度（如性别、城市、邮政编码和年龄）进行人口统计分析。 通过同一个易于使用的拖放界面，可以比以往更容易地确定针对最重要的客户细分执行电子邮件促销活动的方式。<br /> 欲了解更多信息，请参见 <a href="../../reporting/using/about-dynamic-reports.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 具有起源和日期的批量订阅<br /> </td> 
   <td> 借助此批量订阅增强功能，您现在可以通过工作流中的订阅服务活动，将订阅信息（来源和日期）直接存储在Adobe Campaign Standard数据库中。<br /> 欲了解更多信息，请参见 <a href="../../automating/using/subscription-services.md">详细文档</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* 某些客户需要能够利用来自Adobe Campaign Standard的ID，因为他们不会管理唯一密钥来标识自己的记录。 此ID (**ACS ID**)可以导出，并在更新数据时用作协调密钥。 有关更多信息，请参阅[详细文档](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)。
* FTP协议已被弃用。 您现在应改用SFTP。 为了不阻止现有实施，FTP上的现有配置仍会像之前一样工作，但不会为新活动显示选项。

_电子邮件、短信消息和直邮_

* 现在，可以创建新的警报标准以在投放警报通知中使用它们。 有关更多信息，请参阅[详细文档](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion)。
* 投放警报通知具有新设计，投放警报仪表板用户体验得到改进。
* 现在，禁用路由外部帐户后，受影响的投放（电子邮件、短信和推送）和 **预览** 按钮在这些投放中处于隐藏状态。
* 修复了在主题行中启用动态文本时，导致电子邮件内容的A/B测试预览出现错误的问题。

_事务性消息_

* 现在可以定义何时发送跟进消息，例如，在发送事务型消息3天后。 有关更多信息，请参阅[详细文档](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)。
* 现在，可以定义从应发送链接到事件的事务型消息的日期。
* 修复了在删除链接到已接收和已处理事件的用户档案后执行包含跟进消息的工作流时导致SQL错误的问题。
* 修复了阻止删除链接到事件的用户档案的错误。
* 修复了可能导致重定向跟踪链接无法正常工作的问题。
* 修复了导致无法在电子邮件或短信消息中禁用某些链接跟踪的问题。

_报告_

* 此 **热门点击** 报告已得到改进。 此外，现在可以根据投放中定义的每个条件内容显示热门点击，并显示定期投放或事务消息每次执行的热门点击。 有关更多信息，请参阅[详细文档](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion)。
* 修复了阻止隔离量度检索正确数据的问题。
* 日历小部件中新增了预设时间范围。
* 此 [动态报告量度](../../reporting/using/indicator-calculation.md) 和 [营销活动的KPI](../../sending/using/confirming-the-send.md) （显示在已发送消息的仪表板上）已对齐，以实现更协调一致。
* 修复了可能导致管道在debian 7上崩溃的问题。

_工作流_

* 修复了可能导致导入的文件保留无法正常工作的问题。

_集成_

* 现在，Analytics与Campaign集成支持eVar和事件。
* 现在，在发送包含已放弃购物车内容的电子邮件时，对于从购物车中删除的元素，其有效负荷参数是可选的。

_用户档案和受众_

* Adobe Campaign现在提供一个报表，其中显示活动用户档案的数量。 此报告只提供信息，对账单没有直接影响。 有关更多信息，请参阅[详细文档](../../audiences/using/active-profiles.md)。
* 修复了在使用Profiles &amp; Services API时阻止用户档案订阅服务的问题。

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
   <td> 根据自动分段客户的首选语言，通过单一投放定义和执行多语言电子邮件和短信投放。 关于每次投放之绩效的报告，可以细分到语言和各个级别。<br /> 随着国内外企业的成长，越来越多的公司面临着以多种语言提供内容的挑战。 因此，对于跨国公司、使用多种语言的国家/地区的公司以及希望无论客户位于何处，都能在语言层面进一步个性化内容的公司而言，简化本地化的报文交付是有效客户沟通战略的关键部分。 欲了解更多信息，请参见 <a href="../../channels/using/creating-a-multilingual-email.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Campaign通知<br /> </td> 
   <td> 直接在Adobe Campaign Standard中接收有关重要系统活动的通知。 例如，当正在进行中的投放进度或工作流出错时，您会收到通知。<br /> 实时通知可随时告知相关利益相关者，并让用户能够立即直接从应用程序内对活动通知采取行动。 对于团队而言，其结果是提高了营销活动的灵活性、效率和平顺执行。 欲了解更多信息，请参见 <a href="../../administration/using/sending-internal-notifications.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放警报<br /> </td> 
   <td> 除了直接在Adobe Campaign Standard中查看通知之外，Adobe Campaign现在还提供了一个电子邮件警报系统，以触发向用户或外部利益相关者发送有关重要系统活动的电子邮件警报。 创建、管理和接收可自定义的警报和功能板，以跟踪投放成功或失败。<br /> Adobe Campaign投放警报通过电子邮件和仪表板让公司中所有涉及的Adobe Campaign用户自动了解投放执行状态，从而提高效率。 欲了解更多信息，请参见 <a href="../../sending/using/receiving-alerts-when-failures-happen.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 数据源中加密的已声明ID<br /> </td> 
   <td> 使用加密的联系信息（电子邮件地址或电话号码）作为声明的ID，无需在Campaign中现有用户档案即可发送电子邮件和短信触发器。 由于Adobe Campaign Standard可以对加密的声明ID进行解码，因此，在从包含先前未知联系人的其他Experience Cloud解决方案接收受众时，Campaign现在可以创建新的可销售用户档案。<br /> 通过电子邮件和短信实时定位客户和未知潜在客户，以提高现有客户群中的忠诚度并吸引新客户。 一旦潜在客户在Adobe Campaign中验证并利用这些洞察信息，即可充分利用您的第一方Cookie数据(来自Adobe Audience Manager*)。 <br /> *需要Adobe Audience Manager。 欲了解更多信息，请参见 <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 从Campaign到Analytics的KPI共享<br /> </td> 
   <td> 与Adobe Analytics共享促销活动数据，以通过转化、统一点击前和点击后行为来测量促销活动的电子邮件营销量度以及其他营销和广告效果。<br /> 直接跟踪整体绩效并发现Analytics中与外部程序的协同效应。 将来自此整合视图的学习应用回您的营销活动；最终提高开放式、点进和转化率，从而提高收入和整体营销活动效果。 <br /> Adobe Analytics为必填项。 欲了解更多信息，请参见 <a href="../../integrating/using/about-campaign-analytics-integration.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 直邮渠道 — 退回发件人<br /> </td> 
   <td> 现在支持与直邮提供商进行平面文件交换，其中纳入了“返回发件人”信息。 对直邮渠道的这种增强允许从未来的通信中排除相应的邮政地址。<br /> 这样，营销人员就可以收到地址错误的通知，并通过其他渠道与客户互动，或者鼓励他们更新邮政地址。 这还可以减少营销资金浪费的数量，因为营销人员会避免将邮件发送到错误的地址。 <br /> 直邮可用作附加渠道。 欲了解更多信息，请参见 <a href="../../channels/using/return-to-sender.md">详细文档</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_常规_

* 修复了允许任何用户导出列表的问题。 现在，仅限具有以下特征的用户： **[!UICONTROL Export]** 允许角色。

_电子邮件、短信消息和直邮_

* 修复了的问题 **updateDeliveryExecInfo** 工作流设置 **投放** 用于短信投放的指示器为0。
* 在 **高级参数** 的属性中， **路由** 下拉列表现在仅显示与模板消息类型对应的外部帐户。 例如，电子邮件投放模板仅显示电子邮件外部帐户。
* 修复了的问题 **[!UICONTROL Text]** 为测试用户档案定义的首选电子邮件格式。
* 修复了在投放的计划定义屏幕中选择默认时区时导致中出现Javascript错误的问题。
* 修复了阻止发送日志中显示陷阱的问题。
* 在投放创建向导的模板选择屏幕中，后续模板和A/B测试模板现在默认处于隐藏状态。 欲了解更多信息，请参见 [详细文档](../../channels/using/creating-an-email.md).
* 修复了导致任何用户发送投放的问题。 现在，仅限具有以下特征的用户： **[!UICONTROL Start deliveries]** 允许角色。 欲了解更多信息，请参见 [详细文档](../../sending/using/confirming-the-send.md).

_推送通知_

* 修复了的问题 **营销活动跟踪端点** 阻止报告的URL。
* 修复了阻止在Android设备上显示推送通知标题的问题。
* 修复了当推送通知仅包含标题（消息正文中不包含任何内容）时，阻止在iOS设备上显示推送通知的问题。
* 修复了强制跟踪投放中的媒体附件URL，从而阻止在投放中嵌入视频和图片的问题。 默认情况下，推送通知将停用mediaAttachmentURL类型的URL跟踪。

_报告_

* 更正了图表和表之间的值显示不同的问题。
* 更正了将推送通知值显示为电子邮件值的问题。
* 修复了在营销活动之外创建投放时显示未知值的问题。
* 修复了将短信报表数据显示为移动应用程序数据的问题。

_工作流_

* 您现在可以筛选工作流日志（时段和文本搜索）。 欲了解更多信息，请参见 [详细文档](../../automating/using/monitoring-workflow-execution.md).
* 现在工作流投放中提供了一个选项，用于在发送前停用确认。
* 修复了导致无法在定期投放创建向导中设置叫客过渡的问题。
* 修复了在使用基于具有大量值的枚举的自定义资源字段的工作流查询活动时发生的问题

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
   <td> 通过Adobe Campaign Standard的第一个离线渠道Direct Mail，突破数字屏障，连接到物理世界。 通过此功能，您可以个性化和生成直邮提供商所需的文件，作为跨渠道营销活动的一部分。 利用Direct Mail，通过一种吸引人的触觉接触点将客户引导至您的应用程序、网站或商店，从而重新吸引客户或增强客户体验。<br /> 欲了解更多信息，请参见 <a href="../../channels/using/about-direct-mail.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 电子邮件密送<br /> </td> 
   <td> 电子邮件密件抄送功能可以保存发送给每位收件人的独特电子邮件，从而允许品牌存档这些邮件。 通过向所有电子邮件添加密件抄送电子邮件地址，Adobe Campaign Standard客户可以使用此功能保留每封电子邮件的精确副本。 这是金融服务业的常见法律要求，有助于帮助客户服务中心实时解决冲突。<br /> 欲了解更多信息，请参见 <a href="../../sending/using/archiving.md">详细文档</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_界面更新_

* 在顶部栏中， **[!UICONTROL Timeline]** 已删除链接，并替换为指向的链接 **[!UICONTROL Programs & Campaigns]** .

_电子邮件和短信消息_

* 修复了显示错误颜色的问题 **[!UICONTROL Retry in progress]** 投放状态。 颜色是灰色而不是蓝色。

_工作流_

* 修复了将操作更改为在中执行时发生的问题 **[!UICONTROL Transfer file]** 活动。

_报告_

* 此 **[!UICONTROL Spam]** 和 **[!UICONTROL Spam rate]** 指标计算已更改。
* 此 **[!UICONTROL Bounce]** 指标已改进，可获取更准确的结果。

_推送通知_

* 修复了阻止您在用户档案营销历史中单击推送事件的问题。
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
   <td> Creative SDK的增强图像编辑功能<br /> </td> 
   <td> 您现在可以访问由Creative SDK提供支持的完整功能集，以便在编辑电子邮件或登陆页面时直接在内容编辑器中增强图像。<br /> 此功能不需要购买其他Creative Cloud解决方案。<br /> 欲了解更多信息，请参见 <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 事务型推送通知<br /> </td> 
   <td> 移动应用程序渠道已添加到Adobe Campaign的事务性消息传递功能。 事务型消息现在支持三个渠道：电子邮件、短信和推送通知。<br /> 欲了解更多信息，请参见 <a href="../../channels/using/transactional-push-notifications.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 定期推送通知<br /> </td> 
   <td> 您现在可以在工作流中配置定期推送通知。 如果您的客户希望定期更新（如每周提醒）以签出新内容或促销，则可以使用定期推送通知。<br /> 欲了解更多信息，请参见 <a href="../../automating/using/push-notification-delivery.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Amazon Simple Storage Service (S3)连接器<br /> </td> 
   <td> Amazon Simple Storage Service (S3)连接器现在可用于将数据导入或导出到Adobe Campaign。 它可以在工作流活动中设置。 配置在外部帐户中完成。<br /> 欲了解更多信息，请参见 <a href="../../administration/using/external-accounts.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver集成上线<br /> </td> 
   <td> Adobe Campaign与Dreamweaver之间的集成现已上线。 它现在可与Dreamweaver官方上次发布版本(17.0.2)配合使用。<br /> 需要安装Adobe Campaign集成扩展。 有关更多信息，请参阅此 <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=zh-Hans">视频</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* 修复了内存消耗问题。

_电子邮件和短信消息_

* 修复了在预览消息时，内容无法正确与最新更改同步的问题。
* 修复了阻止创建或删除MX或域电子邮件处理规则的问题。
* 修复了可能会阻止您发送具有多个别名的电子邮件的问题。
* 修复了阻止陷阱投放日志显示在投放发送日志中的问题。
* 修复了在内容中没有URL的投放显示跟踪URL时导致出现错误的问题。
* 修复了导致无法在发送的消息中正确应用图像大小属性的问题。

_事务性消息_

* rtEventHistoId字段不再作为事务性消息模板中的个性化字段显示。

_登陆页面_

* 我们已优化 **[!UICONTROL by email]** 在登陆页面中使用的过滤器，用于协调新订阅者与数据库用户档案。
* 修复了在表单配置中使用布尔字段时显示自由文本输入而非复选框的问题。
* 修复了阻止生成登陆页面缩略图的问题。

_工作流_

* 修复了编辑 **[!UICONTROL End]** 或 **[!UICONTROL External Signal]** 活动（仅限于Safari）。
* 改进了编辑时显示的错误消息 **[!UICONTROL Read Audience]** 包含错误受众的活动。
* 修复了在执行订阅活动时可能导致SQL错误的问题。

_集成_

* 兴趣点数据：修复了在计数位置订阅者时发生的错误。

_受众和查询_

* 修复了查询编辑器中的收藏集上无法使用sum和average聚合的问题。
* 修复了在更改筛选器的资源后可能阻止重新加载查询编辑器的问题。

_报告_

* 修复了在表中选择多行时阻止正确计算打开率量度的问题。
* 修复了仅将量度显示为整数的错误。 量度现在可以显示小数。

_推送通知_

* 修复了在创建链接到在MCPNS上未能创建的移动应用程序的Android应用程序时未显示错误消息的问题。
* 修复了允许用户向静默通知添加声音的问题。

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
   <td> Dynamic Reporting提供新一代完全可自定义的实时业务报告。 此功能基于可视动态数据透视表和图形，允许您拖放变量和维度来分析营销活动的效率和效果。 动态报告还允许您从头开始创建自己的业务报告，并将其保存以供将来使用。<br /> 欲了解更多信息，请参见 <a href="../../reporting/using/about-dynamic-reports.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver集成（实验室）<br /> </td> 
   <td> 通过Adobe Campaign与Dreamweaver集成，您现在拥有使用Adobe解决方案创建电子邮件促销活动的集成流程。<br /> 您可以在Dreamweaver中编辑Adobe Campaign电子邮件，并在两个解决方案之间无缝同步内容。<br /> 对于初始版本，该集成以“Labs”功能提供，仅适用于Dreamweaver预发行测试版。 如果想要激活它，请联系AC-DW-integration@adobe.com。<br /> 有关更多信息，请参阅此 <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=zh-Hans">视频</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 手动发送时间优化<br /> </td> 
   <td> 您现在可以在投放级别或使用工作流手动定义每个收件人的自定义发送时间。 <br /> 提供了两个新选项： <br /> 
    <ul> 
     <li> 所有收件人都会收到考虑了当地时区时间的消息。 </li> 
     <li> 每个收件人都会在公式定义的计算日期和时间收到消息。 </li> 
    </ul> 欲了解更多信息，请参见 <a href="../../sending/using/optimizing-the-sending-time.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送通知新功能<br /> </td> 
   <td> 推送通知渠道已得到增强，现在提供了几项新功能：<br /> 
    <ul> 
     <li> 新的创作界面 </li> 
     <li> 静默通知 </li> 
     <li> 交互式推送 </li> 
     <li> 丰富的内容支持 </li> 
     <li> 有效负载大小计算器 </li> 
    </ul> 欲了解更多信息，请参见 <a href="../../channels/using/about-push-notifications.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流：新信号活动<br /> </td> 
   <td> 使用新的触发来自另一个工作流的工作流 <span class="uicontrol">信号</span> 活动。<br /> 由于能够从另一个工作流启动一个工作流，您现在可以支持更复杂的客户历程。 您可以更好地监控客户历程，并在出现问题时做出反应。<br /> 几个工作流活动已更新：<br /> 
    <ul> 
     <li> <span class="uicontrol">结束</span> 活动：您现在可以通过新的选项卡指定要在执行此活动后触发的工作流。 </li> 
     <li> <span class="uicontrol">更新数据</span> 活动：使用新的空叫客过渡添加 <strong>结束</strong> 触发另一个工作流的活动。 空出站转化不携带任何数据，也不会占用系统中不必要的空间 </li> 
    </ul> 欲了解更多信息，请参见 <a href="../../automating/using/external-signal.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流：新的读取受众活动<br /> </td> 
   <td> 使用现有受众开始您的定位流程，您可以轻松地在一个活动中选择和优化这些受众。<br /> 欲了解更多信息，请参见 <a href="../../automating/using/read-audience.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 兴趣点数据<br /> </td> 
   <td> 兴趣点数据将Adobe Campaign与适用于移动设备的Adobe Analytics集成。 品牌可以从用户的移动位置收集数据 — 称为 <strong>目标点</strong>  — 用户打开品牌的应用程序时。 这使品牌能够利用Adobe Campaign工作流程，根据用户的位置发送个性化消息。 此渠道利用Mobile核心服务的SDK。<br /> 请注意，使用此功能需要Analytics for Mobile，这是一个付费解决方案。<br /> 欲了解更多信息，请参见 <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> REST API<br /> </td> 
   <td> 现在，API中提供了在任何级别链接到用户档案或服务资源的资源。<br /> 欲了解更多信息，请参见 <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">详细文档</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_常规_

* 现在，可以在导出投放日志时添加用户档案数据。

_电子邮件和短信消息_

* 修复了导致出现错误的问题 **[!UICONTROL Request confirmation before sending messages]** 选项，以在取消选中并保存投放后仍保持选中状态。
* 修复了可能阻止取消发布事务性电子邮件的问题。
* 修复了在预览投放之前内容无法与最新更改正确同步的问题。

_登陆页面_

* 修复了在单击登陆页面的内容时阻止用户编辑的错误。

_工作流_

* 修复了可能阻止读取的拒绝过渡内容的问题。 **[!UICONTROL Load file]** 活动。
* 修复了在配置时无法正确考虑已交换列的问题 **[!UICONTROL Load file]** 活动。

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
   <td> 导出日志用于外部报告<br /> </td> 
   <td> 导出日志（如投放和跟踪日志），以便在您的首选报告或BI工具中处理它们。 您可以将简单工作流与增量查询结合使用，以自动定期导出新日志。<br /> 除了资源选取器中的日志资源可用性之外，还增强了 <a href="../../automating/using/incremental-query.md">增量查询</a> 和 <a href="../../automating/using/extract-file.md">提取文件</a> 活动：<br /> 
    <ul> 
     <li> <span class="uicontrol">增量查询</span> 现在，允许您使用日期字段检索新数据或更新数据。 以前，即使先前执行得出的所有结果在上次执行后进行了更新，也会自动将其排除。 </li> 
     <li> <span class="uicontrol">提取文件</span> 现在可以导出枚举值的标签而不是ID。 </li> 
    </ul> 管理员可以使用这些活动访问所有地域和组织单位。<br /> 有关导出日志的更多信息，请参阅 <a href="../../automating/using/exporting-logs.md">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 事务性消息的营销功能<br /> </td> 
   <td> 营销人员现在可以根据客户营销用户档案发送事务型消息。 这允许他们：<br /> 
    <ul> 
     <li> 应用营销分类规则，例如 <span class="uicontrol">在阻止列表时的地址</span> . </li> 
     <li> 在消息中包含退订链接。 </li> 
     <li> 将事务型消息添加到全局投放报告。 </li> 
     <li> 在客户历程中使用事务型消息。 </li> 
    </ul> 欲了解更多信息，请参见 <a href="../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities">详细文档</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 事务性消息传递API<br /> </td> 
   <td> 事务性消息传递API现已可用，从而使其更易于使用和监控：<br /> 
    <ul> 
     <li> 您可以从Adobe Developer平台报告和监控功能中获益。 </li> 
     <li> 列入允许列表现在，使用基于adobe.io令牌的身份验证而不是IP身份验证来执行身份验证，使安全过程更加简单。 </li> 
     <li> 现在，所有API都集成在单个平台上，如果您已经支持用户档案和服务API，则向集成添加事务性消息传送功能会比以往更简单。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_常规_

* 此 **[!UICONTROL Access authorization]** 选项已返回到登陆页面属性。
* 修复了可能导致呈现旧图像而不是正确图像的问题。 如果在投放或登陆页面的内容定义中更新了源图像，则会发生此情况。
* 修复了阻止用户编辑现有SFTP外部帐户中某些字段的问题。
* 修复了若干UI问题。 例如，用户现在可以编辑配置文件属性并保存修改，而不会遇到UI问题。

_电子邮件和短信消息_

* 修复了与投放模板相关的问题，该投放模板的HTML包含

_推送通知_

* 修复了可能导致应用程序无法回发到Adobe Campaign服务器的问题。
* 修复了可能导致无法解决的问题 **[!UICONTROL Play a sound]** 和 **[!UICONTROL Custom fields]** 将考虑在Android中。
* 修复了可能导致向用于表情符号的Unicode字符添加额外转义字符的问题。
* 现在，当订户的注册令牌添加到阻止列表时，相应的状态会立即在Adobe Campaign中应用程序的订户列表中更新。

_工作流_

* 修复了可能导致无法预览有关事件资源（如rtEvent）的查询的问题。
* 生成的拒绝文件 **[!UICONTROL Load file]** 现在可以在叫客过渡中检索活动，并在下一个活动中处理。 例如，使用以下方式通过SFTP服务器上传拒绝文件 **[!UICONTROL Transfer file]** .
* 修复了在以下情况下可能阻止用户限制区段群体的问题 **[!UICONTROL Temporary resource]** 已选中的 **[!UICONTROL General]** 选项卡/ **[!UICONTROL Segmentation]** .
* **[!UICONTROL Scheduler]** 不能再将活动设置为每10分钟触发一次以上的工作流。
* 修复了可能导致无法解决的问题 **[!UICONTROL Use common columns]** 无法在中正常工作 **[!UICONTROL Union]** 活动。

_集成_

* 修复了在Adobe Campaign中部署事件触发器时可能导致错误的问题。 将“30天内回访的可能性”元数据添加到Adobe Marketing Cloud中的“放弃”触发器时，会发生此错误。
* 修复了在从“人员”核心服务导入Dimension时，可能导致技术工作流清除“目标受众”字段的问题。 后续查询无法检索导入的受众。
* 修复了可能导致 **[!UICONTROL Save audience]** 选择时工作流活动失败 **[!UICONTROL Share in Adobe Marketing Cloud]** 已选中。
