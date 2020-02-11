---
title: 个性化电子邮件内容
description: 了解如何在电子邮件设计器中个性化电子邮件。
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705

---


# 个性化电子邮件内容 {#personalization}

Adobe Campaign提供的内容和消息显示可以通过多种不同的方式进行个性化。 这些方式可以根据条件根据配置文件进行组合。 一般而言，Adobe Campaign 允许您：

* 插入动态的个性化字段。请参 [阅插入个性化字段](#inserting-a-personalization-field)。
* 插入预定义的个性化基块。 请参 [阅添加内容块](#adding-a-content-block)。
* 个性化电子邮件的发送者。 请参 [阅个性化发送者](#personalizing-the-sender)。
* 个性化电子邮件主题。 See [Personalizing the subject line of an email](../../designing/using/subject-line.md#defining-the-subject-line-of-an-email).
* 创建条件性内容。请参阅 [在电子邮件中定义动态内容](#defining-dynamic-content-in-an-email)。

## 个性化发送者 {#personalizing-the-sender}

要定义将显示在所发送消息标题中的发件人姓名，请转到“电子邮件设计器”主页的选项卡（可通过主页图标访问）。 **[!UICONTROL Properties]** 有关此内容的详细信息，请 [参阅定义电子邮件的发送者](../../designing/using/subject-line.md#email-sender)。

您可以通过单击“发送者姓名”块来更改 **发送者姓名** 。 然后，该字段将变为可编辑字段，您可以输入要使用的名称。

这个领域可以个性化。 为此，您可以通过单击发件人姓名下方的图标来添加个性化字段、内容块和动态内容。

>[!NOTE]
>
>标题参数不得为空。 发送方地址是允许发送电子邮件的必填地址（RFC标准）。 Adobe Campaign检查输入的电子邮件地址的语法。

## 个性化URL{#personalizing-urls}

Adobe Campaign允许您通过向邮件中添加个性化字段、内容块或动态内容，来个性化消息中的一个或多个URL。 操作步骤：

1. 插入外部URL并指定其参数。 请参 [阅插入链接](../../designing/using/links.md#inserting-a-link)。
1. 如果未显示，请单击“设置”窗格中选定URL旁边的铅笔以访问个性化选项。
1. 添加要使用的个性化字段、内容块和动态内容。

   ![](assets/des_personalize_links.png)

1. 保存更改。

>[!NOTE]
>
>个性化URL不能应用于域名或URL扩展。 如果个性化不正确，则在消息分析过程中将显示错误消息。 选择内容块时，不允许您选择元素，如链接到 **镜像页面**。 此类块在链接中被禁止。

## 插入个性化字段{#inserting-a-personalization-field}

Adobe Campaign允许您将数据库中的字段插入页面，如配置文件的名称。

>[!NOTE]
>
>下图显示了如何使用电子邮件设计器插入 [个性化字段](../../designing/using/designing-content-in-adobe-campaign.md) 。

要向内容添加个性化字段，请执行以下操作：

1. 在文本块内单击，单击上下文 **[!UICONTROL Personalize]** 工具栏中的图标，然后选择 **[!UICONTROL Insert personalization field]**。 有关电子邮件设计器界面的详细信息，请参 [阅此部分](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface)。

   ![](assets/email_perso_field_1.png)

1. 选择要插入页面内容的字段。

   ![](assets/email_perso_field_2.png)

1. 单击 **[!UICONTROL Confirm]**.

该字段名称显示在编辑器中，并高亮显示。

![](assets/email_perso_field_3.png)

生成个性化后（例如，在预览和准备电子邮件时），此字段将替换为与目标配置文件对应的值。

>[!NOTE]
>
>如果电子邮件是通过工作流创建的，则在工作流中计算的其他数据也会显示在个性化字段中。 有关从工作流中添加其他数据的详细信息，请参阅 [丰富数据](../../automating/using/targeting-data.md#enriching-data) 。

## 添加内容块{#adding-a-content-block}

Adobe Campaign提供预配置内容块的列表。 这些内容块是动态的、个性化的，并具有特定的呈现效果。 例如，可以添加问候语或指向镜像页面的链接。

>[!NOTE]
>
>下图显示了如何使用电子邮件设计器插 [入内容块](../../designing/using/designing-content-in-adobe-campaign.md) 。

要添加内容块，请执行以下操作：

1. 在文本块内单击，单击上下文 **[!UICONTROL Personalize]** 工具栏中的图标，然后选择 **[!UICONTROL Insert content block]**。 有关电子邮件设计器界面的详细信息，请参 [阅此部分](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface)。

   ![](assets/email_content_block_1.png)

1. 选择要插入的内容块。 可用的区段因上下文（电子邮件或登录页面）而异。

   ![](assets/email_content_block_2.png)

1. 单击 **[!UICONTROL Save]**.

内容块的名称显示在编辑器中，并以黄色突出显示。 在生成个性化时，它会自动适应配置文件。

![](assets/email_content_block_3.png)

现成的内容块包括：

* **[!UICONTROL Database URL in emails (EmailUrlBase)]**:此内容块只能用于分 **发**。
* **[!UICONTROL Mirror page URL (MirrorPageUrl)]**:此内容块只能用于分 **发**。
* **[!UICONTROL Link to mirror page (MirrorPage)]**:此内容块只能用于分 **发**。
* **[!UICONTROL Greetings (Greetings)]**
* **[!UICONTROL Unsubscription link (UnsubscriptionLink)]**:此内容块只能用于分 **发**。
* **[!UICONTROL Social network sharing links (LandingPageViralLinks)]**:此内容块只能用于登 **陆页面**。
* **[!UICONTROL Default sender name (DefaultSenderName)]**:此内容块只能用于分 **发**。
* **[!UICONTROL Name of default reply-to email address (DefaultReplyName)]**:此内容块只能用于分 **发**。
* **[!UICONTROL Email address of default sender (DefaultSenderAddress)]**:此内容块只能用于分 **发**。
* **[!UICONTROL Default error email address (DefaultErrorAddress)]**:此内容块只能用于分 **发**。
* **[!UICONTROL Default reply-to email address (DefaultReplyAddress)]**:此内容块只能用于分 **发**。
* **[!UICONTROL Brand name (BrandingUsualName)]**
* **[!UICONTROL Link to the brand website (BrandingWebSiteLink)]**
* **[!UICONTROL Brand logo (BrandingLogo)]**
* **[!UICONTROL Notification style (notificationStyle)]**

### 创建自定义内容块 {#creating-custom-content-blocks}

您可以定义将插入消息或登录页面的新内容块。

要创建内容块，请执行以下步骤：

1. 从高 **[!UICONTROL Resources > Content blocks]** 级菜单中单击以访问内容块列表。
1. 单击该 **[!UICONTROL Create]** 按钮或复制预先存在的内容块。

   ![](assets/content_bloc_01.png)

1. 输入标签。
1. 选择块的 **[!UICONTROL Content type]**。 有三个可用选项：

   * **[!UICONTROL Shared]**:内容块可用于分发或登录页面。
   * **[!UICONTROL Delivery]**:内容块只能用于分发。
   * **[!UICONTROL Landing page]**:内容块只能用于登陆页面。
   ![](assets/content_bloc_02.png)

1. 您可以选择 **[!UICONTROL Targeting dimension]**。 有关此功能的详细信息，请参 [阅关于定位维](#about-targeting-dimension)。

   ![](assets/content_bloc_04.png)

1. 您可以选择选 **[!UICONTROL Depends on format]** 项来定义两个不同的块：一个用于HTML电子邮件，一个用于文本格式的电子邮件。 随后，编辑器中将显示两个选项卡（HTML和文本）以定义相应的内容。

   ![](assets/content_bloc_03.png)

1. 输入内容块的内容，然后单击按 **[!UICONTROL Create]** 钮。

您的内容块现在可用于消息或登陆页面的内容编辑器中。

>[!CAUTION]
>
>在编辑块的内容时，确保if语句的开始和结尾之间没有额外的空 *格* 。 在HTML中，空白显示在屏幕上，因此它们会影响您的内容布局。

### 关于定位维度 {#about-targeting-dimension}

定位维允许您定义可以使用内容块的消息类型。 这是为了防止在消息中使用不适当的块，这可能会导致错误。

事实上，在编辑消息时，您只能选择具有与消息的定位维兼容的定位维度的内容块。

例如，块的 **[!UICONTROL Unsubscription link]** 定位维是因为它包 **[!UICONTROL Profiles]** 含特定于资源的个性化字 **[!UICONTROL Profiles]** 段。 因此，您不能在事 **[!UICONTROL Unsubscription link]** 件事务消 [息中使用块](../../channels/using/event-transactional-messages.md)，因为该类型消息的定位维度是 **[!UICONTROL Real-time events]**。 但是，您可以在配置文 **件事务消息中使用** “取消订阅”链接块 [，因为该类型消息的定位维度是“配置](../../channels/using/profile-transactional-messages.md)文件” ****。 最后，该 **[!UICONTROL Link to mirror page]** 块没有定位维度，因此您可以在任何消息中使用它。

如果将此字段留空，则无论定位维度是什么，内容块都将与所有消息兼容。 如果设置了定位维，则该块将仅与具有相同定位维的消息兼容。

有关详细信息，请参阅定 [位维和资源](../../automating/using/query.md#targeting-dimensions-and-resources)。

**相关主题：**

* [插入个性化字段](#inserting-a-personalization-field)
* [添加内容块](#adding-a-content-block)
* [在电子邮件中定义动态内容](#defining-dynamic-content-in-an-email)

## 个性化图像源{#personalizing-an-image-source}

Adobe Campaign允许您根据特定标准个性化消息中的一个或多个图像或使用跟踪功能。 这是通过将个性化字段、内容块或动态内容插入图像源来实现的。 操作步骤：

1. 在消息内容中插入图像，或选择已存在的图像。
1. 在图像属性调板中，选中该 **[!UICONTROL Enable personalization]** 选项。

   ![](assets/des_personalize_images_1.png)

   将 **[!UICONTROL Source]** 显示字段，所选图像在编辑器中显示为 **个性化** 。

1. 单击字段按钮旁边 **[!UICONTROL Source]** 的铅笔以访问个性化选项。
1. 添加图像源后，添加您喜欢的个性化字段、内容块和动态内容。

   ![](assets/des_personalize_images_2.png)

   >[!NOTE]
   >
   >域名(http://mydomain.com)无法个性化，必须手动输入。 其余的URL可以个性化。 例如：http://mydomain.com/`[Gender]`.jpg

1. 确认更改。

## 条件内容 {#conditional-content}

### 定义可见性条件{#defining-a-visibility-condition}

可以为任何元素指定可见性条件。 只有在符合条件时，才会显示它。

要添加可见性条件，请选择一个块，并在其设置字段中输入要 **[!UICONTROL Visibility condition]** 考虑的条件。

![](assets/delivery_content_5.png)

此选项仅适用于以下元素：地址、块引号、中心、DIR、DIV、DL、FIELDSET、FORM、H1、H2、H3、H4、H5、H6、NOSCRIPT、OL、P、PRE、UL、TR、TD。

表达式编辑器显示在高级表 [达式编辑部分](../../automating/using/editing-queries.md#about-query-editor) 。

这些条件采用XTK表达式语法(例如， **context.profile.email !=&quot;** or **context.profile.status=&#39;0&#39;**)。 默认情况下，所有字段都可见。

>[!NOTE]
>
>无法为已包含具有动态内容的子元素的块或已构成动态内容的块定义条件。 无法编辑下拉列表等不可见的动态块。

### 在电子邮件中定义动态内容{#defining-dynamic-content-in-an-email}

在电子邮件中，您可以定义不同的内容，这些内容将根据表达式编辑器中定义的条件动态显示给收件人。 例如，从同一封电子邮件中，您可以确保每个配置文件都会根据其年龄范围收到不同的消息。

定义动态内容与定义可见 [性条件不同](#defining-a-visibility-condition)。

1. 选择片段、组件或元素。 在此示例中，选择一个图像。
1. 单击上 **[!UICONTROL Dynamic content]** 下文工具栏中的图标。

   ![](assets/dynamic_content_2.png)

   该 **[!UICONTROL Dynamic content]** 部分显示在左侧的调色板中。

   ![](assets/dynamic_content_3.png)

   默认情况下，此部分包含两个元素：默认变体和新变体。

   >[!NOTE]
   >
   >内容必须始终具有默认变体。 您无法删除它。

1. 单击按 **[!UICONTROL Edit]** 钮可定义第一个替代变体的显示条件。

   ![](assets/dynamic_content_4.png)

1. 指定标签，然后选择要设置为条件的字段。 例如，从节点 **[!UICONTROL General]** 中选择字 **[!UICONTROL Age]** 段

   ![](assets/dynamic_content_5.png)

1. 设置过滤条件。 例如，您希望向18岁到25岁之间的人显示不同的内容。

   ![](assets/dynamic_content_6.png)

1. 设置所有条件后，定义将应用该条件的优先级顺序并保存更改。

   ![](assets/dynamic_content_7.png)

   内容将按优先级从上到下的顺序显示在调色板中。 For more on priorities, refer to [this section](#defining-dynamic-content-in-an-email).

1. 为您刚刚定义的变体上传新图像。

   ![](assets/dynamic_content_8.png)

   18岁到25岁的收件人将看到新图像。

   ![](assets/dynamic_content_10.png)

1. 单击 **[!UICONTROL Add a condition]** 可添加新内容及其链接的规则。

   ![](assets/dynamic_content_9.png)

   例如，您可以添加一个不同的图像，以显示给26岁到35岁之间的人。

1. 以类似方式继续处理您希望动态显示的电子邮件的任何其他元素。 它可以是文本、按钮、片段等。 保存更改。

>[!CAUTION]
>
>在准备好消息后，在发送消息之前，请使用证据测试消息。 如果不这样做，可能会检测到某些错误，并且可能不会发送电子邮件。

**相关主题：**

* [发送校样](../../sending/using/sending-proofs.md)
* [高级表达式编辑](../../automating/using/editing-queries.md#about-query-editor)

### 优先级顺序 {#order-of-priority}

在表达式编辑器中，定义动态内容时，优先级顺序如下。

1. 您使用两种不同的条件定 **义两种不同的动态内容**，例如：

   **** 条件1:侧写的性别是男性的，

   **** 条件2:档案有20到30年历史。

   ![](assets/delivery_content_61.png)

   数据库中的某些配置文件符合这两个条件，但只能发送一封包含一个动态内容的电子邮件。

1. 因此，您必须为动态内容定义优先级。 优先级顺序为 **1** （因此相应的动态内容）的条件将被发送到配置文件，即使优先级顺序为 **2** 或 **** 3的另一个条件也被此配置文件满足。

   ![](assets/delivery_content_62.png)

每个动态内容只能定义一个优先级顺序。

## 示例：电子邮件个性化{#example-email-personalization}

在此示例中，营销服务团队的成员创建了一封电子邮件，通知他的某些客户他们只有一份特别优惠。 该团队成员决定根据客户各自的年龄个性化电子邮件。 18岁至27岁的客户将收到一封电子邮件，其中包含不同的图像和口号，发送给27岁以上的客户。

电子邮件的创建方式如下：

* 动态内容被应用到图像，并且这些动态内容根据年龄范围被配置。

   ![](assets/delivery_content_43.png)

   有关添加和配置动态内容的详细信息，请参阅 [在电子邮件中定义动态内容](#defining-dynamic-content-in-an-email) 。

* 个性化字段和动态内容将应用于文本。 根据个人资料的年龄范围，电子邮件以个人资料的名字或个人资料的标题和姓氏开头。

   ![](assets/delivery_content_44.png)

   添加和配置个性化字段在插入个性化字 [段部分有详细介绍](#inserting-a-personalization-field) 。

### 配置图像 {#configuring-images}

在此示例中，应用于图像的动态内容配置如下：

**目标18-27岁：**

1. 在调色板中选择动态内 **[!UICONTROL Properties]** 容，然后单击 **[!UICONTROL Edit]** 按钮。

   ![](assets/delivery_content_48.png)

1. 编辑标签，然后从节 **[!UICONTROL Age]** 点中选择字 **[!UICONTROL Profile]** 段。

   ![](assets/delivery_content_49.png)

1. 选择“ **大于”或“等于** ”运算符，然后输 **入18** ，以创建 **早于18的表达式** 。

   ![](assets/delivery_content_50.png)

1. 添加新 **[!UICONTROL Age]** 条件。

   在值字 **段中选择小于或等于** (Less than or equal to)运算符，后跟27以创建小 **于27的表达式** 。

   ![](assets/delivery_content_51.png)

1. 确认更改。

**要定位年龄在27岁及以上的档案，请执行以下操作：**

1. 从调色板中选择动态内容并编辑它。
1. 编辑标签，然后从节 **[!UICONTROL Age]** 点中选择字 **[!UICONTROL Profile]** 段。
1. 在值字 **段中添加** “大于”(Greater than)运算符后跟27，以创建 **早于27的表达式** 。

   ![](assets/delivery_content_52.png)

1. 确认更改。

您的动态内容配置正确。

### 配置文本 {#configuring-text}

在此示例中，应用于文本的动态内容配置如下：

**要定位18-27岁之间的档案，请执行以下操作：**

1. 选择所需的结构组件并添加动态内容。
1. 编辑动态内容并配置定位表达式。 请参阅配 [置图像](#configuring-images)。
1. 在结构组件中，在所需位置，单击上下文工 **[!UICONTROL Personalize]** 具栏中的图标并选择 **[!UICONTROL Insert personalization field]**。

   ![](assets/delivery_content_53.png)

1. 在出现的列表中，选择字段并 **[!UICONTROL First name]** 进行确认。

   ![](assets/delivery_content_54.png)

1. 然后，您的个性化字段完美地插入到选定的动态内容中。

**要定位年龄在27岁及以上的档案，请执行以下操作：**

1. 选择所需的结构组件并添加动态内容。
1. 编辑动态内容并配置定位表达式。 请参阅配 [置图像](#configuring-images)。
1. 在结构组件中，在所需位置，单击上下文工 **[!UICONTROL Personalize]** 具栏中的图标并选择 **[!UICONTROL Insert personalization field]**。
1. 从 **[!UICONTROL Title]** 下拉列表中选择。
1. 以类似方式继续添加 **[!UICONTROL Last name]** 字段。

   ![](assets/delivery_content_56.png)

现在，您的个性化字段应完美地插入到所选的动态内容中。

### 预览电子邮件 {#previewing-emails}

预览允许您在发送个性化字段和动态内容之前检查是否已正确配置个性化字段和动态内容 **[!UICONTROL Proofs]**。 在预览过程中，您可以选择与电子邮件目标相对应的不同测试配置文件。

如果没有测试配置文件，默认情况下显示的电子邮件为：

![](assets/delivery_content_45.png)

该电子邮件的口号中没有个性化字段，并且使用默认图像。

第一测试配置文件对应于年龄在18到27之间的客户端。 选择此配置文件后，将显示以下电子邮件：

![](assets/delivery_content_46.png)

与已有18-27年历史的表达式相对应的个性化字段，特别是配置文件的名字，正确配置，并且图像也根据配置文件进行了更改。

第二个配置文件对应于年龄在27岁以上的客户，并生成以下电子邮件：

![](assets/delivery_content_47.png)

由于内容动态，形象也发生了变化，而出现的口号正是为这个目标公众定义的更为正式的口号。

**相关主题：**

* [创建受众](../../audiences/using/creating-audiences.md)
* [准备发送](../../sending/using/preparing-the-send.md)

