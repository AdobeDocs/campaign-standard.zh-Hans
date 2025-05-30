---
title: 在 Adobe Campaign Standard 中配置电子邮件渠道
description: 了解如何在Adobe Campaign Standard中配置电子邮件渠道
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 76d70fd1-dd93-4a6d-b18c-96ebe5a27a7d
source-git-commit: 2e81a05b1b647991250d13d7d37f5da275a8db44
workflow-type: tm+mt
source-wordcount: '2749'
ht-degree: 57%

---

# 配置电子邮件渠道{#configuring-email-channel}

Campaign [管理员](../../administration/using/users-management.md#functional-administrators)可以配置电子邮件渠道设置。这些高级设置包括常规电子邮件渠道参数、电子邮件路由帐户、电子邮件处理规则和电子邮件属性。在此页面上，了解如何编辑常规电子邮件和发送参数的默认值。

## 电子邮件渠道参数 {#email-channel-parameters}

利用电子邮件配置屏幕，可定义电子邮件渠道的参数。管理员通过 **[!UICONTROL Administration]> [!UICONTROL Channels] > [!UICONTROL Email] >[!UICONTROL Configuration]** 菜单访问这些配置。

![](assets/channels_1.png)

* **授权的掩码字段**

  **[!UICONTROL Header parameters of sent emails]** 部分列出了授权电子邮件地址，您可以使用这些地址向收件人发送电子邮件（发件人地址），并允许他们发回自动回复，如异步退件、“不在办公室”回复等（错误地址）。

  Adobe Campaign 会检查在消息准备阶段期间输入的地址是否有效。此操作模式可确保不使用可能触发可投放性问题的地址。

   * 发件人地址和错误地址均由 Adobe 设置。这些字段不能为空。
   * 您无法编辑这些字段。要更新地址，请与 Adobe 客户关怀团队联系。
   * 要添加其他地址，您可以使用[促销活动控制面板](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/setting-up-new-subdomain.html?lang=zh-Hans)来设置新的子域，或与Adobe客户关怀团队联系。 请注意，如果使用多个掩码，则它们之间用逗号分隔。
   * 使用星号(如&#x200B;**@yourdomain.com**)设置地址是很好的做法：它允许您使用以子域名结尾的任何地址。

* **可投放性**

  Adobe 客户关怀团队提供了 **[!UICONTROL Delivery reports ID]**。通过此功能，可使用技术可投放性报告中使用的可投放性 ID 来标识个个实例。
  <!--The Technical Deliverability report is not accessible through the UI in ACS. It will be replaced with 250ok in the future (project starting).-->

* **投放参数**

  Adobe Campaign从开始日期起发送消息。

  当投放中的消息因临时错误或软退回而被拒绝时，Campaign会每天重试发送此消息。 使用&#x200B;**[!UICONTROL Message delivery duration]**&#x200B;字段指定重试期间的时间范围。

  >[!IMPORTANT]
  >
  >**现在，Campaign 中仅使用不超过 3.5 天的该参数设置。**&#x200B;如果定义的值超过 3.5 天，则不会将其考虑在内。

  **[!UICONTROL Online resources validity duration]** 字段用于已上传的资源，主要用于镜像页面和图像。本页上的资源仅在限制时间内有效（以节省磁盘空间）。

* **重试**

  临时未送达的消息将会自动重试。有关更多信息，请参阅[投放临时失败后重试](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)。

  >[!IMPORTANT]
  >
  >要执行的最大重试次数和重试之间的最小延迟现在取决于IP在给定域名的历史和当前表现如何。 Campaign中的&#x200B;**[!UICONTROL Retry period]**&#x200B;和&#x200B;**[!UICONTROL Number of retries]**&#x200B;设置将被忽略。

  <!--This section indicates how many retries should be performed the day after the send is started (**Number of retries**) and the minimum delay between retries (**Retry period**). By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.-->

* **电子邮件隔离参数**

  在 **[!UICONTROL Time between two significant errors]** 字段中，输入一个值，以定义应用程序在软退件失败时，需要等待多久才增加错误计数。默认值为“**1d**”，即 1 天。

  到达 **[!UICONTROL Maximum number of errors before quarantine]** 值后，将隔离该电子邮件地址。默认值为&#x200B;**&quot;5&quot;**：第5次出错时将该地址隔离。 这意味着后续投放中将自动排除改联系人。
  <!--Actually the way ACS works is that the address is already on the quarantine list on the first bounce, but with a different status meaning that the error count has started.-->

  有关隔离的更多信息，请参阅[了解隔离管理](../../sending/using/understanding-quarantine-management.md)。

## 电子邮件路由帐户 {#email-routing-accounts}

默认情况下，会提供 **[!UICONTROL Integrated email routing]** 外部帐户。其中包含允许应用程序发送电子邮件的技术参数。

![](assets/channels_2.png)

帐户类型必须始终设置为 **[!UICONTROL Routing]**、渠道设置为 **[!UICONTROL Email]** 以及投放模式设置为 **[!UICONTROL Bulk delivery]**。

**相关主题**：

[外部帐户](../../administration/using/external-accounts.md)

## 电子邮件处理规则 {#email-processing-rules}

管理员可以通过 **[!UICONTROL Administration > Channels > Email]** 菜单访问 **[!UICONTROL Email processing rules]**。

>[!IMPORTANT]
>
>电子邮件域和MX规则现在将自动管理<!--by the Adobe Campaign Enhanced MTA (Message Transfer Agent)-->，无法更改。

* **DKIM (DomainKeys Indified Mail)**&#x200B;电子邮件身份验证签名已针对所有域的所有邮件完成。 它未使用&#x200B;**发件人ID**、**DomainKeys**&#x200B;或&#x200B;**S/MIME**&#x200B;进行签名。
* MX规则根据您自己的历史电子邮件信誉以及来自您发送电子邮件的域名的实时反馈，按域自动自定义您的吞吐量。

<!--Note that the email domains and the MX rules are now managed by the Adobe Campaign Enhanced MTA:
* **DKIM (DomainKeys Identified Mail)** email authentication signing is done by the Enhanced MTA for all messages with all domains. It does not sign with **Sender ID**, **DomainKeys**, or **S/MIME** unless otherwise specified at the Enhanced MTA level.
* The Enhanced MTA uses its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you are sending emails.-->

### 退回电子邮件 {#bounce-mails}

仍由 Campaign inMail 流程通过 **[!UICONTROL Bounce mails]** 规则对异步退件进行鉴别。

这些规则包含可由远程服务器返回的字符串列表，并可让您鉴别错误（**Hard**、**Soft** 或 **Ignored**）。

>[!IMPORTANT]
>
>同步投放失败错误消息现在由Adobe Campaign Enhanced MTA进行鉴别，该MTA确定退回类型和鉴别，并将该信息发回至Campaign。

有关退回邮件鉴别的更多信息，请参阅[此章节](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)。

<!--Because they are now managed by the Enhanced MTA, the bounce qualifications in the Campaign **[!UICONTROL Message qualification]** table are no longer used. For more on bounce mail qualification, see this [section](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

### Management of email domains {#managing-email-domains}

The email domains are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL Domain management]** rules are no longer used.

**DKIM (DomainKeys Identified Mail)** email authentication signing is done by the Enhanced MTA for all messages with all domains. It does not sign with **Sender ID**, **DomainKeys**, or **S/MIME** unless otherwise specified at the Enhanced MTA level.

### MX management {#mx-management}

The MX rules are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL MX management]** delivery throughput rules are no longer used.

The Enhanced MTA uses its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you are sending emails.-->

## 电子邮件属性列表 {#list-of-email-properties}

本节详细介绍了电子邮件或电子邮件模板之属性屏幕中提供的参数列表。

>[!NOTE]
>
>部分参数仅用在模板中。您可以访问的参数，[取决于您的权限](../../administration/using/users-management.md)。

要编辑电子邮件或电子邮件模板的属性，请使用 **[!UICONTROL Edit properties]** 按钮。

![](assets/delivery_options_1.png)

### 常规参数 {#general-parameters}

在电子邮件参数屏幕的顶部，使用 **[!UICONTROL Label]** 和 **[!UICONTROL ID]** 字段标识电子邮件。此信息显示在界面中，但消息收件人不可见。

![](assets/delivery_options_2.png)

>[!IMPORTANT]
>
>ID 必须具有唯一性。

使用&#x200B;**[!UICONTROL Brand]**&#x200B;字段选择链接到投放的品牌。 有关使用和配置品牌的更多信息，请参阅[品牌策略](../../administration/using/branding.md)一节。

在&#x200B;**[!UICONTROL Campaign]**&#x200B;字段中，输入与电子邮件关联的营销策划。

您还可以在相应的字段中添加 **[!UICONTROL Description]**，并编辑列表中电子邮件缩览图所显示的图像

### 发送参数 {#sending-parameters}

**[!UICONTROL Send]** 部分仅适用于电子邮件模板。其中包含以下参数：

#### 重试参数 {#retries-parameters}

临时未送达的消息将会自动重试。有关更多信息，请参阅[投放临时失败后重试](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)。

>[!IMPORTANT]
>
>重试之间的最短延迟和执行重试的最大次数，现在取决于IP在给定域名的历史和当前表现如何。 Campaign中的&#x200B;**[!UICONTROL Retry period]**&#x200B;和&#x200B;**[!UICONTROL Max. number of retries]**&#x200B;设置将被忽略。

仍会遵从在 Campaign 中设置的&#x200B;**投放持续时间设置**（在[有效期参数](#validity-period-parameters)部分中定义），**但最长只有 3.5 天**。达到该时间后，重试队列中的所有消息都将从队列中删除，并作为退件发回。有关投放失败的更多信息，请参阅此[章节](../../sending/using/understanding-delivery-failures.md#about-delivery-failures)。

#### 电子邮件格式参数 {#email-format-parameters}

您可以配置待发送电子邮件的格式。提供了三个选项：

* **使用收件人首选项** （默认模式）：根据收件人用户档案中存储的数据（默认存储在 **Email format** 字段 (@emailFormat) 中）定义消息格式。如果收件人希望以特定格式接收消息，则会将该格式用于发送的邮件。如果未填写该字段，则会发送 multipart-alternative 消息（请参阅下文）。
* **让收件人邮件客户端选择最合适的格式 (multipart-alternative)**：该消息包含两种格式：文本和 HTML。接收时显示的格式取决于收件人邮件软件的配置 (multipart-alternative)。

  >[!IMPORTANT]
  >
  >此选项包含消息的两个版本。因为增加了消息大小，因此会影响投放吞吐量。

* **以文本格式发送所有消息**：消息以文本格式发送。不会发送 HTML 格式，仅当收件人单击消息中的链接时，才会将其用于镜像页面。

#### SMTP测试模式 {#smtp-test-mode}

使用&#x200B;**[!UICONTROL Enable SMTP test mode]**&#x200B;选项测试通过SMTP连接发送的电子邮件，而不实际发送邮件。 处理投放直至连接到 SMTP 服务器，但不发送：对于投放的每个收件人，Campaign 连接到 SMTP 提供商服务器，执行 SMTP RCPT TO 命令，并在执行 SMTP DATA 命令之前关闭连接。

![](assets/smtp-test-mode.png)

电子邮件和电子邮件模板都可使用此选项。

如果为某个电子邮件模板启用 SMTP 测试模式选项，则从该模板创建的所有电子邮件都将启用此选项。

>[!IMPORTANT]
>
>如果为某一封电子邮件启用此选项，则不会发送任何邮件，直到将其取消选中为止。
>电子邮件或电子邮件模板的仪表板中将显示警告。

有关配置 SMTP 的更多信息，请参阅[电子邮件 SMTP 参数列表](#list-of-email-smtp-parameters)。

### 有效期参数 {#validity-period-parameters}

**[!UICONTROL Validity period]** 部分包含以下参数：

![](assets/delivery-validity-period.png)

* **[!UICONTROL Explicitly set validity dates]**：如果未勾选此框，则必须在 **[!UICONTROL Delivery duration]** 和 **[!UICONTROL Resource validity limit]** 字段中输入持续时间。

  如果要定义特定的时间和日期，请勾选此框。

  ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Delivery duration]** / **[!UICONTROL Validity limit for sending messages]**：Adobe Campaign 从开始日期起发送消息。使用此字段可指定发送消息的时段。

  >[!IMPORTANT]
  >
  >**您必须定义一个最大不超过 3.5 天的值。**&#x200B;如果设置的值超过3.5天，则不会考虑该值。
  >
  >**[!UICONTROL Delivery duration]** 参数不适用于事务型消息。有关事务型消息传递的更多信息，请参阅[此章节](../../channels/using/getting-started-with-transactional-msg.md)。

* **[!UICONTROL Resource validity duration]** / **[!UICONTROL Validity limit date for resources]**：此字段用于已上传的资源，主要用于镜像页面和图像。本页上的资源仅在限制时间内有效（以节省磁盘空间）。
* **[!UICONTROL Mirror page management]**：镜像页面是可通过 Web 浏览器在线访问的 HTML 页面。其内容与电子邮件内容相同。默认情况下，如果将链接插入到邮件内容中，则会生成镜像页面。使用此字段可修改生成此页面的方式：

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]**（默认模式）：如果将链接插入到邮件内容中，则会生成镜像页面。
   * **强制生成镜像页面**：即使消息中未插入指向镜像页面的链接，也会创建镜像页面。
   * **不生成镜像页面**：即使消息中存在链接，也不生成镜像页面。
   * **生成仅可使用消息 ID 访问的镜像页面**：利用此选项，您可以在投放日志窗口中访问带有个性化信息的镜像页面内容。

  >[!IMPORTANT]
  >
  >仅当为电子邮件定义了HTML内容时，才会生成镜像页面。
  >


