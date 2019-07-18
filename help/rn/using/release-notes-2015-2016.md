---
title: 发行说明2015-2016
seo-title: 发行说明2015-2016
description: 发行说明2015-2016
seo-description: 本页列出了Adobe Campaign Standard的所有2015和2016版。
page-status-flag: 从未激活
uuid: d5a0f6cc-0cf-46cf-8dff-1717fb624f8f
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: paign-standard-release
discoiquuid: a3ce6b80-1858-49d1-8880-353418127f4
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Release Notes 2015-2016{#release-notes}

正在寻找Adobe Campaign Standard的特定2015-2016版？

每个版本都附带新增功能和修补程序。单击某个版本可查看其内容。

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a newer release, consult this [page](../../rn/using/release-notes.md).

## Release 16.11 - November 2016 {#release-16-11---november-2016}

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
   <td> Deliverability exclusion rules<br /> </td> 
   <td> 现在，已在可交付实例中管理经过加密的全局抑制列表以避免由于恶意活动而被列入黑名单，特别是使用Spam陷。<br /> 对于每个电子邮件发送，默认的字型规则将接收电子邮件地址与此列表中包含的地址或域名相比较。如果存在匹配项，则该收件人将从目标人群中排除。<br /> 有关详细信息，请参阅 <a href="../../administration/using/filtering-rules.md#default-deliverability-exclusion-rules">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> General optimization<br /> </td> 
   <td> 此更新包含修复客户遇到的问题的大量更改和修补程序。The global platform performances have also been optimized. <br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches}

#### General {#general}

* 修复了多个安全问题。
* 修复了REST API中有关空字段或重复字段的几个问题。
* 您现在可以直接从应用程序主页创建SMS消息和推送通知。

#### Emails and SMS messages {#emails-and-sms-messages}

* 修复了阻止用户在内容编辑器中上传zip文件的问题。
* 修复了在发送证书后阻止打开证据的问题。
* Fixed an issue that led to an error message displaying when accessing the **[!UICONTROL Hot Clicks]** report on an A/B test email.
* Fixed an issue that prevented modifications made using the **[!UICONTROL Show source]** mode from being applied.
* 修复了可能导致无法导入预测性主题xml模型文件的问题。
* A new screen dedicated to importing data for the subject line trained model is now available in **[!UICONTROL Administration > Channels > Emails > Predictive Subject Line]** .
* 修复了允许非管理员用户在电子邮件配置屏幕中编辑授权蒙版的问题。

#### Push notifications {#push-notifications}

* Fixed an issue that prevented sending logs and event logs from being displayed for the recipients after sending a push notification using the **[!UICONTROL Send push on profiles]** template.
* 修复了可阻止创建新移动应用程序的问题。

#### Workflows {#workflows}

* Fixed a performance issue that occured when using the **[!UICONTROL Subscription]** activity.
* 修复了一个问题，该问题导致工作流在其内部名称包含空格时无法正常工作。

#### Integrations {#integrations}

* Fixed an issue that could lead to an error being displayed when using the **Image shared from Adobe Marketing Cloud** option in an email.

#### Custom resources {#custom-resources}

* 增强API字段的两个出版物之间的增强API日志预览。
* 修复了在发布自定义资源之前无法删除自定义资源的问题。
* 修复了阻止扩展配置文件的问题以及使用动态字段设置标识符密钥的问题。
* 修复了在自定义资源中添加链接时可能发生的问题。

## Release 16.10 - October 2016 {#release-16-10---october-2016}

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
   <td> Email predictive subject line<br /> </td> 
   <td> 编辑电子邮件时，新选项可让您尝试不同主题行，并在发送之前评估其打开率。通过根据过去的交付数据或使用特定于您的行业的预定义模型培训自己的模型，可以实现这一点。此功能适用于电子邮件以及仅包含英语内容的数据库。<br /> 有关启用和使用它的详细信息，请参阅 <a href="../../designing/using/personalizing-the-subject-line-of-an-email.md#predictive-subject-line">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> SMS transactional messaging<br /> </td> 
   <td> SMS频道已添加到Adobe Campaign的交易消息功能。交易消息现在支持两个通道：电子邮件和短信。<br /> 有关详细信息，请参阅 <a href="../../administration/using/configuring-transactional-messaging.md#creating-an-event">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Follow-up message for transactional messaging<br /> </td> 
   <td> 现在可以创建一个活动定位工作流。这意味着您可以向之前收到交易消息的客户发送跟进消息。您可以按事件类型、活动日志和跟踪日志过滤目标。在跟进消息中，您将能够利用活动的内容(有效负荷)。<br /> 有关详细信息，请参阅 <a href="../../channels/using/follow-up-messages.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Extended Profile &amp; Services API<br /> </td> 
   <td> 您现在可以在Profile和Services API中暴露扩展字段。发布机制允许API映射配置文件或服务自定义资源的扩展字段。For this to work, the <strong>Datamodel</strong> role has been added. 此新角色允许用户配置一组有权访问数据模型的管理员。<br /> 有关详细信息，请参阅 <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-1}

#### General {#general-1}

* 修复了多个安全问题。

#### Emails and SMS messages {#emails-and-sms-messages-1}

* The SMS external account configuration screen ( **[!UICONTROL Administration > Channels > SMS > SMS accounts]** ) has been improved. **[!UICONTROL SMSC specifics]** 在部分中添加了若干参数以支持“文本”字段中的错误代码。

#### Push notifications {#push-notifications-1}

* Fixed an issue that prevented the predefined filters from being displayed when editing the audience of a push notification based on the **[!UICONTROL Send via push notification]** (mobileApp) template.
* The mobile application configuration screen ( **[!UICONTROL Administration > Channels > Push Notification > Mobile applications]** ) now displays a message to indicate that the iOS or Android platform has been successfully created.

#### Landing pages {#landing-pages}

* 修复了在提交登陆页面表单时无法发送确认电子邮件的问题。

#### Audiences and queries {#audiences-and-queries}

* 修复了在查询编辑器中选择配置文件时出现的几个问题。

#### Transactional messages {#transactional-messages}

* 修复了防止取消发布交易模板的错误。
* 修复了导致在事件列表中显示触发事件的问题。

#### Integrations {#integrations-1}

* 修复了在更新受众之后，阻止共享受众在交付中使用的问题。
* Fixed an issue that prevented a shared asset ( **[!UICONTROL Image shared from Adobe Marketing Cloud]** option) from being used in a landing page.
* 修复了编辑从Adobe Audience Manager导入的共享受众时出现的问题。

