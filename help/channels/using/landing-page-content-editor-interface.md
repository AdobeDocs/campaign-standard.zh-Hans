---
title: 登陆页面内容编辑器界面
seo-title: 登陆页面内容编辑器界面
description: 登陆页面内容编辑器界面
seo-description: 了解如何使用编辑器的不同部分（如操作栏）来修改登录页面内容。
page-status-flag: 从未激活
uuid: 53729a68-eed2-4c5d-bc14-02c80e897c44
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 设计
content-type: 参考
topic-tags: 编辑——登陆——页面内容
discoiquuid: 08e2bbda-e409-467f-b462-d74256dc6ebc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68d96b23f34f505c0a47a74a5e33bc3530fc4d72

---


# 登陆页面内容编辑器界面{#landing-page-content-editor-interface}

登陆页面内容编辑器使您能够轻松定义、修改和个性化Adobe Campaign中的内容。 要访问它，请单击登 **[!UICONTROL Content]** 录页面功能板中的块。

内容编辑器分为三个不同的部分。 这些部分允许您查看和编辑内容。

![](assets/des_lp_content_8.png)

1. 屏 **幕左侧的** “调色板”允许您修改链接到所选块的常规选项。 可修改的选项包括：背景颜色、边框、文本对齐、可见性条件等。 请参 [阅插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)。
1. 操 **作栏包含** 页面的常规选项。 您可以选择模板并更改显示模式。 请参 [阅登陆页面编辑器操作栏](../../channels/using/landing-page-content-editor-interface.md#landing-page-editor-action-bar)。
1. 在主编 **辑区域** ，您可以使用上下文工具栏直接与内容交互：在图像中插入链接、更改字体、删除字段等。 请参阅 [登陆页面编辑器工具栏](../../channels/using/landing-page-content-editor-interface.md#landing-page-editor-toolbar)。

## 登录页面编辑器操作栏 {#landing-page-editor-action-bar}

操作栏包含不同的按钮，通过这些按钮可以与创建的内容交互。

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

## 登陆页面编辑器工具栏 {#landing-page-editor-toolbar}

工具栏是编辑 **器界面的上下文元素** ，根据所选区域提供各种功能。 它包含允许您更改文本样式的操作按钮和按钮。 执行的修改始终适用于所选区域。 选择块后，可删除或复制它。 在选择块内的文本后，可将其转换为链接或变为粗体。

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
   <td> 允许您在内容中插入动态内容。 请参阅定 <a href="../../channels/using/defining-dynamic-content-in-a-landing-page.md">义动态内容</a>。<br /> </td> 
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

