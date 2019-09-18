---
title: 发行说明2015-2016
seo-title: 发行说明2015-2016
description: 发行说明2015-2016
seo-description: 本页列出了所有2015和2016版Adobe Campaign Standard。
page-status-flag: 从未激活
uuid: d5a0f6cc-0bed-46cf-8dff-1717fb624f8f
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: 参考
topic-tags: campaign-standard-releases
discoiquuid: a3ce6b80-1858-49d1-8880-3543181127f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---


# 发行说明2015-2016{#release-notes}

是否正在寻找Adobe Campaign Standard的2015-2016版本？

每个版本都提供新功能和修补程序。 单击某个版本可查看其内容。

查看Adobe Campaign [Standard的最新文档](../../rn/using/documentation-updates.md) 更新。 如果要寻找较新的版本，请查阅此 [页](../../rn/using/release-notes.md)。

## 16.11版- 2016年11月 {#release-16-11---november-2016}

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
   <td> 可交付性排除规则<br /> </td> 
   <td> 加密的全局抑制列表现在在可交付性实例中进行管理，以避免由于恶意活动（特别是使用Spamtrap）而被列入黑名单。<br /> 对于每个电子邮件发送，两个默认的排版规则会比较收件人电子邮件地址与此列表中包含的禁止地址或域名。 如果存在匹配项，则该收件人将被排除在目标人群之外。<br /> 有关详细信息，请参阅详 <a href="../../administration/using/filtering-rules.md#default-deliverability-exclusion-rules">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 常规优化<br /> </td> 
   <td> 此更新包括许多更改和修补程序，可修复我们的客户遇到的问题。 并对全球平台性能进行了优化。 <br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches}

#### 常规 {#general}

* 修复了多个安全问题。
* 修复了REST API中空字段或重复字段的几个问题。
* 您现在可以直接从应用程序主页创建SMS消息和推送通知。

#### 电子邮件和SMS消息 {#emails-and-sms-messages}

* 修复了阻止用户在内容编辑器中上传zip文件的问题。
* 修复了在发送证明后无法打开证明的问题。
* 修复了在访问A/B测试电子邮件上的报告时，导 **[!UICONTROL Hot Clicks]** 致显示错误消息的问题。
* 修复了使用模式进行的修改无 **[!UICONTROL Show source]** 法应用的问题。
* 修复了可能阻止导入预测主题行xml模型文件的问题。
* 现在，中提供了专门用于为受培训的主题行模型导入数据的新屏幕 **[!UICONTROL Administration > Channels > Emails > Predictive Subject Line]** 。
* 修复了允许非管理员用户在电子邮件配置屏幕中编辑授权掩码的问题。

#### 推送通知 {#push-notifications}

* 修复了在使用模板发送推送通知后，发送日志和事件日志无法显示给收件人的问 **[!UICONTROL Send push on profiles]** 题。
* 修复了可能阻止创建新移动应用程序的问题。

#### 工作流 {#workflows}

* 修复了使用活动时发生的性能 **[!UICONTROL Subscription]** 问题。
* 修复了当工作流的内部名称包含空格时，该工作流无法正常工作的问题。

#### 集成 {#integrations}

* 修复了在电子邮件中使用从Adobe Marketing cloud共享的图 **像选项时** ，可能导致显示错误的问题。

#### 自定义资源 {#custom-resources}

* 增强的API在两个扩展API字段的出版物之间记录预览。
* 修复了自定义资源在发布之前无法删除的问题。
* 修复了阻止使用动态字段扩展配置文件和设置标识符键的问题。
* 修复了在自定义资源中添加链接时可能发生的问题。

## 16.10版- 2016年10月 {#release-16-10---october-2016}

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
   <td> 电子邮件预测主题行<br /> </td> 
   <td> 在编辑电子邮件时，新选项可让您尝试不同的主题行并在发送电子邮件之前获得其打开率的估计。 这可以通过根据您过去的交付数据培训自己的模型或使用特定于您所在行业的预定义模型来实现。 此功能适用于电子邮件和仅包含英语内容的数据库。 <br /> 有关启用和使用它的详细信息，请参阅详细 <a href="../../designing/using/subject-line.md#predictive-subject-line">文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> SMS交易消息<br /> </td> 
   <td> SMS渠道已添加到Adobe Campaign的交易消息传递功能中。 交易消息现在支持两个渠道：电子邮件和短信<br /> 有关详细信息，请参阅详 <a href="../../administration/using/configuring-transactional-messaging.md#creating-an-event">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交易消息的跟进消息<br /> </td> 
   <td> 现在可以创建面向活动的工作流。 这意味着您可以向之前收到交易消息的客户发送跟进消息。 您可以按事件类型、事件广播和跟踪日志过滤目标。 在后续消息中，您将能够利用事件的内容（有效负荷）。 <br /> 有关详细信息，请参阅详 <a href="../../channels/using/follow-up-messages.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 扩展的Profile &amp; Services API<br /> </td> 
   <td> 您现在可以在Profile和Services API中显示扩展字段。 发布机制允许API映射配置文件或服务自定义资源的扩展字段。 为了使其正常工作， <strong>已添加Datamodel</strong> 角色。 此新角色允许用户配置一组管理员，他们将有权访问数据模型。<br /> 有关详细信息，请参阅详 <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-1}

#### 常规 {#general-1}

* 修复了多个安全问题。

#### 电子邮件和SMS消息 {#emails-and-sms-messages-1}

* SMS外部帐户配置屏幕( **[!UICONTROL Administration > Channels > SMS > SMS accounts]** )已得到改进。 在部分中添加了多个参 **[!UICONTROL SMSC specifics]** 数，以支持“文本”字段中的错误代码。

#### 推送通知 {#push-notifications-1}

* 修复了在编辑基于(mobileApp)模板的推送通知受众时无法显示预定义过 **[!UICONTROL Send via push notification]** 滤器的问题。
* 移动应用程序配置屏幕( **[!UICONTROL Administration > Channels > Push Notification > Mobile applications]** )现在显示一条消息，指示已成功创建iOS或Android平台。

#### 登陆页面 {#landing-pages}

* 修复了在提交登录页面表单时无法发送确认电子邮件的问题。

#### 受众和查询 {#audiences-and-queries}

* 修复了在查询编辑器中选择配置文件时出现的几个问题。

#### 交易消息 {#transactional-messages}

* 修复了阻止取消发布事务模板的错误。
* 修复了导致触发事件显示在事件列表中的问题。

#### 集成 {#integrations-1}

* 修复了在更新共享受众后无法在分发中使用该受众的问题。
* 修复了阻止在登录页面中使 **[!UICONTROL Image shared from Adobe Marketing Cloud]** 用共享资产（选项）的问题。
* 修复了编辑从Adobe Audience Manager导入的共享受众时发生的问题。

