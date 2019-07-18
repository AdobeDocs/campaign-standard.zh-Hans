---
title: 定义直接邮件内容
seo-title: 定义直接邮件内容
description: 定义直接邮件内容
seo-description: 了解如何定义内容以供直接发送邮件。
page-status-flag: 从未激活
uuid: c1234c06-4d22-46d7-ad1 b-3c88660 f9 b06
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: 直邮
discoiquuid: 9e73d6b5-41b4-474b-a880-a0 cd5999 c2 d1
context-tags: delivery，directmailContent，返回
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Defining the direct mail content{#defining-the-direct-mail-content}

You can either define the content in the last screen of the creation wizard or by clicking on the **Content** section of the delivery dashboard.

![](assets/direct_mail_6.png)

**[!UICONTROL Content]** 定义屏幕特定于直接邮寄渠道。It is divided into four tabs: **[!UICONTROL Extraction]**, **[!UICONTROL File structure]**, **[!UICONTROL Header]** and **[!UICONTROL Footer]**.

![](assets/direct_mail_11.png)

## Defining the extraction {#defining-the-extraction}

1. 首先定义提取文件的名称。Click on the button to the right of the **[!UICONTROL Output file]** field and enter the desired label. You can use personalization fields, content blocks and dynamic text (see [Defining content](../../designing/using/example--email-personalization.md)). 例如，您可以使用配送ID或提取日期完成标签。

   ![](assets/direct_mail_12.png)

1. Click the **[!UICONTROL +]** or **[!UICONTROL Add an element]** button to add an output column. The **[!UICONTROL Output columns]** let you define the profile information (columns) to be exported into the output file.

   >[!CAUTION]
   >
   >请确保您的配置文件包含邮寄地址，因为此信息对于直接邮件提供商至关重要。Also make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information. See [Recommendations](../../channels/using/about-direct-mail.md#recommendations).

   ![](assets/direct_mail_13.png)

1. 根据需要创建任意多个列。您可以通过单击其表达式和标签来编辑列。

>[!NOTE]
>
>For more information on output column definition, refer to the [Extract file](../../automating/using/extract-file.md) workflow activity section.

## Defining the file structure {#defining-the-file-structure}

**“文件结构** ”选项卡允许您配置将导出的文件的输出、日期和编号格式。

![](assets/direct_mail_14.png)

>[!NOTE]
>
>[Extract文件](../../automating/using/extract-file.md) 工作流活动部分中详细介绍了可用选项。

## Defining the header and footer {#defining-the-header-and-footer}

有时可能需要在提取文件的开头或结尾添加信息。For this, use the **[!UICONTROL Header]** and **[!UICONTROL Footer]** tabs of the **[!UICONTROL Content]** configuration screen.

![](assets/direct_mail_7.png)

例如，您可能希望将发送方信息包含在文件标题中的发送方信息中。可以使用交付上下文中提供的信息来个性化页脚和标题。See [Defining content](../../designing/using/example--email-personalization.md).

The sender address is defined in the **[!UICONTROL Send]** section of the direct mail properties or at the template level.

![](assets/direct_mail_24.png)

