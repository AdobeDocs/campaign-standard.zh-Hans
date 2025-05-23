---
title: 个性化电子邮件内容
description: 了解如何在电子邮件Designer中个性化电子邮件。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 3ea58bcf-234e-4dac-b296-da3f57e18a7d
source-git-commit: 9291eb06c35b1d06c0a992fa64a460215477f57e
workflow-type: tm+mt
source-wordcount: '2611'
ht-degree: 4%

---

# 个性化电子邮件内容 {#personalization}

Adobe Campaign投放的消息的内容和显示可以通过几种不同的方式进行个性化。 根据用户档案，可以根据标准组合这些方式。 一般而言，Adobe Campaign 允许您：

* 插入动态的个性化字段。请参阅[插入个性化字段](#inserting-a-personalization-field)。
* 插入预定义的个性化块。 请参阅[添加内容块](#adding-a-content-block)。
* 使电子邮件的发件人个性化。 请参阅[个性化发件人](#personalizing-the-sender)。
* 将电子邮件主题个性化。 请参阅[个性化电子邮件的主题行](../../designing/using/subject-line.md#subject-line)。
* 创建条件性内容。请参阅[在电子邮件中定义动态内容](#defining-dynamic-content-in-an-email)。

## 个性化发件人 {#personalizing-the-sender}

要定义将显示在已发送邮件标题中的发件人名称，请转到Designer主页的&#x200B;**[!UICONTROL Properties]**&#x200B;选项卡（可通过主页图标访问）。 有关此内容的详细信息，请参阅[定义电子邮件的发件人](../../designing/using/subject-line.md#email-sender)。

您可以通过单击&#x200B;**发件人姓名**&#x200B;块来更改发件人姓名。 该字段随后将变为可编辑，您可以输入要使用的名称。

此字段可个性化。 为此，您可以通过单击发件人名称下方的图标，添加个性化字段、内容块和动态内容。

>[!NOTE]
>
>标头参数不能为空。 发件人的地址是允许发送电子邮件的必备项（RFC标准）。 Adobe Campaign检查所输入电子邮件地址的语法。

## 个性化URL {#personalizing-urls}

Adobe Campaign允许您通过向消息中添加个性化字段、内容块或动态内容，来对消息中的一个或多个URL进行个性化。 操作步骤：

1. 插入外部URL并指定其参数。 请参阅[插入链接](../../designing/using/links.md#inserting-a-link)。
1. 如果未显示，请单击“设置”窗格中所选URL旁边的铅笔以访问个性化选项。
1. 添加要使用的个性化字段、内容块和动态内容。

   ![](assets/des_personalize_links.png)

1. 保存您的更改。

>[!NOTE]
>
>如果禁用了用于跟踪链接的URL签名机制，则个性化URL不能应用于域名，也不能应用于URL扩展。 如果个性化不正确，则在消息分析期间将显示错误消息。
>
>选择内容块时，不允许选择元素，如&#x200B;**链接到镜像页面**。 此类块禁止在链接内使用。

## 插入个性化字段{#inserting-a-personalization-field}

利用Adobe Campaign，可将来自数据库的字段插入页面，如用户档案的名字。

>[!NOTE]
>
>下图显示如何使用电子邮件的[电子邮件Designer](../../designing/using/designing-content-in-adobe-campaign.md)插入个性化字段。

要向内容添加个性化字段，请执行以下操作：

1. 单击文本块内部，单击上下文工具栏中的&#x200B;**[!UICONTROL Personalize]**&#x200B;图标并选择&#x200B;**[!UICONTROL Insert personalization field]**。 有关电子邮件Designer界面的详细信息，请参阅[此部分](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface)。

   ![](assets/email_perso_field_1.png)

1. 选择要插入到页面内容中的字段。

   ![](assets/email_perso_field_2.png)

1. 单击 **[!UICONTROL Confirm]**。

该字段名称将显示在编辑器中，并且会高亮显示。

![](assets/email_perso_field_3.png)

生成个性化后（例如，预览和准备电子邮件时），此字段将由与目标用户档案对应的值替换。

>[!NOTE]
>
>如果电子邮件是从工作流创建的，则在工作流中计算的附加数据也可在个性化字段中找到。 有关从工作流添加其他数据的更多信息，请参阅[扩充数据](../../automating/using/about-targeting-activities.md#enriching-data)部分。

## 添加内容块 {#adding-a-content-block}

Adobe Campaign提供了一个预配置内容块列表。 这些内容块是动态的、个性化的，并具有特定的呈现方式。 例如，您可以向镜像页面添加问候语或链接。

>[!NOTE]
>
>下图显示如何使用电子邮件的[电子邮件Designer](../../designing/using/designing-content-in-adobe-campaign.md)插入内容块。

要添加内容块，请执行以下操作：

1. 单击文本块内部，单击上下文工具栏中的&#x200B;**[!UICONTROL Personalize]**&#x200B;图标并选择&#x200B;**[!UICONTROL Insert content block]**。 有关电子邮件Designer界面的详细信息，请参阅[此部分](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface)。

   ![](assets/email_content_block_1.png)

1. 选择要插入的内容块。 可用的块因上下文（电子邮件或登陆页面）而异。

   ![](assets/email_content_block_2.png)

1. 单击 **[!UICONTROL Save]**。

内容块的名称将显示在编辑器中，并以黄色突出显示。 它将在生成个性化时自动适应用户档案。

![](assets/email_content_block_3.png)

现成的内容块包括：

* **[!UICONTROL Database URL in emails (EmailUrlBase)]**：此内容块只能在&#x200B;**投放**&#x200B;中使用。
* **[!UICONTROL Mirror page URL (MirrorPageUrl)]**：此内容块只能在&#x200B;**投放**&#x200B;中使用。
* **[!UICONTROL Link to mirror page (MirrorPage)]**：此内容块只能在&#x200B;**投放**&#x200B;中使用。
* **[!UICONTROL Greetings (Greetings)]**
* **[!UICONTROL Unsubscription link (UnsubscriptionLink)]**：此内容块只能在&#x200B;**投放**&#x200B;中使用。
* **[!UICONTROL Social network sharing links (LandingPageViralLinks)]**：此内容块只能在&#x200B;**登陆页面**&#x200B;中使用。
* **[!UICONTROL Default sender name (DefaultSenderName)]**：此内容块只能在&#x200B;**投放**&#x200B;中使用。
* **[!UICONTROL Name of default reply-to email address (DefaultReplyName)]**：此内容块只能在&#x200B;**投放**&#x200B;中使用。
* **[!UICONTROL Email address of default sender (DefaultSenderAddress)]**：此内容块只能在&#x200B;**投放**&#x200B;中使用。
* **[!UICONTROL Default error email address (DefaultErrorAddress)]**：此内容块只能在&#x200B;**投放**&#x200B;中使用。
* **[!UICONTROL Default reply-to email address (DefaultReplyAddress)]**：此内容块只能在&#x200B;**投放**&#x200B;中使用。
* **[!UICONTROL Brand name (BrandingUsualName)]**
* **[!UICONTROL Link to the brand website (BrandingWebSiteLink)]**
* **[!UICONTROL Brand logo (BrandingLogo)]**
* **[!UICONTROL Notification style (notificationStyle)]**

### 创建自定义内容块 {#creating-custom-content-blocks}

您可以定义将插入到消息或登陆页面中的新内容块。

要创建内容块，请执行以下步骤：

1. 从高级菜单中单击&#x200B;**[!UICONTROL Resources > Content blocks]**&#x200B;以访问内容块列表。
1. 单击&#x200B;**[!UICONTROL Create]**&#x200B;按钮或复制预先存在的内容块。

   ![](assets/content_bloc_01.png)

1. 输入标签。
1. 选择块的&#x200B;**[!UICONTROL Content type]**。 提供了三个选项：

   * **[!UICONTROL Shared]**：内容块可用于投放或登陆页面。
   * **[!UICONTROL Delivery]**：内容块只能在投放中使用。
   * **[!UICONTROL Landing page]**：内容块只能在登陆页面中使用。

   ![](assets/content_bloc_02.png)

1. 您可以选择&#x200B;**[!UICONTROL Targeting dimension]**。 有关此内容的详细信息，请参阅[关于定向维度](#about-targeting-dimension)。

   ![](assets/content_bloc_04.png)

1. 您可以选择&#x200B;**[!UICONTROL Depends on format]**&#x200B;选项来定义两个不同的块：一个用于HTML电子邮件，另一个用于文本格式的电子邮件。 然后，编辑器中将显示两个选项卡(HTML和文本)以定义相应的内容。

   ![](assets/content_bloc_03.png)

1. 输入内容块的内容，然后单击&#x200B;**[!UICONTROL Create]**&#x200B;按钮。

现在，您可以在消息或登陆页面的内容编辑器中使用内容块。

>[!CAUTION]
>
>编辑块的内容时，请确保&#x200B;*if*&#x200B;语句的开头和结尾之间没有额外的空格。 在HTML中，屏幕上会显示空格，因此它们将会影响您的内容布局。

### 关于定位维度 {#about-targeting-dimension}

利用定向维度，可定义可在其中使用内容块的消息类型。 这是为了防止在消息中使用不当的块，因为此类块可能会导致错误。

事实上，在编辑消息时，您只能选择具有与该消息的定向维度兼容的定向维度的内容块。

例如，**[!UICONTROL Unsubscription link]**&#x200B;块的目标维度是&#x200B;**[!UICONTROL Profiles]**，因为它包含特定于&#x200B;**[!UICONTROL Profiles]**&#x200B;资源的个性化字段。 因此，无法在[事件事务型消息](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types)中使用&#x200B;**[!UICONTROL Unsubscription link]**&#x200B;块，因为该类型消息的定向维度是&#x200B;**[!UICONTROL Real-time events]**。 但是，您可以在[用户档案事务型消息](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types)中使用&#x200B;**退订链接**&#x200B;块，因为该类型消息的定向维度是&#x200B;**用户档案**。 最后，**[!UICONTROL Link to mirror page]**&#x200B;块没有定向维度，因此您可以在任何消息中使用它。

如果将此字段留空，则无论定向维度是什么，内容块都将与所有消息兼容。 如果设置定向维度，则该块将仅与具有相同定向维度的消息兼容。

有关更多信息，请参阅[定向维度和资源](../../automating/using/query.md#targeting-dimensions-and-resources)。

**相关主题：**

* [插入个性化字段](#inserting-a-personalization-field)
* [添加内容块](#adding-a-content-block)
* [定义电子邮件中的动态内容](#defining-dynamic-content-in-an-email)

## 个性化图像源{#personalizing-an-image-source}

Adobe Campaign允许您根据特定标准或使用跟踪将消息中的一个或多个图像个性化。 通过将个性化字段、内容块或动态内容插入图像源来实现这一点。 操作步骤：

1. 将图像插入消息的内容，或选择已存在的图像。
1. 在图像属性调色板中，选中&#x200B;**[!UICONTROL Enable personalization]**&#x200B;选项。

   ![](assets/des_personalize_images_1.png)

   在编辑器中显示&#x200B;**[!UICONTROL Source]**&#x200B;字段，所选图像显示为&#x200B;**个性化**。

1. 单击&#x200B;**[!UICONTROL Source]**&#x200B;字段按钮旁边的铅笔可访问个性化选项。
1. 添加图像源后，添加您喜欢的个性化字段、内容块和动态内容。

   ![](assets/des_personalize_images_2.png)

   >[!NOTE]
   >
   >域名(http://mydomain.com)无法个性化，必须手动输入。 URL的其余部分可以进行个性化。 例如： http://mydomain.com/ `[Gender]` .jpg

1. 确认更改。

## 条件内容 {#conditional-content}

### 定义可见性条件{#defining-a-visibility-condition}

可以为任何元素指定可见性条件。 仅当满足条件时，它才可见。

要添加可见性条件，请选择块并在其设置的&#x200B;**[!UICONTROL Visibility condition]**&#x200B;字段中输入要遵循的条件。

![](assets/delivery_content_5.png)

此选项仅适用于以下元素：ADDRESS、BLOCKQUOTE、CENTER、DIR、DIV、DL、FIELDSET、FORM、H1、H2、H3、H4、H5、H6、NOSCRIPT、OL、P、PRE、UL、TR、TD。

表达式编辑器出现在[高级表达式编辑](../../automating/using/editing-queries.md#about-query-editor)部分中。

这些条件采用XTK表达式语法(如&#x200B;**context.profile.email！=“**”或&#x200B;**context.profile.status=&#39;0&#39;**)。 默认情况下，所有字段均可见。

>[!NOTE]
>
>无法为已包含具有动态内容的子元素的块或已构成动态内容的块定义条件。 无法编辑不可见的动态块（如下拉列表）。

### 定义电子邮件中的动态内容{#defining-dynamic-content-in-an-email}

>[!CONTEXTUALHELP]
>id="ac_dynamic_content"
>title="定义动态内容"
>abstract="根据您将定义的条件，定义将仅为某些轮廓显示的不同内容。"

在电子邮件中，您可以定义不同的内容，这些内容将根据表达式编辑器定义的条件动态显示给收件人。 例如，从同一封电子邮件，您可以确保每个用户档案都会根据其年龄范围收到不同的消息。

定义动态内容与[定义可见性条件](#defining-a-visibility-condition)不同。

1. 选择片段、组件或元素。 在此示例中，选择一个图像。
1. 单击上下文工具栏中的&#x200B;**[!UICONTROL Dynamic content]**&#x200B;图标。

   ![](assets/dynamic_content_2.png)

   **[!UICONTROL Dynamic content]**&#x200B;部分显示在左侧的面板中。

   ![](assets/dynamic_content_3.png)

   默认情况下，此部分包含两个元素：默认变体和新变体。

   >[!NOTE]
   >
   >内容必须始终具有默认变体。 您无法删除它。

1. 单击&#x200B;**[!UICONTROL Edit]**&#x200B;按钮定义第一个替代变体的显示条件。

   ![](assets/dynamic_content_4.png)

1. 指定标签并选择要设置为条件的字段。 例如，从&#x200B;**[!UICONTROL General]**&#x200B;节点中选择&#x200B;**[!UICONTROL Age]**&#x200B;字段

   ![](assets/dynamic_content_5.png)

1. 设置筛选条件。 例如，您希望向18至25岁的人显示不同的内容。

   ![](assets/dynamic_content_6.png)

1. 设置所有条件后，定义应用条件的优先级顺序并保存更改。

   ![](assets/dynamic_content_7.png)

   内容将以优先级从上到下的顺序显示在面板中。 有关优先级的详细信息，请参阅[此部分](#defining-dynamic-content-in-an-email)。

1. 为刚刚定义的变体上传新图像。

   ![](assets/dynamic_content_8.png)

   年龄在18到25岁之间的收件人将看到新图像。

   ![](assets/dynamic_content_10.png)

1. 单击&#x200B;**[!UICONTROL Add a condition]**&#x200B;以添加新内容及其链接规则。

   ![](assets/dynamic_content_9.png)

   例如，您可以添加不同的图像以向26到35岁之间的人显示。

1. 对于要动态显示的电子邮件中的任何其他元素，执行相同操作。 它可以是文本、按钮、片段等。 保存您的更改。

>[!CAUTION]
>
>准备好消息后，在发送消息之前，请使用校样进行测试。 如果不这样做，则可能无法检测到某些错误，并且可能无法发送电子邮件。

**相关主题：**

* [发送校样](../../sending/using/sending-proofs.md)
* [高级表达式编辑](../../automating/using/editing-queries.md#about-query-editor)

### 优先级顺序 {#order-of-priority}

在表达式编辑器中，当您定义动态内容时，优先级顺序如下所示。

1. 您使用&#x200B;**两个不同的条件**&#x200B;定义两个不同的动态内容，例如：

   **条件1：**&#x200B;个人资料的性别是男性的，

   **条件2：**&#x200B;配置文件的年龄介于20至30岁之间。

   ![](assets/delivery_content_61.png)

   数据库中的某些用户档案对应于这两个条件，但只能发送一封包含一个动态内容的电子邮件。

1. 因此，您必须定义动态内容的优先级。 优先级顺序为&#x200B;**1**&#x200B;的条件（以及相应的动态内容）将发送到配置文件，即使此配置文件也满足优先级顺序为&#x200B;**2**&#x200B;或&#x200B;**3**&#x200B;的另一个条件。

   ![](assets/delivery_content_62.png)

您只能为每个动态内容定义一个优先级顺序。

## 示例：电子邮件个性化{#example-email-personalization}

在此示例中，营销服务团队的一名成员创建了一封电子邮件，用于通知某些客户，存在专门为其提供的特别优惠。 团队成员决定根据客户各自的年龄对电子邮件进行个性化设置。 18至27岁的客户将收到一封电子邮件，其中包含27岁以上的客户将收到的其他图片和标语。

电子邮件的创建方式如下：

* 动态内容将应用于图像，并根据年龄范围配置这些动态内容。

  ![](assets/delivery_content_43.png)

  有关添加和配置动态内容的详细信息，请参阅[在电子邮件](#defining-dynamic-content-in-an-email)中定义动态内容。

* 个性化字段和动态内容将应用于文本。 根据用户档案的年龄范围，电子邮件会以用户档案的名字开头，或者以用户档案的标题和姓氏开头。

  ![](assets/delivery_content_44.png)

  有关添加和配置个性化字段的详情，请参见[插入个性化字段](#inserting-a-personalization-field)一节。

### 配置图像 {#configuring-images}

>[!CONTEXTUALHELP]
>id="ac_dynamic_image"
>title="管理动态图像"
>abstract="根据您将定义的条件，使用动态图像个性化设置电子邮件。"

在此示例中，应用于图像的动态内容配置如下：

**目标18-27岁：**

1. 在&#x200B;**[!UICONTROL Properties]**&#x200B;调色板中选择动态内容，然后单击&#x200B;**[!UICONTROL Edit]**&#x200B;按钮。

   ![](assets/delivery_content_48.png)

1. 编辑标签，然后从&#x200B;**[!UICONTROL Profile]**&#x200B;节点中选择&#x200B;**[!UICONTROL Age]**&#x200B;字段。

   ![](assets/delivery_content_49.png)

1. 选择&#x200B;**大于或等于**&#x200B;运算符，然后输入&#x200B;**18**&#x200B;以创建早于18 **表达式的**。

   ![](assets/delivery_content_50.png)

1. 添加新的&#x200B;**[!UICONTROL Age]**&#x200B;条件。

   选择值字段中的&#x200B;**小于或等于**&#x200B;运算符后跟27以创建小于27 **的**&#x200B;表达式。

   ![](assets/delivery_content_51.png)

1. 确认更改。

**要定位年龄在27岁及以上的用户档案：**

1. 从面板中选择并编辑动态内容。
1. 编辑标签，然后从&#x200B;**[!UICONTROL Profile]**&#x200B;节点中选择&#x200B;**[!UICONTROL Age]**&#x200B;字段。
1. 在值字段中添加&#x200B;**Greater than**&#x200B;运算符后跟27，以创建早于27 **表达式的**。

   ![](assets/delivery_content_52.png)

1. 确认更改。

您的动态内容已正确配置。

### 配置文本 {#configuring-text}

在此示例中，应用于文本的动态内容配置如下：

**要定位年龄在18-27岁之间的用户档案：**

1. 选择所需的结构组件并添加动态内容。
1. 编辑动态内容并配置定位表达式。 请参阅[配置图像](#configuring-images)。
1. 在结构组件的所需位置，单击上下文工具栏中的&#x200B;**[!UICONTROL Personalize]**&#x200B;图标并选择&#x200B;**[!UICONTROL Insert personalization field]**。

   ![](assets/delivery_content_53.png)

1. 在显示的列表中，选择&#x200B;**[!UICONTROL First name]**&#x200B;字段并确认。

   ![](assets/delivery_content_54.png)

1. 随后，您的个性化字段将完美插入到所选的动态内容中。

**要定位年龄在27岁及以上的用户档案：**

1. 选择所需的结构组件并添加动态内容。
1. 编辑动态内容并配置定位表达式。 请参阅[配置图像](#configuring-images)。
1. 在结构组件的所需位置，单击上下文工具栏中的&#x200B;**[!UICONTROL Personalize]**&#x200B;图标并选择&#x200B;**[!UICONTROL Insert personalization field]**。
1. 从下拉列表中选择&#x200B;**[!UICONTROL Title]**。
1. 以类似方式继续添加&#x200B;**[!UICONTROL Last name]**&#x200B;字段。

   ![](assets/delivery_content_56.png)

现在，应将您的个性化字段完美插入所选的动态内容中。

### 预览电子邮件 {#previewing-emails}

预览允许您在发送&#x200B;**[!UICONTROL Proofs]**&#x200B;之前检查个性化字段和动态内容是否配置正确。 在预览过程中，您可以选择与电子邮件目标对应的不同测试用户档案。

如果没有测试用户档案，则默认显示的电子邮件为：

![](assets/delivery_content_45.png)

电子邮件中的标语没有个性化字段，而是使用默认图像。

第一个测试配置文件对应于年龄在18到27岁之间的客户端。 选择此配置文件后，将显示以下电子邮件：

![](assets/delivery_content_46.png)

正确配置了与18-27年前的表达式（特别是用户档案的名字）对应的个性化字段，并且图像也已根据用户档案发生更改。

第二个用户档案对应于27岁以上的客户，并生成以下电子邮件：

![](assets/delivery_content_47.png)

由于动态内容，图像已发生更改，显示的口号是为此目标公众定义的更正式的口号。

**相关主题：**

* [创建受众](../../audiences/using/creating-audiences.md)
* [准备发送](../../sending/using/preparing-the-send.md)