## 16.9版- 2016年9月 {#release-16-9---september-2016}

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
   <td> 再营销触发器<br /> </td> 
   <td> 核心服务触发器与 <span class="uicontrol">Adobe</span> Campaign之间的集成允许您向客户发送个性化电子邮件，作为对Adobe Analytics在您的网站上跟踪的特定行为的响应（15分钟内）。<br /> 在Adobe Marketing cloud中，您可以定义不同的触发器，即要监视的客户行为，例如所有放弃购物车或其表单的客户、从其购物车中删除产品的客户，甚至会话过期的客户。 在创建触发器时，您定义触发器的条件和在活动（上传）中将发送到Adobe Campaign的数据。 <br /> 在Adobe Campaign中，您选择之前创建的触发器，使用数据库数据丰富活动数据，并定义一个链接到该触发器的交易消息模板。 例如，当客户端放弃其购物车时，会向Adobe Campaign发送一个活动，然后Adobe Campaign会通过再营销电子邮件利用此活动，该电子邮件在15分钟内发送给客户。<br /> 有关详细信息，请参阅详 <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交易消息：暂停／取消发布<br /> </td> 
   <td> 您现在可以在更新事务模板的内容时暂停其发布。 不再发送相应的消息，但是它们存储在数据库中。 恢复时，将处理已排队的消息，如果消息尚未过期，则发送这些消息。<br /> 有关详细信息，请参阅详 <a href="../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication">细文档</a>。<br /> 您现在还可以取消发布活动和交易模板。 相应的消息不再发送，也不再存储在数据库中。<br /> 有关详细信息，请参阅详 <a href="../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 多品牌<br /> </td> 
   <td> 拥有多个品牌的客户现在可以在同一实例中管理它们。 品牌是由Adobe Campaign实例管理员管理的一项功能，它允许您在Adobe Campaign中集中配置与品牌相关的所有参数。 这包括一些事项，如指向更多技术参数（如跟踪URL、Web分析、服务器URL、域名等）的徽标。<br /> 有关详细信息，请参阅详 <a href="../../administration/using/branding.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 响应式电子邮件设计预览<br /> </td> 
   <td> 此功能允许您测试电子邮件对不同类型设备的响应性。 在电子邮件预览中，已添加一个网格，以在各种屏幕大小上测试您的电子邮件。<br /> </td> 
  </tr> 
  <tr> 
   <td> 推送通知<br /> </td> 
   <td> 新的渠道已经添加，使营销人员能够在iOS和Android移动设备上发送个性化的分段推送通知。 消息可以通过单次传送或使用工作流活动发送。 将来版本中将提供与事务消息传递的兼容性。 此渠道利用Mobile核心服务的SDK(在此 <a href="https://marketing.adobe.com/developer/gallery/marketing-cloud-mobile-libraries">提供</a>)。<br /> 有关详细信息，请参阅详 <a href="../../channels/using/about-push-notifications.md">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-2}

#### 常规 {#general-2}

* 此版本在界面列表中引入了新的过滤和搜索功能。 此新增功能可用于日志（交付、跟踪）、服务（订阅、订阅历史记录）、受众和工作流转换。
* 修复了与客户档案中的接触点数有关的几个显示问题。
* 修复了多个类型学问题。

#### 电子邮件和SMS消息 {#emails-and-sms-messages-2}

* 修复了允许编辑错误校样的错误。 它们现在为只读。
* 修复了在SMS过长或存在编码问题时导致收件人被列入黑名单的问题。

#### 自定义资源 {#custom-resources-1}

* 修复了使用自定义资源的高级过滤器时无法显示所有结果的错误。

#### 交易消息 {#transactional-messages-1}

* 前缀现在会自动添加到新事件定义的标识符中。
* 界面中表示事务消息的图标已更改。

#### 集成 {#integrations-2}

* 修复了通过Adobe Target中的动态图像选项插入高分辨率图像时 **会出现的显示错误** 。
* 修复了即使未在AMC数据源中设置目标ID也允许保存共享受众的错误。

## 16.7版- 2016年7月 {#release-16-7---july-2016}

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
   <td> 丰富的交易消息<br /> </td> 
   <td> 您现在可以将交易模板与Adobe Campaign数据库关联起来，以恢复允许您丰富交易消息内容的信息。<br /> 有关详细信息，请参阅详 <a href="../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 图像的动态URL<br /> </td> 
   <td> 此新功能允许您通过插入内容块和动态文本来实现图像源的个性化，以便进行跟踪和个性化。<br /> 然后，通过在图像URL中输入参数，从AEM资产(S7)动态媒体的功能中获利成为可能，这其中之一就是。 例如，您可以发送一封包含个性化图像的电子邮件，其中注明“Hello Alexandre，获取有关即将在巴黎举行的活动的最新消息！” 或者“你好，弗兰克，获取有关即将在纽约举行的活动的最新消息！”<br /> 有关详细信息，请参阅详 <a href="../../designing/using/personalization.md#personalizing-urls">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 与People Core service集成<br /> </td> 
   <td> Adobe Campaign与People Core Service <strong>(Profiles &amp; Audiences)之间的集成现在涵盖Adobe Marketing Cloud</strong> Declared ID。<br /><strong> 这意味着您可以导入区段并导出由访客ID或 </strong>Declared<strong>ID组成 </strong>的受<br />众。 有关详细信息，请参阅详 <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付日志<br /> </td> 
   <td> MTA日志（交付服务器）现在显示每条消息的完整历史记录，特别是所有交付尝试和相关的错误状态，这对应用程序的性能没有影响。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-3}

#### 常规 {#general-3}

* 修复了一个错误，该错误可能会导致显示不相关的字段而不是需要完成的字段。 在查询中编辑条件时，比较运算符多次修改后会发生这种情况。
* 修复了在为日期字段定 **[!UICONTROL The last X days/months/quarters/years]** 义相对筛选条件时选项的行为。 计算的时段现在是相对于服务器日期和时间的滑动时段，而不是基于日历的时段。

#### 工作流 {#workflows-1}

* 修复了一个错误，该错误会在屏幕中返回一个错误的值列表，以便在活动的属性中选择定位维 **[!UICONTROL Query]** 度。
* 修复了在活动中向集合元素添加平均聚合或计数聚合时， **会强制选择** “存在”运算符的错误 **[!UICONTROL Query]** 。

#### 内容编辑 {#content-editing}

* 修复了在导入HTML内容时可能导致显示问题（响应式设计）的错误：当内容在导入后首次打开时，样式属性不再被重写。
* 修复了在动态内容变体中添加条件时导致的非阻塞错误。
* 修复了在登录页面的内容中添加复选框所导致的错误。 复选框不可用。
* 修复了在将光标放在相关块的开头时删除块中的文本时可能发生的错误。

#### 交易消息 {#transactional-messages-2}

* 集成网站时，您现在可以为任何给定活动定义到期日期。 一旦传递了此日期，便无法再发送与活动对应的消息。

