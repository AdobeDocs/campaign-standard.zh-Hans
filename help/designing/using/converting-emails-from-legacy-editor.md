---
title: 将旧版编辑器电子邮件转换为Email Designer
description: 了解如何将旧版编辑器电子邮件中创建的电子邮件用到Email Designer。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 2b024052-ed42-44f3-9990-be7425cc79d7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 8%

---

# 转换旧版编辑器的电子邮件内容 {#converting-an-html-content}

开始使用Email Designer，并通过在旧版编辑器中创建的电子邮件HTML构建可重用模板和片段。

通过此用例，您可以使用HTML电子邮件在Email Designer中将其划分为HTML组件来创建电子邮件设计器模板。

>[!NOTE]
>
>与兼容模式一样，HTML组件也可以使用有限的选项进行编辑：您只能执行就地编辑。

>[!IMPORTANT]
>
>本节适用于熟悉HTML代码的高级用户。

## 准备电子邮件内容

1. 选择HTML电子邮件。
1. 确定用于划分HTML电子邮件的部分。
1. 从HTML中剪下几个街区。

## 创建电子邮件结构

1. 打开 **[!UICONTROL Email Designer]**  创建空的电子邮件内容。
1. 设置正文级别属性：背景颜色、宽度等。 有关更多信息，请参阅[编辑电子邮件样式](../../designing/using/styles.md)。
1. 添加具有部分的结构组件，数量不限。 有关更多信息，请参阅[编辑电子邮件结构](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

## 添加HTML内容

1. 向每个结构组件中添加一个HTML组件。 有关更多信息，请参阅[添加片段和组件](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 将HTML复制并粘贴到每个组件中。

## 管理电子邮件的样式 {#manage-the-style-of-your-email}

1. 切换到 **[!UICONTROL Mobile view]**. 有关更多信息，请参阅[此小节](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)。

1. 要解决此问题，请切换到源代码模式，并将样式部分复制粘贴到新的样式部分中。 例如：

   ```
   <style type="text/css">
   a {text-decoration:none;}
   body {min-width:100% !important; margin:0 auto !important; padding:0 !important;}
   img {line-height:100%; text-decoration:none; -ms-interpolation-mode:bicubic;}
   ...
   </style>
   ```

   >[!NOTE]
   >
   >请确保将样式添加到其他自定义样式标记中。
   >
   >请勿修改Email Designer生成的CSS：
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`

1. 返回移动设备视图以检查内容是否正确显示并保存更改。

## 用例

让我们尝试将此在旧版编辑器中创建的电子邮件转换为 **[!UICONTROL Email Designer]** 模板。

### 识别电子邮件的部分

我们可以确定此电子邮件中的11个部分。

![](assets/html-dce-view-mail.png)

要确定HTML的哪个部分，可以选择该元素。

![](assets/breadcrumbs.png)

要查看电子邮件的HTML版本，请单击 **[!UICONTROL Show source]**.

### 创建电子邮件模板及其结构

1. 拖放 **[!UICONTROL Structure components]**  反映我们电子邮件的布局。

1. 根据需要重复多次。 我们需要创建11个结构组件。

   ![](assets/structure-components-migration.png)

### 插入HTML内容组件

1. 插入 **[!UICONTROL HTML component]**  在每个 **[!UICONTROL Structure component]** .

   ![](assets/html-components.png)

1. 对于每个部分，单击 **[!UICONTROL Show source code]** .

   ![](assets/show-source-code.png)

1. 插入HTML部分。

1. 单击 **[!UICONTROL Save]**。

您现在可以检查电子邮件的呈现方式。

![](assets/migrated-email-result.png)

### 管理样式以适合移动设备视图

1. 插入CSS元素以确保您的电子邮件适合移动设备视图。

1. 切换到源代码，并将您的样式部分复制粘贴到新的样式部分中。

有关详细信息，请参见 [管理电子邮件的样式](#manage-the-style-of-your-email).

您的旧电子邮件现在可在Email Designer中使用。
