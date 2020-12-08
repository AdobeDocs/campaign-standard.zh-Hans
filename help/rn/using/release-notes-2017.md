---
solution: Campaign Standard
product: campaign
title: 发行说明 2017
description: 本页列出了所有 2017 版的 Adobe Campaign Standard。
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
translation-type: tm+mt
source-git-commit: a51943e4da04f5d19aaecdfcf956f5c4f3d804c8
workflow-type: tm+mt
source-wordcount: '4627'
ht-degree: 5%

---


# 发行说明 2017{#release-notes}

是否正在寻找2017年版Adobe Campaign Standard?

每个版本都提供新功能和修补程序。 单击某个版本可视图其内容。

视图Adobe Campaign Standard的最新[文档更新](../../rn/using/documentation-updates.md)。 如果要查找较新的版本，请查阅此[页面](../../rn/using/release-notes.md)。

## 17.10 版 - 2017 年 10 月{#release-17-10---october-2017}

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
   <td> 疲劳管理允许您创建疲劳规则以管理与用户档案的过度通信。 疲劳规则很容易构建，但具有非常灵活的功能，如跨多个渠道(包括事务性消息)计数消息、仅计数特定投放或将规则应用于特定用户档案。<br /> 有关详细信息，请参阅详 <a href="../../sending/using/fatigue-rules.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 内容创建：从URL<br />导入 </td> 
   <td> 通过URL导入，您可以快速从网站检索您的创意内容，为任何投放构建电子邮件。 此外，您还可以通过使第三方直接通过URL共享内容，从而简化您的创作流程。 导入的内容可以灵活地用作单个投放的一部分或在模板级别，确保所有相关活动的品牌一致性，无论这些基于工作流还是事务性消息，并且包括A/B或多变量测试。 从URL导入会自动转换和跟踪所有链接，以通过动态报告监视电子邮件性能。<br /> 有关详细信息，请参阅详 <a href="../../designing/using/using-existing-content.md#importing-content-from-a-url">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* 修复了一个问题，该问题可能会阻止正确解压大文件。
* 品牌管理的安全性已得到改进。 现在，为Adobe技术管理员保留修改品牌名称和发件人地址。
* 为了提高安全性，用户生成的内容(图像、镜像页面、登陆页等) 不能再由adobe.com域提供。 现在，必须使用您自己的域来通过使用品牌来处理这些资源。
* 修复了显示和筛选营销活动时的界面问题。
* 修复了订阅日期字段无法通过POST休息API调用进行更新的问题。

_电子邮件、短信和直邮_

* 修复了一个问题，该问题可能会阻止将消息中的列表类型受众定位为目标，从而导致准备失败。
* 多语言电子邮件投放功能中新增了缺失的语言。
* 在投放仪表板中显示的内容缩略图现在会在用户修改内容并保存时自动更新。
* 修复了阻止打开投放的时区相关问题。

_推送通知_

* 配置推送通知渠道时，iOS的推送提供程序平台应为&#x200B;**apns**&#x200B;和Android **gcm**。
* 修复了阻止在Adobe Campaign界面中添加iOS移动应用程序的错误。
* 现在，GCM和启用FCM的Android移动应用程序都支持推送通知。
* 修复了复制推送通知模板时阻止保存内容的错误。
* 现在，可以通过协调移动应用程序用户的用户档案，从Adobe Campaign数据库创建或更新。
* Adobe Campaign现在优先处理事务推送通知，而不是标准推送通知。

_报告_

* 修复了阻止热点单击百分比显示在电子邮件内容中的问题。
* 修复了计为强阻止列表弹跳而非弹跳的量度的问题。
* 修复了导致在摘要数据中显示负计数的问题。
* 修复了在错误的年龄段中统计用户档案的问题。
* 软弹跳和硬弹跳计算公式已更改。

_工作流_

* 修复了&#x200B;**[!UICONTROL Load file]**&#x200B;活动中在手动添加和删除活动中的列后，可能导致错误的问题。
* **[!UICONTROL deliverabilityUpdate]**&#x200B;技术工作流现在计划在服务器时间凌晨2点运行。
* 修复了允许在不具有导出角色的情况下执行列表导出的安全问题。
* 修复了&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活动的问题。
* 修复了在&#x200B;**[!UICONTROL File Transfer]**&#x200B;活动中使用通配符的问题。

_用户档案和受众_