## 16.6版- 2016年6月 {#release-16-6---june-2016}

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
   <td> Profiles and Services API<br /> </td> 
   <td> Adobe Campaign配 <span class="uicontrol">置文件和服务</span> API可在 <a href="https://www.adobe.io/products/campaign">adobe.io门户中找到</a> 。 这允许更新、添加和删除Adobe Campaign配置文件，并允许它们通过REST调用订阅或取消订阅服务。<br /> 有关详细信息，请参 <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">阅API的详细说明</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-4}

#### 常规 {#general-4}

* 现在，移动设备上禁用了工具提示，以确保屏幕上显示的信息易于阅读。
* 修复了阻止用户在iPad屏幕上滚动特定区域的内容的错误。
* 修复了在Internet Explorer 11中编辑内容时遇到的多个兼容性错误。
* 修复了在首次数据导入失败时无法访问详细日志的错误。
* 修复了可能阻止保存范围过滤器的错误。
* 修复了在配置显示列表的方式时阻止显示资源元素的错误。
* 修复了查询编辑器资源管理器中的错误。 搜索字段返回的结果保留在搜索历史记录中，并在每次新搜索时继续显示。

#### 电子邮件和SMS消息 {#emails-and-sms-messages-3}

* 修复了一个错误，该错误导致链接到弹回的信息无法在交付日志中恢复。
* 修复了阻止访问事务消息的动态内容块中的上下文的错误。
* 修复了阻止在电子邮件内容中的动态文本上定义URL链接的错误。
* 修复了传送创建向导顶栏的显示。
* 交付的主要密钥无法再用作个性化字段。

#### 工作流 {#workflows-2}

* 工作流的两个活动之间的过渡现在显示从一个活动计算并传输到另一个活动的元素计数。
* 现在，在活动中添加其他数据时，不兼容的字段会被隐 **[!UICONTROL Query]** 藏。
* 添加其他数据时显示的聚合定义窗口已改进为仅提供与使用数据兼容的选件选项(例如：计算平均值只能用于数值数据)。
* 现在，只有具有管理权限的用户才能执行现成的技术工作流。

#### 登陆页面 {#landing-pages-1}

* 修复了一个错误，该错误可能会截断登录页面属性中的32位AES编码密钥。
* 修复了在定义可见性条件或向登录页面添加动态内容时，查询编辑器无法正确显示的错误。

#### 自定义资源 {#custom-resources-2}

* 现在， **[!UICONTROL Switch to parameters]** 在定义与配置文件对服务的订阅相关的筛选器时，该选项处于隐藏状态。
* 修复了从自定义资源配置0-1类型链接时可能发生的错误。
* 修复了在自定义资源中添加“日期”和“时间”类型字段时，可能会阻止编辑定义的“常 **数”默认值****** （如果相关）的错误。

## 版本16.5 - 2016年5月 {#release-16-5---may-2016}

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
   <td> 预定义的过滤器<br /> </td> 
   <td> 管理员现在可以创建高级过滤器，这些过滤器以预配置规则的形式显示在查询编辑器中。 例如，选择这些过滤器可让用户在定义受众时更轻松地在简化的界面中开发复杂配置。<br /> 有关详细信息，请参阅详 <a href="../../developing/using/configuring-filter-definition.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流：订阅服务<br /> </td> 
   <td> 新的订 <span class="uicontrol">阅服务活动</span> ，提供了通过单个操作将多个配置文件订阅到服务或从服务取消订阅的可能性。<br /> 执行定位或导入包含已识别数据的文件后，可以使用此活动。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/subscription-services.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流：数据丰富<br /> </td> 
   <td> “其 <span class="uicontrol">他数据</span> ”选项卡现在在“查询 <span class="uicontrol">类型</span> ”活动中可用。 利用此功能，您可以丰富查询所针对的数据，并将这些数据传输到以下可利用的工作流活动。<br /> 在添加了附加数据之后，您可以通过基于定义的附加数据创建条件来对初始目标数据应用附加的过滤器级别。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/query.md#enriching-data">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 上下文帮助<br /> </td> 
   <td> 现在，上下文帮助功能可跨不同的Adobe Campaign屏幕使用。 这意味着，只需单击一下，即可直接访问有关您当前使用的功能的文档。 要显示上下文帮助，请单击“?” 图标，如下例所示。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-5}

#### 常规 {#general-5}

* 各种界面符合Marketing cloud标准的新功能。
* 不同下拉列表类型的标准化。

#### 电子邮件和SMS消息 {#emails-and-sms-messages-4}

* 修复了在指定错误地址掩码时无法发送电子邮件的错误。
* 现在支持TLS协议以通过电子邮件发送。 MX管理中的新列允许您为每个域定义所需的TLS行为。
* SMS界面已得到改进。

#### 工作流 {#workflows-3}

* 各种工作流界面新增功能。
* 修复了显示快速操作时发生的错误。
* 修复了使用包含1-N链接的类型活动时可能导致 **[!UICONTROL Segmentation]** 工作流失败的错误。
* 修复了阻止在混合设备上打开工作流的过渡的错误。
* 修复了首次启动工作流时无法显示暂停按钮的错误。

#### 内容编辑器 {#content-editor}

