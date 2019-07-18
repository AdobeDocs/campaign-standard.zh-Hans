---
title: 编辑电子邮件样式
seo-title: 编辑电子邮件样式
description: 编辑电子邮件样式
seo-description: 借助可轻松访问的设置，通过电子邮件设计器快速编辑内容样式。
page-status-flag: 从未激活
uuid: 1fac228d-c02 c-410a-a4 bd-0c3 b163 ab5 f9
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 设计
content-type: reference
topic-tags: editing-email-content
discoiquuid: 09c66cd5-2bbf-4846-ac8 a-312ab5 c18473
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Editing email styles{#editing-email-styles}

## Editing an element {#editing-an-element}

In the Email Designer, when selecting an element, several options specific to the type of content selected are displayed in the **[!UICONTROL Settings]** pane. 您可以使用这些选项轻松更改电子邮件的样式。

### Selecting an element {#selecting-an-element}

要在电子邮件设计器界面中选择元素，您可以执行以下任一操作：

* 直接在电子邮件中点击，
* or browse the structure tree available from the options located in the left **Palette**.

![](assets/des_tree_structure.png)

浏览结构树可使您更准确地选择。您可以选择以下任一选项：

* 整个结构组件，
* 构成结构组件的列之一，
* 或仅限列内的组件。

![](assets/des_tree_structure_selection.png)

要选择列，您还可以执行以下操作：

1. Select a structure component (directly in the email or using the structure tree available from the left **Palette**).
1. From the **contextual toolbar**, click **[!UICONTROL Select a column]** to choose the desired column.

See an example in [this section](../../designing/using/editing-email-styles.md#example--adjusting-vertical-alignment-and-padding).

### Adjusting style settings {#adjusting-style-settings}

1. 在电子邮件中选择一个元素。For more on this, see [Selecting an element](../../designing/using/editing-email-styles.md#selecting-an-element).
1. 根据需要调整设置。每个选定的元素都提供一组不同的设置。

   You can insert backgrounds, change sizes, modify horizontal or vertical alignment, manage colors, add [padding or margin](../../designing/using/editing-email-styles.md#about-padding-and-margin), and so on.

   To do this, use the options displayed in the **[!UICONTROL Settings]** pane or [add inline styling attributes](../../designing/using/editing-email-styles.md#adding-inline-styling-attributes).

   ![](assets/des_settings_pane.png)

1. 保存内容。

### About padding and margin {#about-padding-and-margin}

通过电子邮件设计器界面，您可以快速调整边距和边距设置。

**[!UICONTROL Padding]**：此设置允许您管理元素边框内的空间。

![](assets/des_padding.png)

例如：

* 使用边距在图像的左侧和右侧设置边距。
* Use top and bottom padding to add more spacing to a **[!UICONTROL Text]** or a **[!UICONTROL Divider]** component.
* 要在结构元素内的列之间设置边框，请为每个列定义边距。

**[!UICONTROL Margin]**：此设置使您能够管理元素边框与下一元素之间的空间。

![](assets/des_margin.png)

>[!NOTE]
>
>根据您的选择(结构组件、列或内容组件)，结果将不相同。Adobe recommends setting the **[!UICONTROL Padding]** and **[!UICONTROL Margin]** parameters at the column level.

For both **[!UICONTROL Padding]** and **[!UICONTROL Margin]**, click the lock icon to break synchronization between top and bottom or right and left parameters. 这使您能够单独调整每个参数。

![](assets/des_padding_lock_icon.png)

### About alignment {#about-alignment}

* **文本对齐**：将鼠标光标放在一些文本上，并使用上下文工具栏将其对齐。

   ![](assets/des_text_alignment.png)

* **水平对齐** 可应用于文本、图像和按钮-当前不适用于 **[!UICONTROL Divider]** 和 **[!UICONTROL Social]** 组件。

   ![](assets/des_horizontal_alignment.png)

* To set **vertical alignment**, select a column inside a structure component and choose an option from the Settings pane.

   ![](assets/des_set_vertical_alignment.png)

### About backgrounds {#about-backgrounds}

在使用电子邮件设计器设置背景时，Adobe建议您执行以下操作：

1. 如果您的设计需要，请将背景颜色应用于电子邮件的正文。
1. 在大多数情况下，在列级别设置背景颜色。
1. 尽量避免在图像或文本组件上使用背景颜色，因为它们难以管理。

下面是可用的背景设置。

* Set a **[!UICONTROL Background color]** for the whole email. 确保在左侧面板中可访问可访问的导航树中的正文设置。

   ![](assets/des_background_body.png)

* Set the same background color for all structure components by selecting **[!UICONTROL Viewport background color]**. 此选项允许您从背景颜色中选择其他设置。

   ![](assets/des_background_viewport.png)

* 为每个结构组件设置不同的背景颜色。从左侧调色板中选择可访问的导航树中的结构，以仅对该结构应用特定背景颜色。

   ![](assets/des_background_structure.png)

   确保不设置视图端口背景颜色，因为它可能隐藏结构背景颜色。

* Set a **[!UICONTROL Background image]** for the content of a structure component.

   ![](assets/des_background_image.png)

   >[!NOTE]
   >
   >某些电子邮件程序不支持背景图像。请确保选择适当的回退背景颜色，以防图像无法显示。

* 在列级别设置背景颜色。

   ![](assets/des_background_column.png)

   >[!NOTE]
   >
   >这是最常用的用例。Adobe建议在列级别设置背景颜色，因为这使得编辑整个电子邮件内容时更灵活。

   您还可以在列级别设置背景图像，但很少使用此设置。

### Example: adjusting vertical alignment and padding {#example--adjusting-vertical-alignment-and-padding}

您希望在三列组成的结构组件内调整边距和垂直对齐。要执行此操作，请执行以下步骤：

1. Select the structure component directly in the email or using the structure tree available from the left **Palette**.
1. From the **contextual toolbar**, click **[!UICONTROL Select a column]** and choose the one that you want to edit. 您还可以从结构树中选择它。

   ![](assets/des_selecting_column.png)

   The editable parameters for that column are displayed in the **[!UICONTROL Settings]** pane on the right.

1. Under **[!UICONTROL Vertical alignment]**, select **[!UICONTROL Up]**.

   ![](assets/des_vertical_alignment.png)

   内容组件将显示在列顶部。

1. Under **[!UICONTROL Padding]**, define the top padding inside the column. 单击锁定图标以断开与底部边距的同步。

   为该列定义左右填充。

   ![](assets/des_adjusting_padding.png)

1. 进行类似操作，以调整其他列的对齐和边距。

   ![](assets/des_adjusting_columns.png)

1. 保存更改。

## Adding inline styling attributes {#adding-inline-styling-attributes}

在电子邮件设计器界面中，当您选择某个元素并在侧面板上显示其设置时，您可以自定义该特定元素的内联属性及其值。

1. 选择内容中的元素。
1. On the side panel, look for the **[!UICONTROL Styles Inline]** settings.

   ![](assets/email_designer_inlineattributes.png)

1. Modify the values of the existing attributes, or add new ones using the **+** button. 您可以添加任何与CSS兼容的属性和值。

然后，样式将应用于所选元素。如果子元素未定义特定的样式属性，则继承父级元素的样式。