## Release 16.9 - September 2016 {#release-16-9---september-2016}

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
   <td> Remarketing Triggers<br /> </td> 
   <td> Integration between the core service <span class="uicontrol">Triggers</span> and Adobe Campaign allows you to send personalized emails to your customers as a reaction to specific behaviors that are tracked on your website by Adobe Analytics (within 15 minutes).<br /> 在Adobe Marketing Cloud中，您可以定义不同触发器，即要监控的客户行为，例如，所有放弃购物车或表单的客户，从购物车中删除的产品，甚至是会话过期的客户。创建触发器时，您可以定义触发器的条件以及将在事件(plo子)中发送到Adobe Campaign的数据。<br /> 在Adobe Campaign中，您可以选择之前创建的触发器，使用datamart数据丰富事件数据，并定义链接到该触发器的事务消息模板。例如，客户端放弃购物车后，将向Adobe Campaign发送一个事件，然后通过再营销电子邮件将此事件利用在15分钟内发送给客户端。<br /> 有关详细信息，请参阅 <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional messages: Pause / Unpublish<br /> </td> 
   <td> 现在，您可以在更新内容模板的同时更新其内容。相应的消息将不再发送，但会存储在数据库中。恢复时，将处理排队的消息，如果它们尚未过期，则发送它们。<br /> 有关详细信息，请参阅 <a href="../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication">详细文档</a>。<br /> 您现在还可以取消发布活动和事务模板。相应的消息不会再发送，而且它们不会存储在数据库中。<br /> 有关详细信息，请参阅 <a href="../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Multibranding<br /> </td> 
   <td> 具有多个品牌的客户现在可以在同一实例中管理它们。品牌是由Adobe Campaign实例管理员管理的一项功能，它允许您集中配置Adobe Campaign中与某个品牌相关的所有参数。这包括徽标等更多技术参数，如跟踪URL、Web分析、服务器URL、域名等。<br /> 有关详细信息，请参阅 <a href="../../administration/using/branding.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Responsive email design preview<br /> </td> 
   <td> 此功能允许您测试电子邮件在不同类型设备上的响应性。In the email preview, a grid has been added to test your email on various screen sizes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push notifications<br /> </td> 
   <td> 新增了一个频道，使营销人员能够在iOS和Android移动设备上发送个性化的分段推送通知。消息可通过单次交付或使用工作流活动发送。将来版本中将提供与交易消息的兼容性。This channel leverages the Mobile core service’s SDK (available <a href="https://marketing.adobe.com/developer/gallery/marketing-cloud-mobile-libraries">here</a>).<br /> 有关详细信息，请参阅 <a href="../../channels/using/about-push-notifications.md">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-2}

#### General {#general-2}

* 此版本在界面列表中引入了新的过滤和搜索功能。此新功能可用，例如，在日志中(交付、跟踪)、服务(订阅、订阅历史记录)、受众和工作流过渡。
* 修复了有关客户档案中接触点数量的几个显示问题。
* 修复了多个类型的问题。

#### Emails and SMS messages {#emails-and-sms-messages-2}

* 修复了允许编辑错误证据的错误。它们现在是只读的。
* 修复了在SMS过长或编码问题导致收件人被列入黑名单时被列入黑名单的问题。

#### Custom resources {#custom-resources-1}

* 修复了在使用自定义资源的高级过滤器时阻止显示所有结果的错误。

#### Transactional messages {#transactional-messages-1}

* 前缀现在自动添加到新事件定义的标识符。
* 表示界面中的事务消息的图标已更改。

#### Integrations {#integrations-2}

* Fixed a display error that would occur when a high resolution image was inserted via the **Dynamic image from Adobe Target** option.
* 修复了一个错误，该错误允许共享受众即使未在AMC数据源中设置目标ID也会被保存。

## Release 16.7 - July 2016 {#release-16-7---july-2016}

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
   <td> Enriched transactional messages<br /> </td> 
   <td> 您现在可以将交易模板与Adobe Campaign数据库链接，以恢复信息，从而丰富交易消息的内容。<br /> 有关详细信息，请参阅 <a href="../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamic URLs for images<br /> </td> 
   <td> 这一新功能允许您插入内容块和动态文本以进行跟踪和个性化，从而个性化图像源。<br /> 然后，可以通过在图像URL中输入参数，从AEM资产(S7)动态媒体的功能中受益。例如，您可以发送带有个性化图像的电子邮件“Hello Alexandre，获得关于即将在巴黎举办的活动的最新新闻！”或“Hello Frank，获取有关即将在纽约举办的活动的最新新闻！”。<br /> 有关详细信息，请参阅 <a href="../../designing/using/personalizing-urls.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Integration with People Core Service<br /> </td> 
   <td> The Adobe Marketing Cloud <strong>Declared IDs</strong> are now covered by the integration between Adobe Campaign and People Core Service (Profiles &amp; Audiences).<br /> 这意味着您可以导入区段并导出由 <strong>访问者ID</strong>或 <strong>声明ID组成的受众</strong>。<br /> 有关详细信息，请参阅 <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery logs<br /> </td> 
   <td> The MTA logs (delivery server) now display the complete history of each message, particularly all of the delivery attempts as well as the associated error statuses, and this has no impact on the application's performance.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-3}

#### General {#general-3}

* 修复了可能会显示不相关字段而不是需要完成的字段的错误。在查询中编辑某个条件时多次修改比较运算符。
* Fixed the behavior of the option **[!UICONTROL The last X days/months/quarters/years]** when defining a relative filtering condition for a date field. 计算的期限现在为相对于服务器日期和时间的滑动期限，而不是基于日历的时间。

#### Workflows {#workflows-1}

* Fixed an error that would return an incorrect list of values in the screen for selecting the targeting dimension in the properties of a **[!UICONTROL Query]** activity.
* Fixed an error that would force the **Exists** operator to be selected when adding an average or count aggregate on a collection element in a **[!UICONTROL Query]** activity.

#### Content editing {#content-editing}

* 修复了导入HTML内容时可能导致显示问题(响应式设计)的错误：导入后第一次打开内容时，不再重写样式属性。
* 修复了在动态内容变体上添加条件时导致的非阻止错误。
* 修复了在登陆页面内容中添加复选框导致的错误。此复选框无法使用。
* 修复了在块的开头放置文本时，在块中删除文本时可能出现的错误。

#### Transactional messages {#transactional-messages-2}

* 在集成网站时，您现在可以为任何给定活动定义过期日期。传递此日期后，不再发送与活动对应的消息。

## Release 16.6 - June 2016 {#release-16-6---june-2016}

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
   <td> Profiles and Services API<br /> </td> 
   <td> The Adobe Campaign <span class="uicontrol">Profiles and Services</span> API is available in the <a href="https://www.adobe.io/products/campaign">adobe.io</a> portal. 这允许更新、添加和删除Adobe Campaign配置文件，并使它们通过REST调用订阅或取消订阅服务。<br /> 有关详细信息，请参阅API <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">的详细说明</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-4}