* 修复了一个问题，该问题可能会导致在某些情况下无法正确考虑查询的条件，从而导致错误结果。
* 修复了在已准备但从未发送和过期的邮件中定位用户档案时，会阻止访问这些数据的问题。

_集成_

* 修复了一个问题，该问题可能会阻止为触发器创建的某些数据源正确显示并被选择。

_自定义资源_

* 修复了列表屏幕中出现的自定义资源行可在没有任何数据的情况下显示的问题。
* 修复了阻止在自定义资源中显示值为“False”的布尔类型字段的问题。

## 17.9 版 - 2017 年 9 月{#release-17-9---september-2017}

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
   <td> 引入了18个全新的响应式模板，它们设计在两个美丽的主题中- Astro和Feather。 这些可自定义的模板与行业无关，可立即使用。 模板包含各种用例的内容，可让电子邮件营销活动比以往更快、更高效、更美观地进行设计和投放。<br /> 有关详细信息，请参阅详 <a href="../../designing/using/using-reusable-content.md#content-templates">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 动态报告用户档案数据<br /> </td> 
   <td> 动态报告提供完全可自定义的实时业务报表。 在此版本中，动态报告的强大增强功能增加了对用户档案数据的访问，除了功能性电子邮件活动数据（如打开和点击）之外，还支持按用户档案维度（如性别、城市、邮政编码和年龄）进行的人口统计分析。 借助相同易用的拖放界面，确定电子邮件活动对最重要的客户细分的执行方式比以往更简单。<br /> 有关详细信息，请参阅详 <a href="../../reporting/using/about-dynamic-reports.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 具有来源和日期的成批订阅<br /> </td> 
   <td> 通过此批量订阅增强，您现在可以通过工作流中的订阅服务活动直接将订阅信息(来源和日期)存储在Adobe Campaign Standard数据库中。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/subscription-services.md">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* 一些客户需要能够利用来自Adobe Campaign Standard的ID，因为他们没有管理唯一的密钥来识别自己的记录。 此ID(**ACS ID**)可以在更新数据时导出并用作合并关键项。 有关详细信息，请参阅[详细文档](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)。
* FTP协议已弃用。 您现在应改用SFTP。 为了不阻止现有实施，FTP上的现有配置仍能正常工作，但新活动将不显示此选项。

_电子邮件、短信和直邮_

* 现在，可以创建新的警报标准，以便在投放警报通知中使用它们。 有关详细信息，请参阅[详细文档](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion)。
* 投放警报通知具有新设计，投放警报仪表板用户体验已得到改进。
* 现在，当路由外部帐户被禁用时，受影响的投放（电子邮件、SMS和推送）中会显示一条警告消息，并且&#x200B;**预览**&#x200B;按钮隐藏在这些投放中。
* 修复了在主题行中启用动态文本时，电子邮件内容的A/B测试预览出错的问题。

_事务型消息传递_

* 现在可以定义何时发送后续消息，例如，在发送事务性消息后3天。 有关详细信息，请参阅[详细文档](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)。
* 现在，可以定义链接到事务性消息的事件的发送日期。
* 修复了在删除链接到已接收和已处理用户档案的事件后，执行包含后续消息的工作流时导致SQL错误的问题。
* 修复了阻止删除链接到用户档案的事件的错误。
* 修复了一个问题，该问题可能会阻止跟踪链接的重定向工作。
* 修复了阻止您对电子邮件或SMS消息中的某些链接禁用跟踪的问题。

_报告_

* **热点单击**&#x200B;报告已得到改进。 此外，现在可以根据在投放中定义的每个条件内容显示热点单击，并可以显示重复投放或事务性消息的每次执行的热点单击。 有关详细信息，请参阅[详细文档](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion)。
* 修复了隔离度量无法检索正确数据的问题。
* 新的预设时间范围已添加到日历构件。
* [动态报告指标](../../reporting/using/indicator-calculation.md)和[活动的KPI](../../sending/using/confirming-the-send.md)(显示在已发送消息的仪表板上)已经一致，以获得更一致的效果。
* 修复了可能导致流水线在debian 7上崩溃的问题。

_工作流_

* 修复了可能阻止导入的文件保留正常工作的问题。

_集成_

* 现在，Analytics和事件集成支持eVar和活动。
* 当发送包含放弃购物车内容的电子邮件时，从购物车中删除的元素的有效负荷参数现在是可选的。

