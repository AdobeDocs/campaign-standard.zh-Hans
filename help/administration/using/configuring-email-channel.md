---
title: 配置电子邮件渠道
description: 了解如何配置电子邮件渠道。
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
source-git-commit: a3f760385da20a3aa39f96d955cfc2d77b708de2

---


# 配置电子邮件渠道{#configuring-email-channel}

## 电子邮件渠道参数 {#email-channel-parameters}

电子邮件配置屏幕允许您为电子邮件渠道定义参数。

![](assets/channels_1.png)

* **已发送电子邮件的标题参数**

   在本节中，您可以指定发 **[!UICONTROL masks]**送者地址和错误地址的授权。 如有必要，这些蒙版可以使用逗号分隔。 此配置是可选的。 输入这些字段后，在消息准备阶段，Adobe Campaign会检查输入的地址是否有效。 此操作模式可确保没有使用可能触发可交付性问题的地址。 传送地址必须在传送服务器上配置。

* **可交付性**

   此ID由支持提供。 必须使可交付性报告正确工作。

* **传送参数**

   Adobe Campaign会从开始日期开始发送消息。 该 **[!UICONTROL Message delivery duration]**字段允许您指定消息的发送持续时间。

   该字 **[!UICONTROL Online resources validity duration]**段用于上传的资源，主要用于镜像页面和图像。 本页上的资源在有限的时间内有效（以节省磁盘空间）。

