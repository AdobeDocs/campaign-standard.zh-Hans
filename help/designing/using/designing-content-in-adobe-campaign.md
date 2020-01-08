---
title: 在Adobe Campaign中设计内容
description: 了解可通过Adobe Campaign在内容中定义的所有元素。
page-status-flag: never-activated
uuid: 8f73407f-ab90-46bc-aeb6-bd87fcb0404c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: about-content-design
discoiquuid: 20800cde-50ad-4d2b-a2f9-812258bec665
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fbfc6cb0c17193abdf2faaf1b949ae88fed48be5

---


# Campaign 电子邮件设计工具{#designing-content-in-adobe-campaign}

在Adobe Campaign中创建电子邮件后，您需要定义其内容。

电子邮件设计器使您能够通过由本机Creative Cloud集成增强的拖放界面创建引人注目的、单独定制的电子邮件。 无论您是从空白的白板开始，还是利用现有内容片段或模板，设计并优化每封电子邮件的所有内容，无论是促销还是交易。

电子邮件设计器旨在提供针对响应式设计而优化的HTML，它允许您通过用户界面轻松定义可视性条件和动态内容并直接将其应用到电子邮件、模板或片段。 只需单击按钮，即可在拖放界面和HTML代码之间无缝切换。

电子邮件设计器允许您创建电子邮件内容和电子邮件内容模板。 它兼容简单的电子邮件、交易电子邮件、A/B测试电子邮件、多语言电子邮件和重复电子邮件。

