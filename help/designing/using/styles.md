---
title: 管理电子邮件样式
description: 了解如何在Email Designer中管理电子邮件样式。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 8daeb12d-4170-464f-ba33-afb681f72a91
source-git-commit: 5435e1dbfbe08399c488322320ac5bb8e681a79d
workflow-type: tm+mt
source-wordcount: '1038'
ht-degree: 26%

---

# 管理电子邮件样式 {#managing-styles}


在电子邮件Designer中，选择元素时，**[!UICONTROL Settings]**&#x200B;窗格中会显示多个特定于所选内容类型的选项。 您可以使用这些选项轻松更改电子邮件的样式。

## 选择元素 {#selecting-an-element}

要在电子邮件Designer界面中选择元素，您可以：

* 直接在电子邮件中单击，
* 或浏览位于左侧&#x200B;**调色板**&#x200B;中的选项中提供的结构树。

![](assets/des_tree_structure.png)

浏览结构树可让您进行更精确的选取。 您可以选择以下任一选项：

* 整个结构组件，
* 构成结构组件的其中一列，
* 或仅位于列中的组件。

![](assets/des_tree_structure_selection.png)

要选择列，还可以执行以下操作：

1. 选择结构组件（直接在电子邮件中或使用左侧&#x200B;**调色板**&#x200B;中提供的结构树）。
1. 从&#x200B;**上下文工具栏**&#x200B;中，单击&#x200B;**[!UICONTROL Select a column]**&#x200B;以选择所需的列。