### 跟踪参数 {#tracking-parameters}

**[!UICONTROL Tracking]** 部分包含以下参数：

* **[!UICONTROL Activate tracking]**：使用此选项可激活/停用邮件URL跟踪。 要管理每个消息 URL 的跟踪，请使用 Email Designer 操作栏中的 **[!UICONTROL Links]** 图标。请参阅[关于跟踪的 URL](../../designing/using/links.md#about-tracked-urls)。
* **[!UICONTROL Tracking validity limit]**：使用此选项定义将在URL上激活跟踪的持续时间。
* **[!UICONTROL Substitution URL for expired URLs]**：使用此选项可输入回退网页的URL：跟踪过期后即会显示该URL。
* **[!UICONTROL Use tracking pixel at the top of email]**：使用此选项可在电子邮件的顶部而不是底部移动跟踪像素。 默认情况下，此像素位于电子邮件的底部。 如果发送大型消息，请考虑将此像素移动到电子邮件的顶部而不是底部，以改进打开跟踪 — 否则，某些电子邮件提供商可能会剪切跟踪像素。

### 高级参数 {#advanced-parameters}

**[!UICONTROL Advanced parameters]** 部分包含多个参数。

利用第一个字段，您可以输入必要的信息以制作电子邮件标题。您可以在此处管理回复地址和文本以及发件人地址（用于填充“From:”字段）。此信息可以个性化。

单击要更改的字段右侧的按钮，然后添加个性化字段、内容块或动态文本。

![](assets/advancedparameters.png)

有关插入和使用个性化内容的详细信息，请参阅[&#128279;](../../designing/using/personalization.md)个性化电子邮件内容文档。

#### 目标上下文 {#target-context}

使用定位上下文定义一组表格，这些表格将用于进行电子邮件定位（在受众定义屏幕中）和个性化(在HTML内容编辑器中定义个性化字段)。

#### 路由 {#routing}

此字段指示所用的路由模式。路由需引用外部帐户。例如，如果您希望使用包含特定品牌策略配置的外部帐户，则可以使用此选项。

>[!NOTE]
>
>可通过 **Administration** > **Application settings** > **External accounts** 菜单访问外部帐户。

#### 准备 {#preparation}

有关准备消息的详情，请参阅[批准消息](../../sending/using/preparing-the-send.md)一节。

* **[!UICONTROL Typology]**：在发送之前，必须准备消息以证内容和配置。在&#x200B;**分类**&#x200B;中定义要在准备阶段期间应用的验证规则。例如，对于电子邮件，准备包括检查主题、URL 和图像等。选择要应用于此字段的分类。

  >[!NOTE]
  >
  >可通过 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** 菜单访问“分类”，请参阅[此章节](../../sending/using/about-typology-rules.md)。

* **[!UICONTROL Compute the label during delivery preparation]**：在邮件准备阶段期间，使用此选项可使用个性化字段、内容块和动态文本计算电子邮件的标签值。

  还可以使用已声明到工作流外部信号活动中的事件变量，将投放标签个性化。有关更多信息，请参阅[此章节](../../automating/using/calling-a-workflow-with-external-parameters.md)。

* **[!UICONTROL Save SQL queries in the log]**：在准备阶段期间，使用此选项在日志中添加SQL查询日志。

#### 校样设置 {#proof-settings}

在此部分中，您可以配置要在验证消息的主题行中使用的默认前缀。 在[本节](../../sending/using/sending-proofs.md)中了解有关校样的更多信息。

### 电子邮件SMTP参数列表 {#list-of-email-smtp-parameters}

**[!UICONTROL SMTP]** 部分包含以下参数：

* **[!UICONTROL Character encoding]**：如果要强制进行消息编码，请选中 **[!UICONTROL Force encoding]** 方框，然后选择要使用的编码。
* **[!UICONTROL Bounce mails]**：默认情况下，平台的错误收件箱中会收到退回的邮件（**[!UICONTROL Administration]** >中 **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Configuration]** 屏幕中定义）。要定义电子邮件的特定错误地址，请在 **[!UICONTROL Error address]** 字段中输入该地址。
* **[!UICONTROL Additional SMTP headers]**：此选项用于向邮件中添加其他 SMTP 标头。在 **[!UICONTROL Headers]** 字段中输入的脚本必须每行引用一个标头，其形式为 **name:value**。如有必要，将自动对值进行编码。

  >[!IMPORTANT]
  >
  >高级用户可随时添加脚本以插入其他 SMTP 标头。此脚本的语法必须符合此内容类型的要求：没有未使用的空格，没有空行等。

  从 2024 年 6 月 1 日开始，Google 和 Yahoo! 要求发件人遵守&#x200B;**一键式列表取消订阅**。 Campaign支持用于投放模板的现成功能。

  若要将&#x200B;**一键式列表取消订阅**&#x200B;应用于所有非模板电子邮件投放，您必须运行&#x200B;**[!UICONTROL Copy headers from delivery templates]**&#x200B;技术工作流。 [了解详情](technical-workflows.md)

  >[!CAUTION]
  >
  >如果修改电子邮件模板&#x200B;**[!UICONTROL Additional SMTP headers]**&#x200B;中的标头值，则可能会违反Google和Yahoo！的&#x200B;**一键式List-Unsubscribe**&#x200B;要求。

### 访问授权参数的列表 {#list-of-access-authorization-parameters}

**[!UICONTROL Access authorization]** 部分包含以下参数：

* **[!UICONTROL Organizational unit]**&#x200B;字段用于限制特定用户访问此电子邮件。 与指定单位或父单位关联的用户，具有此电子邮件的读写权限。与子单位关联的用户，仅具有此电子邮件的读取权限。

  >[!NOTE]
  >
  >您可以通过 **Administration** > **Users &amp; Security** 菜单配置组织单位。

* **[!UICONTROL Created by]**、**[!UICONTROL Created]**、**[!UICONTROL Modified by]** 和 **[!UICONTROL Last modified]** 字段会自动填写。

## 旧版设置 {#legacy-settings}

如果您&#x200B;**NOT**&#x200B;运行的是最新版本的Campaign，则下面描述的参数和UI部分仍适用于您。

### 重试 {#legacy-retries}

[配置菜单](#email-channel-parameters)和电子邮件属性[发送参数](#retries-parameters)中的&#x200B;**[!UICONTROL Retries]**&#x200B;设置指示在发送开始后一天应执行多少次重试(**[!UICONTROL Number of retries]** / **[!UICONTROL Max. number of retries]**)以及两次重试之间的最小延迟(**[!UICONTROL Retry period]**)。

重试次数可以全局更改(请联系您的Adobe技术管理员)，也可以针对每个投放或投放模板进行更改。

默认情况下，第一天将安排五次重试，最小间隔为一小时，分布在一天中的24小时。 每天进行一次重试的程序设置在此之后，并一直到投放截止日期为止，该截止日期在&#x200B;**[!UICONTROL Configuration]**&#x200B;菜单的&#x200B;**[!UICONTROL Delivery parameters]**&#x200B;部分中或在投放级别的&#x200B;**[!UICONTROL Validity period]**&#x200B;部分中全局定义（请参阅下面的[投放持续时间](#legacy-delivery-duration)部分）。

### 投放持续时间 {#legacy-delivery-duration}

使用[配置菜单](#email-channel-parameters)中的&#x200B;**[!UICONTROL Message delivery duration]**&#x200B;参数指定在投放中遇到临时错误或软退回的任何消息将重试的时间范围。

使用[有效期参数](#validity-period-parameters)部分中的&#x200B;**[!UICONTROL Delivery duration]**&#x200B;或&#x200B;**[!UICONTROL Validity limit for sending messages]**&#x200B;参数指定可以发送消息的持续时间。

### 电子邮件处理规则 {#legacy-email-processing-rules}

管理员可以通过&#x200B;**[!UICONTROL Administration > Channels > Email > Email processing rules]**&#x200B;菜单访问和修改&#x200B;**[!UICONTROL MX management]**、**[!UICONTROL Bounce mails]**&#x200B;和&#x200B;**[!UICONTROL Domain management]**&#x200B;规则。 [了解详情](#email-processing-rules)

### 退回邮件鉴别 {#legacy-bounce-mail-qualification}

要列出各种退回及其关联的错误类型和原因，请单击左上方的&#x200B;**Adobe**&#x200B;徽标，然后选择&#x200B;**[!UICONTROL Administration > Channels > Quarantines > Message qualification]**。

退回可以具有以下资格状态：

* **[!UICONTROL To qualify]**：需要限定退回邮件。 必须由可交付性团队进行资格鉴定，以确保平台可交付性正常运行。 只要不满足条件，就不会使用退回邮件来扩充电子邮件处理规则的列表。
* **[!UICONTROL Keep]**：退回邮件已限定，将由&#x200B;**可投放性更新**&#x200B;工作流使用，以与现有电子邮件处理规则进行比较并扩充列表。
* **[!UICONTROL Ignore]**：退回邮件已限定，但&#x200B;**可投放性更新**&#x200B;工作流将不使用退回邮件。 因此，它不会发送到客户端实例。

>[!NOTE]
>
>如果ISP发生中断，通过Campaign发送的电子邮件将被错误地标记为退回。 要更正此问题，您需要更新退回鉴别。 [了解详情](../../administration/using/update-bounce-qualification.md)。

<!--Bounces are qualified through the **[!UICONTROL Bounce mails]** processing rule. For more on accessing this rule, refer to this [section](#legacy-bounce-mail-qualification).-->

### 已交付指示器报告 {#legacy-delivered-status-report}

在每封邮件的&#x200B;**[!UICONTROL Summary]**&#x200B;视图中，随着软退信和硬退信的回发，在投放的有效期内，**[!UICONTROL Delivered]**&#x200B;百分比会逐步上升。

软退回邮件在投放后的第一天显示为&#x200B;**[!UICONTROL Failed]**。 这些消息每天都会重试，直到投放的有效期结束。