* 内容编辑器现在允许您个性化电子邮件或登录页面中包含的任何URL。 请参阅详细 [文档](../../designing/using/personalization.md#personalizing-urls)。
* 修复了在传送的创建向导中添加图像并随后对其内容进行修改时可能导致图像丢失的错误。

#### 自定义资源 {#custom-resources-3}

* 修复了在自定义资源的配置屏幕中添加个性化的1-N类型链接时出现的错误。
* 改进了准备和发布自定义资源时进度栏的显示。
* 修复了显示自定义资源的链接列表时出现的错误。

#### 交易消息 {#transactional-messages-3}

* 优化了界面的用户友好性以及事务消息引擎的性能和鲁棒性。
* 现在可以暂时暂停交易消息模板的发布。 有关详细信息，请参阅详细 [文档](../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication)。
* 修复了可能导致具有不兼容定位维的内容块添加到事务消息模板中的错误。
* 修复了阻止在事件配置屏幕中显示API预览的错误。

#### 受众和查询 {#audiences-and-queries-1}

* 有关在查询编辑器中使用日期的各种修补程序。 请参阅详细 [文档](../../automating/using/editing-queries.md#creating-queries)。

#### 管理 {#administration}

* 修复了“标准用户”安全组名称相关的错误，该错误导致用户无法登录。

## 16.3版- 2016年3月 {#release-16-3---march-2016}

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
   <td> 界面和导航<br /> </td> 
   <td> Adobe Campaign界面经过改进，使导航和操作更简单、直观。<br /> 您现在可以从应用程序的顶栏进行导航。 通过选择 <strong>Adobe Campaign徽标，可以访问高级菜</strong> 单。<br /> 有关详细信息，请参阅详 <a href="../../start/using/interface-description.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流：节省受众<br /> </td> 
   <td> 现在，“保存 <span class="uicontrol">受众”活动中提供了新选项</span> “创建然后更新 <span class="uicontrol">受众</span> ”。 此选项允许您手动输入受众标签。 如果输入的标签与现有受众相对应，则将更新该标签。 如果受众不存在，则将创建该受众。<br /> 此外，每次执行工作流时，受众都将进行更新（再次）。<br /> 您始终可以选择受众更新模式：在每次执行时用新数据完成受众或替换整个受众数据。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/save-audience.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流：细分<br /> </td> 
   <td> “ <span class="uicontrol">分段</span> ”活动现在允许用户对临时资源的数据进行分段。 例如：导入文件的数据。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/segmentation.md">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-6}

#### 常规 {#general-6}

* 修复了在对列表排序时出现的显示错误：只能为某些类型的数据反转表示列排序顺序的箭头。
* 修复了在查询中添加规则时限制下拉菜单中显示的元素数的错误。

#### 电子邮件和SMS消息 {#emails-and-sms-messages-5}

* 修复了可能阻止访问电子邮件呈现报告的错误。
* 如果未提供发送者地址，消息的准备发送阶段现在会返回错误。

#### 工作流 {#workflows-4}

* 在提取CSV格式文件时，某些文件格式选项是可见的，但未考虑这些选项。 这些选项现在不再可见。
* 修复了选中类型文件传 **[!UICONTROL Delete the source files after transfer]** 输选项时导致的 **[!UICONTROL SFTP]** 错误。
* 修复了刷新页面后无法显示计数 **[!UICONTROL Query]** 器和数据预览的错误。
* 修复了在工作流中打开某些过渡导致的错误，尤其是在定位和筛选维度不同的交付活动或查询之后。
* 修复了在添加活动后未保存工作流时，阻止将个性化字段插入工作流的分发活动的错误。
* 修复了阻止显示电子邮件分发活动的出站过渡定位维度的错误。

#### 登陆页面 {#landing-pages-2}

* 修复了导致个性化字段无法在登录页面的可本地化内容块中正常工作的错误。

#### 自定义资源 {#custom-resources-4}

* 修复了一个错误，该错误导致在选中资源屏幕定义选项以及在中选择了多个字段的情况下，无法执行对自定义资源的搜索 **[!UICONTROL Add search fields]****[!UICONTROL Filter zone composition]** 。

## 16.2版- 2016年2月 {#release-16-2---february-2016}

### 新功能 {#new-capabilities-7}

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 说明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 电子邮件的A/B测试<br /> </td> 
   <td> 您现在可以对电子邮件的内容、主题或发件人名称进行A/B测试。 此新功能最多可测试元素的三个变体。<br /> 从特定于A/B测试的新模板之一创建电子邮件时，创建向导中的新步骤允许您定义测试的参数。<br /> 有关详细信息，请参阅详 <a href="../../channels/using/designing-an-a-b-test-email.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 品牌管理<br /> </td> 
   <td> 您现在可以定义一个或多个品牌以集中输入影响品牌标识的参数。 Adobe Campaign允许您创建这些品牌并将它们链接到交付或登录页面模板。<br /> 有关详细信息，请参阅详 <a href="../../administration/using/branding.md#assigning-a-brand-to-an-email">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流：增量查询<br /> </td> 
   <td> 新的工作流活动 <span class="uicontrol">增量查询</span> ，允许您执行查询，每次执行时，该查询只针对新结果。 之前执行的结果将自动排除。 链接到“ <span class="uicontrol">调度程序</span> ”活动，您可以定义增量查询的执 <span class="uicontrol">行频率</span> 。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/incremental-query.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交易消息<br /> </td> 
   <td> 改进了事务消息界面的用户友好性。 与交易消息关联的所有业务流程管理当前都集中在“营销计划 <span class="uicontrol">”&gt;“交</span> 易消息”菜单中 <span class="uicontrol"></span> 。 事件配置也得到改进。 现在，活动可独立于自定义资源进行管理。<br /> 有关详细信息，请参阅详 <a href="../../channels/using/about-transactional-messaging.md">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-7}

#### 常规 {#general-7}

* 修复了报告、列表和查询中的多个显示错误。
* 修复了移动设备上的多个兼容性和显示错误。

#### 电子邮件和SMS消息 {#emails-and-sms-messages-6}

* 修复了在创建消息（电子邮件或SMS）时，用于插入个性化字段的按钮无法显示的错误。
* 修复了一个错误，该错误可能会阻止通过Mblox发送的SMS消息正确传输。

#### 受众和查询 {#audiences-and-queries-2}

* 修复了在修改过滤维后在查询中添加附加条件时可能导致的计数错误。
* 修复了在预览查询结果时可能导致分页错误的错误。

#### 内容编辑 {#content-editing-1}

* 修复了一个错误，该错误可能导致在使用个性化枚举时无法正确考虑动态内容配置。

#### 工作流 {#workflows-5}

* 修复了一个错误，该错误可能会阻止在活动的选项卡中有空行时执行工作流 **[!UICONTROL Fields to update]** 中的任何操 **[!UICONTROL Update data]** 作。
* 修复了阻止导入包含地理／组织单元信息的数据的错误。
* 修复了添加规则类型 **[!UICONTROL Change axis]** 所导致的 **[!UICONTROL Exclusion]** 错误。
* 修复了在操作活动的出站过渡时可能导致创建不需要的额外区段的错 **[!UICONTROL Segmentation]** 误。
* 修复了在工作流模板中加载文件导致的错误。
* 修复了一个错误，该错误会阻止将空间用作活动中的列分隔 **[!UICONTROL Load file]** 符。

#### 自定义资源 {#custom-resources-5}

* 修复了在导出时发布自定义资源时，导入包后无法重新起草自定义资源状态的错误。

#### 包 {#packages}

* 修复了阻止导出包含工作流的包的错误。
* 修复了一个错误，该错误会阻止选择同一资源的多个元素。

## 16.1版- 2016年1月 {#release-16-1---january-2016}

### 新功能 {#new-capabilities-8}

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 说明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 报告<br /> </td> 
   <td> 添加了以下电子邮件特定报告：投 <span class="uicontrol">诉</span> 、打 <span class="uicontrol">开</span> 、取消 <span class="uicontrol">订阅</span> 。<br /> 改进了以下报告：交 <span class="uicontrol">货汇总、弹</span> 回汇总 <span class="uicontrol">、交货</span> 吞吐量 <span class="uicontrol">、跟踪指</span> 标 <span class="uicontrol"></span> 。<br /> 有关详细信息，请参阅详 <a href="../../reporting/using/defining-the-report-period.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 查询编辑<br /> </td> 
   <td> 查询编辑器已得到改进，现在允许您扫描 <strong>1-N类型链接</strong> 。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/editing-queries.md#creating-queries">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 内容个性化<br /> </td> 
   <td> 对于电子邮件或登陆页面编辑，内容块显示条件的输入界面已得到改进。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流：导入时的列定义<br /> </td> 
   <td> 现在 <span class="uicontrol">通过“加载文件</span> ”活动，您可以详细配置导入文件的列：预期的数据类型、日期和时间格式、空值或错误时要应用的处理以及值重映射。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/load-file.md#column-format">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> SMS编码的映射<br /> </td> 
   <td> 现在，可以为不使用标准编码的提供商定义个性化SMS消息的编码映射。 管理员可以进行个性化映射的配置，并定义其应考虑的顺序。<br /> 有关详细信息，请参阅详 <a href="../../administration/using/configuring-sms-channel.md#smsc-specifics">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-8}

