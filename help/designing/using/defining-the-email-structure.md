---
title: 定义电子邮件结构
seo-title: 定义电子邮件结构
description: 定义电子邮件结构
seo-description: 了解如何使用Campaign中的电子邮件设计器来塑造电子邮件，并用内容组件填充它们。
page-status-flag: 从未激活
uuid: 6ec63f65-1425-4c28-84e8-b09574458 db3
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 设计
content-type: reference
topic-tags: editing-email-content
discoiquuid: 207fdf6d-165a-41af-ad53-ba97 d3403 b62
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 2ac7fa8be4c408d75d77d3035af4cec25ac001c2

---


# 定义电子邮件结构{#defining-the-email-structure}

## 编辑电子邮件结构 {#editing-the-email-structure}

通过电子邮件设计器，您可以轻松定义电子邮件的结构。通过简单的拖放操作添加和移动结构元素，您可以在几秒钟内设计电子邮件的形状。

要编辑电子邮件的结构，请执行以下操作：

1. 打开现有内容或创建新的电子邮件内容。
1. 通过选择 **[!UICONTROL Structure components]** 左侧 **的+** 图标来访问。

   ![](assets/email_designer_structure.png)

1. 拖放您需要建立电子邮件形状的结构组件。

   ![](assets/email_designer_structure_components.png)

   在放下结构组件的精确位置之前，一条蓝线会调整其位置。您可以将其拖放到任何其他组件之间或下方，但不能放在内部。

   >[!NOTE]
   >
   >放入电子邮件后，除非已经有内容组件或放入其中，否则您无法移动和删除组件。

1. 可以使用由一列或多列组成的多个结构组件。

   选择 **[!UICONTROL n:n column]** 组件可定义所选的列数(到10之间)。您还可以通过移动每个列底部的箭头来定义每个列的宽度。

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >每个列大小不能低于结构组件总宽度的10%。不能删除不是空的列。

定义结构后，您可以将内容片段和组件添加到电子邮件中。

## 添加片段和内容组件 {#adding-fragments-and-content-components}

通过电子邮件设计器，在向电子邮件中添加结构组件后，您可以定义其内容。为此，您需要在每个结构组件中添加元素。

可使用以下两种类型的内容元素： **片段** 和 **内容组件**。

### 关于片段 {#about-fragments}

片段是可在一封或多封电子邮件中引用的可重用组件。

要在电子邮件设计器中充分利用片段，请执行以下操作：

