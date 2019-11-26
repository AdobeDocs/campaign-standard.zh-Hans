---
title: 设计登陆页面
description: 了解如何设计登陆页面的内容。
page-status-flag: never-activated
uuid: de6fe190-835c-40fd-8101-a809b430b423
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: bd77d6f0-3143-4030-a91b-988a2bebc534
context-tags: landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf

---


# 设计登陆页面{#designing-a-landing-page}

## 关于登陆页面内容设计内容设计 {#about-content-design}

登录页面以任何营销活动 [的形式创建](../../start/using/marketing-activities.md#about-marketing-activities)。

设计登陆页面时，您需要定义页面本身的内容、确认页面和错误页面。 使用操作栏下的切换器显示和配置每个页面。

登陆页面的内容通过Campaign内容编辑器进行设计。

>[!NOTE]
>
>如果您的实例是在Adobe Campaign Standard 19.0版本之前安装的，您仍可以访问旧版电子邮件内容编辑器。 界面、使用原则和配置基本上与登录页面的下面所述相同。 但是，在旧版电子邮件内容编辑器中可能不提供或维护所有功能，该编辑器从19.0版本开始已弃用。 要通过具有扩展功能的拖放界面快速编辑电子邮件内容，请使用电子邮 [件设计器](../../designing/using/overview.md)。

本页介绍了登陆页面内容编辑器的特性。 有关一个或多个营销活动常见的操作的详细信息，请参阅设计电子邮件内容指 **南中的这些部分** :

* [插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)
* [添加内容块](../../designing/using/personalization.md#adding-a-content-block)。
* [插入链接](../../designing/using/links.md#inserting-a-link)。
* [插入图像](../../designing/using/images.md)。
* [内容设计的一般最佳实践](../../designing/using/overview.md#content-design-best-practices)。

>[!NOTE]
>如果您有已预定义为HTML格式的登录页面，则可以使用按钮直接导入该 **[!UICONTROL Change content]** 页面。
>
>在Adobe Campaign中导入HTML页面之前，请确保在各种浏览器中正确打开和显示该页面。 如果HTML页包含JavaScript脚本，则需要在编辑器外执行这些脚本时不会出错。 通常，请避免在邮件内容中使用脚本，以确保电子邮件客户端正确处理该脚本。

## 登陆页面内容编辑器界面{#landing-page-content-editor-interface}

登陆页面内容编辑器使您能够轻松定义、修改和个性化Adobe Campaign中的内容。 要访问它，请单击登 **[!UICONTROL Content]** 录页面功能板中的块。

内容编辑器分为三个不同的部分。 这些部分允许您查看和编辑内容。

![](assets/des_lp_content_8.png)

1. 屏 **幕左侧的** “调色板”允许您修改链接到选定块的常规选项。 可修改的选项包括：背景颜色、边框、文本对齐、可见性条件等。 请参 [阅插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)。
1. 操 **作栏包含** 页面的常规选项。 您可以选择模板并更改显示模式。
1. 在主编 **辑区域** ，您可以使用上下文工具栏直接与内容交互：在图像中插入链接、更改字体、删除字段等。

操 **作栏包含** 不同的按钮，可让您与创建的内容进行交互。

![](assets/des_lp_content_9.png)

<table> 
 <thead> 
  <tr> 
   <th> 图标<br /> </th> 
   <th> 按钮名称<br /> </th> 
   <th> 渠道<br /> </th> 
   <th> 说明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <img height="21px" src="assets/download_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">更改内容</span><br /> </td> 
   <td> 登录页面和电子邮件<br /> </td> 
   <td> 允许您选择现成内容或导入您自己的HTML内容。 请参阅 <a href="../../designing/using/using-existing-content.md">加载现有内容</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/undo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">撤消</span><br /> </td> 
   <td> 全部<br /> </td> 
   <td> 取消执行的上一个操作。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/redo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">重做</span><br /> </td> 
   <td> 全部<br /> </td> 
   <td> 重新执行上次取消的操作。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/display_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">显示块</span><br /> </td> 
   <td> 登录页面和电子邮件<br /> </td> 
   <td> 允许您显示内容块周围的框(与 <strong>&lt;div&gt;</strong> HTML标记相对应)。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/code_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">显示源</span><br /> </td> 
   <td> 登录页面和电子邮件<br /> </td> 
   <td> 允许您显示页面的HTML源代码。<br /> </td> 
  </tr> 
 </tbody> 
</table>

工 **具栏** 是编辑器界面的上下文元素，它根据所选区域提供各种功能。 它包含允许您更改文本样式的操作按钮和按钮。 执行的修改始终适用于所选区域。 选择块后，可删除或复制它。 在选择块内的文本后，可将其转换为链接或变为粗体。

![](assets/delivery_content_17.png)

>[!CAUTION]
>
>某些工具栏功能允许您设置HTML内容的格式。 但是，如果页面包含CSS样式表，则样式表中的 **说明** ，可能会被证明优先于通过工具栏 **指定的说明** 。

<table> 
 <thead> 
  <tr> 
   <th> 图标<br /> </th> 
   <th> 按钮名称<br /> </th> 
   <th> 上下文<br /> </th> 
   <th> 说明<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <img height="21px" src="assets/link_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">链接到外部URL</span><br /> </td> 
   <td> 任何元素<br /> </td> 
   <td> 允许您添加指向URL的链接。 有关如何配置链接的详细信息，请参阅插入 <a href="../../designing/using/links.md#inserting-a-link">链接部分</a> 。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkpage_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">登录页面链接</span><br /> </td> 
   <td> 任何元素<br /> </td> 
   <td> 允许访问Adobe Campaign登录页面。 有关如何配置链接的详细信息，请参阅插入 <a href="../../designing/using/links.md#inserting-a-link">链接部分</a> 。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_subscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">订阅链接</span><br /> </td> 
   <td> 任何元素<br /> </td> 
   <td> 允许您插入服务订阅链接。 有关如何配置链接的详细信息，请参阅插入 <a href="../../designing/using/links.md#inserting-a-link">链接部分</a> 。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_unsubscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">取消订阅链接</span><br /> </td> 
   <td> 任何元素<br /> </td> 
   <td> 允许您插入服务取消订阅链接。 有关如何配置链接的详细信息，请参阅插入 <a href="../../designing/using/links.md#inserting-a-link">链接部分</a> 。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkoff_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">删除链接</span><br /> </td> 
   <td> 链接<br /> </td> 
   <td> 允许您在确认后删除链接以及链接到该链接的所有配置。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_field_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">插入个性化字段</span><br /> </td> 
   <td> 文本元素<br /> </td> 
   <td> 允许您从数据库向内容添加字段。 请参阅 <a href="../../designing/using/personalization.md#inserting-a-personalization-field">插入个性化字段</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">插入内容块</span><br /> </td> 
   <td> 文本元素<br /> </td> 
   <td> 允许您向内容添加个性化区块。 请参阅 <a href="../../designing/using/personalization.md#adding-a-content-block">添加内容块</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontent_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">启用动态内容</span><br /> </td> 
   <td> 文本元素<br /> </td> 
   <td> 允许您在内容中插入动态内容。 请参阅定 <a href="../../channels/using/designing-a-landing-page.md#defining-dynamic-content-in-a-landing-page">义动态内容</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontentdisable_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">禁用动态内容</span><br /> </td> 
   <td> 文本元素<br /> </td> 
   <td> 允许您删除动态内容。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/increase_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">放大字体</span><br /> </td> 
   <td> 文本元素<br /> </td> 
   <td> 增加所选文本的大小(添 <strong>加&lt;span style="font-size:"&gt;</strong>)。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/decrease_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">减少字体</span><br /> </td> 
   <td> 文本元素<br /> </td> 
   <td> 减小所选文本的大小(添 <strong>加&lt;span style="font-size:"&gt;</strong>)。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textbold_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">粗体</span><br /> </td> 
   <td> 文本元素<br /> </td> 
   <td> 将粗体样式添加到选定文本(用 <strong>&lt;strong&gt;</strong><strong>&lt;/strong&gt;标签换行</strong> )。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textitalic_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">斜体</span><br /> </td> 
   <td> 文本元素<br /> </td> 
   <td> 将斜体样式添加到选定文本(用 <strong>&lt;em&gt;</strong><strong>&lt;/em&gt;标记换行</strong> )。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textunderline_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">下划线</span><br /> </td> 
   <td> 文本元素<br /> </td> 
   <td> 为选定文本加下划线(用 <strong>&lt;span style="text-decoration:下划线；"&gt;</strong> 标签)。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/colorselector_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">更改背景颜色</span><br /> </td> 
   <td> 文本元素<br /> </td> 
   <td> 允许您更改所选块的背景颜色(添加style="background-color:rgba(170, 86, 255, 0.87))。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textcolor_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">更改字体颜色</span><br /> </td> 
   <td> 文本元素<br /> </td> 
   <td> 允许您更改块中所有文本的颜色或仅更改块中选定文本的颜色(<strong>&lt;span style="color:#56ff56;"&gt;</strong>)。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/image_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">图像</span><br /> </td> 
   <td> 包含图像的块<br /> </td> 
   <td> 允许您从本地保存的文件插入图像。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/delete_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">删除</span><br /> </td> 
   <td> 任意块<br /> </td> 
   <td> 删除块及其内容。<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/duplicate_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">复制</span><br /> </td> 
   <td> 任意块<br /> </td> 
   <td> 复制块，包括与其链接的任何样式。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 管理登陆页面结构和样式{#managing-landing-page-structure-and-style}

### 在内容编辑器中管理块 {#managing-blocks-in-the-content-editor}

不同的HTML内容元素在登录页面中显示为块，与 **&lt;div&gt;****&lt;/div&gt;标签相对应** 。 选择要与其交互的块。 然后，它将被一个蓝色的盒子包围。

![](assets/des_lp_content_1.png)

如果选择了块，则相应HTML元素的父对象将显示在编辑区域底部的痕迹导航中。

当鼠标悬停在某个痕迹导航元素上时，将高亮显示相关元素。 因此，您可以在不同的块之间轻松导航，并准确选择要修改的HTML元素。

![](assets/des_lp_content_2.png)

使用调色板和上下文工具栏中的选项来修改、删除或复制块。

对于包含文本的块，在块中再次单击以启用文本编辑模式。 块周围的框变为绿色。 然后，您可以选择或输入文本。 使用调色板和上下文工具栏中的选项添加链接或修改文本格式。

![](assets/des_lp_content_3.png)

为块中的元素（链接、个性化字段、内容块等）定义的参数可以随时从调色板中修改。

![](assets/des_lp_content_4.png)

### 在内容编辑器中添加边框和背景 {#adding-a-border-and-a-background-in-the-content-editor}

您还可以通过从图 **表中选择颜色** ，来定义背景颜色。 此颜色将应用于所选块。

![](assets/des_lp_content_5.png)

您可以向选 **定块** 添加边框。

![](assets/des_lp_content_6.png)

### 在内容编辑器中更改文本样式 {#changing-the-text-style-in-the-content-editor}

要更改文本的样式，您必须在文本块内单击。

要更改文本对齐方式，请在左侧的调色板中选择以下三个图标之一：

![](assets/des_lp_content_7.png)

* **左对齐**:将文本与选定块的左侧对齐(添加style="text-align:左；”)。
* **中心**:将所选块中的文本居中(添加style="text-align:中心；”)。
* **右对齐**:将文本与选定块的右侧对齐(添加style="text-align:对；”)。

您还可以使用工具栏更改字体属性：调整字体大小，使文本变为粗体或斜体，为文本添加下划线或更改其颜色。 Refer to [this section](../../channels/using/designing-a-landing-page.md#landing-page-content-editor-interface).

### 在登录页面中插入图像 {#inserting-images-in-a-landing-page}

1. 在登陆页面内容中，选择包含图像的块。
1. 选择按 **[!UICONTROL Insert]** 钮。

   ![](assets/des_insert_images_lp_1.png)

1. 从上 **[!UICONTROL Local image]** 下文工具栏中进行选择。

   ![](assets/des_insert_images_lp_2.png)

1. 选择文件。

   ![](assets/des_insert_images_lp_3.png)

1. 根据需要调整图像属性。

   ![](assets/des_insert_images_lp_4.png)

## 在登陆页面中定义动态内容{#defining-dynamic-content-in-a-landing-page}

要在登陆页面中定义动态内容，请使用痕迹导航或直接单击元素来选择块。

![](assets/dynamic_content_lp_1.png)

某些块（如图像）无法直接选择。 在这种情况下，请使用痕迹导航选择父块。 然后，您可以修改此父元素中包含的所有元素，包括图像。 该条件将应用于父块中的所有子元素。

痕迹导航显示在“管理块 [”部分](../../channels/using/designing-a-landing-page.md#managing-landing-page-structure-and-style) 。

在登录页面中定义动态内容的后续步骤与电子邮件的后续步骤类似。 请参 [阅此部分](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。

>[!NOTE]
>
>如果变体元素以红色列出，则表示尚未定义表达式。

您可以在块的不同动态内容之间导航。 操作步骤：

1. 选择块。

   箭头显示在图像的右侧和左侧。

1. 单击右箭头浏览可用的动态内容。

   ![](assets/dynamic_content_lp_2.png)

   每侧的箭头会根据您是否已到达最后一个或第一个可用的动态内容而变暗。

   ![](assets/dynamic_content_lp_3.png)

1. 要删除应用于某个块的所有条件，请选择该块，然后单击该 **[!UICONTROL Disable dynamic content]** 图标。
1. 选择要保留的动态内容。

   ![](assets/dynamic_content_lp_5.png)

在调色板中：

* 输入了表达式的内容不再以红色列出，而是以灰色显示。
* 当前选择的内容以蓝色显示。

![](assets/dynamic_content_lp_4.png)