#### 常规 {#general-8}

* 改进了与Internet explorer和Chrome的兼容性，用于混合／触摸屏设备。
* 修复了一个错误，该错误可能导致为新用户／配置文件／测试配置文件输入的所有数据丢失（如果指示的电子邮件地址包含语法错误）。

#### 电子邮件和SMS消息 {#emails-and-sms-messages-7}

* 修复了一个错误，该错误会阻止在电子邮件预览屏幕中生成内容缩略图。
* 修复了一个错误，该错误会阻止消息（电子邮件或SMS）的原始内容显示在消息预览屏幕中。

#### 受众和查询 {#audiences-and-queries-3}

* 修复了一个错误，该错误可能会阻 **止在** “服务”资源中创建 **Query** 类型受众。
* 修复了在高级模式下编辑查询条件时可能无法正确显示函数列表的错误。
* 修复了一个错误，该错误可能会阻止在 **Query** 类型受众中包含基于集合的条件时创建该受众。
* 修复了一个错误，该错误可能会阻止创建包含交付KPI筛选器的查询。
* 修复了一个错误，该错误会阻止预览从工作流创建的受众的内容。

#### 自定义资源 {#custom-resources-6}

* 修复了一个错误，该错误在自定义资源包含具有动态默认值的字段时可能导致服务器崩溃。
* 修复了在定义自定义资源的屏幕时，在部分中移 **[!UICONTROL Detail screen configuration]** 动然后删除元素所导致的错误。
* 修复了为未在其可能值范围中包含 **0** 的整数列表定义默认值时 **** 发生的错误。
* 修复了一个错误，该错误可能会阻止在重新初始化后在自定义资源的详细信息屏幕配置中添加元素。

#### 工作流 {#workflows-6}

* 修复了一个错误，该错误可能导致工作流中所有活动的日志被显示，而不是只显示选定活动的日志。
* 修复了活动中的错 **[!UICONTROL Scheduler]** 误。 该 **[!UICONTROL Day of the month]** 选项未正确考虑并替换为 **[!UICONTROL Week day]** 。
* 修复了在过期模式设置 **[!UICONTROL Scheduler]** 为时，可能导致活动无法正确工作的错误 **[!UICONTROL After a certain number of iterations]** 。
* 修复了使用活动导出数据时发生的错 **[!UICONTROL Extract file]** 误。 导出文件中的行数低于导出的元素数。
* 修复了一个错误，该错误可能会阻止选 **[!UICONTROL Load file]** 择活动中的文件。
* 修复了阻止删除活动中要更新的字段 **[!UICONTROL Update data]** 的错误。
* 修复了在打开工作流执行日志后无法保存对工作流所做的修改的错误。
* 修复了将活动配置 **[!UICONTROL Load file]** 为从其入站过渡中使用该文件并且该文件已使用活动加载时导致该活动执行两次的错误 **[!UICONTROL Transfer file]** 问题。
* 修复了一个错误，该错误可能会阻止某些临时实体被排除活动正 **确处理** 。
* 修复了一个错误，该错误可 **[!UICONTROL Query]** 能会在活动中配置的定位维和筛选维不同时，导致活动无法正确执行。
* 修复了一个错误，该错误与添加到活动的出站过渡的自 **[!UICONTROL Fork]** 动命名有关，该错误会阻止保存工作流。

#### 内容编辑 {#content-editing-2}

* 修复了在编辑内容时可能导致图标或搜索栏显示不理想的错误。

#### 登陆页面 {#landing-pages-3}

* 修复了阻止使用包导入导入登录页面的错误。

#### 交易消息 {#transactional-messages-4}

* 现在，可以在消息中心推送代理运营商的安全参数中指定受信任的IP地址。
* 修复了可能阻止创建新类型事件的错误。

## 15.11版- 2015年11月 {#release-15-11---november-2015}

### 新功能 {#new-capabilities-9}

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 说明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> SMS频道<br /> </td> 
   <td> 您现在可以使用Adobe Campaign发送SMS消息。<br /> 与电子邮件一样，您也可以从营销活动和营销活动列表中创建新的SMS分发。 您还可以从工作流中创建单个发送和重复的SMS消息。<br /> 这些SMS发送基于可从分发模板列表中配置的模板。 默认模板可用。<br /> 这些SMS交付使用SMPP 3.4协议，大多数SMS路由器都使用该协议。<br /> 有关详细信息，请参阅详 <a href="../../channels/using/about-sms-messages.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 探索过渡<br /> </td> 
   <td> 您现在可以在工作流的上次过渡中浏览数据及其结构。 这允许您检查由每个活动应用的进程是否与您的需求相对应。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流中的文件预处理和后处理<br /> </td> 
   <td> 现在，通过“加载文件”和“提取文件”活动导入或导出数据文件时，可以对该数据文件进 <span class="uicontrol">行其</span> 他 <span class="uicontrol">处理</span> 。<br /> 默认情况下，您可以在这些活动中解压缩和压缩GZIP格式文件。<br /> 有关详细信息，请参阅有关“加载文件”和“ <a href="../../automating/using/load-file.md">提取文件</a> ” <a href="../../automating/using/extract-file.md">活动的文档</a> 。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付性报告<br /> </td> 
   <td> 现在提供电子邮件渲染报告。 此报告允许您根据用于读取消息的支持和消息服务查看消息的不同呈现方式。<br /> 报告摘要还显示接收的消息、垃圾邮件、未接收的消息和等待接收的消息的数量。<br /> 有关详细信息，请参阅详 <a href="../../sending/using/email-rendering.md#email-rendering-report-description">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 包管理<br /> </td> 
   <td> 现在可以导入和导出包中的图像。<br /> </td> 
  </tr> 
  <tr> 
   <td> 快速操作<br /> </td> 
   <td> 将指针悬停在列表或工作流中的某个元素上方或之后时，会显示某些操作。 其中一些操作现在显示为相关元素周围的图标以便于访问。 这些快速操作可用于复制元素、删除元素、显示详细信息等。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-9}

#### 常规 {#general-9}

* 修复了一个错误，该错误会阻止从管理员帐户访问实例的常规参数。
* **现在** ，自定义资源中正确考虑了浮动数据。
* 修复了在已执行的简化导入列表中的显示错误，该错误在相应模板的状态被修改时导致。

#### 登陆页面 {#landing-pages-4}

* 修复了登录页面模板的某些元素，这些元素在英语实例中可能以法语显示不正确。

#### Audiences {#audiences}

