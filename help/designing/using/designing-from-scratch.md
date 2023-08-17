---
title: 从头开始设计电子邮件
description: 了解如何在Email Designer中从头开始设计电子邮件内容。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Beginner
exl-id: 052d24b7-d3e0-41d7-8b2c-92bd3addb3a2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1239'
ht-degree: 23%

---

# 从头开始设计电子邮件 {#designing-an-email-content-from-scratch}

了解如何掌握电子邮件内容版本。 使用Email Designer，您可以创建包含或不包含您自己的预定义内容的电子邮件和模板。

以下是使用Email Designer从头开始创建和设计电子邮件内容的主要步骤：

1. 创建电子邮件并打开其内容。
1. 添加结构组件以塑造电子邮件的形状。 请参阅 [编辑电子邮件结构](#defining-the-email-structure).
1. 在结构组件中插入内容组件和片段。 请参阅 [添加片段和内容组件](#defining-the-email-structure).
1. 添加图像并编辑电子邮件的文本。 请参阅 [插入图像](../../designing/using/images.md#inserting-images).
1. 通过添加个性化字段、链接等个性化内容，使电子邮件个性化。 请参阅 [插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)， [插入链接](../../designing/using/links.md#inserting-a-link) 和 [定义电子邮件中的动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).
1. 定义电子邮件的主题行。 请参阅 [个性化电子邮件的主题行](../../designing/using/subject-line.md#defining-the-subject-line-of-an-email).
1. 预览电子邮件.
1. 保存您的内容，然后在确保已定义受众并正确计划发送后继续发送消息。

您也可以查看此 [简介视频](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true).

>[!NOTE]
>
>要避免从头开始设计电子邮件内容，您可以使用现成的内容模板。 有关此内容的更多信息，请参阅 [内容模板](../../designing/using/using-reusable-content.md#content-templates).

## 定义电子邮件结构 {#defining-the-email-structure}

>[!CONTEXTUALHELP]
>id="ac_structure_components"
>title="关于结构组件"
>abstract="结构组件定义电子邮件的版面。"

>[!CONTEXTUALHELP]
>id="ac_edition_columns"
>title="定义电子邮件列"
>abstract="使用电子邮件设计器，您可以通过定义列结构来轻松定义电子邮件的版面。"

使用电子邮件设计器，您可以轻松定义电子邮件的结构。通过简单的拖放操作添加和移动结构元素，您可以在几秒钟内设计电子邮件的形状。

要编辑电子邮件的结构，请执行以下操作：

1. 打开现有内容或创建新电子邮件内容。
1. 访问 **[!UICONTROL Structure components]** 通过选择 **+** 图标。

   ![](assets/email_designer_structure.png)

1. 拖放塑造电子邮件所需的结构组件。

   ![](assets/email_designer_structure_components.png)

   在放置结构组件之前，蓝线表示该组件的确切位置。 您可以将其放在任何其他组件之上或之下，但不得放在内部。

   >[!NOTE]
   >
   >请注意，并非所有电子邮件程序都与列堆叠兼容。当不支持时，将不堆叠列。
   >
   >放入电子邮件后，除非内部已放置内容组件或片段，否则无法移动或删除组件。

1. 由一个或多个列组成的多个结构组件是可用的。

   选择 **[!UICONTROL n:n column]** 用于定义所选列数（介于3和10之间）的组件。 还可以通过移动每个列底部的箭头来定义该列的宽度。

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >每个列的大小不能小于结构组件的总宽度的 10%。不能删除非空列。

定义结构后，您便能够将内容片段和组件添加到电子邮件。

## 使用邮件引文 {#preheader}

>[!CONTEXTUALHELP]
>id="ac_edition_preheader"
>title="使用邮件引文"
>abstract="邮件引文可让您配置一个简短的摘要文本，该文本可帮助提高电子邮件的打开率。"

预告文本是简短摘要文本，从收件箱中查看电子邮件时位于主题行之后。 预标头可提供更高的打开率。

选择 **[!UICONTROL Preheader]** 编辑框并完成内容。

![](assets/email_designer_preheader.png)

您可以添加 **[!UICONTROL Content block]**， a **[!UICONTROL Dynamic content]** 或 **[!UICONTROL Personalization fields]** 在预编译标头内容中。

>[!NOTE]
>
>请注意，并非所有电子邮件程序都与邮件引文兼容。当不支持时，将不显示邮件引文。

## 使用内容组件 {#about-content-components}

>[!CONTEXTUALHELP]
>id="ac_content_components"
>title="关于内容组件"
>abstract="内容组件是空的内容占位符，可以编辑它以创建电子邮件。"

内容组件是一旦放入电子邮件中即可编辑的原始空组件。

可以在结构组件中添加所需数量的内容组件。 还可将它们移动到结构组件内部或移动到另一个结构组件。

以下是Email Designer中可用的组件列表：

### **[!UICONTROL Button]**

如果您需要使用多个按钮，而不是从头开始编辑每个按钮，则可以复制 **[!UICONTROL Button]** 组件时所使用的工具栏。

您还可以将按钮保存到可重用的片段中。 有关此内容的更多信息，请参阅 [创建内容片段](../../designing/using/using-reusable-content.md#creating-a-content-fragment) 和 [将内容另存为片段](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).

选择 **[!UICONTROL Fallback view]** 以在Email Designer中显示替代图像。

### **[!UICONTROL Text]**

使用此组件可在电子邮件中插入文本。 您可以调整文本颜色、样式和大小，方法是 **[!UICONTROL Component Settings]**.

### **[!UICONTROL Divider]**

使用此组件可在电子邮件中插入分隔线。 可以在以下位置选择换行线的颜色、样式和大小： **[!UICONTROL Component Settings]**.

### **[!UICONTROL HTML]**

使用此组件可复制并粘贴现有HTML的各个部分。 这使您能够创建免费的模块化HTML组件。

>[!NOTE]
>
>可用的HTML组件可进行编辑，但可用的选项有限。 如果所有样式都未内联，请确保在 **head** HTML部分，否则，电子邮件将不会响应。 使用 **[!UICONTROL Preview]** 按钮来测试内容的响应性(请参阅 [预览消息](../../sending/using/previewing-messages.md))。

为了仅使外部内容与Email Designer兼容，Adobe建议从头开始创建消息，并将内容从现有电子邮件复制到片段和组件中。

当您有无法重新创建的内容时，可以使用从原始电子邮件复制并粘贴HTML代码 **[!UICONTROL Html]** 内容组件。 在继续之前，请确保您熟悉HTML。

>[!NOTE]
>
>新内容不会与原始电子邮件完全相同，但以下步骤将指导您创建尽可能接近的邮件。

**在复制内容之前**

1. 在原始电子邮件中，确定各个部分的可重用部分，这些部分对于您将发送的每封电子邮件都是唯一的。
1. 保存您要使用的所有图像和资产。
1. 如果您熟悉HTML，请将原始HTML内容拆分为多个部分。

### 视频 {#video-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_video"
>title="视频设置"
>abstract="使用此组件可在电子邮件中插入视频。请注意，视频不适用于所有电子邮件客户端。我们建议设置后备图像。"
>additional-url="https://www.emailonacid.com/blog/article/email-development/a_how_to_guide_to_embedding_html5_video_in_email/" text="附加信息"

将视频组件插入电子邮件的结构组件中，然后在中输入视频链接 **[!UICONTROL Component Settings]**.

>[!NOTE]
>
>请注意，并非所有电子邮件程序都与视频兼容。当不支持时，将显示回退。

### 图像

使用此组件可在电子邮件中插入图像。

将图像组件插入到结构组件中，然后单击“浏览”以从计算机上传图像文件。

### **[!UICONTROL Social]**

使用此组件可在电子邮件中插入指向社交媒体页面的链接。 您可以选择要在其中显示的链接及其图标的大小 **[!UICONTROL Component Settings]**.

### 轮播 {#carousel-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_carousel"
>title="轮播设置"
>abstract="了解如何在内容中插入和配置轮播。请注意，轮播不适用于所有电子邮件客户端，如果不支持轮播，则会显示后备图像。"

1. 拖放 **[!UICONTROL Carousel]** 结构组件内的组件。
1. 浏览以从您的计算机中选择图像。

   ![](assets/des_carousel_browse.png)

1. 从 **[!UICONTROL Settings]** 窗格，设置要在轮播中显示的缩略图数量。
1. 从您的计算机中选择一个备用映像。

   ![](assets/des_carousel_fallback.png)

轮盘组件并非与所有电子邮件程序兼容。 当电子邮件不支持轮播时，请上传回退以显示图像。

>[!NOTE]
>
>轮播组件与以下电子邮件平台兼容：Apple Mail 7、Apple Mail 8、Outlook 2011 for Mac、Outlook 2016 for Mac、Mozilla Thunderbird、iPad和iPad mini iOS、iPhone iOS、Android、AOL （Chrome、Firefox和Safari）。

**相关主题**：

- [创建电子邮件](../../channels/using/creating-an-email.md)
- [选择消息的受众](../../audiences/using/selecting-an-audience-in-a-message.md)
- [计划消息发送](../../sending/using/about-scheduling-messages.md)
- [预览消息](../../sending/using/previewing-messages.md)
- [电子邮件渲染](../../sending/using/email-rendering.md)