_用户档案和受众_

* Adobe Campaign现在提供一个报告，其中显示活动用户档案的数量。 此报告仅提供信息，对计费没有直接影响。 有关详细信息，请参阅[详细文档](../../audiences/using/active-profiles.md)。
* 修复了在使用用户档案和服务API时阻止用户档案订阅服务的问题。

## 17.7 版 - 2017 年 7 月{#release-17-7---july-2017}

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
   <td> 多语言电子邮件和SMS投放<br /> </td> 
   <td> 根据自动细分的客户首选语言，通过单一投放定义并执行多语言电子邮件和短信投放。 关于每次投放之绩效的报告，可以细分到语言和各个级别。<br /> 随着内容在国内外的发展，越来越多的公司面临着以多种语言提供内容的挑战。因此，简化本地化消息投放是跨国公司有效客户沟通策略的关键部分；公司在多语言国家／地区；以及希望在语言级别进一步个性化其内容的公司，无论客户位于何处。 有关详细信息，请参阅<a href="../../channels/using/creating-a-multilingual-email.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Campaign通知<br /> </td> 
   <td> 直接在Adobe Campaign Standard内接收有关重要系统活动的通知。 例如，您将收到持续投放进度或工作流出错时的通知。<br /> 实时通知可让相关利益相关方及时获得信息，并让用户能够立即直接从应用程序内对活动通知采取行动。团队的成果是先进的敏捷性、效率和更顺畅的活动执行。 有关详细信息，请参阅<a href="../../administration/using/sending-internal-notifications.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 投放警报<br /> </td> 
   <td> 除了直接在Adobe Campaign Standard查看通知外，Adobe Campaign现在还提供电子邮件警报系统，以向重要系统活动的用户或外部利益相关方触发电子邮件警报。 创建、管理和接收可自定义的警报和仪表板，以跟踪投放成功或失败。<br /> Adobe Campaign投放警报通过电子邮件和仪表板让所有相关Adobe Campaign用户在公司中自动获知投放执行状态，从而提高了效率。有关详细信息，请参阅<a href="../../sending/using/receiving-alerts-when-failures-happen.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 数据源<br />中的已加密Declared ID </td> 
   <td> 使用加密的联系信息（电子邮件地址或电话号码）作为Declared ID，发送电子邮件和短信触发器，而无需活动中的现有用户档案。 由于加密的声明ID可以由Adobe Campaign Standard解码，活动现在可以在从包含先前未知联系人的其他Experience Cloud解决方案接收受众时创建新的可销售用户档案。<br /> 目标客户和未知潜在客户通过电子邮件和短信实时提高现有客户群的忠诚度，并分别赢取新客户。在潜在客户进行身份验证并在Adobe Campaign中利用这些洞察后，充分利用第一方cookie数据(来自Adobe Audience Manager*)。 <br /> *Adobe Audience Manager为必填。有关详细信息，请参阅<a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 从活动到Analytics的KPI共享<br /> </td> 
   <td> 与Adobe Analytics共享活动数据，以通过转化、统一点击前和点击后行为，衡量来自活动的电子邮件营销指标以及其他营销和广告工作。<br /> 在Analytics中直接跟踪整体绩效并发现与外部项目的协同效应。将您从这一整合视图中学到的知识重新应用于活动;最终改进开放、点进和转化率，提高收入和整体活动表现。 <br /> Adobe Analytics是必填。有关详细信息，请参阅<a href="../../integrating/using/about-campaign-analytics-integration.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 直邮渠道-返回发件人<br /> </td> 
   <td> 现在支持与包含“返回给发件人”信息的直邮提供商进行平面文件交换。 对“直邮”渠道的这一增强允许将来的通信中排除相应的邮政地址。<br /> 这使营销人员能够收到错误地址的通知，并通过其他渠道与客户互动，或鼓励他更新其邮政地址。这也减少了营销人员避免将邮件发送到错误地址时浪费的营销资金。 <br /> “直邮”可作为附加渠道。有关详细信息，请参阅<a href="../../channels/using/return-to-sender.md">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_常规_

* 修复了允许任何用户导出列表的问题。 现在，仅允许具有&#x200B;**[!UICONTROL Export]**&#x200B;角色的用户访问。

_电子邮件、短信和直邮_

