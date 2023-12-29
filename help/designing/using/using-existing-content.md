---
title: 使用现有内容设计电子邮件
description: 了解如何使用Email Designer中的现有内容电子邮件内容设计电子邮件。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 3bda4227-2a6e-4813-a288-93a4388a9787
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1277'
ht-degree: 4%

---

# 使用现有内容进行设计 {#designing-using-existing-content}

## 选择现有内容{#selecting-an-existing-content}

Adobe Campaign提供了一组预定义内容来帮助您入门。 您可以使用其中一种方法，或者，如果您需要发送的消息内容是在Adobe Campaign之外准备的，则可以从您的计算机或URL导入该内容。

创建电子邮件或登陆页面时，您可以选择从其他源加载现有内容。

>[!NOTE]
>
>下图显示了如何使用加载现有内容 [电子邮件设计工具](../../designing/using/designing-content-in-adobe-campaign.md).

1. 创建电子邮件或登陆页面后，打开其内容。
1. 单击主页图标以访问 **[!UICONTROL Email Designer]** 主页。

   ![](assets/des_loading_1.png)

1. 选择要加载的内容的源：

   * [内容模板](../../designing/using/using-reusable-content.md#content-templates)：单击 **[!UICONTROL Templates]** 选项卡。
   * [从头开始的内容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)，以重新开始：单击 **[!UICONTROL Create]** 按钮。
   * [计算机中的ZIP或HTML文件内容](#importing-content-from-a-file)：单击 **[!UICONTROL Upload]** 按钮。
   * [来自现有URL的内容](#importing-content-from-a-url) （仅适用于电子邮件）：单击 **[!UICONTROL Import from URL]** 按钮。

   ![](assets/des_loading_2.png)

1. 加载内容。 所选内容替换当前内容。

   导入内容后，即可编辑内容并使其个性化。

   >[!NOTE]
   >
   >此 [电子邮件设计工具](../../designing/using/designing-content-in-adobe-campaign.md) 使用特定标记。 上传到Campaign的标准HTML内容必须与预期的标记匹配，才能在Email Designer中完全兼容和可编辑。 如果不匹配，您的内容将上传到 [兼容模式](#compatibility-mode). 要使现有内容兼容，请参阅 [本节](#editing-existing-contents-with-the-email-designer).

**相关主题：**

* [创建电子邮件](../../channels/using/creating-an-email.md)
* [管理登陆页面](../../channels/using/getting-started-with-landing-pages.md)

## 使用电子邮件设计器编辑现有内容{#editing-existing-contents-with-the-email-designer}

为充分利用 [电子邮件设计工具](../../designing/using/designing-content-in-adobe-campaign.md)，您上传的HTML必须包含特定标记，以便与WYSIWYG编辑器兼容。

如果全部或部分HTML没有此标记，则内容将加载到 [兼容模式](#compatibility-mode)’。

要使现有外部内容在Email Designer中完全可编辑，请参阅 [使用现有内容设计电子邮件](../../designing/using/using-existing-content.md) 部分。

## 导入现有电子邮件内容 {#importing}

### 从文件导入内容 {#importing-content-from-a-file}

在Email Designer主页中，单击 **[!UICONTROL Upload]** 按钮从计算机上传文件，然后进行确认。

zip文件结构没有限制。 但是，引用HTML文件必须是相对的，并且遵循zip文件夹的树结构。

支持导入以下格式：

* 具有合并样式表的HTML文件
* 包含HTML文件、样式表(.CSS)和图像的.zip文件夹

>[!NOTE]
>
>对于电子邮件内容，我们建议您导入具有合并样式表的单个HTML文件。

#### 从URL导入内容 {#importing-content-from-a-url}

在从URL导入内容之前，请确保它遵循以下要求：

* 内容需要通过此URL公开发布。
* 出于安全原因，仅限以开头的URL **[!UICONTROL https]** 是允许的。
* 确保所有资源（图像、CSS）均在绝对链接和HTTPS中进行设置。 否则，在发送电子邮件后，将显示不带其资源的镜像页面。 以下是绝对链接定义的示例：

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

在视频中发现此功能。

>[!VIDEO](https://video.tv.adobe.com/v/25926?quality=12)

提供了其他Campaign Standard操作方法视频 [此处](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hans).

### 在准备期间自动从URL检索内容 {#retrieving-content-from-a-url-automatically-at-preparation-time}

在邮件准备期间从URL导入内容，可让您在每次准备电子邮件时检索最新的HTML内容。 这样，定期电子邮件的内容在发送时始终保持最新。 此功能还允许您创建在特定日期计划的消息，即使内容尚未准备就绪。

要在准备时检索内容，请执行以下步骤：

1. 选择 **[!UICONTROL Content imported during preparation]** 选项。

   ![](assets/email_designer_importfromurl2.png)

1. URL内容在编辑器中显示为只读。

   >[!CAUTION]
   >
   >在此步骤中，不应考虑内容编辑器中显示的HTML。 它将在准备阶段进行检索。

1. 要预览已检索的URL内容，请在创建消息后将其打开，然后单击 **[!UICONTROL Preview]** 按钮。

可以个性化从中检索内容的远程URL。 为此请执行以下操作步骤：

1. 单击屏幕顶部的电子邮件标签以访问电子邮件设计器 **[!UICONTROL Properties]** 选项卡。
1. 查找 **[!UICONTROL Remote URL]** 字段。

   ![](assets/email_designer_importfromurl4.png)

1. 插入所需的个性化字段、内容块或动态文本。

   此 **[!UICONTROL Current date - YYYYMMDD]** 例如，内容块允许您插入一天的日期。

   >[!NOTE]
   >
   >可用的个性化字段已链接到 **投放** 仅限属性（电子邮件创建日期、状态、营销活动标签……）。

如果内容下载在第一次尝试时失败，则可以重试两次：

1. 第二次尝试在第一次尝试后50毫秒开始。
1. 第三次尝试在第二次尝试后100毫秒开始。

这些重试在以下情况下很有帮助：

* 远程服务器上的短期服务故障
* 群集上的服务器故障，在这种情况下，由于对工作服务器的负载平衡，重试更有可能成功

### 兼容模式 {#compatibility-mode}

上传内容时，该内容必须包含特定标记，以便与Email Designer的WYSIWYG编辑器完全兼容并可编辑。

如果全部或部分上传的HTML不符合预期的标记，则内容将在“兼容模式”下加载，这将限制通过UI进行编辑的可能性。

在兼容模式下加载内容时，您仍然可以通过界面执行以下操作（隐藏不可用的操作）：

* 更改文本或更改图像
* 插入链接和个性化字段
* 编辑所选HTML块上的某些样式选项
* 定义条件内容

![](assets/email_designer_compatibility.png)

其他修改（如向电子邮件添加新部分或高级样式）必须通过HTML模式直接在电子邮件的源代码中完成。

有关将现有电子邮件转换为与Email Designer兼容的电子邮件的详细信息，请参阅 [本节](../../designing/using/using-existing-content.md).

**相关主题**：

* [创建电子邮件](../../channels/using/creating-an-email.md)
* [Email Designer简介视频](../../designing/using/designing-content-in-adobe-campaign.md#video)
* [从头开始设计电子邮件内容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## 转换HTML内容 {#converting-an-html-content}

如果要构建可组合成可在多个电子邮件中重复使用的模块化模板和片段的框架，应考虑将电子邮件HTML转换为Email Designer模板。

此用例提供了一种将HTML电子邮件转换为Email Designer组件的快速方法。

>[!CAUTION]
>
>本节适用于熟悉HTML代码的高级用户。

>[!NOTE]
>
>与兼容模式一样，HTML组件也可以使用有限的选项进行编辑：您只能执行就地编辑。

在Email Designer之外，确保将原始HTML划分为可重复使用的部分。

如果不是这种情况，请从您的HTML中切出各个块。 例如：

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

在识别了所有块后，在Email Designer中，对现有电子邮件的每个部分重复以下过程：

1. 打开Email Designer以创建空电子邮件内容。
1. 设置正文级别属性：背景颜色、宽度等。 有关更多信息，请参阅[编辑电子邮件样式](../../designing/using/styles.md)。
1. 添加结构组件。 有关更多信息，请参阅[编辑电子邮件结构](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 添加HTML组件。 有关更多信息，请参阅[添加片段和组件](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 将HTML复制并粘贴到该组件中。
1. 切换到移动视图。 有关更多信息，请参阅[此小节](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)。

   响应视图已损坏，因为您的CSS缺失。

1. 要解决此问题，请切换到源代码模式，并将样式部分复制粘贴到新的样式部分中。 例如：

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
   >请确保将样式添加到其他自定义样式标记中。
   >
   >请勿修改Email Designer生成的CSS：
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`

1. 返回移动设备视图以检查内容是否正确显示并保存更改。