* 修复了一个错误，该错误可能会阻止从Adobe Marketing cloud导入的受众显示在受众列表中。
* 修复了在定义查询时可能强制区分大小写的错误。
* 修复了在定义查询时可能阻止筛选受众的错误。
* 修复了一个错误，该错误可能会阻止在受众中取消操作。

#### 工作流 {#workflows-7}

* 修复了一个错误，该错误可能会阻止手动配置活动中 **[!UICONTROL Update data]** 要更新的字段。
* 修复了在将活动放入图 **[!UICONTROL Query]** 中后，如果未保存工作流，则在打开时可能导致活动无限加载的错误。
* 修复了在计算或预览从工作流中选择的受众时可能导致服务器停止 **[!UICONTROL Query]** 的错误。
* 修复了在工作流中的活动打开时可能显示的非关键错误。
* 修复了阻止将活动配 **[!UICONTROL Scheduler]** 置为每天执行多次工作流的错误。
* 修复了一个错误，该错误可能导致无法执行查询的字段显示在某些工作流活动中。
* 修复了一个错误，该错误可能会阻止用户查找从出站转移的 **[!UICONTROL Query]** 分发中添加的KPI。
* 修复了将文件导入工作流后可能无法创建文件受众的错误。
* 修复了一个错误，该错误在使用了资源的 **location/address3** 字段时可能会阻止在配置文件上更新数据。
* 修复了阻止在工作流中复制异构活动集合的错误。
* 修复了阻止显示SQL的错误，从而允许诊断工作流中重复传送的错误。

#### 内容编辑器 {#content-editor-1}

* 修复了导致无法在登录页面或电子邮件的源代码中进行搜索的错误。

#### 包 {#packages-1}

* 修复了可能阻止某些类型的元素在包中导出的各种错误（特别是登录页面、工作流）。
* 修复了一个错误，该错误会导致在修改标签时显示以前的包导入标签。
* 修复了可能导致不兼容资源显示在可导出资源列表中的错误。

## 版本15.10 - 2015年10月 {#release-15-10---october-2015-}

### 新功能 {#new-capabilities-10}

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 说明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 工作流：重复数据消除活动<br /> </td> 
   <td> 现在，工作流中提供了专用于重复数据消除的新活动。 此活动允许您根据所选条件筛选目标中的任何副本。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/deduplication.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流：改进的图表<br /> </td> 
   <td> 在工作流工作区中，您现在可以使用多个键盘快捷键来选择、打开和删除活动。<br /> 活动对齐方式也得到改进，使工作流能够更好地以可视方式组织。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/workflow-interface.md#workspace">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流：提取文件活动<br /> </td> 
   <td> 现在，导出的日期和时间会自动添加到使用Extract文件活动导出的文件的 <span class="uicontrol">标签中</span> 。 这样生成的文件是唯一的。<br /> </td> 
  </tr> 
  <tr> 
   <td> 简化的数据导入<br /> </td> 
   <td> 现在，执行简化导入的模板的名称在导入列表中和每个导入的详细信息中默认可见。<br /> </td> 
  </tr> 
  <tr> 
   <td> 自定义资源<br /> </td> 
   <td> 改进并扩展了管理和定义自定义资源链接的可能性。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-10}

#### 电子邮件 {#email}

* 修复了一个错误，该错误导致服务取消订阅链接无法从镜像页面正常工作。
* 修复了一个错误，该错误会阻止电子邮件传送标签在电子邮件编辑页面上正确显示。
* 修复了一个错误，该错误可能会阻 **[!UICONTROL Routing]** 止在复制的分发模板中选择外部帐户。

#### Audiences {#audiences-1}

* 修复了在查询中使用1-N链接时在受众计数期间导致的错误。
* 修复了一个错误，该错误可能导致无法在电子邮件分发的目标受众中选择配置文件。

#### 工作流 {#workflows-8}

* 修复了在工作流中配置电子邮件分发时可能导致显示问题的错误。
* 修复了可能导致活动无法正 **[!UICONTROL Load file]** 常工作的错误。 随后将显示空白错误消息。
* 修复了可能导致活动无法正 **[!UICONTROL Transfer file]** 常工作的错误。 访问权限并非始终正确考虑。
* 修复了一个错误，该错误在工作流包含文件时会阻止导出文件 **[!UICONTROL Recurring email]** 。
* 修复了一个错误，该错误可能会阻止在工作流中创建电子邮件分发，或阻止将主题和定义的内容考虑在内。
* 修复了在配置简化的导入模板的工作流时，会阻止在活 **[!UICONTROL Update data]** 动中选择对帐密钥的错误。
* 修复了在删除活动后无法保存工作流的错误。

#### 平台 {#platform}

* 修复了一个错误，该错误可能会阻止在自定义资源包含指向该元素资源类型的链接时创建新元素。
* 修复了可能导致某些日志写入延迟15分钟的错误。
* 修复了一个错误，该错误会阻止在按或列排序时显示营销活 **[!UICONTROL Date]** 动列 **[!UICONTROL Indicators]** 表。

#### 登陆页面 {#landing-pages-5}

* 修复了在选择测试配置文件以预览登陆页面时发生的错误。

#### 交易消息 {#transactional-messages-5}

* 修复了在删除测试配置文件上的事件后可能导致应用程序崩溃的错误。

#### 报告 {#reports}

* 修复了一个错误，该错误可能导致为报告和发送错误 **[!UICONTROL deliveryThroughputReport]** 的数据 **[!UICONTROL deliveryTrackingReport]** 。

#### 内容编辑器 {#content-editor-2}

* 修复了在处理动态内容块时发生的HTML标签管理错误。

## 15.8版- 2015年8月 {#release-15-8---august-2015}

### 新功能 {#new-capabilities-11}

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 说明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 简化的数据导入<br /> </td> 
   <td> 您现在可以以简化的方式导入数据。<br /> 用户只需选择管理员预定义的模板，然后上传包含要导入的数据的文件。 对于用户透明地执行在模板中定义的工作流，该用户可以访问导入结果的详细信息以及任何错误的日志。<br /> 这些文件中的数据可以插入到数据库中，或作为直接创建受众的手段。<br /> 有关详细信息，请参阅详 <a href="../../automating/using/about-data-import-and-export.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 创建计划和营销活动<br /> </td> 
   <td> 现在，营销活动和计划已配置好，因此创建之日会自动用作开始日期。<br /> 结束日期根据开始日期进行配置，例如：<br /> 
    <ul> 
     <li> D+186计划 </li> 
     <li> D+61营销活动 </li> 
    </ul>  有关详细信息，请参阅详 <a href="../../start/using/programs-and-campaigns.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 电子邮件<br /> </td> 
   <td> 跟踪的URL列表现在为只读。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交易消息<br /> </td> 
   <td> 现在，您可以管理针对创建帐户后的密码更改或确认等事件的个性化交易消息。<br /> 有关详细信息，请参阅详 <a href="../../channels/using/about-transactional-messaging.md">细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 自定义资源<br /> </td> 
   <td> 添加了以下几个功能：扩展测试配置文件、状态管理和删除资源。<br /> 有关详细信息，请参阅详 <a href="../../developing/using/resource-statuses.md">细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-11}