* 修复了&#x200B;**updateDeliveryExecInfo**&#x200B;工作流的一个问题，该工作流将SMS投放的&#x200B;**传送**&#x200B;指示符设置为0。
* 在投放模板属性的&#x200B;**高级参数**&#x200B;中，**路由**&#x200B;下拉列表现在仅显示与模板消息类型对应的外部帐户。 例如，电子邮件投放模板仅显示电子邮件外部帐户。
* 修复了为测试电子邮件格式定义的&#x200B;**[!UICONTROL Text]**&#x200B;首选用户档案的问题。
* 修复了在计划定义屏幕中选择默认时区时导致Javascript错误的问题。
* 修复了阻止陷阱显示在发送日志中的问题。
* 现在，在投放创建向导的模板选择屏幕中，默认情况下隐藏后续和A/B测试模板。 有关详细信息，请参阅[详细文档](../../channels/using/creating-an-email.md)。
* 修复了允许任何用户发送投放的问题。 现在，仅允许具有&#x200B;**[!UICONTROL Start deliveries]**&#x200B;角色的用户访问。 有关详细信息，请参阅[详细文档](../../sending/using/confirming-the-send.md)。

_推送通知_

* 修复了&#x200B;**活动跟踪端点** URL中阻止报告的问题。
* 修复了在Android设备上无法显示推送通知标题的问题。
* 修复了当推送通知仅包含标题（消息正文中没有标题）时，在iOS设备上无法显示推送通知的问题。
* 修复了强制跟踪投放中的媒体附件URL的问题，该问题导致视频和图片无法嵌入投放中。 现在，对于推送通知，默认情况下将停用对mediaAttachmentURL类型URL的跟踪。

_报告_

* 更正了图表和表之间显示值不同的问题。
* 更正了将推送通知值显示为电子邮件值的问题。
* 修复了在投放之外创建活动时，值显示为未知的问题。
* 更正了将SMS报告数据显示为移动应用程序数据的问题。

_工作流_

* 您现在可以过滤工作流日志（时间段和文本搜索）。 有关详细信息，请参阅[详细文档](../../automating/using/monitoring-workflow-execution.md)。
* 现在，工作流投放中有一个选项可用于在发送之前取消激活确认。
* 修复了在循环过渡的创建向导中无法设置出站投放的问题。
* 修复了在使用基于自定义资源字段的工作流查询活动时发生的具有大量值的明细列表的问题

## 17.5 版 - 2017 年 5 月{#release-17-5---may-2017}

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
   <td> 借助Adobe Campaign Standard的第一家线下渠道“直邮”突破数字障碍，与现实世界建立联系。 此功能允许您个性化并生成直接邮件提供商所需的文件，作为跨渠道活动的一部分。 利用直邮重新吸引客户或通过吸引客户的触碰性接触点增强客户体验，将客户带到您的应用程序、网站或商店。<br /> 有关详细信息，请参阅详 <a href="../../channels/using/about-direct-mail.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 密件抄送<br /> </td> 
   <td> 密件抄送功能可保存发送给个别收件人的独特电子邮件，使品牌能够存档这些邮件。 通过向所有电子邮件添加密送电子邮件地址，Adobe Campaign Standard客户可以利用此功能保留每封电子邮件的准确副本。 这是金融服务业的常见法律要求，有助于客户服务中心实时解决冲突。<br /> 有关详细信息，请参阅详 <a href="../../sending/using/archiving.md">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_界面更新_

* 在顶栏中，**[!UICONTROL Timeline]**&#x200B;链接已被删除，并替换为指向&#x200B;**[!UICONTROL Programs & Campaigns]**&#x200B;的链接。

_电子邮件和短信_

* 修复了&#x200B;**[!UICONTROL Retry in progress]**&#x200B;投放状态显示错误颜色的问题。 颜色是灰色而不是蓝色。

_工作流_

* 修复了在&#x200B;**[!UICONTROL Transfer file]**&#x200B;活动中将操作更改为执行时发生的问题。

_报告_

* **[!UICONTROL Spam]**&#x200B;和&#x200B;**[!UICONTROL Spam rate]**&#x200B;指示器计算已更改。
* **[!UICONTROL Bounce]**&#x200B;指标已得到改进，以获得更准确的结果。

_推送通知_

* 修复了阻止您在用户档案事件中单击推送营销历史的问题。
* 工作流中推送通知的使用已得到改进。

