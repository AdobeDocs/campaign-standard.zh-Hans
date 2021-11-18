---
title: '使用现有内容设计电子邮件 '
description: 了解如何使用Email Designer中的现有内容设计电子邮件内容。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 3bda4227-2a6e-4813-a288-93a4388a9787
source-git-commit: 0d645de54106d49452a846ee650335607dbf21d3
workflow-type: tm+mt
source-wordcount: '1282'
ht-degree: 5%

---

# 使用现有内容进行设计 {#designing-using-existing-content}

## 选择现有内容{#selecting-an-existing-content}

Adobe Campaign提供了一组预定义内容，可帮助您快速入门。 您可以使用其中一种方法，或者，如果您需要发送的消息的内容是在Adobe Campaign之外准备的，则可以从计算机或URL导入该消息。

创建电子邮件或登陆页面时，您可以选择从其他源加载现有内容。

>[!NOTE]
>
>下图显示了如何使用 [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md).

1. 创建电子邮件或登陆页面后，打开其内容。
1. 单击主页图标以访问 **[!UICONTROL Email Designer]** 主页。

   ![](assets/des_loading_1.png)

1. 选择要加载的内容源：

   * [内容模板](../../designing/using/using-reusable-content.md#content-templates):单击 **[!UICONTROL Templates]** 选项卡。
   * [从头开始创建内容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)，以重新开始：单击 **[!UICONTROL Create]** 按钮。
   * [以ZIP或HTML文件形式从您的计算机中获取的内容](#importing-content-from-a-file):单击 **[!UICONTROL Upload]** 按钮。
   * [现有URL中的内容](#importing-content-from-a-url) （仅适用于电子邮件）：单击 **[!UICONTROL Import from URL]** 按钮。

   ![](assets/des_loading_2.png)

1. 加载内容。 所选内容将替换当前内容。

   导入后，即可编辑和个性化内容。

   >[!NOTE]
   >
   >的 [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md) 使用特定标记。 上传到Campaign的标准HTML内容必须与预期的标记相匹配，才能在Email Designer中完全兼容和可编辑。 如果不匹配，则会在 [兼容模式](#compatibility-mode). 要使现有内容兼容，请参阅 [此部分](#editing-existing-contents-with-the-email-designer).

**相关主题：**

* [创建电子邮件](../../channels/using/creating-an-email.md)
* [管理登陆页面](../../channels/using/getting-started-with-landing-pages.md)

## 使用Email Designer编辑现有内容{#editing-existing-contents-with-the-email-designer}

充分利用 [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md)，则上传的HTML必须包含特定标记，才能与所见即所得(WYSIWYG)编辑器兼容。

如果HTML的全部或部分不包含此标记，则内容随后将加载到“ [兼容模式](#compatibility-mode)&#39;。

要使现有外部内容在Email Designer中完全可编辑，请参阅 [使用现有内容设计电子邮件](../../designing/using/using-existing-content.md) 中。

## 导入现有电子邮件内容 {#importing}

### 从文件导入内容 {#importing-content-from-a-file}

在Email Designer主页中，单击 **[!UICONTROL Upload]** 按钮从计算机上传文件，然后进行确认。

zip文件结构没有限制。 但是，引用HTML文件必须是相对的，并遵循zip文件夹的树结构。

支持以下格式进行导入：

* 带有合并样式表的HTML文件
* 包含HTML文件、样式表(.CSS)和图像的.zip文件夹

>[!NOTE]
>
>对于电子邮件内容，我们建议您导入包含样式表的单个HTML文件。

#### 从URL导入内容 {#importing-content-from-a-url}

在从URL导入内容之前，请确保它遵循以下要求：

* 内容需要通过此URL公开提供。
* 出于安全考虑，仅URL以开头 **[!UICONTROL https]** 。
* 确保在绝对链接和HTTPS中设置所有资源（图像、CSS）。 否则，在发送电子邮件后，将不显示镜像页面及其资源。 以下是绝对链接定义的示例：

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>从URL加载内容仅适用于电子邮件渠道。

要从URL检索现有内容，请执行以下步骤：

1. 从Email Designer主页中，选择 **[!UICONTROL Import from URL]** 按钮。

   ![](assets/email_designer_importfromurl.png)

1. 定义从中检索内容的URL。
1. 单击 **[!UICONTROL Confirm]**。

在视频中发现此功能.

>[!VIDEO](https://video.tv.adobe.com/v/25926?quality=12)

提供了其他Campaign Standard操作方法视频 [此处](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hans).

### 在准备时自动从URL检索内容 {#retrieving-content-from-a-url-automatically-at-preparation-time}

在准备消息期间从URL导入内容，使您能够在每次准备电子邮件时检索最新的HTML内容。 这样，定期电子邮件的内容在发送时始终保持为最新。 此功能还允许您创建计划在特定日期发送的消息，即使内容尚未准备就绪也是如此。

要在准备时检索内容，请执行以下步骤：

1. 选择 **[!UICONTROL Content imported during preparation]** 选项。

   ![](assets/email_designer_importfromurl2.png)

1. URL内容在编辑器中以只读方式显示。

   >[!CAUTION]
   >
   >在此步骤中，不应考虑内容编辑器中显示的HTML。 将在准备阶段进行检索。

1. 要预览已检索的URL内容，请在创建消息后打开该消息，然后单击 **[!UICONTROL Preview]** 按钮。

可以将检索内容的远程URL个性化。 为此请执行以下操作步骤：

1. 单击屏幕顶部的电子邮件标签以访问Email Designer **[!UICONTROL Properties]** 选项卡。
1. 查找 **[!UICONTROL Remote URL]** 字段。

   ![](assets/email_designer_importfromurl4.png)

1. 插入所需的个性化字段、内容块或动态文本。

   的 **[!UICONTROL Current date - YYYYMMDD]** 例如，内容块允许您插入日期。

   >[!NOTE]
   >
   >可用的个性化字段已链接到 **投放** 仅属性（电子邮件创建日期、状态、营销活动标签……）。

如果内容下载在首次尝试时失败，则可重试两次：

1. 第二次尝试在第一次尝试后50毫秒开始。
1. 第三次尝试在第二次尝试后100毫秒开始。

在以下情况下，这些重试非常有用：

* 远程服务器上的短时服务故障
* 群集上的服务器故障，在这种情况下，由于对工作服务器的负载平衡，重试更有可能成功

### 兼容性模式 {#compatibility-mode}

在上传内容时，内容必须包含特定标记，才能与Email Designer的WYSIWYG编辑器完全兼容和可编辑。

如果上传HTML的全部或部分内容与预期标记不兼容，则内容随后会以“兼容模式”加载，这会限制通过UI进行编辑的可能性。

在兼容性模式下加载内容时，您仍可以通过界面执行以下修改（隐藏不可用的操作）：

* 更改文本或更改图像
* 插入链接和个性化字段
* 编辑所选HTML块上的一些样式选项
* 定义条件内容

![](assets/email_designer_compatibility.png)

其他修改（如向电子邮件添加新部分或高级样式）必须直接在电子邮件的源代码中通过HTML模式进行。

有关将现有电子邮件转换为与Email Designer兼容的电子邮件的更多信息，请参阅 [此部分](../../designing/using/using-existing-content.md).

**相关主题**：

* [创建电子邮件](../../channels/using/creating-an-email.md)
* [Email Designer简介视频](../../designing/using/designing-content-in-adobe-campaign.md#video)
* [从头开始设计电子邮件内容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## 转换HTML内容 {#converting-an-html-content}

如果要构建一个模块化模板和片段框架，以便将其组合以在多封电子邮件中重复使用，则应当考虑将电子邮件HTML转换为Email Designer模板。

此用例提供了一种将HTML电子邮件转换为Email Designer组件的快速方法。

>[!CAUTION]
>
>此部分面向熟悉HTML代码的高级用户。

>[!NOTE]
>
>与兼容性模式一样，HTML组件也可编辑，但选项有限：您只能执行就地版本。

在Email Designer之外，确保将原始HTML分为可重复使用的部分。

如果不是这种情况，请从HTML中切出不同的块。 例如：

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

识别所有块后，在Email Designer中，对现有电子邮件的每个部分重复以下步骤：

1. 打开Email Designer以创建空的电子邮件内容。
1. 设置主体级别属性：背景颜色、宽度等 有关更多信息，请参阅[编辑电子邮件样式](../../designing/using/styles.md)。
1. 添加结构组件。 有关更多信息，请参阅[编辑电子邮件结构](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 添加HTML组件。 有关更多信息，请参阅[添加片段和组件](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 将HTML复制并粘贴到该组件中。
1. 切换到移动设备视图。 有关更多信息，请参阅[此章节](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)。

   响应视图已损坏，因为缺少CSS。

1. 要修复此问题，请切换到源代码模式，然后将样式部分复制并粘贴到新样式部分中。 例如：

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
   >请确保在另一个自定义样式标记中将样式添加到此之后。
   >
   >请勿修改由Email Designer生成的CSS:
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`


1. 返回到移动设备视图，检查内容是否正确显示并保存更改。
