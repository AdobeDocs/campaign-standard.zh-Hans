---
title: 电子邮件设计器入门
description: 开始使用Email Designer构建电子邮件内容。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Beginner
exl-id: 47f53290-2190-4181-bcd5-e60287189c41
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 5%

---

# 电子邮件设计器入门 {#quick-start}

电子邮件Designer提供了四种创建电子邮件的方式。

您可以在电子邮件Designer[&#128279;](#without-existing-content)中新建电子邮件：

1. 通过轻松添加结构和内容组件并个性化其内容以快速发送投放，您可以&#x200B;**从空白画布**&#x200B;创建电子邮件。 您还可以完全管理样式元素。 有关详细信息，[快速入门](#from-scratch-email)或参阅[完整的文档](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

1. 您可以&#x200B;**从现成模板**&#x200B;创建电子邮件，方法是：选择一个模板，然后从此处构建新的电子邮件内容。 [了解详情](#building-content-from-an-out-of-the-box-template)

您还可以创建包含现有内容[&#128279;](#with-existing-content)的电子邮件：

1. 您可以&#x200B;**转换现有HTML内容**（在外部或在旧版编辑器中创建）。 [了解详情](#converting-an-html-content)
1. 您可以在兼容模式下立即&#x200B;**导入现有HTML内容**。 [了解详情](#compatibility-mode)

| 无内容 | 包含内容 |
|---|---|
| [从头开始创建电子邮件](#from-scratch-email) | [转换现有HTML内容](#converting-an-html-content) |
| [从现成模板生成内容](#building-content-from-an-out-of-the-box-template) | [正在导入现有HTML](#compatibility-mode) |

## 使用编辑器设计电子邮件 {#without-existing-content}

>[!NOTE]
>
>在这两种创建策略中，在发送电子邮件之前填写主题行都至关重要。 了解如何[添加主题行](#add-a-subject-line)。

### 从头开始创建电子邮件 {#from-scratch-email}

您可以轻松创建电子邮件、添加组件并个性化其内容以快速发送投放。 如果需要，您可以根据内容调整样式选项。 有关管理样式设置和内联属性的详细信息，请参阅[编辑电子邮件样式](../../designing/using/styles.md)。

1. 创建电子邮件。
1. 关闭主页。

### 添加主题行 {#add-a-subject-line}

发送电子邮件时，必须填写主题行。 有关详细信息，请参阅[定义电子邮件的主题行](../../designing/using/subject-line.md)。

1. 转到Email Designer主页的&#x200B;**[!UICONTROL Properties]**&#x200B;选项卡（通过“主页”图标访问）并填写&#x200B;**[!UICONTROL Subject]**&#x200B;部分。

![](assets/subject-line-quick-start.png)

### 添加结构组件 {#add-structure-components}

结构组件将定义电子邮件的布局。 有关详细信息，请参阅[定义电子邮件的结构](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

在结构组件中，拖放要使用的布局的组件。

>[!NOTE]
>
>您可以选择将在电子邮件中加总的不同内容布局。

![](assets/structure-components-quick-start.png)

### 添加内容组件 {#add-content-components}

您可以向电子邮件添加多个内容组件，如图像、文本和按钮。 有关详细信息，请参阅[内容组件](../../designing/using/designing-from-scratch.md#about-content-components)。

* **图像**

   1. 在&#x200B;**内容组件**&#x200B;中，将图像拖放到某个结构组件中。
   1. 单击&#x200B;**浏览**。
   1. 从计算机中选择图像文件。

  ![](assets/browse-image-quick-start.png)

* **个性化文本**

   1. 在&#x200B;**内容组件**&#x200B;中，将文本拖放到某个结构组件中。
   1. 单击组件并输入文本。
   1. 要添加个性化字段，请单击工具栏中的&#x200B;**插入个性化字段**。
   1. 选择所需的字段，如“First Name（名字）”。

  ![](assets/edit-text-quick-start.png)

* **HTML**

   1. 在&#x200B;**内容组件**&#x200B;中，将HTML拖放到您的某个结构组件中。
   1. 单击&#x200B;**显示源代码**。
   1. 输入您的HTML内容。
   1. 单击&#x200B;**保存**。

  ![](assets/html-component-source-code.png)

  如果您熟悉HTML，可以使用&#x200B;**[!UICONTROL Html]** HTML组件从原始页脚复制粘贴内容代码。 有关此内容的详细信息，请参阅[关于内容组件](../../designing/using/designing-from-scratch.md#about-content-components)。

  ![](assets/des_loading_compatible_fragment_9.png)

### 设置电子邮件组件的样式

您可以调整电子邮件样式，例如通过更改组件的边距。 有关管理样式设置和内联属性的详细信息，请参阅[编辑电子邮件样式](../../designing/using/styles.md)。

1. 单击您的&#x200B;**文本组件**。
1. 在右侧的调色板中，转到&#x200B;**填充**。
1. 单击锁定图标可中断上下或左右参数之间的同步。
1. 根据需要调整&#x200B;**填充**。
1. 单击&#x200B;**保存**。

![](assets/padding-quick-start.png)

您现在可以保存并发送电子邮件。

### 从现成模板构建内容 {#building-content-from-an-out-of-the-box-template}

您可以从现成模板（如客户欢迎消息、新闻稿和重新参与电子邮件）构建电子邮件并对其进行个性化。

1. 创建电子邮件并打开其内容。 有关此内容的详细信息，请参阅[创建电子邮件](../../channels/using/creating-an-email.md)。
1. 单击主页图标以访问&#x200B;**[!UICONTROL Email Designer]**&#x200B;主页。
1. 单击&#x200B;**[!UICONTROL Templates]**&#x200B;选项卡。
1. 选择现成的HTML模板。
不同的模板提供了几种类型元素的各种组合。 例如，“羽化”模板具有边距，而“阿斯特罗”模板没有。 有关详细信息，请参阅[内容模板](../../designing/using/using-reusable-content.md#content-templates)。
1. 转到Email Designer主页的&#x200B;**[!UICONTROL Properties]**&#x200B;选项卡（通过“主页”图标访问）并填写&#x200B;**[!UICONTROL Subject]**&#x200B;部分。
1. 您可以组合这些元素以构建许多电子邮件变体。 例如，您可以通过选择结构组件并单击上下文工具栏中的&#x200B;**[!UICONTROL Duplicate]**&#x200B;来复制电子邮件部分。
1. 您可以使用左侧的蓝色箭头来移动元素，以将结构组件拖动到另一个组件下方或上方。 有关更多信息，请参阅[编辑电子邮件结构](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 您还可以移动组件以更改每个结构元素的组织。 有关更多信息，请参阅[添加片段和组件](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 根据需要修改每个元素的内容：图像、文本、链接。
1. 如果需要，根据内容调整样式选项。 有关更多信息，请参阅[编辑电子邮件样式](../../designing/using/styles.md)。

## 使用现有电子邮件内容 {#with-existing-content}

如果要构建可组合成可在多个电子邮件中重复使用的模块化模板和片段的框架，应考虑将电子邮件HTML转换为电子邮件Designer模板。

### 转换HTML内容 {#converting-an-html-content}

此用例提供了一种将HTML电子邮件快速转换为电子邮件Designer组件的方法。 有关此主题的更多信息，请参阅[转换HTML内容](../../designing/using/using-existing-content.md#converting-an-html-content)。

>[!CAUTION]
>
>本节适用于熟悉HTML代码的用户。

>[!NOTE]
>
>与兼容模式一样，HTML组件也可以使用有限的选项进行编辑：您只能执行就地编辑。


### 导入和编辑HTML电子邮件 {#compatibility-mode}

上传内容时，该内容必须包含特定标记，以便与电子邮件Designer的WYSIWYG编辑器完全兼容并可编辑。

有关将现有电子邮件转换为与Designer兼容的电子邮件的详细信息，请参阅[此部分](../../designing/using/using-existing-content.md#compatibility-mode)。