## 17.4 版 - 2017 年 4 月{#release-17-4---april-2017}

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
   <td> Creative SDK<br />增强的图像编辑功能 </td> 
   <td> 您现在可以访问以Creative SDK为后盾的一整套功能，在编辑电子邮件或登陆页时直接在内容编辑器中增强您的图像。<br /> 此功能不需要获取其他Creative Cloud解决方案。<br /> 有关详细信息，请参阅详 <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 事务型推送通知<br /> </td> 
   <td> 移动应用渠道已添加到Adobe Campaign的事务消息传递功能中。 现在支持三种渠道事务性消息:电子邮件、短信和推送通知。<br /> 有关详细信息，请参阅详 <a href="../../channels/using/transactional-push-notifications.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 循环推送通知<br /> </td> 
   <td> 您现在可以在工作流中配置循环推送通知。 在客户希望定期更新（如每周提醒注销新内容或促销）的情况下，您可以使用循环推送通知。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/push-notification-delivery.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Amazon简单存储服务(S3)连接器<br /> </td> 
   <td> Amazon简单存储服务(S3)连接器现在可用于导入或将数据导出到Adobe Campaign。 可以在工作流活动中设置。 配置在外部帐户中完成。<br /> 有关详细信息，请参阅详 <a href="../../administration/using/external-accounts.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver集成live<br /> </td> 
   <td> Adobe Campaign和Dreamweaver的融合现已实现。 它现在与官方上次发布的Dreamweaver版(17.0.2)配合使用。<br /> 这需要从以下位置安装Adobe Campaign集成扩展： <a href="https://adobe.ly/acdw_addon">https://adobe.ly/acdw_</a><br /> 加载项有关详细信息，请参阅此 <a href="https://docs.adobe.com/content/help/zh-Hans/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.translate.html">视频</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_平台_

* 修复了内存消耗问题。

_电子邮件和短信_

* 修复了在预览消息时内容无法与最新更改正确同步的问题。
* 修复了阻止创建或删除MX或域电子邮件处理规则的问题。
* 修复了可能阻止您发送具有多个别名的电子邮件的问题。
* 修复了阻止陷印投放日志显示在投放发送日志中的问题。
* 修复了在显示内容中没有URL的投放的跟踪URL时导致错误的问题。
* 修复了在发送的消息中无法正确应用图像大小属性的问题。

_事务型消息传递_

* rtEventHistoId字段不再作为事务性消息模板中的个性化字段公开。

_登陆页面_

* 我们优化了登陆页中使用的&#x200B;**[!UICONTROL by email]**&#x200B;过滤器，使新订阅者与数据库用户档案保持一致。
* 修复了在表单配置中使用布尔字段时显示自由文本输入而非复选框的问题。
* 修复了无法生成登陆页缩略图的问题。

_工作流_

* 修复了编辑&#x200B;**[!UICONTROL End]**&#x200B;或&#x200B;**[!UICONTROL External Signal]**&#x200B;活动时（仅在Safari上）出现的显示错误。
* 改进了编辑包含错误活动的&#x200B;**[!UICONTROL Read Audience]**&#x200B;受众时显示的错误消息。
* 修复了在执行订阅活动时可能导致SQL错误的问题。

_集成_

* 兴趣点数据：修复了计算位置订阅者时发生的错误。

_受众和查询_

* 修复了阻止在聚合编辑器中对集合使用和和平均查询的问题。
* 修复了在更改筛选器资源后可能阻止重新加载查询编辑器的问题。

_报告_

* 修复了在表中选择多行时无法正确计算开放率度量的问题。
* 修复了仅将度量显示为整数值的错误。 现在可以使用小数显示度量。

_推送通知_

* 修复了在创建链接到MCPNS上创建失败的移动应用程序的Android应用程序时，不显示错误消息的问题。
* 修复了允许用户向无提示通知添加声音的问题。

