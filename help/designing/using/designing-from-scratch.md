---
title: '从头开始设计电子邮件 '
description: 了解如何在电子邮件设计器中从头开始设计电子邮件内容。
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
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 从头开始设计电子邮件 {#designing-an-email-content-from-scratch}

了解如何掌握电子邮件内容版本。 使用Email Designer，您可以创建电子邮件和模板，无论这些电子邮件和模板是以您自己的预定义内容开始还是不用。

## 创建电子邮件的关键步骤 {#key-steps-to-create-your-email}

以下是使用电子邮件设计器从头开始创建和设计电子邮件内容的主要步骤：

1. 创建电子邮件并打开其内容。
1. 添加结构组件以塑造电子邮件。 请参阅 [编辑电子邮件结构](#defining-the-email-structure)。
1. 在结构组件中插入内容组件和片段。 请参阅 [添加片段和内容组件](#defining-the-email-structure)。
1. 添加图像并编辑电子邮件的文本。 请参阅 [插入图像](../../designing/using/images.md#inserting-images)。
1. 通过添加个性化字段、链接等，个性化您的电子邮件。 请参 [阅插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)、插入 [链接和在电子邮](../../designing/using/links.md#inserting-a-link) 件中定义动态内容 [](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。
1. 定义电子邮件的主题行。 See [Personalizing the subject line of an email](../../designing/using/subject-line.md#defining-the-subject-line-of-an-email).
1. 预览电子邮件。
1. 保存您的内容，并在确保已定义受众并正确计划发送后继续处理您的消息。

您还可以查看此简介 [视频](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=chi_hans)。

>[!NOTE]
>
>为避免从头开始设计电子邮件内容，您可以使用现成的内容模板。 有关此内容的详细信息，请参 [阅内容模板](../../designing/using/using-reusable-content.md#content-templates)。

### 定义电子邮件结构 {#defining-the-email-structure}

电子邮件设计人员可让您轻松定义电子邮件的结构。 通过使用简单的拖放操作添加和移动结构元素，您可以在数秒内设计电子邮件的形状。

要编辑电子邮件的结构，请执行以下操作：

1. 打开现有内容或创建新的电子邮件内容。
1. 通过 **[!UICONTROL Structure components]** 选择左侧的 **+** 图标访问。

   ![](assets/email_designer_structure.png)

1. 拖放您需要构建电子邮件的结构组件。

   ![](assets/email_designer_structure_components.png)

   在放置结构组件之前，蓝线将实现结构组件的精确位置。 您可以将它放在任何其他组件之间或之下，但不能放在组件内。

   >[!NOTE]
   >
   >一旦放入电子邮件中，您便无法移动或删除组件，除非其中已有内容组件或片段。

1. 多个由一个或多个列组成的结构组件可用。

   选择 **[!UICONTROL n:n column]** 组件以定义所选的列数（3到10）。 您还可以通过移动每列底部的箭头来定义每列的宽度。

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >每个列大小不能低于结构组件总宽度的10%。 无法删除非空列。

定义结构后，您便可以向电子邮件中添加内容片段和组件。

### 使用内容组件 {#about-content-components}

内容组件是原始的空组件，放置到电子邮件中后，您可以编辑这些组件。

您可以在结构组件中添加所需数量的内容组件。 您还可以在结构组件中或移动到其他结构组件中。

以下是电子邮件设计器中可用组件的列表：

- **[!UICONTROL Button]**

   如果需要使用多个按钮，而不是从头开始编辑每个按钮，则可以使用上下文工具栏 **[!UICONTROL Button]** 复制组件。

   您还可以将按钮保存到可重用的片段中。 有关此内容的详细信息，请 [参阅创建内容片段](../../designing/using/using-reusable-content.md#creating-a-content-fragment)[和将内容另存为片段](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)。

1. 选择 **[!UICONTROL Fallback view]** 以在电子邮件设计器中显示回退图像。

- **[!UICONTROL Text]**

   使用此组件可在电子邮件中插入文本。 您可以调整中文本的颜色、样式和大小 **[!UICONTROL Component Settings]**。

- **[!UICONTROL Divider]**

   使用此组件可在电子邮件中插入分隔线。 您可以在中选择换行的颜色、样式和大小 **[!UICONTROL Component Settings]**。

- **[!UICONTROL Html]**

   使用此组件可复制粘贴现有HTML的不同部分。 这使您能够创建免费的模块化HTML组件。

   >[!NOTE]
   >
   >免费的HTML组件可编辑，但选项有限。 如果未嵌入所有样式，请确保在HTML代码的 **head** （头）部分添加正确的CSS，否则电子邮件将无响应。 使用按 **[!UICONTROL Preview]** 钮测试内容的响应性(请参阅预 [览消息](../../sending/using/previewing-messages.md))。

   为了使外部内容符合电子邮件设计人员的要求，Adobe建议从头开始创建邮件，并将现有电子邮件中的内容复制到片段和组件中。

   当您有无法重新创建的内容时，可以使用内容组件从原始电子邮件中复制并粘贴HTML **[!UICONTROL Html]** 代码。 在继续操作之前，请确保您熟悉HTML。

   <!-- A full example is presented below. -->

   >[!NOTE]
   >
   >新内容不会是原始电子邮件的精确副本，但以下步骤将指导您完成尽可能接近的消息创建过程。

   **复制内容之前**

   1. 在您的原始电子邮件中，从您将发送的每封电子邮件中确定每个电子邮件特有的可重用部分。
   1. 保存您要使用的所有图像和资产。
   1. 如果您熟悉HTML，请将原始HTML内容拆分为不同部分。

- **[!UICONTROL Video]**

   使用此组件可在电子邮件中插入视频。

   将视频组件插入电子邮件的结构组件中，然后在中输入视频链接 **[!UICONTROL Component Settings]**。

- **[!UICONTROL Image]**

   使用此组件可在电子邮件中插入图像。

   将图像组件插入结构组件中，然后单击“浏览”以从您的计算机上传图像文件。

- **[!UICONTROL Social]**

   使用此组件可在电子邮件中插入指向社交媒体页面的链接。 您可以选择要显示的链接及其图标的大小 **[!UICONTROL Component Settings]**。

- **[!UICONTROL Carousel]**

   1. 将组件拖放 **[!UICONTROL Carousel]** 到结构组件内。
   1. 浏览以从计算机中选择图像。
   ![](assets/des_carousel_browse.png)

   1. 在窗格 **[!UICONTROL Settings]** 中，设置要在传送中显示的缩略图数。
   1. 从计算机中选择一个备用图像。
   ![](assets/des_carousel_fallback.png)

   传送组件与所有电子邮件程序不兼容。 当电子邮件中不支持传送时，请上传回退以显示图像。

   >[!NOTE]
   >
   >传送组件与以下电子邮件平台兼容：Apple Mail 7、Apple Mail 8、Outlook 2011(Mac)、Outlook 2016(Mac)、Mozilla Thunderbird、iPad和iPad mini iOS、iPhone iOS、Android、AOL（Chrome、Firefox和Safari）。

**相关主题**:

- [创建电子邮件](../../channels/using/creating-an-email.md)
- [在消息中选择受众](../../audiences/using/selecting-an-audience-in-a-message.md)
- [计划消息](../../sending/using/about-scheduling-messages.md)
- [预览消息](../../sending/using/previewing-messages.md)
- [电子邮件渲染](../../sending/using/email-rendering.md)