要开始使用电子邮件设计器，请观看 [这组视频](https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html#GettingStarted) ，其中解释了电子邮件设计器的一般功能以及如何从头开始或使用模板设计电子邮件。

<!--The Email Designer has more features than the Legacy Editor and is backward compatible.-->

* 要了解如何创建电子邮件内容，请参 [阅电子邮件设计人员入门](../../designing/using/quick-start.md)。
* 有关电子邮件设计器的概述，请参阅 [使用电子邮件设计器](../../designing/using/designing-content-in-adobe-campaign.md)。
* 有关构建内容的更多信息：
   * 从头开始，请参阅 [从头开始设计电子邮件](../../designing/using/designing-from-scratch.md)。
   * 使用现有内容，请参阅 [使用现有内容进行设计](../../designing/using/using-existing-content.md)。
   * 使用Creative cloud集成，请参阅多 [解决方案电子邮件设计](../../designing/using/using-integrations.md)。
* 有关个性化的更多信息，请参 [阅个性化](../../designing/using/personalization.md)。

创建电子邮件时，您可以选择使用预定义的模板或从其他源加载现有内容。 请参 [阅选择现有内容](../../designing/using/using-existing-content.md#selecting-an-existing-content)。

要提高营销活动的效率，请个性化您的内容。 请参 [阅插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)[和添加内容块](../../designing/using/personalization.md#adding-a-content-block)。

您还可以定义因每个配置文件而异的动态内容。 请参 [阅在电子邮件中定义动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) , [在登陆页面中定义动态内容](../../channels/using/designing-a-landing-page.md#defining-dynamic-content-in-a-landing-page)。

使用链接和图像增强您的消息和登录页面。 请参 [阅插入链接](../../designing/using/links.md#inserting-a-link)[和插入图像](../../designing/using/images.md#inserting-images)。

## 电子邮件设计器界面 {#email-designer-interface}

电子邮件设计器提供了许多选项，允许您创建、编辑和自定义内容的各个方面。

该界面由提供不同功能的几个区域组成：

![](assets/email_designer_overview.png)

从调色板 **(1)中可用的元素，将结构组件和内容片段拖放到主** Workspace **** (2)中。 在 **Workspace** (2)中选择一个组件或元素，并从“设置”窗格(3)中自定义其主要样式 **和显示特征** 。

从主工具栏(4)访问更多常规 **选项** 和设置。

>[!NOTE]
>
>“设 **置** ”窗格可以根据屏幕分辨率和显示屏向左移动。

![](assets/email_designer_toolbar.png)

编辑 **器界面的** “上下文”工具栏根据所选区域提供各种功能。 它包含允许您更改文本样式的操作按钮和按钮。 执行的修改始终适用于所选区域。

### Email Designer主页 {#email-designer-home-page}

创 [建电子邮件时](../../channels/using/creating-an-email.md)，主页 **[!UICONTROL Email Designer]**会在选择电子邮件内容时自动显示。

![](assets/email_designer_home_page.png)

该选 **[!UICONTROL Properties]**项卡允许您编辑电子邮件详细信息，如标签、发件人地址和姓名或电子邮件主题。 您还可以通过单击屏幕顶部的电子邮件标签来访问此选项卡。

![](assets/email_designer_home_properties.png)

该选 **[!UICONTROL Templates]**项卡允许您从现成的HTML内容或您已创建的模板中进行选择，以快速开始设计电子邮件。 请参阅[内容模板](../../designing/using/using-reusable-content.md#content-templates)。

![](assets/email_designer_home_templates.png)

通过 **[!UICONTROL Learn & support]**该选项卡，您可以轻松访问相关文档和教程。

![](assets/email_designer_home_support.png)

如果不选择模板，“电子邮件设计器”主页还允许您选择开始设计内容的方式：

* 单击该 **[!UICONTROL Create]**按钮可从头开始创建新内容。 请参[阅从头开始设计电子邮件内容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
* 单击该 **[!UICONTROL Upload]**按钮可从您的计算机上传文件。 请参[阅从文件导入内容](../../designing/using/using-existing-content.md#importing-content-from-a-file)。
* 单击该 **[!UICONTROL Import from URL]**按钮可从URL检索现有内容。 请参[阅从URL导入内容](../../designing/using/using-existing-content.md#importing-content-from-a-url)。

## 术语 {#terminology}

**模板**:模板是电子邮件的结构，您可以为多个分发构建和重复使用。

**片段**:片段是可重用的组件，可在一个或多个电子邮件中引用。

**结构组件**:定义电子邮件布局的结构元素。

**内容组件**:内容组件是原始的空组件，放置到电子邮件中后，您可以编辑这些组件。

## 内容设计最佳实践 {#content-design-best-practices}

为了合理使用电子邮件设计器并尽可能简单地创建最佳电子邮件，我们建议应用以下原则：

* 在HTML的&lt;head>部分中，使用内联样式，而不是单独的CSS和CSS。 通过使用内联样式，您可以优化内容片段的保存和重用。

   请参阅 [添加内联样式属性](../../designing/using/styles.md#adding-inline-styling-attributes)。

* 如果导入包含HTML内容的ZIP文件，请使用常规CSS。 不支持SCSS样式表。

* 通过创建和重用内容片段来保持营销活动的一致性，轻松解决您的品牌问题。

   请参 [阅创建内容片段](../../designing/using/using-reusable-content.md#creating-a-content-fragment)。

* 编辑电子邮件 **内容时**:

   在发送邮件之前先预览邮件。 Adobe Campaign提供了一种使用Litmus测试电子邮件呈现的方法。 有关此内容的详细信息，请参阅电 [子邮件渲染](../../sending/using/email-rendering.md)。

有关消息的更多设计和一般最佳实践，请参阅以下Adobe Campaign分步指南：使 [用Adobe Campaign交付最佳实践](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html)。

### 更新片段 {#email-designer-updates}

电子邮件设计人员正在不断改进。 如果您从头开始、从现成模板创建电子邮件内容，或者如果您创建了片段，则您下次打开内容时可能会收到以下更新消息：

![](assets/email_designer_fragment_patch_message.png)

Adobe建议将您的内容更新到最新版本，以避免CSS冲突问题等问题。 单击 **[!UICONTROL Update now]**.

如果内容更新期间发生错误，请检查HTML并修复它，然后再次运行此更新。

在涉及片段时，请注意以下事项：

* 如果要向新电子邮件或模板中添加片段，并且如果收到此消息，则需要先更新此片段。

* 如果您有多个片段，则必须更新要在电子邮件内容中使用的每个片段。

* 为避免对当前尚未准备的电子邮件产生影响，您可以选择不更新某些片段。

* 您仍可以发送电子邮件，其中已使用未更新的片段，但该片段不可编辑。

* 更新已准备好的电子邮件中使用的片段对这些电子邮件没有影响。

## 电子邮件设计人员限制 {#email-designer-limitations}

* 不能在片段中使用个性化字段。 有关片段的详细信息，请参 [阅此部分](../../designing/using/using-reusable-content.md#about-fragments)。

<!--* You cannot save directly as a fragment some content of an email that you are editing within the Email Designer. You need to copy-paste the HTML corresponding to that content into a new fragment. For more on this, see [Saving content as a fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).-->

* 编辑样式时，只有大多数电子邮件客户端正式支持的Web字体才可用。
* 样式无法保存为主题以供将来重用。 但是，CSS样式可保存在内容模板或电子邮件中。 有关样式的更多信息，请参 [阅此部分](../../designing/using/styles.md)。

**相关主题**:

* [创建电子邮件](../../channels/using/creating-an-email.md)
* [设计登陆页面](../../channels/using/designing-a-landing-page.md)
* [创建短信消息](../../channels/using/creating-an-sms-message.md)
* [创建和发送推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)
