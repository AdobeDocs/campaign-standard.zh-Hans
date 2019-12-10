---
title: 编辑纯文本、HTML和移动电子邮件格式
description: 发现纯文本和HTML模式
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
source-git-commit: 5e2ea8020c82f578b2cf8c00fa7b9f55b6ce2edd

---


# 编辑纯文本、HTML和移动电子邮件格式 {#plain-text-and-html-modes}

电子邮件设计器允许您编辑多个电子邮件渲染。 您可以生成电子邮件的文本版本、编辑电子邮件的HTML源并为移动视图设计电子邮件。

## 生成电子邮件的文本版本 {#generating-a-text-version-of-the-email}

默认情况下，系 **[!UICONTROL Plain text]** 统会自动生成电子邮件的版本并与该版本同 **[!UICONTROL Edit]** 步。

添加到HTML版本的个性化字段和内容块也与纯文本版本同步。

>[!NOTE]
>
>要在纯文本版本中使用内容块，请确保它们不包含HTML代码。

要使纯文本版本与HTML版本不同，您可以通过从电子邮件视图中单击 **[!UICONTROL Sync with HTML]** 切换来禁 **[!UICONTROL Plain text]** 用此同步。

![](assets/email_designer_textversion.png)

然后，您可以根据需要编辑纯文本版本。

>[!NOTE]
>
>如果在禁用同 **[!UICONTROL Plain text]****[!UICONTROL Sync with HTML]** 步时编辑版本，下次启用该选项时，在纯文本版本中所做的所有更改将替换为HTML版本。 在视图中所做的 **[!UICONTROL Plain text]** 更改无法反映在视 **[!UICONTROL HTML]** 图中。

## 在HTML中编辑电子邮件内容源 {#editing-an-email-content-source-in-html}

对于最高级的用户和调试，您可以直接以HTML形式查看和编辑电子邮件内容。

有两种方法可编辑HTML版本的电子邮件：

* 选择 **[!UICONTROL Edit]** &gt; **[!UICONTROL HTML]** 以打开整个电子邮件的HTML版本。

   ![](assets/email_designer_html1.png)

* 从WYSIWYG界面中，选择一个元素并单击该 **[!UICONTROL Source code]** 图标。

   只显示所选元素的源。 如果所选元素是内容组件，则可以编辑 **[!UICONTROL HTML]** 源代码。 其他组件处于只读模式，但仍可以在电子邮件的完整HTML版本中编辑。

   ![](assets/email_designer_html2.png)

如果修改HTML代码，则电子邮件的响应性可能会中断。 确保使用按钮测试该 **[!UICONTROL Preview]** 组件。 请参阅 [预览消息](../../sending/using/previewing-messages.md)。

## 为移动渲染设计电子邮件 {#switching-to-mobile-view}

您可以通过单独编辑移动显示的所有样式选项来微调电子邮件的响应式设计。 例如，您可以调整边距和填充、使用较小或较大的字体大小、更改按钮或应用特定于移动版电子邮件的不同背景颜色。

所有样式选项均在移动视图中可用。 “电子邮件设计器”样式设置以前在本页中显示。

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
