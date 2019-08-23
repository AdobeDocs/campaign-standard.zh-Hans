---
title: 关于电子邮件内容设计
seo-title: 关于电子邮件内容设计
description: 关于电子邮件内容设计
seo-description: 发现使您能够为电子邮件设计内容的电子邮件设计器。
page-status-flag: 从未激活
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 设计
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536 ab66 b3
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# 关于电子邮件内容设计{#about-email-content-design}

使用电子邮件设计器拖放界面在Adobe Campaign中创建和修改电子邮件内容。

本节介绍电子邮件设计器的具体特性：

* [关于电子邮件设计器](../../designing/using/about-email-content-design.md#about-the-email-designer)
* [定义电子邮件结构](../../designing/using/defining-the-email-structure.md)
* [编辑电子邮件样式](../../designing/using/editing-email-styles.md)

要了解有关一个或多个营销活动通用的操作，请参阅以下部分：

* 有关个性化电子邮件内容的更多信息，请参阅 [插入个性化字段](../../designing/using/inserting-a-personalization-field.md) 和 [添加内容块](../../designing/using/adding-a-content-block.md)。
* 有关导入其他电子邮件内容的详细信息，请参阅 [选择现有内容](../../designing/using/selecting-an-existing-content.md)。
* 有关在电子邮件中定义动态内容的详细信息，请参阅 [在电子邮件中定义动态内容](../../designing/using/defining-dynamic-content-in-an-email.md)。
* 有关在电子邮件中插入链接的详细信息，请参阅 [插入链接](../../designing/using/inserting-a-link.md)。
* 有关在电子邮件中插入图像的详细信息，请参阅 [插入图像](../../designing/using/inserting-images.md)。

同时检查 [内容设计的最佳实践](../../designing/using/content-design-best-practices.md)。

## 关于电子邮件设计器 {#about-the-email-designer}

通过电子邮件设计器，您可以创建电子邮件内容和电子邮件内容模板。它与简单的电子邮件、交易电子邮件、A/B测试电子邮件、多语言电子邮件和重复的电子邮件兼容。

要开始使用电子邮件设计器，请观看这 [套视频](https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html#GettingStarted) ，这些视频解释了电子邮件设计器的一般功能以及如何从头开始或使用模板设计电子邮件。

### 电子邮件设计器主页 {#email-designer-home-page}

[创建电子邮件](../../channels/using/creating-an-email.md)时， **[!UICONTROL Email Designer]** 主页会在选择电子邮件内容时自动显示。

![](assets/email_designer_home_page.png)

**[!UICONTROL Properties]** 选项卡允许您编辑电子邮件详细信息，如标签、发送者的地址和姓名或电子邮件主题。您还可以通过单击屏幕顶部的电子邮件标签来访问此选项卡。

![](assets/email_designer_home_properties.png)

**[!UICONTROL Templates]** 此选项卡允许您从现成的HTML内容中进行选择，或选择您已经创建的模板来快速开始设计电子邮件。请参阅 [内容模板](../../start/using/about-templates.md#content-templates)。

![](assets/email_designer_home_templates.png)

**[!UICONTROL Learn & support]** 使用该选项卡，您可以轻松访问相关文档和教程。

![](assets/email_designer_home_support.png)

如果您不选择模板，则电子邮件设计器主页还允许您选择如何开始设计内容：

* 单击 **[!UICONTROL Create]** 按钮可从头开始创建新内容。请参阅 [从头开始设计电子邮件内容](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)。
* 单击 **[!UICONTROL Upload]** 按钮可从计算机上传文件。请参阅 [从文件导入内容](../../designing/using/importing-content-from-a-file.md)。
* 单击 **[!UICONTROL Import from URL]** 按钮可检索现有内容表单URL。请参阅 [从URL导入内容](../../designing/using/importing-content-from-a-url.md)。

### 电子邮件设计器界面 {#email-designer-interface}

电子邮件设计器提供了许多选项，用于创建、编辑和自定义内容的各个方面。

该界面由几个提供不同功能的区域组成：

![](assets/email_designer_overview.png)

从 **调色板** (1)中可用的元素，将结构组件和内容片段拖放到 **主Workspace** (2)中。在 **Workspace** (2)中选择一个组件或元素，并从 **“设置** ”窗格(3)中自定义其主样式和显示特性。

从主 **工具栏** (4)访问更多一般选项和设置。

>[!NOTE]
>
>**“设置** ”窗格可根据屏幕分辨率和显示情况向左移动。

![](assets/email_designer_toolbar.png)

编辑器界面 **的上下文工具栏** 根据所选区域提供各种功能。它包含允许您更改文本样式的操作按钮和按钮。执行的修改始终适用于所选区域。

### 使用电子邮件设计器的一般建议 {#general-recommendations-for-using-the-email-designer}

为了合理使用电子邮件设计器并尽可能简单地创建最佳电子邮件，我们建议您遵循以下原则：

* 在HTML的&lt; head&gt;部分使用内联样式而不是单独的CSS和CSS。通过使用内嵌样式，您可以优化内容片段保存和重复使用。

   请参阅 [添加内嵌样式属性](../../designing/using/editing-email-styles.md#adding-inline-styling-attributes)。

* 通过创建和重用内容片段来使营销活动保持一致性，从而轻松解决您的品牌。

   请参阅 [创建内容片段](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment)。

同时检查 [内容设计的最佳实践](../../designing/using/content-design-best-practices.md)。

### 电子邮件设计器兼容性模式 {#email-designer-compatibility-mode}

上传内容时，它必须包含特定标记才能完全兼容并可使用电子邮件设计器的WYSIWYG编辑器编辑。

如果所有或部分上传的HTML不符合预期的标记，则内容随后会以“兼容性模式”加载，这会通过UI限制版本可能。

在兼容性模式下加载内容时，您仍然可以通过界面执行以下修改(隐藏不可用的操作)：

* 更改文本或更改图像
* 插入链接和个性化字段
* 在选定的HTML块上编辑一些样式选项
* 定义条件内容

![](assets/email_designer_compatibility.png)

其他修改(如向电子邮件或高级样式添加新章节)必须通过HTML模式直接在电子邮件的源代码中完成。

有关将现有电子邮件转换为电子邮件设计人员兼容电子邮件的更多信息，请参阅 [此部分](../../designing/using/about-email-content-design.md#designing-an-email-using-existing-contents)。

### 电子邮件设计器限制 {#email-designer-limitations}

* 不能在片段中使用个性化字段。有关片段的详细信息，请参阅 [此部分](../../designing/using/defining-the-email-structure.md#about-fragments)。
* 编辑样式时，只有大多数电子邮件客户端正式支持的Web字体才可用。
* 样式无法保存为主题，供以后重复使用。但是，CSS样式可以保存在内容模板或电子邮件中。有关样式的更多信息，请参阅 [此部分](../../designing/using/editing-email-styles.md)。

### 电子邮件设计器更新 {#email-designer-updates}

电子邮件设计器不断改进。如果您从现成的模板中创建了电子邮件内容，或者如果您创建了片段，则在下次打开内容时，您可能会收到以下更新消息：

![](assets/email_designer_fragment_patch_message.png)

Adobe建议将您的内容更新到最新版本，以避免出现CSS冲突问题等问题。Click **[!UICONTROL Update now]**.

如果在内容更新过程中出错，请检查HTML并在再次运行此更新之前修复它。

谈到片段，请注意以下事项：

* 如果要向新的电子邮件或模板添加片段，如果收到此消息，则需要先更新此片段。

* 如果有多个片段，则必须更新要在电子邮件内容中使用的每个片段。

* 为避免影响当前尚未准备好的电子邮件，您可以选择不更新某些片段。

* 您仍可以发送未更新片段的电子邮件，但该片段不可编辑。

* 更新已准备就绪的电子邮件中使用的片段不会影响这些电子邮件。

## 从头开始设计电子邮件内容 {#designing-an-email-content-from-scratch}

以下是使用电子邮件设计器从头开始创建和设计电子邮件内容的主要步骤：

1. 创建电子邮件并打开其内容。
1. 添加结构组件以使电子邮件成为形状。请参阅 [编辑电子邮件结构](../../designing/using/defining-the-email-structure.md#editing-the-email-structure)。
1. 在结构组件中插入内容组件和片段。请参阅 [添加片段和内容组件](../../designing/using/defining-the-email-structure.md#adding-fragments-and-content-components)。
1. 添加图像并编辑电子邮件的文本。请参阅 [插入图像](../../designing/using/inserting-images.md)。
1. 通过添加个性化字段、链接等，个性化您的电子邮件。请参阅 [插入个性化字段](../../designing/using/inserting-a-personalization-field.md)、 [插入链接](../../designing/using/inserting-a-link.md) 和 [在电子邮件中定义动态内容](../../designing/using/defining-dynamic-content-in-an-email.md)。
1. 定义电子邮件的主题行。请参阅 [个性化电子邮件主题行](../../designing/using/personalizing-the-subject-line-of-an-email.md)。
1. 预览您的电子邮件。
1. 保存您的内容，并在确保您已定义受众并正确安排发送后继续处理您的消息。

您还可以查看此 [介绍视频](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=chi_hans)。

>[!NOTE]
>
>为避免从头开始设计电子邮件内容，您可以使用现成的内容模板。有关此操作的详细信息，请参阅 [内容模板](../../start/using/about-templates.md#content-templates)。

**相关主题**：

* [创建电子邮件](../../channels/using/creating-an-email.md)
* [选择现有内容](../../designing/using/selecting-an-existing-content.md)
* [在信息中选择受众](../../audiences/using/selecting-an-audience-in-a-message.md)
* [安排消息](../../sending/using/about-scheduling-messages.md)
* [预览消息](../../sending/using/previewing-messages.md)
* [电子邮件渲染](../../sending/using/email-rendering.md)
* [无需HTML即可构建个性化电子邮件](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Createcompellingcontenttailoredtoeveryindividual)

## 使用现有内容设计电子邮件 {#designing-an-email-using-existing-contents}

本节介绍如何将现有电子邮件转换为电子邮件设计人员兼容电子邮件。

默认情况下，如果只上传任何HTML(请参阅 [从某个文件](../../designing/using/importing-content-from-a-file.md)导入内容)，则会在“[兼容性模式](../../designing/using/about-email-content-design.md#email-designer-compatibility-mode)”中加载该内容，这会通过UI限制版本可能(只有就地版本，无需拖放)。

但是，如果您要构建可组合到多个电子邮件中的模块化模板和片段框架，应考虑将电子邮件HTML转换为电子邮件设计器模板。

使用电子邮件设计器设计内容时，您有三个选项：

* [通过现成的模板构建内容](../../designing/using/about-email-content-design.md#building-content-from-an-out-of-the-box-template)
* [使用片段和组件](../../designing/using/about-email-content-design.md#using-fragments-and-components)从头开始创建HTML设计
* [将HTML内容](../../designing/using/about-email-content-design.md#converting-an-html-content) 电子邮件转换为模块化电子邮件设计器内容

### 通过现成的模板构建内容 {#building-content-from-an-out-of-the-box-template}

1. 创建电子邮件并打开其内容。有关此操作的详细信息，请参阅 [创建电子邮件](../../channels/using/creating-an-email.md)。
1. 单击主页图标可访问 **[!UICONTROL Email Designer]** 主页。
1. 单击 **[!UICONTROL Templates]** 选项卡。
1. 选择现成的HTML模板。

   不同的模板提供多种类型元素的各种组合。例如，“羽化”模板具有边距，而“Astro”模板没有边距。有关此操作的详细信息，请参阅 [内容模板](../../start/using/about-templates.md#content-templates)。

1. 您可以组合这些元素以构建许多电子邮件变体。例如，您可以通过选择结构组件并从上下文工具栏单击来 **[!UICONTROL Duplicate]** 复制电子邮件部分。
1. 您可以使用左侧的蓝色箭头来回拖动结构组件，从而移动元素。有关此操作的详细信息，请参阅 [编辑电子邮件结构](../../designing/using/defining-the-email-structure.md#editing-the-email-structure)。
1. 您还可以移动组件以更改每个结构元素的组织。有关此操作的详细信息，请参阅 [添加片段和组件](../../designing/using/defining-the-email-structure.md#adding-fragments-and-content-components)。
1. 根据需要修改每个元素的内容：图像、文本、链接。
1. 根据需要调整样式选项到内容。有关此操作的详细信息，请参阅 [编辑电子邮件样式](../../designing/using/editing-email-styles.md)。

### 使用片段和组件 {#using-fragments-and-components}

为了简单地使外部内容符合电子邮件设计器的要求，Adobe建议从头开始创建一条消息，并将现有电子邮件中的内容复制到片段和组件中。

当您有无法重新创建的内容时，可以使用 **[!UICONTROL Html]** 内容组件复制原始电子邮件中的HTML代码。请确保在继续操作之前熟悉HTML。

下面介绍了一个完整的示例。

>[!NOTE]
>
>新内容不会是原始电子邮件的精确副本，但下面的步骤将指导您创建尽可能关闭的消息。

假设您要使用在Adobe Campaign之外创建的现有新闻稿。

您希望在将随Adobe Campaign发送的所有电子邮件中具有相同的页眉和页脚。电子邮件正文将根据您希望在每个新闻稿中显示的内容进行更改。

**先决条件**

1. 在您的原始电子邮件中，识别您将发送的每封电子邮件特有的部分中可重复使用的部分。
1. 保存所有要使用的图像和资产。
1. 如果您熟悉HTML，请将原始HTML内容拆分为不同部分。

**为可重用内容创建片段**

使用电子邮件设计器为每个可重用部分创建一个片段。在此示例中，您将创建两个片段：一个用于标题，另一个用于页脚。然后，您可以将现有内容中的相关部分复制到这些片段中。

要执行此操作，请执行以下步骤：

1. 在Adobe Campaign中，转至 **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** 并为标题创建一个片段。有关此操作的详细信息，请参阅 [创建内容片段](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment)。
1. 为片段添加任意所需的结构组件。

   ![](assets/des_loading_compatible_fragment_1.png)

1. 在结构中插入图像和文本组件。

   ![](assets/des_loading_compatible_fragment_2.png)

1. 上传相应的图像，输入文本并调整设置。

   有关管理样式设置和内嵌属性的更多信息，请参阅 [编辑电子邮件样式](../../designing/using/editing-email-styles.md)。

   ![](assets/des_loading_compatible_fragment_3.png)

1. 保存片段。
1. 以同样的方式继续创建页脚并保存。

   ![](assets/des_loading_compatible_fragment_4.png)

   如果您熟悉HTML，可以使用 **[!UICONTROL Html]** 内容组件从原始页脚复制HTML代码。有关此操作的详细信息，请参阅 [关于内容组件](../../designing/using/defining-the-email-structure.md#about-content-components)。

   ![](assets/des_loading_compatible_fragment_9.png)

您的片段现在可用于模板中。

**将片段和组件插入模板**

您现在可以使用电子邮件设计器创建电子邮件模板。使用内容组件反映电子邮件的不同部分，并调整设置，使其尽可能接近原始Newsletter。最后，插入刚刚创建的片段。

1. 使用电子邮件设计器创建模板。有关此操作的详细信息，请参阅 [内容模板](../../start/using/about-templates.md#content-templates)。
1. 将多个结构组件插入模板-对应于电子邮件的标题、页脚和正文。有关添加结构组件的详细信息，请参阅 [使用电子邮件设计器编辑电子邮件结构](../../designing/using/defining-the-email-structure.md#editing-the-email-structure)。
1. 根据需要插入任意数量的内容组件以创建Newsletter正文。这将是您每月更新的电子邮件的可编辑内容。

   ![](assets/des_loading_compatible_fragment_5.png)

   如果您熟悉HTML代码，Adobe建议利用 **[!UICONTROL Html]** 组件，您可以在其中复制粘贴原始电子邮件中更复杂的元素。使用其他组件，如 **[!UICONTROL Button]**&#x200B;或 **[!UICONTROL Image]****[!UICONTROL Text]** 其他内容。有关此操作的详细信息，请参阅 [关于内容组件](../../designing/using/defining-the-email-structure.md#about-content-components)。

   >[!NOTE]
   >
   >使用 **[!UICONTROL Html]** 组件创建可编辑的组件，但选项有限。在选择此组件之前，请确保您知道如何处理HTML代码。

1. 调整内容组件，以尽可能多地匹配原始电子邮件。

   ![](assets/des_loading_compatible_fragment_6.png)

   有关管理样式设置和内嵌属性的更多信息，请参阅 [编辑电子邮件样式](../../designing/using/editing-email-styles.md)。

1. 将之前创建的两个片段(页眉和页脚)插入到所需结构组件中。

   ![](assets/des_loading_compatible_fragment_10.png)

1. 保存模板。

您现在可以在电子邮件设计器中完全管理此模板，以创建和更新每月发送给收件人的Newsletter。

要使用该电子邮件，请创建电子邮件并选择刚刚创建的内容模板。

**相关主题**：

* [创建电子邮件](../../channels/using/creating-an-email.md)
* [电子邮件设计器的简介视频](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=chi_hans)
* [从头开始设计电子邮件内容](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)

### 转换HTML内容 {#converting-an-html-content}

此用例提供了将HTML电子邮件转换为电子邮件设计器组件的快速方法。

>[!CAUTION]
>
>本节面向熟悉HTML代码的高级用户。

>[!NOTE]
>
>与兼容性模式一样，HTML组件可编辑，但选项有限：您只能执行就地版本。

在电子邮件设计器之外，确保原始HTML分为可重用部分。

如果不是这样，请从HTML剪切不同的块。例如：

```
<!-- 3 COLUMN w/CTA (SCALED) -->
<table width="100%" align="center" cellspacing="0" cellpadding="0" border="0" role="presentation" style="max-width:680px;">
<tbody>
<tr>
<td class="padh10" align="center" valign="top" style="padding:0 5px 20px 5px;">
<table width="100%" cellspacing="0" cellpadding="0" border="0" role="presentation">
<tbody>
<tr>
...
</tr>
</tbody>
</table>
</td>
</tr>
</tbody>
</table>
<!-- //3 COLUMN w/CTA (SCALED) -->
```

识别完所有块后，在电子邮件设计器中，对现有电子邮件的每个部分重复以下步骤：

1. 打开电子邮件设计器以创建空电子邮件内容。
1. 设置正文属性：背景颜色、宽度等。有关此操作的详细信息，请参阅 [编辑电子邮件样式](../../designing/using/editing-email-styles.md)。
1. 添加结构组件。有关此操作的详细信息，请参阅 [编辑电子邮件结构](../../designing/using/defining-the-email-structure.md#editing-the-email-structure)。
1. 添加HTML组件。有关此操作的详细信息，请参阅 [添加片段和组件](../../designing/using/defining-the-email-structure.md#adding-fragments-and-content-components)。
1. 将HTML复制粘贴到该组件中。
1. 切换到移动视图。有关此操作的详细信息，请参阅 [此部分](../../designing/using/about-email-content-design.md#switching-to-mobile-view)。

   响应式视图已断开，因为您的CSS丢失。

1. 要修复此问题，请切换到源代码模式并将样式部分复制粘贴到新样式部分。例如：

   ```
   <style type="text/css">
   a {text-decoration:none;}
   body {min-width:100% !important; margin:0 auto !important; padding:0 !important;}
   img {line-height:100%; text-decoration:none; -ms-interpolation-mode:bicubic;}
   ...
   </style>
   ```

   >[!NOTE]
   >
   >请勿修改电子邮件设计器生成的CSS： `<style acrite-template-css="true">``<style acrite-custom-styles="" type="text/css">`和.请确保在此之后添加样式。

1. 返回移动视图以检查内容是否正确显示并保存更改。

## 切换到移动视图 {#switching-to-mobile-view}

您可以通过单独编辑移动显示屏的所有样式选项，微调电子邮件的响应式设计。例如，您可以调整边距和填充，使用较小或更大的字体大小、更改按钮或应用电子邮件的移动版本特有的不同背景颜色。

移动视图中提供所有样式选项。“电子邮件设计器”样式设置显示在 [“编辑电子邮件样式](../../designing/using/editing-email-styles.md) ”部分中。

1. 创建电子邮件并开始编辑内容。有关此操作的详细信息，请参阅 [从头开始设计电子邮件内容](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)。
1. 要访问专用的移动视图，请选择 **[!UICONTROL Switch to mobile view]** 按钮。

   ![](assets/email_designer_mobile_view_switch.png)

   将显示电子邮件的移动版本。它包含在桌面视图中定义的所有组件和样式。

1. 单独编辑所有样式设置，如背景颜色、对齐方式、填充、边距、字体系列、文本颜色等。

   ![](assets/email_designer_mobile_view.png)

1. 在移动视图中编辑任何样式设置时，修改只会应用于移动显示。

   例如，减少图像的大小，添加绿色背景并在移动视图中更改填充。

   ![](assets/email_designer_mobile_view_change.png)

1. 在移动设备上显示时，您可以隐藏组件。为此，请从中选择 **[!UICONTROL Show only on desktop devices]****[!UICONTROL Display options]**。
您还可以选择在桌面设备上隐藏此组件，这意味着它将仅在移动设备上显示。**[!UICONTROL Show only on mobile devices]**为此，请选择。
例如，此选项允许您在移动设备上显示特定图像，在桌面设备上显示另一幅图像。
您可以从移动视图或桌面视图中设置此选项。

   ![](assets/email_designer_mobile_hide.png)

1. 再次单击 **[!UICONTROL Switch to mobile view]** 按钮可返回标准桌面视图。您刚刚制作的样式更改不会反映出来。

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >唯一的例外是 **[!UICONTROL Style inline]** 设置。任何样式内嵌设置更改也将应用于标准桌面视图。

1. 对电子邮件结构或内容的任何其他更改，如文本编辑、上传新图像、添加新组件等。也会应用于标准视图。

   例如，切换回移动视图，编辑某些文本并替换图像。

   ![](assets/email_designer_mobile_view_change_content.png)

   再次单击 **[!UICONTROL Switch to mobile view]** 按钮可返回标准桌面视图。更改会反映出来。

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. 在移动视图中删除样式可返回到桌面模式下应用的样式。

   例如，在移动视图中，将绿色背景颜色应用到按钮。

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. 切换到桌面视图，并将灰色背景应用到同一按钮。

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. 再次切换到移动视图，现在禁用 **[!UICONTROL Background color]** 设置。

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   现在应用桌面视图中定义的背景颜色：它变灰(而非空白)。

   唯一的例外是 **[!UICONTROL Border color]** 设置。在移动视图中禁用时，即使在桌面视图中定义了边框颜色，也不再应用边框。

## 纯文本和HTML模式 {#plain-text-and-html-modes}

### 生成电子邮件的文本版本 {#generating-a-text-version-of-the-email}

默认情况下，会自动生成电子邮件的 **[!UICONTROL Plain text]** 版本并与 **[!UICONTROL Edit]** 版本同步。

个性化字段和添加到HTML版本的内容块也与纯文本版本同步。

>[!NOTE]
>
>要在纯文本版本中使用内容块，请确保它们不包含HTML代码。

要有与HTML版本不同的纯文本版本，您可以通过从电子邮件视图中单击 **[!UICONTROL Sync with HTML]** 切换来禁用 **[!UICONTROL Plain text]** 此同步。

![](assets/email_designer_textversion.png)

然后，您可以根据需要编辑纯文本版本。

>[!NOTE]
>
>如果在同步处于禁用状态时编辑 **[!UICONTROL Plain text]** 版本，下次启用该选项 **[!UICONTROL Sync with HTML]** 时，您在纯文本版本中所做的所有更改将替换为HTML版本。**[!UICONTROL Plain text]** 视图中所做的更改不能反映在 **[!UICONTROL HTML]** 视图中。

### 在HTML中编辑电子邮件内容源 {#editing-an-email-content-source-in-html}

对于最高级的用户和调试，您可以直接在HTML中查看和编辑电子邮件内容。

您有两种方法可以编辑电子邮件的HTML版本：

* 选择 **[!UICONTROL Edit]** &gt; **[!UICONTROL HTML]** 以打开整个电子邮件的HTML版本。

   ![](assets/email_designer_html1.png)

* 从WYSIWYG界面中，选择元素并单击 **[!UICONTROL Source code]** 图标。

   只显示选定元素的源。如果选定元素是 **[!UICONTROL HTML]** 内容组件，则可以编辑源代码。其他组件处于只读模式，但仍可在电子邮件的完整HTML版本中编辑。

   ![](assets/email_designer_html2.png)

如果修改HTML代码，则电子邮件的响应性可能会被破坏。确保使用 **[!UICONTROL Preview]** 按钮测试它。请参阅 [预览消息](../../sending/using/previewing-messages.md)。

## 通过Adobe Campaign集成进行设计 {#design-through-adobe-campaign-integrations}

### 在Dreamweaver中编辑内容 {#editing-content-in-dreamweaver}

通过Adobe Campaign Standard与Dreamweaver的集成，您可以在Dreamweaver界面中编辑电子邮件的内容。您可以访问Dreamweaver的强大界面，设计和开发响应式电子邮件内容。

* **双向同步**

   只要在一个产品中进行编辑，就会在另一个产品中实时更新。如果要在Dreamweaver中更改文本的颜色，一旦进行了编辑，文本的颜色就会在Campaign中实时显示。此外，当您在Dreamweaver或Campaign中选择代码时，由于行号相同，选择仍会保留在两个产品之间，这在查找代码中特定的内容时非常有用。

* **通过Dreamweaver将本地图像上传到AC**

   在Dreamweaver中创建或编辑电子邮件时，只需从桌面或本地计算机中选择一幅图像即可。当Dreamweaver始终允许您这样做时，当Dreamweaver和Campaign已连接时，本地文件将立即上传到Adobe Campaign服务器：无需在内容更改时手动上传图像。此外，它还确保了最新图像在Campaign中始终处于实时状态。

* **在Dreamweaver中添加营销活动个性化**

   对于电子邮件开发人员，不再需要添加 ```[[FIRSTNAME_PLACEHOLDER]]``` 类似文本或查找数据模型表的语法。Dreamweaver中的Campaign工具栏直接连接到Campaign实例的数据模型。这意味着您可以将希望个性化的任何数据从“名字”(如“名字”)拉到地址中。如果您在Campaign中创建了内容块，则还可以将这些内容直接拖入Dreamweaver。

此功能在可从此处访问 [的Dreamweaver文档中进行详细](https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html)介绍。还提供演示 [视频](https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html) 。

### 在Experience Manager中编辑内容 {#editing-content-in-experience-manager}

电子邮件内容可在Experience Manager中进行编辑，然后用于Adobe Campaign Standard中的一个或多个电子邮件。请参阅 [本文档](../../integrating/using/integrating-with-experience-manager.md)。

### 电子邮件设计选项比较 {#email-design-options-comparison}

Adobe Campaign提供多个电子邮件创作选项。下表显示了它们的主要可能性、优点和限制。

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> 电子邮件设计器<br /> </th> 
   <th> Experience Manager<br /> </th> 
   <th> Dreamweaver<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <strong>启动空白电子邮件</strong><br /> </td> 
   <td> 支持的<br /> </td> 
   <td> 支持的<br /> </td> 
   <td> 支持的<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>编写HTML</strong><br /> </td> 
   <td> 支持的<br /> </td> 
   <td> 不受支持<br /> </td> 
   <td> 支持的<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>更新HTML</strong><br /> </td> 
   <td> 仅在HTML组件内<br /> </td> 
   <td> 不受支持<br /> </td> 
   <td> 支持的<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>基本个性化</strong><br /> </td> 
   <td> 支持的<br /> </td> 
   <td> 支持的<br /> </td> 
   <td> 支持的<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>高级个性化</strong><br /> </td> 
   <td> 支持的<br /> </td> 
   <td> 不受支持<br /> </td> 
   <td> 不受支持<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>校样/预览</strong><br /> </td> 
   <td> 支持的<br /> </td> 
   <td> Campaign中的AEM<br /> 校样预览<br /> </td> 
   <td> Campaign中的预览和校样<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>产品列表</strong><br /> </td> 
   <td> 电子邮件交易消息支持<br /> </td> 
   <td> 不受支持<br /> </td> 
   <td> 不受支持<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>益处</strong><br /> </td> 
   <td> 
     - 通过拖放体验轻松构建电子邮件<br/>-与传统内容编辑器类似的功能<br/>-可重复使用的片段内容
  </td> 
   <td> 
     - 重用电子邮件中网站的资产<br/>-利用电子邮件内容中Experience
 Manager的强大功能
    </td> 
   <td> 
    - 开发人员可以直接编码电子邮件<br/>-双向同步<br/>-在Dreamweaver中脱机编辑和稍后同步<br/>-通过Dreamweaver将图像上载到Adobe
 Campaign
  </td> 
  </tr> 
  <tr> 
   <td> <strong>限制</strong><br /> </td> 
   <td> 
     - 片段中没有条件内容<br/>-不可能使用Experience
 Manager片段
  </td> 
   <td> 
     - 高级个性化难以实现<br/>-需要在Adobe
 Campaign中发送测试
  </td> 
   <td> 不支持动态内容<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>受众</strong><br /> </td> 
   <td> 希望将HTML组件与拖放功能结合使用的营销人员<br /> </td> 
   <td> 已经使用Experience Manager的营销人员希望在很少个性化的情况下使用标准电子邮件模板<br /> </td> 
   <td> 希望编码电子邮件内容并直接与Adobe Campaign集成的开发人员<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>了解更多信息</strong><br /> </td> 
   <td> 请参阅 <a href="../../designing/using/about-email-content-design.md#about-the-email-designer">关于电子邮件设计器</a><br /> </td> 
   <td> 请参阅 <a href="../../integrating/using/integrating-with-experience-manager.md">与Experience Manager集成</a><br /> </td> 
   <td> 请参阅 <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver和Campaign</a> ，观看此 <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">视频</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

