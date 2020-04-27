---
title: 在Adobe Campaign标准中配置电子邮件渠道
description: 了解如何在Adobe Campaign标准中配置电子邮件渠道。
page-status-flag: never-activated
uuid: 9fddb655-b445-41f3-9b02-5d356fc88aa1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 3752d41f-8c59-4fad-b30f-e98e09cd74a8
context-tags: extAccountEmail,overview;emailConfig,main;ruleSet,overview;delivery,properties,open
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3cd089751423d9e165b1d44425b1fdfd20b62546

---


# 配置电子邮件渠道{#configuring-email-channel}

作为活动管 [理员](../../administration/using/users-management.md#functional-administrators)，您可以配置电子邮件渠道设置。 这些高级设置包括常规电子邮件渠道参数、电子邮件路由帐户、电子邮件处理规则和电子邮件属性。 在此页上，您将学习如何编辑常规电子邮件和发送参数的默认值。

请注意，某些电子邮件设置现在由Adobe Campaign增强MTA管理。 因此：
* 活动用户界面中的某些配置不再应用：
   * “配 **[!UICONTROL Retries]** 置”菜单 [和电子邮件属性的“发](#email-channel-parameters) 送”参数中的设置 [](#retries-parameters) 。
   * “电 **[!UICONTROL MX management]** 子邮 **[!UICONTROL Domain management]** 件处理规 [则”菜单中的和规则](#email-processing-rules)。

* 其他参数现在由增强的MTA部分管理，而某些配置仍可在活动内完成。 受影响的设置如下：
   * 菜 **[!UICONTROL Message delivery duration]** 单中的参 **[!UICONTROL Configuration]** 数。 For more on this, see [this section](#email-channel-parameters).
   * 部分 **[!UICONTROL Delivery duration]** 中 **[!UICONTROL Validity limit for sending messages]** 的或 **[!UICONTROL Validity period]** 参数。 For more on this, see [this section](#validity-period-parameters).
   * 中 **[!UICONTROL Bounce mails]** 的规则 **[!UICONTROL Email processing rules]**。 For more on this, see [this section](#email-processing-rules).

## 电子邮件渠道参数 {#email-channel-parameters}

电子邮件配置屏幕允许为电子邮件渠道定义参数。 管理员可以在> **[!UICONTROL Administration]>[!UICONTROL Channels]>[!UICONTROL Email]>菜单中访问这[!UICONTROL Configuration]**些配置。

![](assets/channels_1.png)

* **已发送电子邮件的标题参数**

   在本节中，您可以指定发 **[!UICONTROL masks]** 送者地址和错误地址的授权。 如果使用了多个蒙版，则必须用逗号分隔这些蒙版。 填充这些字段后，Adobe Campaign会检查在消息准备阶段输入的地址是否有效。 此操作模式可确保没有使用可能触发可交付性问题的地址。 发送方地址和错误地址均由Adobe设置。 您需要与Adobe客户关怀团队联系以更新它们。

* **可交付性**

   此ID由Adobe客户关怀团队提供。 交付能力报告必须正确运行。

* **投放参数**

   Adobe Campaign会从开始日期开始发送消息。 该 **[!UICONTROL Message delivery duration]** 字段允许您指定消息的发送持续时间。

   >[!IMPORTANT]
   >
   >**活动中的此参数现在仅在设置为3.5天或更少时使用。** 如果定义的值高于3.5天，则不会将其考虑在内，因为它现在由Adobe Campaign增强MTA管理。

   该字 **[!UICONTROL Online resources validity duration]** 段用于上传的资源，主要用于镜像页面和图像。 本页上的资源在有限的时间内有效（以节省磁盘空间）。

* **重试**

   临时未传送的消息可能会自动重试。 有关详细信息，请参阅 [投放临时故障后的重试](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)。

   >[!NOTE]
   >
   >根据IP在历史和当前给定域上的表现情况，将要执行的最大重试数和重试之间的最小延迟现在由Adobe Campaign增强MTA管理。 将忽 **** 略活动中的重试设置。

   <!--This section indicates how many retries should be performed the day after the send is started (**Number of retries**) and the minimum delay between retries (**Retry period**). By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.-->

* **电子邮件隔离参数**

   在字段 **[!UICONTROL Time between two significant errors]** 中，输入一个值以定义应用程序在出现故障时在增加错误计数器之前等待的时间。 默认值为 **&quot;1d&quot;**，表示1天。

   到达该 **[!UICONTROL Maximum number of errors before quarantine]** 值后，将隔离电子邮件地址。 默认值为 **&quot;5&quot;**:地址将在第五个错误时被隔离。 这意味着联系人将自动从后续投放中排除。

   有关隔离的详细信息，请参阅 [了解隔离管理](../../sending/using/understanding-quarantine-management.md)。

## 电子邮件路由帐户 {#email-routing-accounts}

默 **[!UICONTROL Integrated email routing]** 认情况下提供外部帐户。 它包含允许应用程序发送电子邮件的技术参数。

![](assets/channels_2.png)

帐户类型必须始终设置为 **[!UICONTROL Routing]**、渠道设置为 **[!UICONTROL Email]** 和投放模式设置为 **[!UICONTROL Bulk delivery]**。

**相关主题**:

[外部帐户](../../administration/using/external-accounts.md)

## 电子邮件处理规则 {#email-processing-rules}

管理 **[!UICONTROL Email processing rules]** 员可以通过菜单访问该 **[!UICONTROL Administration > Channels > Email]** 文件。

请注意，电子邮件域和MX规则现在由Adobe Campaign增强MTA管理：
* **DKIM(DomainKeys Indentifed Mail)** ，电子邮件身份验证签名由增强的MTA对所有域的所有消息执行。 除非在增强的MTA级别 **另有指定，否则它不**&#x200B;会使用发送者ID **、** DomainKeys **或** S/MIME进行签名。
* 增强的MTA使用其自己的MX规则，该规则允许它根据您自己的历史电子邮件信誉以及来自您发送电子邮件的域的实时反馈按域自定义您的吞吐量。

### 弹回邮件 {#bounce-mails}

异步弹回仍由活动inMail进程通过规则进行 **[!UICONTROL Bounce mails]** 限定。

此规则包含可由远程服务器返回的字符串列表，并允许您限定错误(**Hard**、 **Soft** 或 **Ignored**)。

>[!NOTE]
>
>对于同步投放失败错误消息，Adobe Campaign增强MTA确定弹出类型和资格，并将该信息发回给活动。

有关弹回邮件资格的更多信息，请参阅此 [部分](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)。

<!--Because they are now managed by the Enhanced MTA, the bounce qualifications in the Campaign **[!UICONTROL Message qualification]** table are no longer used. For more on bounce mail qualification, see this [section](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

### Management of email domains {#managing-email-domains}

The email domains are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL Domain management]** rules are no longer used.

**DKIM (DomainKeys Identified Mail)** email authentication signing is done by the Enhanced MTA for all messages with all domains. It does not sign with **Sender ID**, **DomainKeys**, or **S/MIME** unless otherwise specified at the Enhanced MTA level.

### MX management {#mx-management}

The MX rules are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL MX management]** delivery throughput rules are no longer used.

The Enhanced MTA uses its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you are sending emails.-->

## 列表电子邮件属性 {#list-of-email-properties}

本节详细介绍了电子邮件或电子邮件模板的属性屏幕中可用参数的列表。

>[!NOTE]
>
>某些参数仅在模板中可用。 您可以访问的参 [数取决于您的权限](../../administration/using/users-management.md)。

要编辑电子邮件或电子邮件模板的属性，请使用按 **[!UICONTROL Edit properties]** 钮。

![](assets/delivery_options_1.png)

### 常规参数 {#general-parameters}

在电子邮件参数屏幕顶部，使用和字段标识电 **[!UICONTROL Label]** 子邮 **[!UICONTROL ID]** 件。 此信息显示在界面中，但消息收件人不可见。

![](assets/delivery_options_2.png)

>[!IMPORTANT]
>
>该ID必须是唯一的。

该字 **[!UICONTROL Brand]** 段允许您选择链接到投放的品牌。 有关使用和配置品牌的更多信息，请参阅品 [牌](../../administration/using/branding.md) 。

该字 **[!UICONTROL Campaign]** 段允许您输入链接到电子邮件的活动。

您还可以在相应的字 **[!UICONTROL Description]** 段中添加一个，并编辑列表中电子邮件缩略图上显示的图像。

### 发送参数 {#sending-parameters}

该 **[!UICONTROL Send]** 部分仅适用于电子邮件模板。 它包含以下参数：

#### 重试参数 {#retries-parameters}

临时未传送的消息可能会自动重试。 有关详细信息，请参阅 [投放临时故障后的重试](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)。

>[!NOTE]
>
>现在，基于IP在历史和当前给定域上的表现情况，重试之间的最小延迟和要执行的重试的最大数量由Adobe Campaign增强MTA管理。 将忽略 **活动** 重试设置。

<!--This section indicates how many retries should be performed the day after the send is started ( **[!UICONTROL Max. number of retries]** ) and the minimum delay between retries ( **[!UICONTROL Retry period]** ).

By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the [Validity period parameters](#validity-period-parameters) section.

The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template.-->

在 **活动中设置的** 投放持续时间设置 [(在“有效期参数”部分中定义](#validity-period-parameters) ) **仍将保留，但最多只有3.5天**。 此时，重试队列中的任何消息都将从队列中删除，并作为弹回发送回来。 有关投放故障的详细信息，请参阅此 [部分](../../sending/using/understanding-delivery-failures.md#about-delivery-failures)。

#### 电子邮件格式参数 {#email-format-parameters}

您可以配置要发送的电子邮件的格式。 有三个可用选项：

* **使用收件人首选项** （默认模式）:消息格式根据收件人用户档案中存储的数据定义，默认情况下存储在 **电子邮件格式字段** (@emailFormat)中。 如果收件人希望以某种格式接收消息，则此格式为发送的格式。 如果字段未完成，则会发送复合-可选消息（请参阅下文）。
* **让收件人邮件客户选择最合适的格式(复合-可选)**:该消息包含两种格式：文本和HTML。 接收时显示的格式取决于收件人邮件软件(复合-可选)的配置。

   >[!IMPORTANT]
   >
   >此选项包括两个版本的消息。 因此，它会影响投放吞吐量，因为消息大小较大。

* **以文本格式发送所有消息**:消息以文本格式发送。 不会发送HTML格式，但仅当镜像页面单击消息中的链接时，才会将其用于收件人。

#### SMTP测试模式 {#smtp-test-mode}

该选 **[!UICONTROL Enable SMTP test mode]** 项允许您测试通过SMTP连接发送的电子邮件，而不实际发送邮件。
这些消息将一直处理到与SMTP服务器建立连接，但不会发送。

![](assets/smtp-test-mode.png)

此选项适用于电子邮件和电子邮件模板。

如果为电子邮件模板启用SMTP测试模式选项，则通过此模板创建的所有电子邮件都将启用此选项。

>[!IMPORTANT]
>
>如果为电子邮件启用了此选项，则在取消选中该选项之前，不会发送任何消息。
>电子邮件或电子邮件模板仪表板中将显示一条警告消息。

有关配置SMTP的详细信息，请参阅电子邮 [件SMTP参数的列表](#list-of-email-smtp-parameters) 。

### 有效期参数 {#validity-period-parameters}

该部 **[!UICONTROL Validity period]** 分包含以下参数：

![](assets/delivery-validity-period.png)

* **[!UICONTROL Explicitly set validity dates]**:取消选中此框后，必须在和字段中输入持续 **[!UICONTROL Delivery duration]** 时间 **[!UICONTROL Resource validity limit]** 。

   如果要定义特定的时间和日期，请选中此框。

   ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Delivery duration]** / **[!UICONTROL Validity limit for sending messages]**:Adobe Campaign会从开始日期开始发送消息。 此字段允许您指定消息的发送持续时间。

   >[!IMPORTANT]
   >
   >此参数现在由Adobe Campaign增强MTA管理。 **您必须定义一个最多3.5天的值。** 如果定义的值高于3.5天，则不会将其考虑在内。

* **[!UICONTROL Resource validity duration]** / **[!UICONTROL Validity limit date for resources]**:此字段用于上传的资源，主要用于镜像页面和图像。 本页上的资源在有限的时间内有效（以节省磁盘空间）。
* **[!UICONTROL Mirror page management]**:镜像页面是可通过Web浏览器在线访问的HTML页面。 其内容与电子邮件内容相同。 默认情况下，如果链接已插入邮件内容，则会生成镜像页面。 此字段允许您修改生成此页面的方式：

   >[!IMPORTANT]
   >
   >必须为要创建镜像页面的电子邮件定义HTML内容。

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** （默认模式）:如果链接已插入到邮件内容中，则会生成镜像页面。
   * **强制生成镜像页面**:即使消息中未插入指向镜像页面的链接，也将创建镜像页面。
   * **请勿生成镜像页面**:不会生成镜像页面，即使链接位于消息中也是如此。
   * **生成仅使用消息ID可访问的镜像页面**:此选项允许您在镜像页面日志窗口中访问包含个性化信息的投放内容。

>[!NOTE]
>
>该 **[!UICONTROL Delivery duration]** 参数不适用于事务性消息。 有关事务性消息传递的更多信息，请参 [阅此部分](../../channels/using/about-transactional-messaging.md)。

### 跟踪参数 {#tracking-parameters}

该部 **[!UICONTROL Tracking]** 分包含以下参数：

* **[!UICONTROL Activate tracking]**:允许您激活／取消激活消息URL跟踪。 要管理每个消息URL的跟踪，请使用“电子邮 **[!UICONTROL Links]** 件设计器”操作栏中的图标。 请参 [阅关于跟踪的URL](../../designing/using/links.md#about-tracked-urls)。
* **[!UICONTROL Tracking validity limit]**:允许您定义在URL上激活跟踪的持续时间。
* **[!UICONTROL Substitution URL for expired URLs]**:您可以输入一个指向网页的URL，该网页将在跟踪过期后显示。

### 高级参数 {#advanced-parameters}

该部 **[!UICONTROL Advanced parameters]** 分包含多个参数。

在前面的字段中，您可以输入必要的信息，以详细描述电子邮件标头。 您可以在此处管理回复地址和文本以及发件人地址（填充“发件人：”字段）。 此信息可以个性化。

单击要更改的字段右侧的按钮，然后添加个性化字段、内容块或动态文本。

![](assets/advancedparameters.png)

个性化电子邮件内容文档中详细介绍了插入和 [使用个性化内容](../../designing/using/personalization.md) 。

#### 目标环境 {#target-context}

定位上下文允许您定义一组表，这些表将用于电子邮件定位(在受众定义屏幕中)和个性化(在HTML内容编辑器中定义个性化字段)。

#### 路由 {#routing}

此字段指示使用的路由模式。 它引用了外部帐户。 例如，如果您希望使用包含特定品牌配置的外部帐户，则可以使用此选项。

>[!NOTE]
>
>外部帐户可通过“管理” **>“应用程** 序设置” **>“** 外部帐户 **** ”菜单访问。

#### 准备 {#preparation}

“批准消息”部分详细介绍了准 [备消息](../../sending/using/preparing-the-send.md) 。

* **[!UICONTROL Typology]**:在发送之前，必须准备消息才能验证内容和配置。 在准备阶段应用的验证规则在类型学中进 **行定义**。 例如，对于电子邮件，准备过程包括检查主题、URL和图像等。 选择要在此字段中应用的类型学。

   >[!NOTE]
   >
   >可通过> **[!UICONTROL Administration]** >菜单访问 **[!UICONTROL Channels]** 的类型在本节 **[!UICONTROL Typologies]** 中显示 [](../../sending/using/about-typology-rules.md)。

* **[!UICONTROL Compute the label during delivery preparation]**:允许您使用个性化字段、内容块和动态文本在消息准备阶段计算电子邮件的标签值。

   还可以使用已声明到工作流外部信号投放中的事件变量个性化活动标签。 如需详细信息，请参阅[此部分](../../automating/using/calling-a-workflow-with-external-parameters.md)。

* **[!UICONTROL Save SQL queries in the log]**:此选项允许您在准备阶段在日志中添加SQL查询日志。

#### 验证设置 {#proof-settings}

此部分允许您配置要在验证的主题行中使用的默认前缀。 For more in this, refer to [this section](../../sending/using/sending-proofs.md).

### 列表电子邮件SMTP参数 {#list-of-email-smtp-parameters}

该部 **[!UICONTROL SMTP]** 分包含以下参数：

* **[!UICONTROL Character encoding]**:如果 **[!UICONTROL Force encoding]** 要强制进行消息编码，请选中此框，然后选择要使用的编码。
* **[!UICONTROL Bounce mails]**:默认情况下，平台的错误收件箱中会收到弹回邮件(在 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** >屏幕中 **[!UICONTROL Configuration]** 定义)。 要为电子邮件定义特定的错误地址，请在字段中输入该地 **[!UICONTROL Error address]** 址。
* **[!UICONTROL Additional SMTP headers]**:此选项允许向消息中添加其他SMTP头。 在字段中输入的脚 **[!UICONTROL Headers]** 本必须引用每行一个标题，形式 **为name:value**。 值会根据需要自动编码。

   >[!IMPORTANT]
   >
   >为高级用户保留添加用于插入其他SMTP头的脚本。 此脚本的语法必须符合以下内容类型的要求：没有未使用的空间，没有空行等。

### 访问授权参数的列表 {#list-of-access-authorization-parameters}

该部 **[!UICONTROL Access authorization]** 分包含以下参数：

* 该字 **[!UICONTROL Organizational unit]** 段允许您将访问此电子邮件的权限限制给某些用户。 与指定设备或父设备关联的用户将有权访问此电子邮件。 与子设备关联的用户将仅对此电子邮件具有读取权限。

   >[!NOTE]
   >
   >您可以通过“管理” **>“用户和安** 全”菜 **单配置组织单位** 。

* 自 **[!UICONTROL Created by]**&#x200B;动完 **[!UICONTROL Created]**&#x200B;成、 **[!UICONTROL Modified by]** 和 **[!UICONTROL Last modified]** 字段。