#### 显示 {#display}

* 修复了一个错误，该错误可能导致在Safari的查询编辑器中并列两个字段。

#### 内容编辑器 {#content-editor-3}

* 修复了阻止在电子邮件主题中使用字符“&lt;”、“&amp;”和“&gt;”的错误。

#### 电子邮件 {#email-1}

* 修复了阻止用户在动态文本后添加文本的错误。

#### 列表 {#lists}

* 修复了阻止正确导 **出工作流执行日志** “消息”列的错误。

#### 档案和受众 {#profiles-and-audiences}

* 修复了导致重复或删除元素时间的双重确认的错误。 **仅使用Internet Explorer 11的混合设备**。

#### 工作流 {#workflows-9}

* 修复了可能阻止从工作流发送电子邮件的错误。
* 修复了在活动中未指定拒绝文件名称时，可能会阻止工作流执行的错 **[!UICONTROL Load file]** 误。
* 修复了一个错误，该错误可能会阻止在将活动 **[!UICONTROL Execution frequency]** 设置为时 **[!UICONTROL Schedule]** 执行工作流 **[!UICONTROL Daily]** 。

#### 平台 {#platform-1}

* 修复了在负载平衡环境中无法生成缩略图的错误。

## 15.7版- 2015年7月 {#release-15-7---july-2015}

### 新功能 {#new-capabilities-12}

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 说明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 导出列表<br /> </td> 
   <td> 您现在可以将列表中的内容导出为CSV格式的文件。 此函数在具有列表模式的所有屏幕 <strong>中都可用</strong> (例如：配置文件列表)。<br /> 导出的数据是导出时显示的列中的数据。 因此，通过编辑列表，您可以选择要导出的数据。<br /> 有关使用此功能的详细信息，请参阅详细 <a href="../../automating/using/exporting-lists.md">文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 与Adobe档案和受众集成<br /> </td> 
   <td> 您现在可以在Adobe Campaign和您的其他Adobe Marketing cloud解决方案之间共享受众：<br /> 
    <ul> 
     <li> 导出：在工作流中保存由档案组成的受众时，Adobe Marketing Cloud <span class="uicontrol"></span> （在Adobe Marketing Cloud中共享）新选项允许您向现有受众添加档案或创建新受众。 </li> 
     <li> 导入：通过从受 <strong>众管理屏幕创建</strong> List类型受众，新选项允许您将其标识为 <span class="uicontrol">Adobe Marketing cloud受众</span> 。 然后，您可以选择现有共享受众以将其导入Adobe Campaign。 </li> 
    </ul> 有关配置和使用此功能的详细信息，请参阅详细 <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 数字内容编辑器——动态内容<br /> </td> 
   <td> 动态内容界面已得到改进。 现在，箭头允许您直接在电子邮件正文中在不同的动态内容之间导航。<br /> 有关使用此功能的详细信息，请参阅详细 <a href="../../channels/using/defining-dynamic-content-in-a-landing-page.md">文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 数字内容编辑器——动态文本<br /> </td> 
   <td> 现在，您可以从电子邮件的内容编辑器中定义动态文本：<br /> 
    <ul> 
     <li> 在电子邮件主题中， </li> 
     <li> 在HTML模式下， </li> 
     <li> 或文本模式。 </li> 
    </ul>  有关使用此功能的详细信息，请参阅详细 <a href="../../channels/using/defining-dynamic-text.md">文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 计划和营销活动——报告<br /> </td> 
   <td> 报表的界面和图形已得到改进。<br /> 有关使用此功能的详细信息，请参阅详细 <a href="../../reporting/using/defining-the-report-period.md">文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-12}

#### 安装 {#installation}

* Adobe Campaign实例名称现在限制为32个字符。

#### 工作流 {#workflows-10}

* 修复了在工作流中编辑查询时可能无法定位“交付”资源的错误。
* 修复了在工作流中编辑查询时可能无法处理某些链接资源的错误。
* 修复了一个错误，该错误可能会 **阻止在工作流已执行的情况下** ，修改重复的交付活动。

#### 电子邮件 {#emails}

* 修复了在通过表达式编辑器添加动态内容后，在发送电子邮件之前无法检查JavaScript语法错误的错误。

#### 登陆页面 {#landing-pages-6}

* 修复了阻止从平板电脑编辑登录页面的错误。

#### Assets Core Service {#assets-core-service}

* 当从正在编辑的电子邮件或登录页面中选择共享资源时，现在会为Adobe Campaign筛选可用资源列表。

## 15.6版- 2015年6月 {#release-15-6---june-2015}

### 新功能 {#new-capabilities-13}

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 说明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 工作流：协调活动<br /> </td> 
   <td> 新的“ <strong>协调</strong> ”活动将无法识别的数据（例如，在导入文件后）与工作流中的现有资源链接起来。<br /> 此活动主要用于数据管理用途。 它响应两个不同的用例：<br /> 
    <ul> 
     <li> <strong>添加关系</strong>:“关 <strong>系</strong> ”选项卡允许您在入站数据和Adobe Campaign数据库的多个其他维之间添加链接。 </li> 
     <li> <strong>数据识别</strong>:标 <strong>识</strong> 选项卡允许您将入站数据只与Adobe Campaign数据库中现有维中的列相关联。 当它离开活动时，数据将标识为属于指定的维。 </li> 
    </ul> 请参阅详细 <a href="../../automating/using/reconciliation.md">文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流：提取文件活动<br /> </td> 
   <td> 利用新 <strong>的Extract文件</strong> ，您可以从工作流中以外部文件的形式从Adobe Campaign数据库导出数据。 <br /> 限制：当前无法对输出文件使用动态名称。<br /> 请参阅详细 <a href="../../automating/using/extract-file.md">文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流：调度程序活动<br /> </td> 
   <td> 改进了构件，允许您在工作流中选择 <strong>Scheduler</strong> （调度程序）活动的执行时间。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流：传输文件活动<br /> </td> 
   <td> 现在支持SFTP。<br /> </td> 
  </tr> 
  <tr> 
   <td> 自定义资源<br /> </td> 
   <td> “开 <span class="uicontrol">发</span> ”菜单现在允许拥有管理员权限的用户通过创建自己的自定义资源（如购买表或产品表）来丰富提供的数据模板。 <br /> 还可以扩展开箱即用的资源，以向其添加新字段。<br /> 此外，可以配置与新的或扩展的自定义资源相对应的屏幕中的导航。<br /> 请参阅详细 <a href="../../developing/using/data-model-concepts.md">文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 测试配置文件<br /> </td> 
   <td> 配置 <strong>测试配置文件列表时</strong><strong></strong> ，现在可以选择测试配置文件的中间名和标题。<br /> </td> 
  </tr> 
  <tr> 
   <td> 内容编辑器：动态内容<br /> </td> 
   <td> 您可以定义不同的内容，这些内容将根据表达式编辑器定义的条件动态显示给用户。<br /> 请参阅详细 <a href="../../channels/using/defining-dynamic-content-in-a-landing-page.md">文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 电子邮件<br /> </td> 
   <td> 测试 <strong>配置文件列</strong> ，现在可在电子邮件的发送日志中显示。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-13}

