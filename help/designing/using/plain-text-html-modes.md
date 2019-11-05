---
title: 纯文本和 HTML 模式
description: 发现纯文本和HTML模式
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


# 纯文本和 HTML 模式 {#plain-text-and-html-modes}

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
