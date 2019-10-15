---
title: '创建和使用可重用内容 '
seo-title: 创建和使用可重用内容
description: 创建和使用可重用内容
seo-description: 开始使用电子邮件设计器构建可重复使用的电子邮件内容。
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
source-git-commit: 7d044652c58c3fc66dac64f9d080852dbe29044d

---

# 创建和使用可重用内容 {#using-reusable-content}

了解如何掌握电子邮件内容版本。 使用Email Designer，您可以使用自己的预定义内容创建模板和片段，并重复使用它们进行后续分发。

## 使用模板进行设计 {#designing-templates}

>[!NOTE]
>
> 在Adobe Campaign Standard中，您可以创建可从“资源” **&gt;“模板”菜单访问的不** 同类型 **的** 模板。 电子邮件设计器中使用的模板是内容模板。 有关详细信息，请参阅 [关于模板](../../start/using/about-templates.md)。

### 内容模板 {#content-templates}

您可以管理将在“电子邮件设计器”主页的选 **[!UICONTROL Templates]** 项卡中提供 [的HTML内容](../../designing/using/overview.md) 。 不同的模板显示了几种类型的元素的各种组合。 例如，“羽化”模板具有边距，而“Astro”模板没有边距。 有关此内容的详细信息，请参 [阅内容模板](../../designing/using/using-reusable-content.md#content-templates)。

![](assets/template_content.png)

要了解如何从现成模板构建电子邮件，请参阅电子邮 [件设计器](../../designing/using/quick-start.md#building-content-from-an-out-of-the-box-template)。

### Creating a content template {#creating-a-content-template}

您可以创建自己的内容模板，以根据需要多次使用它们。

以下示例演示如何创建电子邮件内容模板。

1. 转到 **[!UICONTROL Resources]** &gt;并 **[!UICONTROL Content templates & fragments]** 单击 **[!UICONTROL Create]**。
1. 单击电子邮件标签以访问电子 **[!UICONTROL Properties]** 邮件设计器的选项卡。
1. 指定可识别的标签，并选择以下参数以便能够在电子邮件中使用此模板：

   * 从 **[!UICONTROL Shared]** 下拉 **[!UICONTROL Delivery]** 列表 **[!UICONTROL Content type]** 中选择或。
   * 从下 **[!UICONTROL Template]** 拉列 **[!UICONTROL HTML type]** 表中进行选择。
   ![](assets/email_designer_create-template.png)

1. 如果需要，您可以设置一幅图像，该图像将用作模板的缩略图。 从模板属性的选 **[!UICONTROL Thumbnail]** 项卡中选择它。

   ![](assets/email_designer_create-template_thumbnail.png)

   此缩略图将显示在“电子邮 **[!UICONTROL Templates]** 件设计器”主 [页的选项卡中](../../designing/using/overview.md#about-the-email-designer) 。

1. 关闭选 **[!UICONTROL Properties]** 项卡以返回到主工作区。
1. 添加结构组件和内容组件，您可以根据需要自定义这些组件和内容组件。
   >[!NOTE]
   >
   > 不能在内容模板中插入个性化字段或条件内容。
1. 编辑后，保存模板。

此模板现在可用于使用电子邮件设计器构建的任何电子邮件。 从“电子邮件设计 **[!UICONTROL Templates]** 器”主页的选 [项卡中选择](../../designing/using/overview.md#about-the-email-designer) 。

![](assets/content_template_new.png)

### 将内容另存为模板 {#saving-content-as-template}

使用电子邮件设计器编辑电子邮件时，您可以直接将该电子邮件的内容另存为模板。

<!--[!CAUTION]
>
>You cannot save as template a structure containing personalization fields or dynamic content.-->

1. 从“电 **[!UICONTROL Save as template]** 子邮件设计器”主工具栏中进行选择。

   ![](assets/email_designer_save-as-template.png)

1. 根据需要添加标签和说明，然后单击 **[!UICONTROL Save]**。

   ![](assets/email_designer_save-as-template_creation.png)

1. 要查找您刚刚创建的模板，请转至 **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]**。

1. 要使用新模板，请从“电子邮件设计器”主 **[!UICONTROL Templates]** 页的选项卡 [中选择它](../../designing/using/overview.md#about-the-email-designer) 。

   ![](assets/content_template_new.png)

### 使用片段和组件创建模板 {#template-fragments-components}

您现在可以使用电子邮件设计器创建电子邮件模板。 使用内容组件反映电子邮件的不同部分，并调整设置，使其尽可能接近原始新闻稿。 最后，插入您刚刚创建的片段。

1. 使用电子邮件设计器创建模板。 有关此内容的详细信息，请参 [阅内容模板](../../designing/using/using-reusable-content.md#content-templates)。
1. 将多个结构组件插入模板中——与电子邮件的页眉、页脚和正文相对应。 有关添加结构组件的更多信息，请参 [阅使用电子邮件设计器编辑电子邮件结构](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 插入所需数量的内容组件以创建新闻稿的正文。 这将是您每月更新的电子邮件的可编辑内容。

   ![](assets/des_loading_compatible_fragment_5.png)

   如果您熟悉HTML代码，Adobe建议您利用 **[!UICONTROL Html]** 组件复制粘贴原始电子邮件中较复杂的元素。 将其他组件( **[!UICONTROL Button]**&#x200B;如 **[!UICONTROL Image]** 或 **[!UICONTROL Text]** 用于其余内容)。 有关此内容的详细信息，请参 [阅关于内容组件](../../designing/using/designing-from-scratch.md#about-content-components)。

   >[!NOTE]
   >
   >使用组 **[!UICONTROL Html]** 件可创建可编辑且选项有限的组件。 在选择此组件之前，请确保您知道如何处理HTML代码。

1. 调整内容组件，尽可能与原始电子邮件匹配。

   ![](assets/des_loading_compatible_fragment_6.png)

   有关管理样式设置和内联属性的更多信息，请参阅编 [辑电子邮件样式](../../designing/using/styles.md)。

1. 将您之前创建的两个片段（页眉和页脚）插入到所需的结构组件中。

   ![](assets/des_loading_compatible_fragment_10.png)

1. 保存模板。

您现在可以在电子邮件设计器中完全管理此模板，以创建和更新每月将发送给收件人的新闻稿。

要使用它，请创建电子邮件，然后选择您刚刚创建的内容模板。

**相关主题**:

* [创建电子邮件](../../channels/using/creating-an-email.md)
* [电子邮件设计人员简介视频](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=chi_hans)
* [从头开始设计电子邮件内容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## 关于片段 {#about-fragments}

片段是可重用的组件，可在一个或多个电子邮件中引用。
可以在“资源” **&gt;“内容片段和模板”下** 的界面中找到这些片段 ****。

要在电子邮件设计器中充分利用片段，请执行以下操作：

* 创建您自己的片段。 请参 [阅创建内容片段](../../designing/using/using-reusable-content.md#creating-a-content-fragment)[和将内容另存为片段](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)。
* 在电子邮件中根据需要多次使用它们。 请参 [阅将元素插入电子邮件](../../designing/using/using-reusable-content.md#inserting-elements-into-an-email)。
* 编辑片段时，将同步更改：它们会自动传播到包含该片段的所有电子邮件（前提是尚未准备或发送它们）。

在添加到电子邮件中时，片段默认处于锁定状态。 如果要修改特定电子邮件的片段，您可以在使用该片段的电子邮件中解锁该片段，从而中断与原始片段的同步。 更改将不再同步。

要解锁电子邮件中的片段，请选择该片段，然后单击上下文工具栏中的锁定图标。

![](assets/des_unlocking_fragment.png)

该片段将成为不再链接到原始片段的独立组件。 然后，可以将其编辑为任何其他内容组件。 请参阅 [关于内容组件](../../designing/using/designing-from-scratch.md#about-content-components)。

### 在电子邮件中插入片段 {#inserting-elements-into-an-email}

要定义电子邮件的内容，您可以在预先放置的结构组件中添加内容元素。 请参阅 [编辑电子邮件结构](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

1. 通过选择左侧的+图 **标** ，访问内容元素。 选择 [片段](../../designing/using/using-reusable-content.md#about-fragments)[或内容组件](../../designing/using/designing-from-scratch.md#about-content-components)。
1. 如果您已经知道要添加的片段的标签或部分标签，则可以搜索它。

   ![](assets/email_designer_fragmentsearch.png)

1. 将片段或内容组件从调色板拖放到电子邮件的结构组件中。

   ![](assets/email_designer_addfragment.png)

   将元素添加到电子邮件后，即可将其移动到结构组件中或电子邮件中的其他结构组件中。

   ![](assets/email_designer_movefragment.png)

1. 编辑元素以满足此电子邮件的确切需求。 您可以添加文本、链接、图像等。

   >[!NOTE]
   >
   >将片段添加到电子邮件时，默认情况下会锁定。 如果要修改特定电子邮件的片段，或直接在片段中进行更改，则可以中断与原始片段的同步。 请参阅 [关于片段](../../designing/using/using-reusable-content.md#about-fragments)。

1. 对您需要添加到电子邮件中的所有元素重复此过程。
1. 保存电子邮件。

现在，您的电子邮件结构已填充，您可以编辑每个内容元素的样式。 请参 [阅编辑元素](../../designing/using/styles.md#editing-an-element)。

>[!NOTE]
>
>如果修改了片段，则更改会自动传播到使用该片段的电子邮件中。 有关此方面的详细信息，请参 [阅关于片段](../../designing/using/using-reusable-content.md#about-fragments)。

### 创建内容片段 {#creating-a-content-fragment}

您可以根据需要在一个或多个电子邮件中创建您自己的内容片段。

1. 转到 **[!UICONTROL Resources]** &gt;并 **[!UICONTROL Content templates & fragments]** 单击 **[!UICONTROL Create]**。
1. 单击电子邮件标签以访问电子 **[!UICONTROL Properties]** 邮件设计器的选项卡。
1. 指定可识别的标签，并选择以下参数以在编辑电子邮件内容时查找片段：

   * 由于片段仅与电子邮件兼容，因此请 **[!UICONTROL Delivery]** 从下拉列 **[!UICONTROL Content type]** 表中进行选择。
   * 从下 **[!UICONTROL Fragment]** 拉列 **[!UICONTROL HTML type]** 表中进行选择，以便能够将此内容用作片段。
   ![](assets/email_designer_createfragment.png)

1. 如果需要，您可以设置一幅将用作片段缩略图的图像。 从模板属性的选 **[!UICONTROL Thumbnail]** 项卡中选择它。

   ![](assets/email_designer_createfragment_thumbnail.png)

   编辑电子邮件时，此缩略图将显示在片段标签旁边。

1. 关闭选 **[!UICONTROL Properties]** 项卡以返回到主工作区。
1. 添加结构组件和内容组件，您可以根据需要自定义这些组件和内容组件。

   >[!CAUTION]
   >
   >片段不能包括个性化字段、动态内容或其他片段。
   >
   >避免另存为具有空结构组件的片段内容。 插入&gt;fragment后，它们便不可编辑。
   >
   >移 [动视图](../../designing/using/styles.md#switching-to-mobile-view) （片段）不可用。

1. 编辑后，保存您的片段。

此片段现在可用于使用电子邮件设计器构建的任何电子邮件。 它显示在“调 **[!UICONTROL Fragments]** 色板”部分下。

>[!NOTE]
>
>除非在电子邮件中使用并且已解锁，否则不能在片段中插入个性化字段。 请参阅 [关于片段](../../designing/using/using-reusable-content.md#about-fragments)。

### 将内容另存为片段 {#saving-content-as-a-fragment}

使用电子邮件设计器编辑电子邮件时，您可以直接将该电子邮件的一部分另存为片段。

* 不能将包含个性化字段、动态内容或其他片段的结构另存为片段。
* 只能选择彼此相邻的结构。
<!-- - You cannot select an empty structure.-->

1. 在电子邮件设计器中编辑电子邮件时，从主 **[!UICONTROL Save as fragment]** 工具栏中进行选择。

   ![](assets/email_designer_save-as-fragment.png)

1. 从工作区中，选择将构成片段的结构。

   ![](assets/email_designer_save-as-fragment_select.png)

   >[!NOTE]
   >
   >确保选择彼此相邻且不包含个性化字段、动态内容或其他片段的结构。
   <!--You cannot select an empty structure.-->

1. Click **[!UICONTROL Create]**.

1. 根据需要添加标签和说明，然后单击 **[!UICONTROL Save]**。

   ![](assets/email_designer_save-as-fragment_popup.png)

1. 要查找您刚刚创建的片段，请转到 **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]**。

   ![](assets/email_designer_save-as-fragment_list.png)

1. 要使用新片段，请打开任何电子邮件内容，然后从片段列表中选择它。

![](assets/email_designer_save-as-fragment_in-new-email.png)

>[!NOTE]
>移 [动视图](../../designing/using/styles.md#switching-to-mobile-view) （片段）不可用。 如果要编辑电子邮件移动视图，请在将内容另存为片段之前进行编辑。

<!--You need to copy-paste the HTML corresponding to the section that you want to save into a new fragment.

>[!NOTE]
>
>To do this, you need to be familiar with HTML code.

To save as a fragment some email content that you created, follow the steps below.

1. When editing an email in the Email Designer, select **[!UICONTROL Edit]** > **[!UICONTROL HTML]** to open the HTML version of that email.
1. Select and copy the HTML corresponding to the part that you want to save.
1. Go to **[!UICONTROL Resources]** > **[!UICONTROL Content templates & fragments]** and click **[!UICONTROL Create]**.
1. Click the email label to access the **[!UICONTROL Properties]** tab of the Email Designer and select **[!UICONTROL Fragment]** from the **[!UICONTROL HTML type]** drop-down list.
1. Select **[!UICONTROL Edit]** > **[!UICONTROL HTML]** to open the HTML version of the fragment.
1. Paste the HTML that you copied where appropriate.
1. Switch back to the **[!UICONTROL Edit]** view to check the result and save the new fragment.-->

## 使用片段创建可重用的页眉和页脚 {#header-footer-fragments}

使用电子邮件设计器，为每个可重用的部分创建一个片段。 在此示例中，您将创建两个片段：一个用于表头，一个用于表尾。 然后，您可以将现有内容中的相关部分复制到这些片段中。

为此请执行以下操作步骤：

1. 在Adobe Campaign中，转到 **[!UICONTROL Resources]** &gt;并 **[!UICONTROL Content templates & fragments]** 为标题创建片段。 有关此内容的详细信息，请 [参阅创建内容片段](../../designing/using/using-reusable-content.md#creating-a-content-fragment)。
1. 向片段添加所需数量的结构组件。

![](assets/des_loading_compatible_fragment_1.png)

1. 将图像和文本组件插入结构中。

![](assets/des_loading_compatible_fragment_2.png)

1. 上传相应的图像，输入文本并调整设置。

![](assets/des_loading_compatible_fragment_3.png)

1. 保存片段。
1. 以类似方式继续创建页脚并保存它。

![](assets/des_loading_compatible_fragment_4.png)

您的片段现已准备好在模板中使用。