#### 列表 {#lists-1}

* 现在，从列表中删除元素会导致列表自动刷新。
* 修复了阻止从仅包含一列的列表中选择元素的错误。
* 修复了在刷新页面后导致应用于列表显示的更改丢失的错误。
* 测试配置文件的中间名称和标题现在都可以显示在测试配置文件列表中。
* 修复了在Mozilla Firefox的列表中选择复选框时发生的错误。

#### Audiences {#audiences-2}

* 修复了阻止在受众界 **[!UICONTROL Add]** 面中使用按钮的错误。

#### 电子邮件 {#emails-1}

* 修复了在编辑电子邮件时，预览按钮在行中不能被使用两次的JavaScript错误。
* 修复了使用Internet Explorer 11 **[!UICONTROL Edit properties]** 在Microsoft Surface Pro3 **[!UICONTROL Show proofs]** 平板电脑上无法使用和按钮的错误。
* 修复了可能阻止显示电子邮件发送日志的错误。

#### 登陆页面 {#landing-pages-7}

* 修复了在登录页面中编 **辑内容时** ，无法使用品牌徽标内容块的错误。
* 修复了在为登录页面指定了有效日期时，导致登录页面无法显示在营销活动列表中的错误。

#### 工作流 {#workflows-11}

* 修复了在配置分段活动时，在组模式下限制区段时无法正常工作的 **错误** 。
* 修复了在配置了分段活动后无法选择过渡的 **错误** 。
* 修复了在配置了分段活动后无法删除过渡的 **错误** 。
* 修复了阻止在分段活动中计数和预览人群的 **错误** 。
* 修复了导致重复电子邮件无法有效删除的错误。
* 修复了导致删除的传输文件活动中的 **数据显示在** 新的传输文件活 **动中的错误** 。
* 修复了阻止排除规则在排除活动中正确考虑的错 **误** 。
* 修复了在工作流中删除电子邮件分发活动时发生的错误。 相应的分发现在也从营销活动列表中删除。

#### 导航 {#navigation}

* 您现在可以使用Tab键在同一页面上的字段之间正确导航。

## 15.4版- 2015年4月 {#release-15-4---april-2015}

### 新功能 {#new-capabilities-14}

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 说明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 包导出／包导入<br /> </td> 
   <td> “部 <strong>署</strong> ”菜单现在允许拥有管理员权限的用户通过导出和导入包在不同的Adobe Campaign实例之间交换资源。<br /> 请参阅详细 <a href="../../automating/using/managing-packages.md">文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 报告<br /> </td> 
   <td> 现在可以从程序访问所 <strong>有报告(热点单击</strong> )。 这些报告包括：<br /> 
    <ul> 
     <li> 计划交付吞吐量 </li> 
     <li> 方案跟踪指标 </li> 
     <li> 按域划分的计划 </li> 
     <li> 计划非交付项和退回 </li> 
     <li> 程序URL并单击流 </li> 
    </ul> 这些报告可以在给定时间段（例如三个月、六个月等）内过滤。 还可以过滤系列活动报告。<br /> 请参阅详细 <a href="../../reporting/using/about-dynamic-reports.md">文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流：电子 <strong>邮件发送活动</strong><br /> </td> 
   <td> 工作 <strong>流中的</strong> “电子邮件交付”活动已得到改进。 您现在可以从应用程序营销活动列表中查找电子邮件、重复电子邮件以及有关重复执行电子邮件的详细信息。<br /> 请参阅详细 <a href="../../automating/using/email-delivery.md">文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 工作流：细 <strong>分活动</strong><br /> </td> 
   <td> 现 <strong>在</strong> ，分段活动在工作流中可用。 此活动允许您创建一个或多个区段，并将区段代码从在同一工作流中上游的活动计算的人群链接到这些区段。 从此活动中，可以在一个过渡或不同的多个过渡中处理区段。 现在有多种选项可用于过滤人口和限制每个区段的大小，以优化个性化。 例如，您可以随机选择与特定条件对应的配置文件。<br /> 请参阅详细 <a href="../../automating/using/segmentation.md">文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 集成：资 <strong>产核心服务</strong><br /> </td> 
   <td> 您现在可以通过电子邮件和登 <strong>录页面内容中的Assets Core</strong> service使用共享资源。 您可以直接从Adobe Marketing cloud管理您的共享资源。<br /> 请参阅详细 <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 集成：Adobe <strong>Target</strong><br /> </td> 
   <td> 您现在可以将 <strong>Adobe Target动态计算的图像插入</strong> Adobe Campaign电子邮件。 这允许您根据Adobe Target区段中定义的标准个性化同一电子邮件的多个版本。<br /> 请参阅详细 <a href="../../integrating/using/about-campaign-target-integration.md">文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 数字内容编辑器：块选 <strong>择器</strong><br /> </td> 
   <td> 在HTML内容编辑器中选择块后，编辑区域底部将显示痕迹导航。 这样，您便可以轻松导航到不同的元素并进行选择。<br /> 请参阅详细 <a href="../../channels/using/managing-landing-page-structure-and-style.md">文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 15.3版- 2015年3月 {#release-15-3---march-2015}

### 新功能 {#new-capabilities-15}

<table> 
 <thead> 
  <tr> 
   <th> 功能<br /> </th> 
   <th> 说明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 报告<br /> </td> 
   <td> 现在可以直接从程序或营销活动访问报告。 “交 <strong>付摘要</strong> ”报告已添加到计划级别。<br /> 请参阅详细 <a href="../../reporting/using/delivery-summary.md">文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 更新数据<br /> </td> 
   <td> 在工作流中，可用的 <strong>更新数据活动有一个新选项</strong> ，该选项允许您自动将入站数据字段与应用程序架构的字段关联起来。 这有助于简化更新字段的选择过程。<br /> 请参阅详细 <a href="../../automating/using/update-data.md">文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 电子邮件发送<br /> </td> 
   <td> 在工作流中，现在可以通过操 <strong>作栏中的特定按钮访问</strong> “电子邮件交付”活动的高级选项。 此按钮仅在选择“电子邮件 <strong>分发</strong> ”活动时可用。 主要益处是它允许您向活动添加出站转移，并编辑活动在工作流中显示的名称。<br /> 请参阅详细 <a href="../../automating/using/email-delivery.md">文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### 修补程序 {#patches-14}

#### 常规 {#general-10}

* 修复了在创建分发时无法显示收件人的错误。
* 修复了阻止使用基于“已打开的收件人”条件的受众的错误。
* 修复了禁止删除空配置文件的错误。
* 修复了预览分发时发生的错误。
* 修复了阻止复制营销活动的错误。
* 修复了删除营销活动时发生的错误。

