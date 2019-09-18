---
title: '使用现有内容设计电子邮件 '
seo-title: '使用现有内容设计电子邮件 '
description: '使用现有内容设计电子邮件 '
seo-description: 了解如何使用电子邮件设计器中的现有内容电子邮件内容设计电子邮件。
page-status-flag: 从未激活
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 设计
content-type: 参考
topic-tags: 编辑——电子邮件——内容
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a7de545e9eec675444245576cddc6eaf8dce05f4

---

# 使用现有内容进行设计 {#designing-using-existing-content}

## 选择现有内容{#selecting-an-existing-content}

Adobe Campaign附带一组预定义的内容，可帮助您快速入门。 您可以使用其中一种，或者，如果需要发送的消息的内容是在Adobe Campaign之外准备的，则可以从计算机或URL导入该消息。

创建电子邮件或登陆页面时，您可以选择从其他源加载现有内容。

>[!NOTE]
>
>下图显示了如何使用电子邮件设计器加载现 [有内容](../../designing/using/overview.md)。

1. 创建电子邮件或登录页面后，打开其内容。
1. 单击主页图标以访问 **[!UICONTROL Email Designer]** 主页。

   ![](assets/des_loading_1.png)

1. 选择要加载的内容的源：

   * [内容模板](../../designing/using/using-reusable-content.md#content-templates):单击选 **[!UICONTROL Templates]** 项卡。
   * [内容从头开始](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)，从新开始：单击该 **[!UICONTROL Create]** 按钮。
   * [以ZIP或HTML文件形式从您的计算机中获取内容](../../designing/using/using-existing-content.md#importing-content-from-a-file):单击该 **[!UICONTROL Upload]** 按钮。
   * [来自现有URL的内容](../../designing/using/using-existing-content.md#importing-content-from-a-url) （仅适用于电子邮件）:单击该 **[!UICONTROL Import from URL]** 按钮。
   ![](assets/des_loading_2.png)

1. 加载内容。 所选内容将替换当前内容。

   导入后，内容即可进行编辑和个性化。

   >[!NOTE]
   >
   >电子邮 [件设计器使用特定](../../designing/using/overview.md) 的标签。 上传到Campaign的标准HTML内容必须与期望的标记匹配，才能完全兼容并从电子邮件设计器中编辑。 如果不匹配，您的内容将以兼容性模 [式上传](../../designing/using/using-existing-content.md#compatibility-mode)。 要使现有内容兼容，请参 [阅此部分](../../designing/using/using-existing-content.md#editing-existing-contents-with-the-email-designer)。

**相关主题：**

* [创建电子邮件](../../channels/using/creating-an-email.md)
* [管理登陆页面](../../channels/using/about-landing-pages.md)

## 使用电子邮件设计器编辑现有内容{#editing-existing-contents-with-the-email-designer}

要充分利用电子邮件设计器的 [版本可能性](../../designing/using/overview.md)，上传的HTML必须包含使其符合所见即所得编辑器的特定标记。

如果HTML的全部或部分内容没有此标记，则内容随后将以“兼容模式” [加载](../../designing/using/using-existing-content.md#compatibility-mode)。

要使现有外部内容在电子邮件设计器中完全可编辑，请参阅使 [用现有内容设计电子邮件一节](../../designing/using/using-existing-content.md) 。

## 导入 {#importing}

### 从文件导入内容 {#importing-content-from-a-file}

在“电子邮件设计器”主页中，单击 **[!UICONTROL Upload]** 按钮以从计算机上传文件，然后进行确认。

zip文件结构没有限制。 但是，引用HTML文件必须是相对的，并且必须遵循zip文件夹的树结构。

导入支持以下格式：

* 包含合并样式表的HTML文件
* 包含HTML文件、样式表(.CSS)和图像的。zip文件夹

>[!NOTE]
>
>对于电子邮件内容，我们建议您导入单个HTML文件并包含一个合并的样式表。

#### 从URL导入内容 {#importing-content-from-a-url}

在从URL导入内容之前，请确保它符合以下要求：

* 内容需要通过此URL公开可用。
* 出于安全原因，仅允许以 **[!UICONTROL https]** 开头的URL。
* 确保在绝对链接和HTTPS中设置所有资源（图像、CSS）。 否则，在发送电子邮件后，将显示镜像页面，而不显示其资源。 以下是绝对链接定义的示例：

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>从URL加载内容仅适用于电子邮件渠道。

要从URL检索现有内容，请执行以下步骤：

1. 从“电子邮件设计器”主页中，选择按 **[!UICONTROL Import from URL]** 钮。

   ![](assets/email_designer_importfromurl.png)

1. 定义从中检索内容的URL。
1. Click **[!UICONTROL Confirm]**.

**相关主题：**

[从URL视频导入内容](https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html#Workingwithexistingcontent)

### 在准备时自动从URL检索内容 {#retrieving-content-from-a-url-automatically-at-preparation-time}

在准备邮件期间从URL导入内容使您能够在每次准备电子邮件时检索最新的HTML内容。 这样，重复电子邮件的内容在发送时始终保持最新。 此功能还允许您创建在特定日期预定的消息，即使该内容尚未准备好。

要在准备时检索内容，请执行以下步骤：

1. 选择选 **[!UICONTROL Content imported during preparation]** 项。

   ![](assets/email_designer_importfromurl2.png)

1. URL内容在编辑器中显示为只读。

   >[!CAUTION]
   >
   >在此步骤中，不应考虑内容编辑器中的HTML显示。 将在准备阶段检索。

1. 要预览已检索的URL内容，请在创建消息后打开该消息，然后单击按 **[!UICONTROL Preview]** 钮。

可以个性化从中检索内容的远程URL。 为此，请按照以下步骤操作：

1. 单击屏幕顶部的电子邮件标签以访问“电子邮件设计器”选 **[!UICONTROL Properties]** 项卡。
1. 查找字 **[!UICONTROL Remote URL]** 段。

   ![](assets/email_designer_importfromurl4.png)

1. 插入所需的个性化字段、内容块或动态文本。

   例 **[!UICONTROL Current date - YYYYMMDD]** 如，内容块允许您插入日期。

   >[!NOTE]
   >
   >可用的个性化字段仅链接到 **“交付** ”属性（电子邮件创建日期、状态、营销活动标签……）。

### 兼容性模式 {#compatibility-mode}

上传内容时，它必须包含特定标记才能与电子邮件设计器的WYSIWYG编辑器完全兼容和可编辑。

如果上传的HTML的全部或部分内容不符合预期的标记，则内容会以“兼容性模式”加载，这会限制通过UI进行编辑的可能性。

在兼容性模式下加载内容时，您仍可以通过界面执行以下修改（不可用的操作是隐藏的）:

* 更改文本或更改图像
* 插入链接和个性化字段
* 编辑选定HTML块上的一些样式选项
* 定义条件内容

![](assets/email_designer_compatibility.png)

其他修改（如向电子邮件添加新章节或高级样式）必须通过HTML模式直接在电子邮件的源代码中完成。

有关将现有电子邮件转换为与电子邮件设计人员兼容的电子邮件的更多信息，请参 [阅此部分](../../designing/using/using-existing-content.md)。

**相关主题**:

* [创建电子邮件](../../channels/using/creating-an-email.md)
* [电子邮件设计人员简介视频](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=chi_hans)
* [从头开始设计电子邮件内容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## 转换HTML内容 {#converting-an-html-content}

如果要构建一个模块化模板和片段框架，这些模板和片段可以组合在一起以在多个电子邮件中重复使用，您应考虑将电子邮件HTML转换为电子邮件设计器模板。

此用例提供了一种将HTML电子邮件转换为电子邮件设计器组件的快速方法。

>[!CAUTION]
>
>本节面向熟悉HTML代码的高级用户。

>[!NOTE]
>
>与兼容性模式一样，HTML组件也可编辑，但选项有限：您只能执行就地版本。

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

识别所有区块后，在电子邮件设计器中，对现有电子邮件的每个部分重复以下步骤：

1. 打开电子邮件设计器以创建空的电子邮件内容。
1. 设置正文级属性：背景颜色、宽度等。 有关此内容的详细信息，请参阅 [编辑电子邮件样式](../../designing/using/styles.md)。
1. 添加结构组件。 有关此内容的详细信息，请参 [阅编辑电子邮件结构](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 添加HTML组件。 有关此方面的详细信息，请参 [阅添加片段和组件](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 将HTML复制并粘贴到该组件中。
1. 切换到移动视图。 有关此方面的详细信息，请参 [阅此部分](../../designing/using/styles.md#switching-to-mobile-view)。

   响应式视图因CSS缺失而中断。

1. 要解决此问题，请切换到源代码模式，然后将样式部分复制并粘贴到新的样式部分。 例如：

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
   >请勿修改由电子邮件设计人员生成的CSS: `<style acrite-template-css="true">` 和 `<style acrite-custom-styles="" type="text/css">`。 确保在此之后添加样式。

1. 返回移动视图，检查内容是否正确显示并保存更改。