## 17.2 版 - 2017 年 3 月{#release-17-2---march-2017}

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
   <td> 动态报告提供新一代完全可自定义的实时业务报表。 此功能基于可视的动态透视表和图形，允许您拖放变量和尺寸以分析营销活动的效率和有效性。 动态报告还允许您从头开始创建自己的业务报表并保存以备以后使用。<br /> 有关详细信息，请参阅详 <a href="../../reporting/using/about-dynamic-reports.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver集成（实验室）<br /> </td> 
   <td> 通过Adobe Campaign和Dreamweaver的集成，您现在可以利用Adobe解决方案创建电子邮件活动。<br /> 您可以编辑Dreamweaver的Adobe Campaign电子邮件，并让内容在两个解决方案之间无缝同步。<br /> 对于初始版本，该集成可作为“实验室”功能提供，并且只能与Dreamweaver预发行版测试版一起使用。如果要激活它，请联系AC-DW-integration@adobe.com。<br /> 有关详细信息，请参阅此 <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">视频</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 手动发送时间优化<br /> </td> 
   <td> 您现在可以在收件人级别或使用工作流手动定义每个投放的自定义发送时间。 <br /> 有两个新选项可用：  <br /> 
    <ul> 
     <li> 所有收件人都会收到消息，并将时区考虑在内。 </li> 
     <li> 每个收件人在由公式定义的计算日期和时间接收消息。 </li> 
    </ul> 有关详细信息，请参阅<a href="../../sending/using/optimizing-the-sending-time.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送通知新功能<br /> </td> 
   <td> 推送通知渠道已通过以下几项新功能得到增强：<br /> 
    <ul> 
     <li> 新的创作界面 </li> 
     <li> 静默通知 </li> 
     <li> 交互式推送 </li> 
     <li> 丰富内容支持 </li> 
     <li> 有效负荷大小计算器 </li> 
    </ul> 有关详细信息，请参阅<a href="../../channels/using/about-push-notifications.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流:新信号活动<br /> </td> 
   <td> 使用新的<span class="uicontrol">Signal</span>活动从另一个工作流触发工作流。<br /> 利用从另一个工作流开始一个工作流的能力，您现在可以支持更复杂的客户旅程。您可以更好地监控客户旅程，并在出现问题时做出反应。<br /> 已更新多个工作流活动:<br /> 
    <ul> 
     <li> <span class="uicontrol">结</span> 尾活动：新选项卡允许您指定在执行此活动后触发的工作流。 </li> 
     <li> <span class="uicontrol">更新</span> 数据活动：使用新的空出站过渡添加可触 <strong></strong> 发另一个工作流的“结束”活动。空出站过渡不携带任何数据，并且不占用系统上的不必要空间 </li> 
    </ul> 有关详细信息，请参阅<a href="../../automating/using/external-signal.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流:新读取受众活动<br /> </td> 
   <td> 将定位流程与现有受众开始，您可以在一个活动中轻松选择和优化。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/read-audience.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 兴趣点数据<br /> </td> 
   <td> Points of Interest数据将Adobe Campaign与Adobe Analytics的移动平台集成。 当用户打开品牌的应用程序时，品牌可以从用户的移动位置（称为<strong>兴趣点</strong>）收集数据。 这使品牌能够利用Adobe Campaign工作流，以便根据用户的位置发送个性化消息。 此渠道利用Mobile核心服务的SDK。<br /> 请注意，使用此功能需要Analytics for Mobile（一种付费解决方案）。<br /> 有关详细信息，请参阅详 <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> REST API<br /> </td> 
   <td> API中现在提供任何级别链接到用户档案或服务资源的资源。<br /> 有关详细信息，请参阅详 <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_常规_

* 现在，在导出用户档案时可以添加投放日志数据。

_电子邮件和短信_

* 修复了导致&#x200B;**[!UICONTROL Request confirmation before sending messages]**&#x200B;选项在取消选中并保存投放后仍保持选中的问题。
* 修复了可能阻止取消发布交易电子邮件的问题。
* 修复了在预览投放之前，内容无法与最新更改正确同步的问题。

_登陆页面_

* 修复了用户在单击登陆页内容时无法进行编辑的错误。

_工作流_

* 修复了一个问题，该问题可能会阻止读取&#x200B;**[!UICONTROL Load file]**&#x200B;过渡的拒绝活动的内容。
* 修复了在配置&#x200B;**[!UICONTROL Load file]**&#x200B;活动时，无法正确考虑交换列的问题。