* 创建您自己的片段。请参阅 [创建内容片段](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment) 和 [将内容保存为片段](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment)。
* 在电子邮件中多次使用它们。请参阅 [将元素插入电子邮件](../../designing/using/defining-the-email-structure.md#inserting-elements-into-an-email)。
* 编辑片段时，更改会同步：它们会自动传播到包含该片段的所有电子邮件(尚未准备或发送)。

添加到电子邮件时，片段默认处于锁定状态。如果要修改特定电子邮件的片段，可通过将其解锁到使用该片段的电子邮件中，中断与原始片段的同步。更改将不再同步。

要将某个片段解锁到电子邮件中，请选择该片段，然后单击上下文工具栏中的锁定图标。

![](assets/des_unlocking_fragment.png)

该片段将成为不再链接到原始片段的独立组件。然后，可以将其作为任何其他内容组件进行编辑。请参阅 [关于内容组件](../../designing/using/defining-the-email-structure.md#about-content-components)。

### 关于内容组件 {#about-content-components}

内容组件是原始的、空的组件，一旦放入电子邮件，您就可以编辑这些组件。

您可以在结构组件中添加任意数量的内容组件。您还可以将它们移到结构组件中或其他结构组件中。

下面是电子邮件设计器中可用组件的列表：

* **[!UICONTROL Button]**

   如果需要使用多个按钮，而不是从头开始编辑每个按钮，则可以使用上下文工具栏复制 **[!UICONTROL Button]** 组件。

   您还可以将按钮保存到可重复使用的片段中。有关此操作的详细信息，请参阅 [创建内容片段](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment) 和 [将内容保存为片段](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment)。

* **[!UICONTROL Carousel]**

   有关此操作的详细信息，请参阅 [使用传送组件](../../designing/using/defining-the-email-structure.md#using-the-carousel-component)。

* **[!UICONTROL Divider]**
* **[!UICONTROL Html]**

   使用此组件可复制现有HTML的不同部分。这使您能够创建免费的模块化HTML组件。

   >[!NOTE]
   >
   >可编辑的免费HTML组件具有有限的选项。如果所有样式未嵌入，请确保在HTML代码的 **head** 部分添加正确的CSS，否则电子邮件将不会响应。使用 **[!UICONTROL Preview]** 该按钮测试内容的响应性(请参阅 [预览消息](../../sending/using/previewing-messages.md))。

* **[!UICONTROL Image]**
* **[!UICONTROL Social]**
* **[!UICONTROL Text]**

#### 使用传送组件 {#using-the-carousel-component}

1. 将 **[!UICONTROL Carousel]** 组件拖放到结构组件中。
1. 浏览以从计算机中选择图像。

   ![](assets/des_carousel_browse.png)

1. 在 **[!UICONTROL Settings]** 窗格中，设置您在传送中需要的缩略图数。
1. 从计算机中选择回退图像。

   ![](assets/des_carousel_fallback.png)

   传送组件与所有电子邮件程序不兼容。在电子邮件中不支持传送时，上传回退以显示图像。

   >[!NOTE]
   >
   >传送组件与以下电子邮件平台兼容：Apple Mail7、Apple Mail8、Outlook2011for Mac、Outlook2016for Mac、Mozilla ThunderBird、iPad和iPad mini iOS、iPhone iOS、Android、AOL(Chrome、Firefox和Safari)。

1. 选择 **[!UICONTROL Fallback view]** 以在电子邮件设计器中显示回退图像。

### 将元素插入电子邮件 {#inserting-elements-into-an-email}

要定义电子邮件的内容，您可以在预先置入的结构组件中添加内容元素。请参阅 [编辑电子邮件结构](../../designing/using/defining-the-email-structure.md#editing-the-email-structure)。

1. 通过选择左侧 **的+** 图标访问内容元素。选择 [片段](../../designing/using/defining-the-email-structure.md#about-fragments) 或 [内容组件](../../designing/using/defining-the-email-structure.md#about-content-components)。
1. 如果您已经知道要添加的片段标签或部分标签，则可以搜索该标签。

   ![](assets/email_designer_fragmentsearch.png)

1. 将片段或内容组件从调色板拖放到电子邮件的结构组件。

   ![](assets/email_designer_addfragment.png)

   将元素添加到电子邮件后，可以在结构组件中或电子邮件中的其他结构组件中移动该元素。

   ![](assets/email_designer_movefragment.png)

1. 编辑元素以匹配此电子邮件的精确需求。您可以添加文本、链接、图像等。

   >[!NOTE]
   >
   >在添加到电子邮件时，片段默认处于锁定状态。如果要修改特定电子邮件的片段，您可以中断与原始片段的同步，或者直接在片段中进行更改。请参阅 [关于片段](../../designing/using/defining-the-email-structure.md#about-fragments)。

1. 对需要添加到电子邮件中的所有元素重复此步骤。
1. 保存电子邮件。

现在已填充电子邮件结构，您可以编辑每个内容元素的样式。请参阅 [编辑元素](../../designing/using/editing-email-styles.md#editing-an-element)。

>[!NOTE]
>
>如果某个片段被修改，则这些更改会自动传播到使用该片段的电子邮件中。有关此操作的详细信息，请参阅 [关于片段](../../designing/using/defining-the-email-structure.md#about-fragments)。

### 创建内容片段 {#creating-a-content-fragment}

您可以创建自己的内容片段，以便在一封或多封电子邮件中根据需要使用它们。

1. 转到 **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** 并单击 **[!UICONTROL Create]**。
1. 单击电子邮件标签以访问电子邮件设计器 **[!UICONTROL Properties]** 的选项卡。
1. 指定可识别的标签，并在编辑电子邮件内容时选择以下参数以查找片段：

   * 由于片段只与电子邮件兼容，请 **[!UICONTROL Delivery]** 从 **[!UICONTROL Content type]** 下拉列表中进行选择。
   * **[!UICONTROL Fragment]** 从 **[!UICONTROL HTML type]** 下拉列表中选择可将此内容用作片段。
   ![](assets/email_designer_createfragment.png)

1. 如果需要，您可以设置将用作片段缩略图的图像。从模板属性 **[!UICONTROL Thumbnail]** 的选项卡中选择它。

   ![](assets/email_designer_createfragment_thumbnail.png)

   编辑电子邮件时，该缩略图将显示在片段标签旁边。

1. 关闭 **[!UICONTROL Properties]** 选项卡以返回主工作区。
1. 添加可根据需要自定义的结构组件和内容组件。

   >[!NOTE]
   >
   >片段不能包括个性化字段、动态内容或其他片段。
   >[移动视图](../../designing/using/about-email-content-design.md#switching-to-mobile-view) 在片段中不可用。

1. 编辑后，保存片段。

此片段现在可用于使用电子邮件设计器构建的任何电子邮件。它显示在调色板的 **[!UICONTROL Fragments]** 部分下方。

>[!NOTE]
>
>除非在电子邮件中使用并未锁定，否则您无法插入片段中的个性化字段。请参阅 [关于片段](../../designing/using/defining-the-email-structure.md#about-fragments)。

### 将内容保存为片段 {#saving-content-as-a-fragment}

使用电子邮件设计器编辑电子邮件时，您可以将该电子邮件的一部分直接保存为片段。

* 您不能另存为包含个性化字段、动态内容或其他片段的结构。
* 您只能选择彼此相邻的结构。
<!--* You cannot select an empty structure.-->

1. 在电子邮件设计器中编辑电子邮件时，从主工具栏中进行选择 **[!UICONTROL Save as fragment]** 。

   ![](assets/email_designer_save-as-fragment.png)

1. 在工作区中，选择将合成片段的结构。

   ![](assets/email_designer_save-as-fragment_select.png)

   >[!NOTE]
   >
   >确保选择彼此相邻且不包括个性化字段、动态内容或其他片段的结构。
   <!--You cannot select an empty structure.-->

1. Click **[!UICONTROL Create]**.

1. 根据需要添加标签和说明，然后单击 **[!UICONTROL Save]**。

   ![](assets/email_designer_save-as-fragment_popup.png)

1. 要查找刚刚创建的片段，请转到 **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]**。

   ![](assets/email_designer_save-as-fragment_list.png)

1. 要使用新的片段，请打开任何电子邮件内容并从片段列表中选择它。

![](assets/email_designer_save-as-fragment_in-new-email.png)

>[!NOTE]
>[移动视图](../../designing/using/about-email-content-design.md#switching-to-mobile-view) 在片段中不可用。如果要编辑电子邮件移动视图，请先将其保存为片段，然后再将其保存为片段。

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