#### General {#general-4}

* 现在，移动设备上禁用了工具提示，以确保屏幕上显示的信息易于阅读。
* 修复了阻止用户滚动iPad屏幕上特定区域内容的错误。
* 修复了在Internet Explorer11中编辑内容时遇到的一些兼容性错误。
* 修复了一个错误，该错误可能导致在数据导入失败时无法访问详细日志。
* 修复了可能阻止保存范围过滤器的错误。
* 修复了在配置列表的方式时阻止资源元素显示的错误。
* 修复了查询编辑器浏览器中的错误。搜索字段返回的结果保留在搜索历史记录中，在每次新搜索时继续显示。

#### Emails and SMS messages {#emails-and-sms-messages-3}

* 修复了一个错误，该错误导致链接到弹回的信息无法在交付日志中恢复。
* 修复了防止访问交易消息动态内容块中的上下文的错误。
* 修复了阻止在电子邮件内容中的动态文本中定义URL链接的错误。
* 修复了交付创建向导顶部栏的显示。
* 交付的主要密钥不再用作个性化字段。

#### Workflows {#workflows-2}

* 工作流的两个活动之间的过渡现在可显示计算元素的计数并从一个活动转移到另一个活动。
* **[!UICONTROL Query]** 在活动中添加其他数据时，现在隐藏不兼容的字段。
* 在添加额外数据时显示的聚合定义窗口改进为仅提供与使用中的数据兼容的选项(例如：计算平均值仅适用于数字数据)。
* 启动或重新启动现成的技术工作流程现在只能由具有管理权限的用户执行。

#### Landing pages {#landing-pages-1}

* 修复了一个错误，该错误可能会截断登陆页面属性中的32位AES编码密钥。
* 修复了在定义可见性条件或将动态内容添加到登陆页面时无法正确显示查询编辑器的错误。

#### Custom resources {#custom-resources-2}

* The **[!UICONTROL Switch to parameters]** option is now hidden when defining a filter related to a profile's subscriptions to a service.
* 修复了在从自定义资源配置0-1类型链接时可能发生的错误。
* Fixed an error that, where relevant, could prevent the defined **Constant default value** from being edited when adding a **Date and time** type field in a custom resource.

## Release 16.5 - May 2016 {#release-16-5---may-2016}

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
   <td> Predefined filters<br /> </td> 
   <td> 管理员现在可以创建在查询编辑器中显示预配置规则的高级过滤器。选择这些过滤器可使用户在定义受众时更轻松地在简化界面中开发复杂的配置。<br /> 有关详细信息，请参阅 <a href="../../developing/using/configuring-filter-definition.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Subscription Services<br /> </td> 
   <td> <span class="uicontrol">新的订阅服务</span> 活动提供了将多个配置文件订阅一个服务或通过一个操作取消订阅服务的可能性。<br /> 此活动可在执行定位或导入包含已识别数据的文件后使用。<br /> 有关详细信息，请参阅 <a href="../../automating/using/subscription-services.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: data enrichment<br /> </td> 
   <td> The <span class="uicontrol">Additional data</span> tab is now available in <span class="uicontrol">Query</span> type activities. 通过此功能，您可以丰富查询目标，并将此数据传输到可被利用的下列工作流活动。<br /> 添加额外数据之后，您可以根据定义的其他数据创建条件，以对最初目标数据应用额外的过滤器级别。<br /> 有关详细信息，请参阅 <a href="../../automating/using/query.md#enriching-data">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Contextual help<br /> </td> 
   <td> 上下文帮助功能现在不同的Adobe Campaign屏幕上可用。这意味着，只需单击一下，即可直接访问当前使用的功能的相关文档。要显示上下文帮助，请单击“？”icon in the upper-right corner of the screen, as shown in the example below.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-5}

#### General {#general-5}

* 各种界面新增功能，符合Marketing Cloud标准。
* 标准化不同的下拉列表类型。

#### Emails and SMS messages {#emails-and-sms-messages-4}

* 修复了在指定错误地址掩码时阻止发送电子邮件的错误。
* 现在支持通过TLS协议发送电子邮件。利用MX管理中的新列，您可以为每个域定义所需的TLS行为。
* SMS界面已得到改进。

#### Workflows {#workflows-3}

* 各种工作流程界面新增功能。
* 修复了显示快速操作时出现的错误。
* Fixed an error that could cause a workflow to fail when using a **[!UICONTROL Segmentation]** type activity containing a 1-N link.
* 修复了一个错误，该错误导致工作流无法在混合设备上打开。
* 修复了第一次启动工作流时无法显示暂停按钮的错误。

#### Content editor {#content-editor}

* 内容编辑器现在允许您个性化电子邮件或登陆页面中包含的任何URL。Refer to the [detailed documentation](../../designing/using/personalizing-urls.md).
* 修复了一个错误，该错误可能导致图像在发送的创建向导及其内容之后被添加，从而导致图像丢失。

#### Custom resources {#custom-resources-3}

* 修复了在自定义资源的配置屏幕中添加个性化的1-N类型链接时发生的错误。
* 改进了准备和发布自定义资源时进度栏的显示。
* 修复了显示自定义资源的链接列表时出现的错误。

#### Transactional messages {#transactional-messages-3}

* 优化了界面的用户友好度以及交易消息引擎的性能和可靠性。
* 现在可以暂时暂停交易消息模板的发布。For more on this, refer to the [detailed documentation](../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication).
* 修复了可能导致内容块被添加到交易消息模板中的不兼容定位维度的错误。
* 修复了API预览无法在活动配置屏幕中显示的错误。

#### Audiences and queries {#audiences-and-queries-1}

* 有关在查询编辑器中使用日期的各种修补程序。Refer to the [detailed documentation](../../automating/using/editing-queries.md#creating-queries).

#### Administration {#administration}

* 修复了有关“标准用户”安全组的名称的错误，该错误阻止用户登录。

## Release 16.3 - March 2016 {#release-16-3---march-2016}

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
   <td> Interface and navigation<br /> </td> 
   <td> 改进了Adobe Campaign界面，以使导航和操作变得简单直观。<br /> 您现在可以从应用程序的顶部栏进行导航。The advanced menus are accessible by selecting the <strong>Adobe Campaign</strong> logo.<br /> 有关详细信息，请参阅 <a href="../../start/using/interface-description.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Save audience<br /> </td> 
   <td> A new option, <span class="uicontrol">Create then update an audience</span> , is now available in the <span class="uicontrol">Save audience</span> activity. 此选项允许您手动输入受众标签。如果输入的标签与现有受众相对应，则将更新该标签。如果受众不存在，将创建该受众。<br /> 此外，每次执行工作流时，受众都将更新。<br /> 您始终可以选择受众更新模式：在每次执行时用新数据完成受众，或替换整个受众数据。<br /> 有关详细信息，请参阅 <a href="../../automating/using/save-audience.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Segmentation<br /> </td> 
   <td> <span class="uicontrol">分段</span> 活动现在允许用户对临时资源的数据进行分组。例如：导入的文件的数据。<br /> 有关详细信息，请参阅 <a href="../../automating/using/segmentation.md">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-6}

