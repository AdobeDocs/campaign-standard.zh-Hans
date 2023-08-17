---
title: 编辑纯文本、HTML和移动电子邮件格式
description: 了解纯文本和HTML模式
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 760c3c30-c899-4cf4-ba59-fb2fade9fc5e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 1%

---

# 编辑纯文本、HTML和移动电子邮件格式 {#plain-text-and-html-modes}

Email Designer允许您编辑电子邮件的多种呈现。 您可以生成电子邮件的文本版本，编辑电子邮件的HTML源，并设计用于移动设备查看的电子邮件。

## 生成电子邮件的文本版本 {#generating-a-text-version-of-the-email}

默认情况下， **[!UICONTROL Plain text]** 您的电子邮件版本会自动生成，并与 **[!UICONTROL Edit]** 版本。

添加到HTML版本的个性化字段和内容块也将与纯文本版本同步。

>[!NOTE]
>
>要在纯文本版本中使用内容块，请确保它们不包含HTML代码。

若要使用与HTML版本不同的纯文本版本，您可以通过单击 **[!UICONTROL Sync with HTML]** 从 **[!UICONTROL Plain text]** 查看您的电子邮件。

![](assets/email_designer_textversion.png)

之后，您可以根据需要编辑纯文本版本。

>[!NOTE]
>
>如果您编辑 **[!UICONTROL Plain text]** 版本，如果同步被禁用，则下次启用 **[!UICONTROL Sync with HTML]** 选项，您在纯文本版本中所做的所有更改都将替换为HTML版本。 中所做的更改 **[!UICONTROL Plain text]** 视图不能反映在 **[!UICONTROL HTML]** 视图。

## 在HTML中编辑电子邮件内容源 {#editing-an-email-content-source-in-html}

对于最高级的用户和调试，您可以直接在HTML中查看和编辑电子邮件内容。

您可以通过两种方式编辑电子邮件的HTML版本：

* 选择 **[!UICONTROL Edit]** > **[!UICONTROL HTML]** 以打开整个电子邮件的HTML版本。

  ![](assets/email_designer_html1.png)

* 在WYSIWYG界面中，选择一个元素，然后单击 **[!UICONTROL Source code]** 图标。

  仅显示选定元素的源。 如果选定的元素为，则可以编辑源代码 **[!UICONTROL HTML]** 内容组件。 其他组件处于只读模式，但仍可以在电子邮件的完整HTML版本中进行编辑。

  ![](assets/email_designer_html2.png)

如果修改代码的HTML，则电子邮件的响应速度可能会中断。 确保使用 **[!UICONTROL Preview]** 按钮。 请参阅[预览消息](../../sending/using/previewing-messages.md)。

## 为移动渲染设计电子邮件 {#switching-to-mobile-view}

您可以通过单独编辑移动设备显示的所有样式选项来微调电子邮件的响应式设计。 例如，您可以调整边距和边距，使用较小或较大的字体大小，更改按钮，或应用特定于电子邮件移动设备版本的不同背景颜色。

所有样式选项在移动设备视图中均可用。 此页面上以前显示过Email Designer样式设置。

1. 创建电子邮件并开始编辑内容。 有关此内容的更多信息，请参阅 [从头开始设计电子邮件内容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. 要访问专用移动设备视图，请选择 **[!UICONTROL Switch to mobile view]** 按钮。

   ![](assets/email_designer_mobile_view_switch.png)

   此时会显示电子邮件的移动设备版本。 它包含桌面视图中定义的所有组件和样式。

1. 独立编辑所有样式设置，如背景颜色、对齐、填充、边距、字体系列、文本颜色等。

   ![](assets/email_designer_mobile_view.png)

1. 在移动设备视图中编辑任何样式设置时，修改仅应用于移动设备显示。

   例如，减小图像的大小，添加绿色背景并更改移动视图中的边距。

   ![](assets/email_designer_mobile_view_change.png)

1. 在移动设备上显示组件时，您可以隐藏组件。 要执行此操作，请选择 **[!UICONTROL Show only on desktop devices]** 从 **[!UICONTROL Display options]**.

   您还可以选择在桌面设备上隐藏此组件，这意味着它仅在移动设备上显示。 要执行此操作，请选择 **[!UICONTROL Show only on mobile devices]**.

   例如，使用此选项可以在移动设备上显示特定图像，在桌面设备上显示其他图像。

   您可以从移动设备视图或桌面视图设置此选项。

   ![](assets/email_designer_mobile_hide.png)

1. 再次单击 **[!UICONTROL Switch to mobile view]** 按钮以返回到标准桌面视图。 您刚才所做的样式更改不会反映出来。

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >唯一的例外是 **[!UICONTROL Style inline]** 设置。 任何样式内联设置更改也会应用于标准桌面视图。

1. 对电子邮件的结构或内容进行的任何其他更改，如文本编辑、上传新图像、添加新组件等。 也会应用于标准视图。

   例如，切换回移动设备视图，编辑某些文本并替换图像。

   ![](assets/email_designer_mobile_view_change_content.png)

1. 再次单击 **[!UICONTROL Switch to mobile view]** 按钮以返回到标准桌面视图。 更改会反映出来。

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. 删除移动设备视图中的样式会返回到在桌面模式下应用的样式。

   例如，在移动设备视图中，将绿色背景颜色应用于按钮。

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. 切换到桌面视图并将灰色背景应用于同一按钮。

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. 再次切换到移动视图，现在禁用 **[!UICONTROL Background color]** 设置。

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   现在应用桌面视图中定义的背景颜色：它变为灰色（非空白）。

   唯一的例外是 **[!UICONTROL Border color]** 设置。 在移动设备视图中禁用后，即使桌面视图中定义了边框颜色，也不会再应用边框。

>[!NOTE]
>
>移动设备视图在中不可用 [片段](../../designing/using/using-reusable-content.md#about-fragments).
