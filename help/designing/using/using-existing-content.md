---
solution: Campaign Standard
product: campaign
title: '使用现有内容设计电子邮件 '
description: 了解如何使用电子邮件设计器中的现有内容电子邮件内容设计电子邮件。
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 5%

---

# Designing using existing content {#designing-using-existing-content}

## Selecting an existing content{#selecting-an-existing-content}

Adobe Campaign附带一组预定义的内容，可帮助您快速入门。 您可以使用其中一项，或者，如果需要发送的消息的内容是在Adobe Campaign之外准备的，则可以从计算机或URL导入该消息。

创建电子邮件或登陆页时，您可以选择从其他源加载现有内容。

>[!NOTE]
>
>下图显示了如何使用电子邮件设计器加载现 [有内容](../../designing/using/designing-content-in-adobe-campaign.md)。

1. 创建电子邮件或登陆页后，打开其内容。
1. 单击主页图标以访问 **[!UICONTROL Email Designer]** 主页。

   ![](assets/des_loading_1.png)

1. 选择要加载的内容的源：

   * [内容模板](../../designing/using/using-reusable-content.md#content-templates):单击选 **[!UICONTROL Templates]** 项卡。
   * [从头开始](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)，到开始新鲜：单击按 **[!UICONTROL Create]** 钮。
   * [以ZIP或HTML文件形式从您的计算机中获取内容](#importing-content-from-a-file):单击按 **[!UICONTROL Upload]** 钮。
   * [来自现有URL的内容](#importing-content-from-a-url) （仅适用于电子邮件）:单击按 **[!UICONTROL Import from URL]** 钮。

   ![](assets/des_loading_2.png)

1. 加载内容。 所选内容将替换当前内容。

   导入后，内容即可进行编辑和个性化。

   >[!NOTE]
   >
   >电子邮 [件设计器](../../designing/using/designing-content-in-adobe-campaign.md) 使用特定的标签。 上传到活动的标准HTML内容必须与期望的标签相匹配，才能完全兼容并从电子邮件设计器中进行编辑。 如果不匹配，您的内容将以兼容性模 [式上传](#compatibility-mode)。 要使现有内容兼容，请参 [阅此部分](#editing-existing-contents-with-the-email-designer)。

**相关主题：**

* [创建电子邮件](../../channels/using/creating-an-email.md)
* [管理登陆页](../../channels/using/getting-started-with-landing-pages.md)

## 使用电子邮件设计器编辑现有内容{#editing-existing-contents-with-the-email-designer}

要充分利用电子邮件设计器的 [版本功能](../../designing/using/designing-content-in-adobe-campaign.md)，上传的HTML必须包含使其符合所见即所得编辑器的特定标记。

如果HTML的全部或部分没有此标记，则内容随后将以“兼容模式” [加载](#compatibility-mode)。

要使现有外部内容在电子邮件设计器中完全可编辑，请参 [阅使用现有内容设计电子邮件](../../designing/using/using-existing-content.md) 。

## 导入现有电子邮件内容 {#importing}

### Importing content from a file {#importing-content-from-a-file}

在“电子邮件设计器”主页下，单 **[!UICONTROL Upload]** 击按钮从您的计算机上传文件，然后进行确认。

zip文件结构没有限制。 但是，引用HTML文件必须是相对的，并且必须遵循zip文件夹的树结构。

支持以下格式进行导入：

* 带有合并样式表的HTML文件
* 包含HTML文件、样式表(.CSS)和图像的。zip文件夹

>[!NOTE]
>
>对于电子邮件内容，我们建议您导入一个包含样式表的HTML文件。

#### Importing content from a URL {#importing-content-from-a-url}

在从URL导入内容之前，请确保它符合以下要求：

* 内容需要通过此URL公开。
* 出于安全原因，仅允许以 **[!UICONTROL https]** 开头的URL。
* 确保所有资源（图像、CSS）均在绝对链接和HTTPS中设置。 否则，在发送电子邮件后，镜像页面将在没有其资源的情况下显示。 以下是绝对链接定义的示例：

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>从URL加载内容仅适用于电子邮件渠道。

要从URL检索现有内容，请按照以下步骤操作：

1. 从“电子邮件设计器”主页中，选择 **[!UICONTROL Import from URL]** 按钮。

   ![](assets/email_designer_importfromurl.png)

1. 定义从中检索内容的URL。
1. 单击 **[!UICONTROL Confirm]**.

**相关主题：**

[从URL视频导入内容](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html#Workingwithexistingcontent) 。

### 在准备时自动从URL检索内容 {#retrieving-content-from-a-url-automatically-at-preparation-time}

在准备邮件期间从URL导入内容使您能够在每次准备电子邮件时检索最新的HTML内容。 这样，重复电子邮件的内容在发送时始终保持最新。 此功能还允许您创建预定在特定日期的消息，即使该内容尚未准备就绪。

要在准备时检索内容，请执行以下步骤：

1. 选择选 **[!UICONTROL Content imported during preparation]** 项。

   ![](assets/email_designer_importfromurl2.png)

1. URL内容在编辑器中显示为只读。

   >[!CAUTION]
   >
   >在此步骤中，不应考虑内容编辑器中的HTML显示。 将在准备阶段检索。

1. 要预览已检索的URL内容，请在创建消息后打开该消息，然后单击 **[!UICONTROL Preview]** 按钮。

可以对从中检索内容的远程URL进行个性化。 为此请执行以下操作步骤：

1. 单击屏幕顶部的电子邮件标签以访问“电子邮件设计器” **[!UICONTROL Properties]** 选项卡。
1. 查找字 **[!UICONTROL Remote URL]** 段。

   ![](assets/email_designer_importfromurl4.png)

1. 插入所需的个性化字段、内容块或动态文本。

   例 **[!UICONTROL Current date - YYYYMMDD]** 如，内容块允许您插入日期。

   >[!NOTE]
   >
   >可用个性化字段仅链接到 **投放** 属性(电子邮件创建日期、状态、活动标签……)。

### 兼容性模式 {#compatibility-mode}

上传内容时，内容中必须包含特定标记，以使其完全符合规范并可以使用电子邮件设计器的WYSIWYG编辑器进行编辑。

如果所上传HTML的全部或部分内容不符合预期的标记，则内容将以“兼容性模式”加载，这将限制通过UI进行编辑的可能性。

当内容以兼容模式加载时，您仍可以通过界面执行以下修改（不可用的操作被隐藏）:

* 更改文本或更改图像
* 插入链接和个性化字段
* 编辑选定HTML块上的一些样式选项
* 定义条件内容

![](assets/email_designer_compatibility.png)

其他修改（如向电子邮件添加新章节或高级样式）必须直接在电子邮件的源代码中通过HTML模式进行。

有关将现有电子邮件转换为与电子邮件设计器兼容的电子邮件的更多信息，请参 [阅此部分](../../designing/using/using-existing-content.md)。

**相关主题**：

* [创建电子邮件](../../channels/using/creating-an-email.md)
* [电子邮件设计人员简介视频](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=chi_hans)
* [从头开始设计电子邮件内容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## 转换HTML内容 {#converting-an-html-content}

如果要构建一个模块化模板和片段框架，这些模板和片段可以合并在多个电子邮件中重复使用，您应考虑将电子邮件HTML转换为电子邮件设计器模板。

此用例优惠了将HTML电子邮件转换为电子邮件设计器组件的快速方法。

>[!CAUTION]
>
>此部分面向熟悉HTML代码的高级用户。

>[!NOTE]
>
>与兼容性模式一样，HTML组件也可编辑，但选项有限：只能执行就地版本。

在电子邮件设计器之外，确保将原始HTML分为可重用的部分。

如果不是这样，请从HTML中剪切不同的块。 例如：

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

在确定所有区块后，在电子邮件设计器中，对现有电子邮件的每个区域重复以下步骤：

1. 打开电子邮件设计器以创建空的电子邮件内容。
1. 设置正文级属性：背景颜色、宽度等。 有关更多信息，请参阅[编辑电子邮件样式](../../designing/using/styles.md)。
1. 添加结构组件。 有关更多信息，请参阅[编辑电子邮件结构](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 添加HTML组件。 有关更多信息，请参阅[添加片段和组件](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 将HTML复制并粘贴到该组件中。
1. 切换到移动视图。 有关更多信息，请参阅[此章节](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)。

   响应式视图中断，因为您的CSS缺失。

1. 要解决此问题，请切换到源代码模式，并将样式部分复制粘贴到新样式部分。 例如：

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
   >确保在此之后在另一个自定义样式标签中添加样式。
   >
   >请勿修改电子邮件设计器生成的CSS:
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`


1. 返回移动视图，检查内容是否正确显示并保存更改。