#### General {#general-6}

* 修复了对列表进行排序时出现的显示错误：表示列的排序顺序的箭头只能反转特定类型的数据。
* 修复了在查询中添加规则时，限制下拉菜单中显示的元素数量的错误。

#### Emails and SMS messages {#emails-and-sms-messages-5}

* 修复了可能阻止访问电子邮件呈现报告的错误。
* 如果未提供发送者地址，则为消息准备发送舞台现在会返回错误。

#### Workflows {#workflows-4}

* 提取CSV格式文件时，某些文件格式选项是可见的，但不考虑。现在不再可见这些选项。
* Fixed an error caused when the **[!UICONTROL Delete the source files after transfer]** option was checked for a **[!UICONTROL SFTP]** type file transfer.
* Fixed an error that could prevent the counter and preview of **[!UICONTROL Query]** data from being displayed after refreshing the page.
* 修复了通过在工作流中打开特定过渡而导致的错误，尤其是在传送活动或定位和筛选维度不同的查询之后。
* 修复了在添加活动后未保存工作流，导致个性化字段插入工作流的交付活动的错误。
* 修复了阻止显示电子邮件分发活动的出站转移定位维度的错误。

#### Landing pages {#landing-pages-2}

* 修复了一个错误，该错误导致个性化字段无法在登陆页面的可本地化内容块中正确运行。

#### Custom resources {#custom-resources-4}

* Fixed an error that prevented a search on a custom resource from being carried out if the **[!UICONTROL Add search fields]** option of the resource screen definition was checked and if several fields were selected in the **[!UICONTROL Filter zone composition]** .

## Release 16.2 - February 2016 {#release-16-2---february-2016}

### New capabilities {#new-capabilities-7}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> A/B test for emails<br /> </td> 
   <td> 您现在可以对电子邮件的内容、主题或发送方姓名执行A/B测试。此新功能可测试元素的三个变体。<br /> 从特定于A/B测试的新模板创建电子邮件时，创建向导中的新步骤允许您定义测试的参数。<br /> 有关详细信息，请参阅 <a href="../../channels/using/designing-an-a-b-test-email.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Brand management<br /> </td> 
   <td> 您现在可以定义一个或多个品牌以集中输入影响品牌身份的参数。Adobe Campaign允许您创建这些品牌并将其链接到交付或登陆页面模板。<br /> 有关详细信息，请参阅 <a href="../../administration/using/branding.md#assigning-a-brand-to-an-email">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Incremental query<br /> </td> 
   <td> A new workflow activity, <span class="uicontrol">Incremental query</span> , allows you to carry out a query which, on every execution, targets only the new results. 之前执行的结果会自动排除。Linked to a <span class="uicontrol">Scheduler</span> activity, you can define the execution frequency of the <span class="uicontrol">Incremental query</span> .<br /> 有关详细信息，请参阅 <a href="../../automating/using/incremental-query.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional messages<br /> </td> 
   <td> 改进了交易消息界面的用户友好性。All business process management linked to transactional messages is currently centralized in the <span class="uicontrol">Marketing plans</span> &gt; <span class="uicontrol">Transactional messages</span> menu. 活动配置也得到了改进。现在，活动可以独立于自定义资源进行管理。<br /> 有关详细信息，请参阅 <a href="../../channels/using/about-transactional-messaging.md">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-7}

#### General {#general-7}

* 修复了报告、列表和查询中的几个显示错误。
* 修复了移动设备上的多个兼容性和显示错误。

#### Emails and SMS messages {#emails-and-sms-messages-6}

* 修复了在创建消息(电子邮件或SMS)时可能阻止插入个性化字段显示个性化字段的错误。
* 修复了一个错误，该错误可能导致通过Mblox发送的SMS消息无法正确传输。

#### Audiences and queries {#audiences-and-queries-2}

* 修复了在修改筛选维度之后在查询中添加其他条件时可能导致计数错误的计数错误。
* 修复了在预览查询结果时可能导致分页错误的错误。

#### Content editing {#content-editing-1}

* 修复了在使用个性化枚举时无法正确考虑动态内容配置的错误。

#### Workflows {#workflows-5}

* Fixed an error that could prevent any action in a workflow from being carried out if there was an empty line in the **[!UICONTROL Fields to update]** tab of an **[!UICONTROL Update data]** activity.
* 修复了阻止包含地理/组织单位信息的数据被导入的错误。
* Fixed an error caused by adding a **[!UICONTROL Change axis]** type of **[!UICONTROL Exclusion]** rule.
* Fixed an error that could lead to an unwanted additional segment being created when manipulating an outbound transition of a **[!UICONTROL Segmentation]** activity.
* 修复了加载工作流模板中的文件导致的错误。
* Fixed an error that could prevent spaces from being used as column separators in a **[!UICONTROL Load file]** activity.

#### Custom resources {#custom-resources-5}

* 修复了一个错误，该错误导致自定义资源的状态在导入包后重新起草，如果在导出时已发布资源。

#### Packages {#packages}

* 修复了一个错误，该错误导致包含工作流的包无法导出。
* 修复了一个错误，该错误可能会阻止选择同一资源的多个元素。

## Release 16.1 - January 2016 {#release-16-1---january-2016}

### New capabilities {#new-capabilities-8}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Reports<br /> </td> 
   <td> The following email specific reports have been added: <span class="uicontrol">Complaints</span> , <span class="uicontrol">Opens</span> , and <span class="uicontrol">Unsubscriptions</span> .<br /> 以下报表已得到改进： <span class="uicontrol">交付摘要</span> 、 <span class="uicontrol">退回摘要</span> 、 <span class="uicontrol">交付吞吐量</span> 和 <span class="uicontrol">跟踪指示器</span> 。<br /> 有关详细信息，请参阅 <a href="../../reporting/using/defining-the-report-period.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Query editing<br /> </td> 
   <td> The query editor has been improved and now allows you to scan the <strong>1-N</strong> type links.<br /> 有关详细信息，请参阅 <a href="../../automating/using/editing-queries.md#creating-queries">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Content personalization<br /> </td> 
   <td> As for email or landing page editing, the input interface for content block display conditions has been improved.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: column definition when importing<br /> </td> 
   <td> <span class="uicontrol">现在，加载文件</span> 活动允许您详细配置导入的文件的列：预期的数据类型、日期和时间格式、处理以在空值或错误以及值重映射的情况下应用。<br /> 有关详细信息，请参阅 <a href="../../automating/using/load-file.md#column-format">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Mapping of SMS encodings<br /> </td> 
   <td> 现在，可以为未使用标准编码的提供者定义个性化SMS消息的编码映射。管理员可以执行个性化映射的配置，并定义应考虑到的顺序。<br /> 有关详细信息，请参阅 <a href="../../administration/using/configuring-sms-channel.md#smsc-specifics">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-8}