* **重试次数**

   临时未传送的消息可能会自动重试。 此部分指示在发送开始后的一天(重试次数&#x200B;**)和重试之间的最小延迟(重试**&#x200B;期&#x200B;****)应执行多少次重试。

   默认情况下，在第一天内计划5次重试，最小时间间隔为1小时，在一天的24小时内展开。 每天一次重试的程序设定在此之后，直到交付截止日期（在部分中定义） **[!UICONTROL Delivery parameters]**为止。

* **电子邮件隔离参数**

   在字段 **[!UICONTROL Time between two significant errors]**中，输入一个值以定义应用程序在出现故障时在增加错误计数器之前等待的时间。 默认值：**&quot;1d&quot;**,1天。

   到达该 **[!UICONTROL Maximum number of errors before quarantine]**值后，将隔离电子邮件地址。 默认值：**&quot;5&quot;**:地址将在第六个错误时被隔离。 这意味着联系人将自动从后续分发中排除。

**相关主题**:

[了解隔离管理](../../sending/using/understanding-quarantine-management.md)

## 电子邮件路由帐户 {#email-routing-accounts}

默认 **[!UICONTROL Integrated email routing]**情况下提供外部帐户。 它包含允许应用程序发送电子邮件的技术参数。

![](assets/channels_2.png)

帐户类型必须始终设置为 **[!UICONTROL Routing]**、渠道设置**[!UICONTROL Email]** 和交付模式设置为 **[!UICONTROL Bulk delivery]**。

**相关主题**:

[外部帐户](../../administration/using/external-accounts.md)

## 电子邮件处理规则 {#email-processing-rules}

这些规则包含可由远程服务器返回的字符串列表，您可以通过该列表确定错误(**硬**、软 **或** 忽略 ****)。

默认规则如下：

**弹回邮件**

当电子邮件失败时，远程消息服务器会向应用程序设置中指定的地址返回弹回错误消息。 Adobe Campaign会将每封弹回邮件的内容与规则列表中的字符串进行比较，然后为其分配三个错误类型之一。

用户可以创建自己的规则。

>[!CAUTION]
>
>在导入包时以及通过“更新以实现可交付性 **”工作流更新数据时** ，将覆盖用户创建的规则。

**管理电子邮件域**

域管理规则用于调节特定域的传出电子邮件的流。 他们对弹回消息进行采样，并在适当时阻止发送。 Adobe Campaign消息传递服务器应用特定于域的规则，然后应用规则列表中以星号表示的一般大小写规则。 默认情况下，Adobe Campaign中提供Hotmail和MSN域的规则。

要配置域管理规则，只需设置阈值并选择某些SMTP参数。 阈 **值** (Threshold)是计算为错误百分比的限制，超过该百分比，向特定域的所有消息都被阻止。

例如，在一般情况下，如果错误率达到90%，则至少300条邮件的发送将被阻止3小时。

SMTP参 **数用作应用于阻止规则的过滤器** 。

* 您可以选择是否激活某些标识标准和加密密钥以检查域名，如 **Sender ID**、 **DomainKeys**、 **DKIM**&#x200B;和 **** S/MIMEConnect。
* **SMTP中继**:允许您为特定域配置IP地址和中继服务器的端口。

**MX管理**

每个规则都为MX定义了地址掩码。 因此，其名称与此掩码匹配的任何MX都符合条件。 遮罩可以包含“*”和“?” 常规字符。

例如，以下地址：

* a.mx.yahoo.com
* b.mx.yahoo.com
* c.mx.yahoo.com

与以下蒙版兼容：

* *.yahoo.com
* ?.mx.yahoo.com

这些规则按顺序应用：应用其MX掩码与目标MX兼容的第一条规则。

以下参数可用于每个规则：

* **[!UICONTROL Range of IDs]**:通过此选项，可以指示应用规则的标识符(publicId)范围。 您可以指定：

   * 数字：该规则将仅适用于此publicId。
   * 数字范围（数字1-数字2）:该规则将适用于这两个数字之间的所有publicId。
   如果字段为空，则该规则适用于所有ID。

* **[!UICONTROL Shared]**:此选项指示每小时最多的消息数和连接数适用于所有链接到此规则的MX。
* **[!UICONTROL Maximum number of connections]**:从给定地址到MX的同时连接的最大数量。
* **最大消息数**:可通过一个连接发送的最大消息数。 在此数量后，连接将关闭，并重新打开新连接。
* **[!UICONTROL Messages per hour]**:MX通过给定地址在一小时内可发送的最大消息数。

>[!CAUTION]
>
>* 如果参数已更改，则必须重新启动交付服务器(MTA)。
>* 管理规则的修改或创建仅适用于专家用户。
>



## 电子邮件属性列表 {#list-of-email-properties}

此部分详细列出了电子邮件或电子邮件模板的属性屏幕中可用的参数。

>[!NOTE]
>
>某些参数仅在模板中可用。 您可以访问的参 [数取决于您的权限](../../administration/using/users-management.md)。

要编辑电子邮件或电子邮件模板的属性，请使用按 **[!UICONTROL Edit properties]**钮。

![](assets/delivery_options_1.png)

### 常规参数 {#general-parameters}

在电子邮件参数屏幕顶部，使用和字段标识电 **[!UICONTROL Label]**子邮**[!UICONTROL ID]** 件。 此信息显示在界面中，但邮件收件人不可见。

![](assets/delivery_options_2.png)

>[!CAUTION]
>
>该ID必须是唯一的。

该字 **[!UICONTROL Brand]**段允许您选择链接到分发的品牌。 有关使用和配置品牌的更多信息，请参阅品[牌](../../administration/using/branding.md)。

该字 **[!UICONTROL Campaign]**段允许您输入链接到电子邮件的营销活动。

您还可以在相应的字 **[!UICONTROL Description]**段中添加一个图像，并编辑列表中电子邮件缩略图上显示的图像。

### 发送参数 {#sending-parameters}

该 **[!UICONTROL Send]**部分仅适用于电子邮件模板。 它包含以下参数：

#### 重试次数参数 {#retries-parameters}

临时未传送的消息可能会自动重试。 此部分指示在发送开始( **[!UICONTROL Max. number of retries]**)后应执行的重试次数和重试之间的最小延迟(**[!UICONTROL Retry period]** )。

默认情况下，在第一天内计划5次重试，最小时间间隔为1小时，在一天的24小时内展开。 每天一次重试的程序设置为在此之后，直到交付截止日期为止，该截止日期在“有效性”期间 [参数部分中定义](#validity-period-parameters) 。

可以全局更改重试次数（与Adobe技术管理员联系）或每个交付或交付模板的重试次数

#### 电子邮件格式参数 {#email-format-parameters}

您可以配置要发送的电子邮件的格式。 有三个可用选项：

* **使用收件人首选项** （默认模式）:消息格式根据存储在收件人配置文件中的数据定义，并默认存储在 **Email格式字段** (@emailFormat)中。 如果收件人希望以某种格式接收消息，则此格式为发送的格式。 如果字段未完成，则会发送多部分替代消息（请参阅下文）。
* **让收件人邮件客户端选择最合适的格式（多部分替代）**:该消息包含两种格式：文本和HTML。 接收时显示的格式取决于接收方的邮件软件（多部分替代）的配置。

   >[!CAUTION]
   >
   >此选项包括两个版本的消息。 因此，它会影响交付吞吐量，因为消息大小较大。

* **以文本格式发送所有消息**:消息以文本格式发送。 不会发送HTML格式，但仅当收件人单击消息中的链接时，才用于镜像页面。

#### SMTP测试模式 {#smtp-test-mode}

该选 **[!UICONTROL Enable SMTP test mode]**项允许您测试通过SMTP连接发送的电子邮件，而不实际发送邮件。
这些消息将一直处理到与SMTP服务器建立连接，但不会发送。

![](assets/smtp-test-mode.png)

此选项适用于电子邮件和电子邮件模板。

如果为电子邮件模板启用SMTP测试模式选项，则通过此模板创建的所有电子邮件都将启用此选项。

>[!CAUTION]
>
>如果为电子邮件启用了此选项，则在取消选中该选项之前，不会发送任何消息。
>电子邮件或电子邮件模板功能板中将显示警告。

有关配置SMTP的详细信息，请参阅电 [子邮件SMTP参数列表](#list-of-email-smtp-parameters) 。

### 有效期参数 {#validity-period-parameters}

该部 **[!UICONTROL Validity]**分包含以下参数：

* **[!UICONTROL Explicitly set validity dates]**:取消选中此框后，必须在和字段中输入持续**[!UICONTROL Delivery duration]** 时间 **[!UICONTROL Resource validity limit]**。 如果要定义特定的时间和日期，请选中此框。
* **[!UICONTROL Delivery duration]**:Adobe Campaign会从开始日期开始发送消息。 此字段允许您指定消息的发送持续时间。
* **[!UICONTROL Resource validity duration]**:此字段用于上传的资源，主要用于镜像页面和图像。 本页上的资源在有限的时间内有效（以节省磁盘空间）。
* **[!UICONTROL Mirror page management]**:镜像页面是可通过Web浏览器在线访问的HTML页面。 其内容与电子邮件内容相同。 默认情况下，如果链接已插入邮件内容中，则会生成镜像页面。 此字段允许您修改生成此页面的方式：

   >[!CAUTION]
   >
   >必须为要创建的镜像页面的电子邮件定义HTML内容。

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]**（默认模式）:如果链接已插入到邮件内容中，则会生成镜像页面。
   * **强制生成镜像页面**:即使消息中未插入指向镜像页面的链接，也会创建镜像页面。
   * **请勿生成镜像页面**:不会生成镜像页面，即使该链接位于消息中也是如此。
   * **生成仅使用消息ID可访问的镜像页面**:通过此选项，您可以在分发日志窗口中访问包含个性化信息的镜像页面的内容。

>[!NOTE]
>
>和 **[!UICONTROL Explicitly set validity dates]**参**[!UICONTROL Delivery duration]** 数不适用于事务消息。 有关事务性消息传递的更多信息，请参 [阅此部分](../../channels/using/about-transactional-messaging.md)。

### 跟踪参数 {#tracking-parameters}

该部 **[!UICONTROL Tracking]**分包含以下参数：

* **[!UICONTROL Activate tracking]**:允许您激活／取消激活消息URL跟踪。 要管理每个消息URL的跟踪，请使用“电子邮**[!UICONTROL Links]** 件设计器”操作栏中的图标。 请参 [阅关于跟踪的URL](../../designing/using/links.md#about-tracked-urls)。
* **[!UICONTROL Tracking validity limit]**:允许您定义在URL上激活跟踪的持续时间。
* **[!UICONTROL Substitution URL for expired URLs]**:您可以输入一个指向网页的URL，该网页将在跟踪过期后显示。

### 高级参数 {#advanced-parameters}

该部 **[!UICONTROL Advanced parameters]**分包含多个参数。

在前面的字段中，您可以输入必要的信息，以详细描述电子邮件标头。 您可以在此处管理回复地址和文本以及发件人地址（填充“发件人：”字段）。 此信息可以个性化。

单击要更改的字段右侧的按钮，然后添加个性化字段、内容块或动态文本。

![](assets/advancedparameters.png)

个性化电子邮件内容文档中详细介绍了插入和 [使用个性化内容](../../designing/using/personalization.md) 。

#### Target上下文 {#target-context}

定位上下文允许您定义一组表，这些表将用于电子邮件定位（在受众定义屏幕中）和个性化（在HTML内容编辑器中定义个性化字段）。

#### 路由 {#routing}

此字段指示使用的路由模式。 它引用一个外部帐户。 例如，如果您希望使用包含特定品牌配置的外部帐户，则可以使用此帐户。

>[!NOTE]
>
>可通过“管理” **>“应用程序设** 置” **>“外部帐户”菜** 单访问外部帐户 **** 。

#### 准备 {#preparation}

“批准消息”部分详细介绍了准 [备消息](../../sending/using/preparing-the-send.md) 。

* **[!UICONTROL Typology]**:在发送之前，必须准备消息才能验证内容和配置。 在准备阶段应用的验证规则在类型学中进**&#x200B;行定义&#x200B;**。 例如，对于电子邮件，准备过程包括检查主题、URL和图像等。 选择要在此字段中应用的类型学。

   >[!NOTE]
   >
   >可通过> **[!UICONTROL Administration]**>菜单访问的**[!UICONTROL Channels]** 排版在“排 **[!UICONTROL Typologies]**版[](../../administration/using/about-typology-rules.md)”部分中显示。

* **[!UICONTROL Compute the label during delivery preparation]**:允许您使用个性化字段、内容块和动态文本在消息准备阶段计算电子邮件的标签值。

   还可以使用已声明到工作流的外部信号活动中的事件变量个性化传送标签。 如需详细信息，请参阅[此部分](../../automating/using/calling-a-workflow-with-external-parameters.md)。

* **[!UICONTROL Save SQL queries in the log]**:此选项允许您在准备阶段将SQL查询日志添加到日志中。

### 电子邮件SMTP参数列表 {#list-of-email-smtp-parameters}

该部 **[!UICONTROL SMTP]**分包含以下参数：

* **[!UICONTROL Character encoding]**:如果**[!UICONTROL Force encoding]** 要强制进行消息编码，请选中此框，然后选择要使用的编码。
* **[!UICONTROL Bounce mails]**:默认情况下，平台的错误收件箱中会收到弹回邮件(在**[!UICONTROL Administration]** > **[!UICONTROL Channels]**>**[!UICONTROL Email]** >屏幕中 **[!UICONTROL Configuration]**定义)。 要为电子邮件定义特定的错误地址，请在字段中输入该地**[!UICONTROL Error address]** 址。
* **[!UICONTROL Additional SMTP headers]**:此选项允许向消息中添加其他SMTP头。 在字段中输入的脚**[!UICONTROL Headers]** 本必须引用每行一个标题，形式 **为name:value**。 值会根据需要自动编码。

   >[!CAUTION]
   >
   >为高级用户保留添加用于插入其他SMTP头的脚本。 此脚本的语法必须符合以下内容类型的要求：没有未使用的空间，没有空行等。

### 访问授权参数列表 {#list-of-access-authorization-parameters}

该部 **[!UICONTROL Access authorization]**分包含以下参数：

* 该字 **[!UICONTROL Organizational unit]**段允许您将访问此电子邮件的权限限制给某些用户。 与指定设备或父设备关联的用户将有权访问此电子邮件。 与子单元关联的用户将仅对此电子邮件具有读取权限。

   >[!NOTE]
   >
   >您可以通过“管理” **>“用户和安** 全”菜 **单配置组织单位** 。

* 自 **[!UICONTROL Created by]**动完**[!UICONTROL Created]**&#x200B;成、 **[!UICONTROL Modified by]**和**[!UICONTROL Last modified]** 字段。

## 存档电子邮件 {#archiving-emails}

您可以配置Adobe Campaign以保留从您的平台发送的电子邮件副本。

但是，Adobe Campaign本身不管理存档的文件。 它确实允许您将您选择的消息发送到专用地址，从中可以使用外部系统处理和存档消息。

当在传送模板中激活时，此功能允许您将相应已发送消息的精确副本发送到您必须指定的密件抄送电子邮件地址（对传送收件人不可见）。

### 建议和限制 {#recommendations-and-limitations}

* 此功能是可选的。 请检查您的许可协议，并联系您的帐户管理员以激活它。
* 您只能使用一个密送电子邮件地址。
* 只有成功发送的电子邮件才会被考虑在内。 弹回次数不是。
* 出于隐私原因，密件抄送电子邮件必须由能够安全地存储个人身份信息(PII)的存档系统处理。
* 在创建新的分发模板时，默认情况下不启用电子邮件密送，即使已购买此选项也是如此。 您必须在要使用它的每个分发模板中手动启用它。

### 激活电子邮件存档 {#activating-email-archiving}

密件抄送电子邮件在电子邮件模 [板中通过](../../start/using/marketing-activity-templates.md)专用选项激活：

1. 转到“资 **源** ”>“模 **板** ” **>“交**&#x200B;付模板”。
1. 复制现成模 **[!UICONTROL Send via email]**板。
1. 选择复制的模板。
1. 单击 **[!UICONTROL Edit properties]**按钮可编辑模板的属性。
1. 展开该 **[!UICONTROL Send]**部分。
1. 选中此 **[!UICONTROL Archive emails]**框可保留每个基于此模板的传送的所有已发送消息的副本。

   ![](assets/email_archiving.png)

>[!NOTE]
>
>如果打开并点进发送到密件抄送地址的电子邮件，则在发送分析中和发送分析中会考虑这一问题， **[!UICONTROL Total opens]****[!UICONTROL Clicks]** 这可能会导致一些计算错误。