在[此部分](#example--adjusting-vertical-alignment-and-padding)中查看示例。

## 调整样式设置 {#adjusting-style-settings}

1. 在电子邮件中选择元素。 有关详细信息，请参阅[选择元素](#selecting-an-element)。
1. 根据需要调整设置。 每个选定的元素均提供一组不同的设置。

   您可以插入背景、更改大小、修改水平或垂直对齐方式、管理颜色、添加[填充或边距](#selecting-an-element)等等。

   为此，请使用&#x200B;**[!UICONTROL Settings]**&#x200B;窗格中显示的选项或[添加内联样式属性](#adding-inline-styling-attributes)。

   ![](assets/des_settings_pane.png)

1. 保存您的内容。

## 调整边距和边距 {#about-padding-and-margin}

通过Email Designer界面，您可以快速调整填充和边距设置。

**[!UICONTROL Padding]**：此设置允许您管理位于元素边框内的空间。

![](assets/des_padding.png)

例如：

* 使用填充在图像的左右两侧设置边距。
* 使用顶部和底部内边距为&#x200B;**[!UICONTROL Text]**&#x200B;或&#x200B;**[!UICONTROL Divider]**&#x200B;组件添加更多间距。
* 要设置结构元素内各列之间的边框，请为每个列定义边距。

**[!UICONTROL Margin]**：此设置允许您管理元素的边框与下一个元素之间的间距。

![](assets/des_margin.png)

>[!NOTE]
>
>根据您的选择（结构组件、列或内容组件），结果将不同。 Adobe建议在列级别设置&#x200B;**[!UICONTROL Padding]**&#x200B;和&#x200B;**[!UICONTROL Margin]**&#x200B;参数。

对于&#x200B;**[!UICONTROL Padding]**&#x200B;和&#x200B;**[!UICONTROL Margin]**，单击锁定图标可中断上下或左右参数之间的同步。 这使您能够单独调整每个参数。

![](assets/des_padding_lock_icon.png)

## 样式对齐方式 {#about-alignment}

* **文本对齐方式**：将鼠标光标放在某些文本上，并使用上下文工具栏对其进行对齐。

  ![](assets/des_text_alignment.png)

* **水平对齐方式**&#x200B;可应用于文本、图像和按钮 — 当前不适用于&#x200B;**[!UICONTROL Divider]**&#x200B;和&#x200B;**[!UICONTROL Social]**&#x200B;组件。

  ![](assets/des_horizontal_alignment.png)

* 要设置&#x200B;**垂直对齐方式**，请在结构组件内选择一个列，然后从“设置”窗格中选择一个选项。

  ![](assets/des_set_vertical_alignment.png)

## 设置背景 {#about-backgrounds}

>[!CONTEXTUALHELP]
>id="ac_edition_backgroundimage"
>title="背景设置"
>abstract="电子邮件设计器可让您个性化设置内容的背景颜色或背景图像。请注意，并非所有电子邮件客户端都支持背景图像。"

在使用电子邮件设计器设置背景时，Adobe 有以下建议：

1. 如果设计需要，可对电子邮件正文应用背景颜色。
1. 在大多数情况下，在列级别设置背景颜色。
1. 尽量不要在图像或文本组件上使用背景颜色，因为它们难以管理。

以下是可使用的可用背景设置。

* 为整个电子邮件设置&#x200B;**[!UICONTROL Background color]**。 确保在可从左侧面板访问的导航树中选择正文设置。

  ![](assets/des_background_body.png)

* 通过选择&#x200B;**[!UICONTROL Viewport background color]**，为所有结构组件设置相同的背景颜色。 此选项可让您从背景颜色中选择其他设置。

  ![](assets/des_background_viewport.png)

* 为每个结构组件设置不同的背景颜色。在导航树中选择可从左侧面板访问的结构，以便仅对该结构应用特定的背景颜色。

  ![](assets/des_background_structure.png)

  切勿设置视口背景颜色，因为它可能会隐藏结构背景颜色。

* 为结构组件的内容设置&#x200B;**[!UICONTROL Background image]**。

  ![](assets/des_background_image.png)

  >[!NOTE]
  >
  >某些电子邮件程序不支持背景图像。当不支持时，将改用行背景颜色。 请务必选择合适的备用背景颜色，以防图像无法显示。

* 在列级别设置背景颜色。

  ![](assets/des_background_column.png)

  >[!NOTE]
  >
  >这是最常见的用例。Adobe 建议在列级别设置背景颜色，因为这可在编辑整个电子邮件内容时提供更大的灵活性。

  您也可以在列级别设置背景图像，但很少这样做。

### 示例：调整垂直对齐和填充 {#example--adjusting-vertical-alignment-and-padding}

要在由三列组成的结构组件内调整填充和垂直对齐。 为此请执行以下操作步骤：

1. 直接在电子邮件中或使用左侧&#x200B;**调色板**&#x200B;中提供的结构树选择结构组件。
1. 从&#x200B;**上下文工具栏**&#x200B;中，单击&#x200B;**[!UICONTROL Select a column]**&#x200B;并选择要编辑的内容。 也可以从结构树中选择它。

   ![](assets/des_selecting_column.png)

   该列的可编辑参数显示在右侧的&#x200B;**[!UICONTROL Settings]**&#x200B;窗格中。

1. 在&#x200B;**[!UICONTROL Vertical alignment]**&#x200B;下，选择&#x200B;**[!UICONTROL Up]**。

   ![](assets/des_vertical_alignment.png)

   内容组件显示在列顶部。

1. 在&#x200B;**[!UICONTROL Padding]**&#x200B;下，定义列中的顶部边距。 单击锁定图标可中断与底部填充的同步。

   为该列定义左右边距。

   ![](assets/des_adjusting_padding.png)

1. 以类似的方式继续调整其他列的对齐方式和内边距。

   ![](assets/des_adjusting_columns.png)

1. 保存您的更改。

## 样式链接 {#about-styling-links}

可以在电子邮件设计器中为链接添加下划线并选择其颜色和目标。

1. 在插入了链接的组件中，选择链接的标签文本。

1. 在组件设置中，选中&#x200B;**[!UICONTROL Underline link]**&#x200B;以将链接的标签文本加下划线。

   ![](assets/stylelinks-selecttext.png)

1. 要选择将在其中打开链接的浏览上下文，请选择&#x200B;**[!UICONTROL Target]**。

   ![](assets/stylelinks-target.png)

1. 要更改链接的颜色，请单击&#x200B;**[!UICONTROL Link color]**。

   ![](assets/stylelinks-colorpicker.png)

1. 选择您需要的颜色。

   ![](assets/stylelinks-colorchanged.png)

1. 保存您的更改。

## 添加内联样式属性 {#adding-inline-styling-attributes}

在Email Designer界面中，当您选择元素并在侧面板上显示其设置时，您可以自定义该特定元素的内联属性及其值。

1. 在内容中选择元素。
1. 在侧面板上，查找&#x200B;**[!UICONTROL Styles Inline]**&#x200B;设置。

   ![](assets/email_designer_inlineattributes.png)

1. 修改现有属性的值，或使用&#x200B;**+**&#x200B;按钮添加新属性。 可以添加任何符合 CSS 的属性和值。

然后，样式将应用于所选的元素。 如果子元素不具有定义的特定样式属性，则继承父元素的样式。