#### General {#general-8}

* 改进了混合/触摸屏设备与Internet Explorer和Chrome的兼容性。
* 修复了在指定的电子邮件地址包含语法错误时，可能导致为新用户/配置文件/测试配置文件输入的所有数据丢失的错误。

#### Emails and SMS messages {#emails-and-sms-messages-7}

* 修复了一个错误，该错误可能会阻止在电子邮件预览屏幕中生成内容缩略图。
* 修复了可能阻止消息(电子邮件或SMS)在消息预览屏幕中显示的错误。

#### Audiences and queries {#audiences-and-queries-3}

* Fixed an error that could prevent a **Query** type audience from being created in the **Service** resource.
* 修复了在高级模式中编辑查询条件时，可能无法正确显示函数列表的错误。
* Fixed an error that could prevent a **Query** type audience from being created if it contained criteria based on collections.
* 修复了一个错误，该错误可能会阻止在创建KPI时包含过滤器的查询。
* 修复了一个错误，该错误可能会阻止预览从工作流创建的受众的内容。

#### Custom resources {#custom-resources-6}

* 修复了一个错误，该错误可能导致自定义资源包含具有动态默认值的字段。
* Fixed an error caused by moving, then deleting an element in the **[!UICONTROL Detail screen configuration]** section while defining screens of a custom resource.
* Fixed an error that occurred when a default value had been defined for an **integer** list that did not include **0** in its range of possible values.
* 修复了一个错误，该错误导致在重新初始化后，可能无法在自定义资源的详细信息屏幕配置中添加元素。

#### Workflows {#workflows-6}

* 修复了一个错误，该错误可能会导致显示工作流中的所有活动，而不是只显示选定活动的那些活动。
* Fixed an error in the **[!UICONTROL Scheduler]** activity. **[!UICONTROL Day of the month]** 未正确考虑该选项并替换为该选项 **[!UICONTROL Week day]** 。
* Fixed an error that could prevent a **[!UICONTROL Scheduler]** activity from working correctly with the expiration mode set to **[!UICONTROL After a certain number of iterations]** .
* Fixed an error that occurred when exporting data using an **[!UICONTROL Extract file]** activity. 导出文件中的行数不如导出元素的数量。
* Fixed an error that could prevent a file in a **[!UICONTROL Load file]** activity from being selected.
* Fixed an error that prevented fields that were to be updated in an **[!UICONTROL Update data]** activity from being deleted.
* 修复了在打开工作流执行日志后无法保存对工作流所做修改的错误。
* Fixed an error that caused a **[!UICONTROL Load file]** activity to be executed twice if it was configured to use the file from its inbound transition and this file had been loaded using a **[!UICONTROL Transfer file]** activity.
* Fixed an error that could prevent certain temporary entities from being correctly processed by an **Exclusion** activity.
* Fixed an error that could prevent a **[!UICONTROL Query]** activity from being executed correctly if the targeting dimension and the filtering dimension configured in the activity were different.
* Fixed an error concerning the automatic naming of outbound transitions added to a **[!UICONTROL Fork]** activity that could prevent the workflow from being saved.

#### Content editing {#content-editing-2}

* 修复了在编辑内容时可能会导致图标或搜索栏不灵活显示的错误。

#### Landing pages {#landing-pages-3}

* 修复了阻止登陆页面使用包导入导入的错误。

#### Transactional messages {#transactional-messages-4}

* 现在可以在Message Center Push Agent运算符的安全参数中指定一个可信IP地址。
* 修复了一个错误，该错误可能会阻止创建新类型的事件。

## Release 15.11 - November 2015 {#release-15-11---november-2015}

### New capabilities {#new-capabilities-9}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> SMS Channel<br /> </td> 
   <td> 您现在可以使用Adobe Campaign发送SMS消息。<br /> 与电子邮件一样，您可以从营销活动和营销活动列表中创建新的SMS分发。您还可以从工作流中创建单一发送和重复的SMS消息。<br /> 这些SMS交付基于可从交付模板列表中配置的模板。默认模板可用。<br /> 这些SMS交付使用SMPP3.4协议，大多数SMS路由器使用。<br /> 有关详细信息，请参阅 <a href="../../channels/using/about-sms-messages.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploring transitions<br /> </td> 
   <td> 您现在可以在工作流的最后一个过渡中探索数据及其结构。This allows you to check that the processes applied by each activity correspond to your needs.<br /> </td> 
  </tr> 
  <tr> 
   <td> File pre- and post-processing in workflows<br /> </td> 
   <td> You can now carry out additional processing on a data file when importing or exporting it via the <span class="uicontrol">Load file</span> and <span class="uicontrol">Extract file</span> activities.<br /> 默认情况下，您可以在这些活动中解压缩GZIP格式文件并将其压缩。<br /> 有关详细信息，请参阅 <a href="../../automating/using/load-file.md">有关加载文件</a> 和 <a href="../../automating/using/extract-file.md">提取文件</a> 活动的文档。<br /> </td> 
  </tr> 
  <tr> 
   <td> Deliverability reports<br /> </td> 
   <td> 电子邮件渲染报告现已可用。此报告允许您根据用于读取消息的支持和消息服务查看消息的不同呈现。<br /> 报告摘要还显示接收接收的消息、垃圾邮件消息、未接收消息和消息的数量。<br /> 有关详细信息，请参阅 <a href="../../sending/using/email-rendering.md#email-rendering-report-description">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Package Management<br /> </td> 
   <td> It is now possible to import and export images in packages.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quick actions<br /> </td> 
   <td> 在列表或工作流中选择某个元素上方或之后时，某些操作会出现。其中一些操作现在相关元素周围显示为图标，以便于访问。These quick actions can be used to duplicate an element, delete it, show the detail, etc.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-9}

#### General {#general-9}

* 修复了一个错误，该错误可能会阻止从管理员帐户访问实例的常规参数。
* **现在，在自定义资源中正确考虑浮动** 数据。
* 修复了执行简化的导入列表中的显示错误，该错误是在修改相应模板的状态时导致的。

#### Landing pages {#landing-pages-4}

