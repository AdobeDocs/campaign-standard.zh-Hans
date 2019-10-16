---
title: 管理样式
seo-title: 管理样式
description: 管理样式
seo-description: 了解如何在电子邮件设计器中管理电子邮件样式。
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
source-git-commit: 45916918fc9e8008d4eb583a9c92886672c04b71

---


# 管理样式 {#managing-styles}

## 编辑电子邮件样式{#editing-email-styles}

### 编辑元素 {#editing-an-element}

在电子邮件设计器中，选择元素时，窗格中将显示特定于所选内容类型的多个选 **[!UICONTROL Settings]** 项。 您可以使用这些选项轻松更改电子邮件的样式。

### 选择元素 {#selecting-an-element}

要在“电子邮件设计器”界面中选择元素，您可以：

* 直接在电子邮件中单击，
* 或浏览左侧“调色板”( **Palette)选项中可用的结构树**。

![](assets/des_tree_structure.png)

通过浏览结构树，您可以做出更准确的选择。 您可以选择以下任一选项：

* 整个结构，
* 组成结构组件的列之一，
* 或者仅包含位于列内的组件。

![](assets/des_tree_structure_selection.png)

要选择列，还可以执行以下操作：

1. 选择一个结构组件(直接在电子邮件中或使用左侧调色板中提供的结构 **树**)。
1. 在上下文 **工具栏中**，单 **[!UICONTROL Select a column]** 击以选择所需的列。