## 17.1 版 - 2017 年 1 月{#release-17-1---january-2017}

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
   <td> 外部报告的日志导出<br /> </td> 
   <td> 导出投放和跟踪日志等日志，在您喜欢的报告或BI工具中处理它们。 您可以使用简单的工作流和增量查询自动定期导出新日志。<br /> 除了资源选取器提供的日志资源可用性外，还对增量查询和提取文 <a href="../../automating/using/incremental-query.md">件活</a> 动进 <a href="../../automating/using/extract-file.md">行了</a> 增强：<br /> 
    <ul> 
     <li> <span class="uicontrol">增量</span> 查询现在允许您使用日期字段检索新数据或更新数据。以前，先前执行的所有结果都会自动排除，即使它们自上次执行以来已更新。 </li> 
     <li> <span class="uicontrol">提取</span> 文件现在可导出明细列表值的标签，而不是ID。 </li> 
    </ul> 这些活动适用于有权访问所有地理和组织单位的管理员。<br /> 有关导出日志的详细信息，请参阅详 <a href="../../automating/using/exporting-logs.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 事务性消息的营销能力<br /> </td> 
   <td> 营销人员现在可以根据客户营销用户档案发送事务性消息。 这允许他们：<br /> 
    <ul> 
     <li> 应用<span class="uicontrol">类型规则地址&lt;a1/阻止列表&gt;等营销。</span> </li> 
     <li> 在消息中包含退订链接。 </li> 
     <li> 将事务型消息添加到全局投放报告。 </li> 
     <li> 在客户历程中使用事务型消息。 </li> 
    </ul> 有关详细信息，请参阅<a href="../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional Messaging API<br /> </td> 
   <td> Transactional Messaging API现在可通过<a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io</a>使用，更易于使用和监控：<br /> 
    <ul> 
     <li> 您可以从adobe.io平台报告和监控功能中受益。 </li> 
     <li> 身份验证现在使用基于adobe.io令牌的身份验证而不是IP列入允许列表来执行，从而简化了安全过程。 </li> 
     <li> 所有API现在都集成在单一平台上，因此，如果您已经支持用户档案和服务API，向集成添加交易消息功能将变得前所未有的简单。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**修补程序**

_常规_

* **[!UICONTROL Access authorization]**&#x200B;选项已返回到登陆页属性。
* 修复了可能导致旧图像而不是正确图像呈现的问题。 如果源图像在投放或登陆页的内容定义中已更新，则会发生此问题。
* 修复了阻止用户编辑现有SFTP外部帐户中的特定字段的问题。
* 修复了多个UI问题。 例如，用户现在可以编辑用户档案属性并保存修改，而不会遇到UI问题。

_电子邮件和短信_

* 修复了与包含HTML内容的投放模板相关的问题

_推送通知_

* 修复了可能阻止从应用程序回传到Adobe Campaign服务器的问题。
* 修复了可能阻止将&#x200B;**[!UICONTROL Play a sound]**&#x200B;和&#x200B;**[!UICONTROL Custom fields]**&#x200B;考虑到Android的问题。
* 修复了可能导致额外转义字符添加到用于Emoji的Unicode字符的问题。
* 当将订户的注册令牌添加到阻止列表器时，现在在Adobe Campaign中的订户列表中立即更新相应的状态。

_工作流_

* 修复了可能阻止预览查询事件资源（例如rtEvent）的问题。
* 现在，可以在&#x200B;**[!UICONTROL Load file]**&#x200B;活动生成的拒绝文件的出站过渡中检索并在下一个活动中处理。 例如，使用&#x200B;**[!UICONTROL Transfer file]**&#x200B;通过SFTP服务器上传拒绝文件。
* 修复了在&#x200B;**[!UICONTROL Segmentation]**&#x200B;的&#x200B;**[!UICONTROL General]**&#x200B;选项卡中选择了&#x200B;**[!UICONTROL Temporary resource]**&#x200B;后，用户可能无法限制段的填充的问题。
* **[!UICONTROL Scheduler]** 活动不能再设置为每10分钟多触发一次工作流。
* 修复了可能导致&#x200B;**[!UICONTROL Use common columns]**&#x200B;在&#x200B;**[!UICONTROL Union]**&#x200B;活动中无法正常工作的问题。

_集成_

* 修复了在Adobe Campaign中部署事件触发器时可能导致错误的问题。 此错误是在将“30天后返回的可能性”元数据添加到Adobe Marketing Cloud的“放弃”触发器时发生的。
* 修复了在从People核心服务导入目标时，技术工作流可能会清除受众Dimension字段的问题。 后续查询无法检索导入的受众。
* 修复了在选中选项&#x200B;**[!UICONTROL Share in Adobe Marketing Cloud]**&#x200B;时可能导致工作流的&#x200B;**[!UICONTROL Save audience]**&#x200B;活动失败的问题。