* 修复了在英语实例上可能出现法语错误显示的登录页面模板的某些元素。

#### Audiences {#audiences}

* 修复了一个错误，该错误可能会阻止从Adobe Marketing Cloud导入的受众显示在受众列表中。
* 修复了在定义查询时可能强制区分大小写的错误。
* 修复了在定义查询时无法过滤受众的错误。
* 修复了一个错误，该错误可能会阻止在受众中取消操作。

#### Workflows {#workflows-7}

* Fixed an error that could prevent the fields that were to be updated in an **[!UICONTROL Update data]** activity from manually being configured.
* Fixed an error that could cause the **[!UICONTROL Query]** activity to load infinitely when opened if the workflow had not been saved after having placed the activity in the diagram.
* Fixed an error that could cause the server to stop while counting or previewing an audience selected from a **[!UICONTROL Query]** in a workflow.
* 修复了打开工作流中的活动时可能出现的非关键错误。
* Fixed an error that prevented a **[!UICONTROL Scheduler]** activity from being configured to execute a workflow several times a day.
* 修复了可能导致在某些工作流活动中无法执行查询的字段的错误。
* Fixed an error that could prevent the user from locating the KPIs added from a **[!UICONTROL Query]** on deliveries in the outbound transition.
* 修复了将文件导入工作流后无法创建文件受众的错误。
* Fixed an error that could prevent data from being updated on profiles if the **location/address3** field of the resource was used.
* 修复了一个错误，该错误导致活动中的各个集合无法在工作流中重复。
* 修复了阻止显示SQL的错误，从而允许诊断工作流中重复的分发。

#### Content editor {#content-editor-1}

* 修复了一个错误，该错误会导致在登录页面的源代码中搜索或不可能进行搜索。

#### Packages {#packages-1}

* 修复了可能导致某些类型的元素(尤其是登陆页面、工作流)无法导出的各种错误。
* 修复了一个错误，该错误导致在标签被修改时，将显示之前的包导入标签。
* 修复了可能导致不兼容资源显示在可导出资源列表中的错误。

## Release 15.10 - October 2015 {#release-15-10---october-2015-}

### New capabilities {#new-capabilities-10}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Workflows: Deduplication activity<br /> </td> 
   <td> 现在，工作流中提供专用于取消复制数据的新活动。此活动允许您根据选定条件筛选目标中的任何副本。<br /> 有关详细信息，请参阅 <a href="../../automating/using/deduplication.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Improved diagram<br /> </td> 
   <td> 现在，您可以从工作流工作区中使用多个键盘快捷键来选择、打开和删除活动。<br /> 活动对齐方式也得到了改进，并允许更好地组织工作流。<br /> 有关详细信息，请参阅 <a href="../../automating/using/workflow-interface.md#workspace">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Extract file activity<br /> </td> 
   <td> The date and time of the export is now automatically added to the labels of the files exported using an <span class="uicontrol">Extract file</span> activity. This way the files generated are unique.<br /> </td> 
  </tr> 
  <tr> 
   <td> Simplified data import<br /> </td> 
   <td> The name of the template from which a simplified import was carried out is now visible by default in the import list and in the detail of each import.<br /> </td> 
  </tr> 
  <tr> 
   <td> Custom resources<br /> </td> 
   <td> Improvement and extended possibilities for managing and defining links for custom resources.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-10}

#### Email {#email}

* 修复了阻止服务取消订阅链接从镜像页面正确工作的错误。
* 修复了一个错误，该错误可能导致电子邮件分发标签无法正确显示在电子邮件编辑页面上。
* Fixed an error that could prevent an external **[!UICONTROL Routing]** account from being selected in a duplicated delivery template.

#### Audiences {#audiences-1}

* 修复了在查询中使用1-N链接时受众计数导致的错误。
* 修复了一个错误，该错误可能会阻止在电子邮件分发的目标受众中选择配置文件。

#### Workflows {#workflows-8}

* 修复了在工作流中配置电子邮件分发时可能出现显示问题的错误。
* Fixed an error that could prevent the **[!UICONTROL Load file]** activity from working correctly. 随后将显示空白错误消息。
* Fixed an error that could prevent the **[!UICONTROL Transfer file]** activity from working correctly. 并非总能正确地考虑访问权限。
* Fixed an error that could prevent a file from being exported if the workflow contained a **[!UICONTROL Recurring email]** .
* 修复了一个错误，该错误可能会阻止在工作流中创建电子邮件分发，或阻止主题和定义的内容被考虑。
* Fixed an error that could prevent a reconciliation key from being selected in an **[!UICONTROL Update data]** activity when configuring the workflow of a simplified import template.
* 修复了一个错误，该错误可能会阻止在删除活动后保存工作流。

#### Platform {#platform}

* 修复了一个错误，该错误导致在自定义资源包含指向该元素的资源类型的链接时，无法创建新元素。
* 修复了可能导致写入某些日志的延迟15分钟的错误。
* Fixed an error that could prevent the marketing activity list from being displayed when sorted by the **[!UICONTROL Date]** or **[!UICONTROL Indicators]** columns.

#### Landing pages {#landing-pages-5}

* 修复了在选择测试配置文件以预览登陆页面时出现的错误。

#### Transactional messages {#transactional-messages-5}

* 修复了在测试配置文件上删除活动后应用程序崩溃的错误。

#### Reports {#reports}

* Fixed an error that could cause incorrect data to be sent for the reports **[!UICONTROL deliveryThroughputReport]** and **[!UICONTROL deliveryTrackingReport]** .

#### Content editor {#content-editor-2}

* 修复了处理动态内容块时出现的HTML标签管理错误。

## Release 15.8 - August 2015 {#release-15-8---august-2015}

### New capabilities {#new-capabilities-11}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Simplified data import<br /> </td> 
   <td> 您现在可以以简化的方式导入数据。<br /> 用户只需选择由管理员预定义的模板，然后上传包含要导入的数据的文件。用户透明地执行模板中定义的工作流，用户可以访问导入结果的详细信息以及记录任何错误的日志。<br /> 这些文件中的数据可以插入数据库中，或用作直接创建受众的方法。<br /> 有关详细信息，请参阅 <a href="../../automating/using/about-data-import-and-export.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Creating programs and campaigns<br /> </td> 
   <td> 现在，已配置营销活动和计划，以使创建它们的日期自动用作开始日期。<br /> 结束日期根据开始日期进行配置，如：<br /> 
    <ul> 
     <li> 适用于计划的D+186 </li> 
     <li> 适用于营销活动的D+61 </li> 
    </ul> For more information, refer to the <a href="../../start/using/programs-and-campaigns.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email<br /> </td> 
   <td> The list of tracked URLs is now read only.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional messages<br /> </td> 
   <td> 您现在可以管理在创建帐户后的密码更改或确认等活动的个性化交易消息。<br /> 有关详细信息，请参阅 <a href="../../channels/using/about-transactional-messaging.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Custom resources<br /> </td> 
   <td> 添加了多种功能，例如：扩展测试配置文件、状态管理和删除资源。<br /> 有关详细信息，请参阅 <a href="../../developing/using/resource-statuses.md">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-11}