请参阅此部分 [的示例](../../designing/using/styles.md#example--adjusting-vertical-alignment-and-padding)。

### 调整样式设置 {#adjusting-style-settings}

1. 在电子邮件中选择元素。 有关此内容的详细信息，请参 [阅选择元素](../../designing/using/styles.md#selecting-an-element)。
1. 根据您的需要调整设置。 每个选定的元素提供一组不同的设置。

   您可以插入背景、更改大小、修改水平或垂直对齐方式、管理颜色、 [添加填充](../../designing/using/styles.md#selecting-an-element)或边距等。

   为此，请使用窗格中显示的选项或 **[!UICONTROL Settings]** 添加内 [联样式属性](../../designing/using/styles.md#adding-inline-styling-attributes)。

   ![](assets/des_settings_pane.png)

1. 保存您的内容。

### 关于填充和边距 {#about-padding-and-margin}

通过电子邮件设计器界面，您可以快速调整填充和边距设置。

**[!UICONTROL Padding]**:此设置允许您管理位于元素边框内的空间。

![](assets/des_padding.png)

例如：

* 使用填充在图像的左侧和右侧设置边距。
* 使用顶部和底部填充为组件添加更 **[!UICONTROL Text]** 多间 **[!UICONTROL Divider]** 距。
* 要设置结构元素内各列之间的边框，请为每列定义填充。

**[!UICONTROL Margin]**:此设置允许您管理元素边框与下一个元素之间的间距。

![](assets/des_margin.png)

>[!NOTE]
>
>根据您的选择（结构组件、列或内容组件），结果将不相同。 Adobe建议在列 **[!UICONTROL Padding]** 级别 **[!UICONTROL Margin]** 设置和参数。

对于和 **[!UICONTROL Padding]** ，单 **[!UICONTROL Margin]**&#x200B;击锁图标可中断顶部和底部参数或右和左参数之间的同步。 这使您能够单独调整每个参数。

![](assets/des_padding_lock_icon.png)

### 关于对齐 {#about-alignment}

* **文本对齐**:将鼠标光标放在某些文本上，然后使用上下文工具栏对齐它。

   ![](assets/des_text_alignment.png)

* **水平对齐** (Horizontal alignment can be applied to text)、图像和按钮- currently not to the **[!UICONTROL Divider]** and components **[!UICONTROL Social]** .

   ![](assets/des_horizontal_alignment.png)

* 要设置垂 **直对齐**，请在结构组件中选择一列，然后从“设置”窗格中选择一个选项。

   ![](assets/des_set_vertical_alignment.png)

### 关于背景 {#about-backgrounds}

在设置电子邮件设计器的背景时，Adobe建议：

1. 根据您的设计要求，将背景色应用于电子邮件正文。
1. 在大多数情况下，在列级别设置背景颜色。
1. 由于图像或文本组件难以管理，请尽量不要在它们上使用背景色。

以下是可用的背景设置。

* 为整 **[!UICONTROL Background color]** 个电子邮件设置。 确保在可从左侧调色板访问的导航树中选择正文设置。

   ![](assets/des_background_body.png)

* 通过选择，为所有结构组件设置相同的背景颜色 **[!UICONTROL Viewport background color]**。 此选项允许您从背景颜色中选择其他设置。

   ![](assets/des_background_viewport.png)

* 为每个结构组件设置不同的背景颜色。 在导航树中选择一个结构（可从左侧调色板访问），以仅将特定背景色应用于该结构。

   ![](assets/des_background_structure.png)

   请确保未设置视口背景颜色，因为它可能隐藏结构背景颜色。

* 为结 **[!UICONTROL Background image]** 构组件的内容设置。

   ![](assets/des_background_image.png)

   >[!NOTE]
   >
   >某些电子邮件程序不支持背景图像。 确保在无法显示图像时选择适当的回退背景颜色。

* 在列级别设置背景颜色。

   ![](assets/des_background_column.png)

   >[!NOTE]
   >
   >这是最常见的用例。 Adobe建议在列级别设置背景颜色，因为这样在编辑整个电子邮件内容时可以更灵活。

   您还可以在列级别设置背景图像，但很少使用此图像。

#### 示例：调整垂直对齐和填充 {#example--adjusting-vertical-alignment-and-padding}

要调整由三列组成的结构组件中的填充和垂直对齐方式。 为此请执行以下操作步骤：

1. 直接在电子邮件中或使用左侧调色板中提供的结构树选择结构 **组件**。
1. 在上下 **文工具栏**，单 **[!UICONTROL Select a column]** 击并选择要编辑的工具栏。 也可以从结构树中选择它。

   ![](assets/des_selecting_column.png)

   该列的可编辑参数显示在右 **[!UICONTROL Settings]** 侧的窗格中。

1. 在下 **[!UICONTROL Vertical alignment]**&#x200B;面，选择 **[!UICONTROL Up]**。

   ![](assets/des_vertical_alignment.png)

   内容组件显示在列的顶部。

1. 在 **[!UICONTROL Padding]**&#x200B;下，定义列内的顶部填充。 单击锁图标可中断与底部填充的同步。

   定义该列的左边距和右边距。

   ![](assets/des_adjusting_padding.png)

1. 以类似的方式继续调整其他列的对齐方式和填充。

   ![](assets/des_adjusting_columns.png)

1. 保存更改。

### 关于样式链接 {#about-styling-links}

>[!NOTE]
>
>从Campaign Standard 19.4版本开始，将提供此功能。

您可以在电子邮件设计器中为链接添加下划线并选择其颜色和目标。

1. 在插入链接的组件中，选择链接的标签文本。

1. 在组件设置中，选中 **[!UICONTROL Underline link]** 以在链接的标签文本上加下划线。

   ![](assets/stylelinks-selecttext.png)

1. 要选择将在其中打开您的链接的浏览上下文，请选择一个 **[!UICONTROL Target]**。

   ![](assets/stylelinks-target.png)

1. 要更改链接的颜色，请单击 **[!UICONTROL Link color]**。

   ![](assets/stylelinks-colorpicker.png)

1. 选择所需的颜色。

   ![](assets/stylelinks-colorchanged.png)

1. 保存更改。

### 添加内联样式属性 {#adding-inline-styling-attributes}

在“电子邮件设计器”界面中，选择某个元素并在侧面板上显示其设置时，您可以自定义该特定元素的内联属性及其值。

1. 在内容中选择元素。
1. 在侧面板上，查找设 **[!UICONTROL Styles Inline]** 置。

   ![](assets/email_designer_inlineattributes.png)

1. 修改现有属性的值，或使用 **+按钮添加新** 属性。 您可以添加任何符合CSS规范的属性和值。

样式随后将应用于所选元素。 如果子元素没有定义特定的样式属性，则继承父元素的样式。

## 切换到移动视图 {#switching-to-mobile-view}

您可以通过单独编辑移动显示的所有样式选项来微调电子邮件的响应式设计。 例如，您可以调整边距和填充、使用较小或较大的字体大小、更改按钮或应用特定于移动版电子邮件的不同背景颜色。

所有样式选项均在移动视图中可用。 “电子邮件设计器”样式设置显示在“编辑电子 [邮件样式”部分](../../designing/using/styles.md) 。

1. 创建电子邮件并开始编辑内容。 有关此方面的详细信息，请参 [阅从头开始设计电子邮件内容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
1. 要访问专用的移动视图，请选择 **[!UICONTROL Switch to mobile view]** 按钮。

   ![](assets/email_designer_mobile_view_switch.png)

   此时将显示电子邮件的移动版本。 它包含在桌面视图中定义的所有组件和样式。

1. 独立编辑所有样式设置，如背景颜色、对齐方式、填充、边距、字体系列、文本颜色等。

   ![](assets/email_designer_mobile_view.png)

1. 在移动视图中编辑任何样式设置时，修改仅应用于移动显示。

   例如，减小图像的大小，添加绿色背景，并更改移动视图中的填充。

   ![](assets/email_designer_mobile_view_change.png)

1. 在移动设备上显示组件时，可以隐藏组件。 为此，请从 **[!UICONTROL Show only on desktop devices]** 中选择 **[!UICONTROL Display options]**。
您还可以选择在桌面设备上隐藏此组件，这意味着它将仅在移动设备上显示。 为此，请选择 **[!UICONTROL Show only on mobile devices]**。
例如，此选项允许您在移动设备上显示特定图像，在桌面设备上显示另一个图像。
您可以从移动视图或桌面视图中设置此选项。

   ![](assets/email_designer_mobile_hide.png)

1. 再次单击 **[!UICONTROL Switch to mobile view]** 该按钮以返回标准桌面视图。 您刚做的样式更改不会反映出来。

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >唯一的例外是设置 **[!UICONTROL Style inline]** 问题。 任何样式内联设置更改也会应用于标准桌面视图。

1. 对电子邮件结构或内容的任何其他更改，如文本编辑、上传新图像、添加新组件等。 也适用于标准视图。

   例如，切换回移动视图，编辑一些文本并替换图像。

   ![](assets/email_designer_mobile_view_change_content.png)

   再次单击 **[!UICONTROL Switch to mobile view]** 该按钮以返回标准桌面视图。 将反映更改。

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. 在移动视图中删除样式会返回到在桌面模式下应用的样式。

   例如，在移动视图中，将绿色背景色应用于按钮。

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. 切换到桌面视图并将灰色背景应用于同一按钮。

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. 再次切换到移动视图，现在禁用该 **[!UICONTROL Background color]** 设置。

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   桌面视图中定义的背景颜色现已应用：它将变灰（而非空白）。

   唯一的例外是设置 **[!UICONTROL Border color]** 问题。 在移动视图中禁用时，即使在桌面视图中定义了边框颜色，也不再应用边框。

>[!NOTE]
>
>移动视图在片段中不 [可用](../../designing/using/using-reusable-content.md#about-fragments)。
