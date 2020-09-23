---
title: 管理电子邮件样式
description: 了解如何在电子邮件设计器中管理电子邮件样式。
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 40199be7858dba4660a941fc6b960f20fac9f9e5
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 1%

---


# 管理电子邮件样式 {#managing-styles}


在电子邮件设计器中，选择元素时，窗格中将显示特定于所选内容类型的多个选 **[!UICONTROL Settings]** 项。 您可以使用这些选项轻松更改电子邮件的样式。

## 选择元素 {#selecting-an-element}

要在“电子邮件设计器”界面中选择元素，您可以：

* 直接在电子邮件中单击，
* 或浏览左侧调色板中的选项提供的结构 **树**。

![](assets/des_tree_structure.png)

通过浏览结构树，可以进行更准确的选择。 您可以选择：

* 整个结构，
* 组成结构组件的列之一，
* 或仅列内的组件。

![](assets/des_tree_structure_selection.png)

要选择列，还可以执行以下操作：

1. 选择一个结构组件(直接在电子邮件中或使用左侧调色板中提供的结构 **树**)。
1. 在上下文 **工具栏**，单击 **[!UICONTROL Select a column]** 以选择所需的列。

请参阅此部 [分的示例](#example--adjusting-vertical-alignment-and-padding)。

## 调整样式设置 {#adjusting-style-settings}

1. 在电子邮件中选择元素。 For more on this, see [Selecting an element](#selecting-an-element).
1. 根据您的需要调整设置。 每个选定的元素优惠一组不同的设置。

   您可以插入背景、更改大小、修改水平或垂直对齐方式、管理颜色 [、添加边距](#selecting-an-element)或边距等。

   为此，请使用窗格中显示的选项或 **[!UICONTROL Settings]** 添加内 [联样式属性](#adding-inline-styling-attributes)。

   ![](assets/des_settings_pane.png)

1. 保存您的内容。

## 调整边距和边距 {#about-padding-and-margin}

通过电子邮件设计器界面，您可以快速调整边距和边距设置。

**[!UICONTROL Padding]**:此设置允许您管理位于元素边框内的空间。

![](assets/des_padding.png)

例如：

* 使用边距在图像的左侧和右侧设置边距。
* 使用顶部和底部填充为组件添加更 **[!UICONTROL Text]** 多间 **[!UICONTROL Divider]** 距。
* 要设置结构元素内各列之间的边框，请为每列定义填充。

**[!UICONTROL Margin]**:此设置允许您管理元素边框与下一个元素之间的空间。

![](assets/des_margin.png)

>[!NOTE]
>
>根据您的选择（结构组件、列或内容组件），结果将不相同。 Adobe建议在 **[!UICONTROL Padding]** 列级 **[!UICONTROL Margin]** 别设置和参数。

对于和 **[!UICONTROL Padding]** , **[!UICONTROL Margin]**&#x200B;单击锁图标可中断顶部和底部参数或右和左参数之间的同步。 这使您能够单独调整每个参数。

![](assets/des_padding_lock_icon.png)

## 样式对齐 {#about-alignment}

* **文本对齐**:将鼠标光标放在某些文本上，然后使用上下文工具栏对齐它。

   ![](assets/des_text_alignment.png)

* **水平对齐** 可应用于文本、图像和按钮——当前不适用于文本和 **[!UICONTROL Divider]** 组件 **[!UICONTROL Social]** 。

   ![](assets/des_horizontal_alignment.png)

* 要设置 **垂直对齐**，请在结构组件内选择一列，然后从“设置”窗格中选择一个选项。

   ![](assets/des_set_vertical_alignment.png)

## 设置背景 {#about-backgrounds}

>[!CONTEXTUALHELP]
>id="ac_edition_backgroundimage"
>title="背景设置"
>abstract="通过电子邮件设计器，您可以个性化内容的背景颜色或背景图像。请注意，并非所有电子邮件客户都支持背景图像。"
>additional-url="https://docs.google.com/spreadsheets/d/1TLo62YKm3tThUWDOIliCQFWs3dpNjpDfw6DdTr1oGOw/edit#gid=0" text="其他信息"

在设置电子邮件设计器的背景时，Adobe建议：

1. 根据您的设计需要，将背景色应用于电子邮件正文。
1. 在大多数情况下，在列级别设置背景颜色。
1. 由于图像或文本组件难以管理，请尽量不要在它们上使用背景颜色。

下面是您可以使用的可用背景设置。

* 为整个 **[!UICONTROL Background color]** 电子邮件设置一个。 确保在可从左侧面板访问的导航树中选择正文设置。

   ![](assets/des_background_body.png)

* 通过选择，为所有结构组件设置相同的背景颜 **[!UICONTROL Viewport background color]**&#x200B;色。 此选项允许您从背景颜色中选择其他设置。

   ![](assets/des_background_viewport.png)

* 为每个结构组件设置不同的背景颜色。 在可从左侧调色板访问的导航树中选择一个结构，以仅将特定背景颜色应用于该结构。

   ![](assets/des_background_structure.png)

   请确保未设置视区背景颜色，因为它可能隐藏结构背景颜色。

* 为结 **[!UICONTROL Background image]** 构组件的内容设置。

   ![](assets/des_background_image.png)

   >[!NOTE]
   >
   >某些电子邮件项目不支持背景图像。 不支持时，将改用行背景颜色。 确保在无法显示图像时选择适当的回退背景颜色。

* 在列级设置背景颜色。

   ![](assets/des_background_column.png)

   >[!NOTE]
   >
   >这是最常见的用例。 Adobe建议在列级设置背景颜色，因为这样在编辑整个电子邮件内容时可以更灵活。

   您还可以在列级别设置背景图像，但很少使用此图像。

### 示例：调整垂直对齐和填充 {#example--adjusting-vertical-alignment-and-padding}

要调整由三列组成的结构组件中的填充和垂直对齐方式。 为此请执行以下操作步骤：

1. 直接在电子邮件中或使用左侧调色板中提供的结构树选择结构 **组件**。
1. 在上 **下文工具栏**，单 **[!UICONTROL Select a column]** 击并选择要编辑的工具栏。 也可以从结构树中选择它。

   ![](assets/des_selecting_column.png)

   该列的可编辑参数显示在右 **[!UICONTROL Settings]** 侧的窗格中。

1. 在下 **[!UICONTROL Vertical alignment]**&#x200B;面，选 **[!UICONTROL Up]**&#x200B;择。

   ![](assets/des_vertical_alignment.png)

   内容组件显示在列的顶部。

1. 在 **[!UICONTROL Padding]**&#x200B;下，定义列内的顶部边距。 单击锁图标以中断与底部边距的同步。

   定义该列的左边距和右边距。

   ![](assets/des_adjusting_padding.png)

1. 以类似方式继续调整其他列的对齐和填充。

   ![](assets/des_adjusting_columns.png)

1. 保存更改。

## 样式链接 {#about-styling-links}

您可以为链接添加下划线，并在电子邮件设计器中选择其颜色和目标。

1. 在插入链接的组件中，选择链接的标签文本。

1. 在组件设置中，选 **[!UICONTROL Underline link]** 中以下划线标记链接的文本。

   ![](assets/stylelinks-selecttext.png)

1. 要选择将在其中打开您的链接的浏览上下文，请选择 **[!UICONTROL Target]**。

   ![](assets/stylelinks-target.png)

1. 要更改链接的颜色，请单击 **[!UICONTROL Link color]**。

   ![](assets/stylelinks-colorpicker.png)

1. 选择所需颜色。

   ![](assets/stylelinks-colorchanged.png)

1. 保存更改。

## 添加内联样式属性 {#adding-inline-styling-attributes}

在“电子邮件设计器”界面中，选择某个元素并在侧面板中显示其设置时，您可以自定义该特定元素的内联属性及其值。

1. 在内容中选择元素。
1. 在侧面板上，查找设 **[!UICONTROL Styles Inline]** 置。

   ![](assets/email_designer_inlineattributes.png)

1. 修改现有属性的值，或使用+按钮添加新 **属** 性。 您可以添加任何符合CSS的属性和值。

样式随后将应用于所选元素。 如果子元素未定义特定样式属性，则继承父元素的样式。