#### Display {#display}

* 修复了Safari中的查询编辑器中可能导致两个字段并列的错误。

#### Content editor {#content-editor-3}

* 修复了一个错误，该错误导致在电子邮件主题中使用字符'&lt;'、'&amp;'和'&gt;'。

#### Email {#email-1}

* 修复了阻止用户在动态文本后添加文本的错误。

#### Lists {#lists}

* Fixed an error that prevented the **Message** column in workflow execution logs from being exported correctly.

#### Profiles and audiences {#profiles-and-audiences}

* 修复了导致重复或删除元素时出现双重确认的错误。**仅使用Internet Explorer11的混合设备**。

#### Workflows {#workflows-9}

* 修复了可能阻止从工作流发送电子邮件的错误。
* Fixed an error that could prevent a workflow from executing when the name of the rejection file was not specified in a **[!UICONTROL Load file]** activity.
* Fixed an error that could prevent a workflow from executing when the **[!UICONTROL Execution frequency]** of a **[!UICONTROL Schedule]** activity was set to **[!UICONTROL Daily]** .

#### Platform {#platform-1}

* 修复了阻止在负载平衡环境中生成缩略图的错误。

## Release 15.7 - July 2015 {#release-15-7---july-2015}

### New capabilities {#new-capabilities-12}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Exporting lists<br /> </td> 
   <td> 现在，您可以将列表中的内容导出到CSV格式的文件中。This function is available in all screens with a <strong>List</strong> mode (for example: profile list).<br /> 导出的数据是导出时显示的列中的数据。通过编辑列表，您可以选择要导出的数据。<br /> 有关使用此功能的详细信息，请参阅 <a href="../../automating/using/exporting-lists.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Integration with Adobe Profiles &amp; Audiences<br /> </td> 
   <td> You can now share audiences between Adobe Campaign and your other Adobe Marketing Cloud solutions:<br /> 
    <ul> 
     <li> Export: when you save an audience composed of profiles in a workflow, a new <span class="uicontrol">Share in Adobe Marketing Cloud</span> option allows you to add profiles to an existing audience or to create a new audience. </li> 
     <li> Import: by creating a <strong>List</strong> type audience from the audience management screen, a new option allows you to identify it as an <span class="uicontrol">Adobe Marketing Cloud Audience</span> . 然后，您可以选择现有共享受众，将其导入Adobe Campaign。 </li> 
    </ul> For more information on configuring and using this functionality, refer to the <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor - Dynamic content<br /> </td> 
   <td> 动态内容界面已得到改进。现在，箭头显示允许您直接在电子邮件正文中导航不同的动态内容。<br /> 有关使用此功能的详细信息，请参阅 <a href="../../designing/using/defining-dynamic-content-in-a-landing-page.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor - Dynamic text<br /> </td> 
   <td> From the content editor of an email, you can now define dynamic text:<br /> 
    <ul> 
     <li> 在电子邮件主题中， </li> 
     <li> 在HTML模式下， </li> 
     <li> 或在文本模式下。 </li> 
    </ul> For more information on using this functionality, refer to the <a href="../../designing/using/defining-dynamic-text.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Programs and campaigns - Reports<br /> </td> 
   <td> 报表的界面和图形已得到改进。<br /> 有关使用此功能的详细信息，请参阅 <a href="../../reporting/using/defining-the-report-period.md">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-12}

#### Installation {#installation}

* Adobe Campaign实例名称现在限制为32个字符。

#### Workflows {#workflows-10}

* 修复了在工作流中编辑查询时可能阻止“交付”资源的错误。
* 修复了在工作流中编辑查询时无法处理某些链接资源的错误。
* Fixed an error that could prevent a **Recurring delivery** activity from being modified if the workflow had already been executed.

#### Emails {#emails}

* 修复了在通过表达式编辑器添加动态内容时，阻止JavaScript语法错误被选中的错误。

#### Landing pages {#landing-pages-6}

* 修复了阻止登录页面从平板电脑编辑的错误。

#### Assets Core Service {#assets-core-service}

* 从正在编辑的电子邮件或登陆页面中选择共享资源时，Adobe Campaign会过滤可用资源的列表。

## Release 15.6 - June 2015 {#release-15-6---june-2015}

### New capabilities {#new-capabilities-13}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Workflows: Reconciliation activity<br /> </td> 
   <td> A new <strong>Reconciliation</strong> activity links unidentified data (for example, after importing a file) with existing resources within a workflow.<br /> 此活动主要用于数据管理用途。It responds to two different use cases:<br /> 
    <ul> 
     <li> <strong>添加关系</strong>： <strong>“关系”</strong> 选项卡允许您在Adobe Campaign数据库的入站数据和其他多个维度之间添加链接。 </li> 
     <li> <strong>数据识别</strong>： <strong>通过标识</strong> 选项卡，您只需将入站数据关联到Adobe Campaign数据库中现有维度中的列。在退出活动时，数据被识别为属于指定维度。 </li> 
    </ul> Refer to the <a href="../../automating/using/reconciliation.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Extract file activity<br /> </td> 
   <td> <strong>新的提取文件</strong> 活动允许您以外部文件的形式从工作流中导出Adobe Campaign数据库中的数据。<br /> 限制：当前无法为输出文件使用动态名称。<br /> 请参阅 <a href="../../automating/using/extract-file.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Scheduler activity<br /> </td> 
   <td> Improved widget that allows you to select the execution time of the <strong>Scheduler</strong> activity in a workflow.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Transfer file activity<br /> </td> 
   <td> SFTP is now supported.<br /> </td> 
  </tr> 
  <tr> 
   <td> Custom resources<br /> </td> 
   <td> <span class="uicontrol">“开发”</span> 菜单现在允许具有管理员权限的用户通过创建自己的自定义资源(如购买或产品表)丰富提供的数据模板。<br /> 现成的资源也可以扩展，以便为它们添加新字段。<br /> 此外，可以配置与新的或扩展的自定义资源对应的屏幕中的导航。<br /> 请参阅 <a href="../../developing/using/data-model-concepts.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Test profiles<br /> </td> 
   <td> The <strong>Middle name</strong> and <strong>Title</strong> of the test profiles can now be selected when configuring the list of test profiles.<br /> </td> 
  </tr> 
  <tr> 
   <td> Content editor: Dynamic content<br /> </td> 
   <td> 您可以定义不同的内容，这些内容将根据通过表达式编辑器定义的条件动态地显示给用户。<br /> 请参阅 <a href="../../designing/using/defining-dynamic-content-in-a-landing-page.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Email<br /> </td> 
   <td> <strong>现在，电子邮件的发送日志中提供了测试配置文件</strong> 列。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-13}

