---
title: 定义直邮内容
seo-title: 定义直邮内容
description: 定义直邮内容
seo-description: 了解如何为直邮交付定义内容。
page-status-flag: 从未激活
uuid: c1234c06-4d22-46d7-ad1b-3c88660f9b06
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 频道
content-type: 参考
topic-tags: 直邮
discoiquuid: 9e73d6b5-41b4-474b-a880-a0cd599c2d1
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 781904d58f520987e978ad5d1cdc9e34871ca876

---


# 定义直邮内容{#defining-the-direct-mail-content}

您可以在创建向导的最后一个屏幕中定义内容，也可以通过单击交付功能板的“ **内容** ”部分来定义内容。

![](assets/direct_mail_6.png)

定 **[!UICONTROL Content]** 义屏幕特定于直邮渠道。 它分为四个选项卡： **[!UICONTROL Extraction]**、 **[!UICONTROL File structure]****[!UICONTROL Header]** 和 **[!UICONTROL Footer]**。

![](assets/direct_mail_11.png)

## 定义提取 {#defining-the-extraction}

1. 首先，定义提取文件的名称。 单击字段右侧的按钮， **[!UICONTROL Output file]** 然后输入所需的标签。 您可以使用个性化字段、内容块和动态文本(请参 [阅定义内容](../../designing/using/personalization.md#example-email-personalization))。 例如，您可以使用交付ID或提取日期完成标签。

   ![](assets/direct_mail_12.png)

1. 单击或 **[!UICONTROL +]** 按钮 **[!UICONTROL Add an element]** 可添加输出列。 您 **[!UICONTROL Output columns]** 可以定义要导出到输出文件的配置文件信息（列）。

   >[!CAUTION]
   >
   >确保您的配置文件包含邮政地址，因为这些信息对直邮提供商至关重要。 另外，请确保已选中配 **[!UICONTROL Address specified]** 置文件信息中的复选框。 请参阅 [推荐](../../channels/using/about-direct-mail.md#recommendations)。

   ![](assets/direct_mail_13.png)

1. 创建所需数量的列。 您可以通过单击列的表达式和标签来编辑列。

>[!NOTE]
>
>有关输出列定义的详细信息，请参阅“提取文 [件](../../automating/using/extract-file.md) ”工作流活动部分。

## 定义文件结构 {#defining-the-file-structure}

“文 **件结构** ”选项卡允许您配置要导出的文件的输出、日期和编号格式。

![](assets/direct_mail_14.png)

>[!NOTE]
>
>“提取文件”工作流活动部分详细介绍 [了可用](../../automating/using/extract-file.md) 的选项。

## 定义页眉和页脚 {#defining-the-header-and-footer}

有时，您可能需要在提取文件的开头或结尾添加信息。 为此，请使用配 **[!UICONTROL Header]** 置屏 **[!UICONTROL Footer]** 幕的和选 **[!UICONTROL Content]** 项卡。

![](assets/direct_mail_7.png)

例如，您可能希望在文件标题中包含发送者信息（对于直邮提供者）。 可以使用交付上下文中提供的信息个性化页脚和页眉。 请参阅 [定义内容](../../designing/using/personalization.md#example-email-personalization)。

发送者地址在直接邮件属 **[!UICONTROL Send]** 性的部分或模板级别定义。

![](assets/direct_mail_24.png)