#### Lists {#lists-1}

* 现在，从列表中删除元素会导致列表自动刷新。
* 修复了阻止从仅包含一列的列表中选择元素的错误。
* 修复了一个错误，该错误导致应用于列表的更改在刷新页面之后会丢失。
* 中间名称和测试配置文件标题现在都可以显示在测试配置文件列表中。
* 修复了在使用Mozilla Firefox选择列表中的复选框时出现的错误。

#### Audiences {#audiences-2}

* Fixed an error that prevented the **[!UICONTROL Add]** button from being used in the audience interface.

#### Emails {#emails-1}

* 修复了一个JavaScript错误，该错误导致预览按钮在编辑电子邮件时无法在行中重复使用两次。
* Fixed an error that prevented the **[!UICONTROL Edit properties]** and **[!UICONTROL Show proofs]** buttons from being used on Microsoft Surface Pro3 tablets using Internet Explorer 11.
* 修复了一个错误，该错误可能会阻止显示电子邮件的发送日志。

#### Landing pages {#landing-pages-7}

* Fixed an error that prevented the **Brand logo** content block from being used when editing content in a landing page.
* 修复了登陆页面指定的有效性日期，阻止登陆页面显示在营销活动列表中的错误。

#### Workflows {#workflows-11}

* Fixed an error that prevented limiting a segment in group mode from working correctly when configuring a **Segmentation** activity.
* Fixed an error that prevented a transition from being selected after having configured a **Segmentation** activity.
* Fixed an error that prevented a transition from being deleted after having configured a **Segmentation** activity.
* Fixed an error that prevented populations from being counted and previewed within a **Segmentation** activity.
* 修复了一个错误，该错误导致有效删除重复的电子邮件。
* Fixed an error that caused data from a deleted **Transfer file** activity to appear in a new **Transfer file** activity.
* Fixed an error that prevented an exclusion rule from being correctly taken into account within an **Exclusion** activity.
* 修复了在工作流中删除电子邮件分发活动时出现的错误。此时，也会从营销活动列表中删除相应的分发。

#### Navigation {#navigation}

* 您现在可以使用Tab键在同一页面上的字段之间正确导航。

## Release 15.4 - April 2015 {#release-15-4---april-2015}

### New capabilities {#new-capabilities-14}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Package exports / Package imports<br /> </td> 
   <td> <strong>“部署”</strong> 菜单现在允许具有管理员权限的用户通过导出和导入包在不同Adobe Campaign实例之间交换资源。<br /> 请参阅 <a href="../../automating/using/managing-packages.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Reports<br /> </td> 
   <td> All reports (except the <strong>Hot clicks</strong> report) can now be accessed from a program. These reports are:<br /> 
    <ul> 
     <li> 计划交付量 </li> 
     <li> 计划跟踪指示器 </li> 
     <li> 按域划分的计划划分 </li> 
     <li> 计划不可交付和弹回 </li> 
     <li> 计划URL和单击流 </li> 
    </ul> 这些报告可在特定时间段内筛选(例如三个月、六个月等)。营销活动报告也可以过滤。<br /> 请参阅 <a href="../../reporting/using/about-dynamic-reports.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: <strong>Email delivery</strong> activity<br /> </td> 
   <td> The <strong>Email delivery</strong> activity in the workflows has been improved. 您现在可以从应用程序营销活动列表中查找电子邮件、重复电子邮件和有关重复电子邮件执行的详细信息。<br /> 请参阅 <a href="../../automating/using/email-delivery.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: <strong>Segmentation</strong> activity<br /> </td> 
   <td> <strong>分段</strong> 活动现在在工作流中可用。此活动允许您创建一个或多个区段，并将区段代码与在同一工作流程中放置的活动所计算的人群相关联。在此活动中，可以在一个过渡中或在不同的过渡中处理区段。现在有了筛选人群和限制每个区段的规模以优化个性化的选项。例如，您可以随机选择符合特定条件的配置文件。<br /> 请参阅 <a href="../../automating/using/segmentation.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrations: <strong>Assets Core Service</strong><br /> </td> 
   <td> You can now use shared resources via <strong>Assets Core Service</strong> in your email and landing page contents. 您可以直接从Adobe Marketing Cloud管理共享资源。<br /> 请参阅 <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrations: <strong>Adobe Target</strong><br /> </td> 
   <td> You can now insert images that are dynamically computed by <strong>Adobe Target</strong> into your Adobe Campaign emails. 这允许您根据在Adobe Target区段中定义的条件个性化内容，从而提供同一电子邮件的几个版本。<br /> 请参阅 <a href="../../integrating/using/about-campaign-target-integration.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor: <strong>Block selector</strong><br /> </td> 
   <td> 在HTML内容编辑器中选择块后，将在编辑区域的底部显示痕迹导航。这使您能够轻松导航到不同的元素并选择它们。<br /> 请参阅 <a href="../../designing/using/managing-landing-page-structure-and-style.md">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Release 15.3 - March 2015 {#release-15-3---march-2015}

### New capabilities {#new-capabilities-15}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Reports<br /> </td> 
   <td> 现在可以直接从计划或营销活动访问报告。<strong>提交摘要</strong> 报告已添加到计划级别。<br /> 请参阅 <a href="../../reporting/using/delivery-summary.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Update data<br /> </td> 
   <td> In the workflows, the available <strong>Update data</strong> activity has a new option, which allows you to automatically link inbound data fields with the fields of an application schema. 这有助于促进更新字段的选择过程。<br /> 请参阅 <a href="../../automating/using/update-data.md">详细文档</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> Email delivery<br /> </td> 
   <td> In workflows, the advanced options of the <strong>Email delivery</strong> activity can now be accessed via a specific button in the action bar. This button is only available if an <strong>Email delivery</strong> activity is selected. 主要优点是它允许您向活动添加出站过渡，并在工作流中显示活动的名称时编辑活动的名称。<br /> 请参阅 <a href="../../automating/using/email-delivery.md">详细文档</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-14}

#### General {#general-10}

* 修复了一个错误，该错误导致收件人在创建分发时无法显示。
* 修复了导致基于“已打开”条件的受众无法使用的错误。
* 修复了禁止删除空配置文件的错误。
* 修复了预览交付时出现的错误。
* 修复了导致营销活动重复的错误。
* 修复了删除营销活动时发生的错误。

