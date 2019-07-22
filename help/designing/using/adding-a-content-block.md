---
title: 添加内容块
seo-title: 添加内容块
description: 添加内容块
seo-description: 发现可用于个性化消息的各种现成动态内容块，并了解如何创建自定义内容块。
page-status-flag: 从未激活
uuid: 08153ea0-42fb-4c0b-8d4b-940740748d6
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 设计
content-type: reference
topic-tags: 个性化内容
discoiquuid: 3ffda143-f42 a-4cf9-b43 c-e53 d2454025
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 84bc011b079c9f620ea672bf081e54adc023aa07

---


# Adding a content block{#adding-a-content-block}

Adobe Campaign提供预配置的内容块列表。这些内容块是动态的、个性化的并具有特定的渲染。例如，您可以添加问候或指向镜像页面的链接。

>[!NOTE]
>
>The images below show how to insert a content block using the [Email Designer](../../designing/using/about-email-content-design.md#about-the-email-designer) for an email.

添加内容块：

1. Click inside a text block, click the **[!UICONTROL Personalize]** icon from the contextual toolbar and select **[!UICONTROL Insert content block]**. For more on the Email Designer interface, see [this section](../../designing/using/about-email-content-design.md#email-designer-interface).

   ![](assets/email_content_block_1.png)

1. 选择要插入的内容块。可用的基块因上下文(电子邮件或登陆页面)而异。

   ![](assets/email_content_block_2.png)

1. Click **[!UICONTROL Save]**.

内容块的名称会显示在编辑器中，并以黄色突出显示。在生成个性化时，它会自动适应配置文件。

![](assets/email_content_block_3.png)

现成的内容块有：

* **[!UICONTROL Database URL in emails (EmailUrlBase)]**：此内容块只能在 **交付**&#x200B;中使用。
* **[!UICONTROL Mirror page URL (MirrorPageUrl)]**：此内容块只能在 **交付**&#x200B;中使用。
* **[!UICONTROL Link to mirror page (MirrorPage)]**：此内容块只能在 **交付**&#x200B;中使用。
* **[!UICONTROL Greetings (Greetings)]**
* **[!UICONTROL Unsubscription link (UnsubscriptionLink)]**：此内容块只能在 **交付**&#x200B;中使用。
* **[!UICONTROL Social network sharing links (LandingPageViralLinks)]**：此内容块只能在 **登陆页面**&#x200B;中使用。
* **[!UICONTROL Default sender name (DefaultSenderName)]**：此内容块只能在 **交付**&#x200B;中使用。
* **[!UICONTROL Name of default reply-to email address (DefaultReplyName)]**：此内容块只能在 **交付**&#x200B;中使用。
* **[!UICONTROL Email address of default sender (DefaultSenderAddress)]**：此内容块只能在 **交付**&#x200B;中使用。
* **[!UICONTROL Default error email address (DefaultErrorAddress)]**：此内容块只能在 **交付**&#x200B;中使用。
* **[!UICONTROL Default reply-to email address (DefaultReplyAddress)]**：此内容块只能在 **交付**&#x200B;中使用。
* **[!UICONTROL Brand name (BrandingUsualName)]**
* **[!UICONTROL Link to the brand website (BrandingWebSiteLink)]**
* **[!UICONTROL Brand logo (BrandingLogo)]**
* **[!UICONTROL Notification style (notificationStyle)]**

## Creating custom content blocks {#creating-custom-content-blocks}

您可以定义将插入消息或登陆页面的新内容块。

要创建内容块，请执行以下步骤：

1. Click **[!UICONTROL Resources > Content blocks]** from the advanced menu to access the list of content blocks.
1. Click the **[!UICONTROL Create]** button or duplicate a pre-existing content block.

   ![](assets/content_bloc_01.png)

1. 输入标签。
1. Select the block's **[!UICONTROL Content type]**. 有三个可用选项：

   * **[!UICONTROL Shared]**：内容块可用于交付或登陆页面。
   * **[!UICONTROL Delivery]**：内容块只能在交付中使用。
   * **[!UICONTROL Landing page]**：内容块只能在登陆页面中使用。
   ![](assets/content_bloc_02.png)

1. You can select a **[!UICONTROL Targeting dimension]**. For more on this, see [About targeting dimension](../../designing/using/adding-a-content-block.md#about-targeting-dimension).

   ![](assets/content_bloc_04.png)

1. You can select the **[!UICONTROL Depends on format]** option to define two different blocks: one for HTML emails, and one for emails in text format. 随后将在编辑器中显示两个选项卡(HTML和文本)以定义相应的内容。

   ![](assets/content_bloc_03.png)

1. Enter the content of the content block(s), and click the **[!UICONTROL Create]** button.

您的内容块现在可用于消息或登陆页面的内容编辑器。

>[!CAUTION]
>
>When editing the content of a block, make sure there are no extra white spaces between the beginning and the end of your *if* statements. 在HTML中，空白会显示在屏幕上，因此它们会影响您的内容布局。

## About targeting dimension {#about-targeting-dimension}

定位维度允许您定义可以使用内容块的消息类型。这是为了防止在消息中使用不适当的块，这会导致错误。

实际上，在编辑消息时，您只能选择包含与该消息的定位维度兼容的定位维度的内容块。

For example, the **[!UICONTROL Unsubscription link]** block's targeting dimension is **[!UICONTROL Profiles]** because it contains personalization fields specific to the **[!UICONTROL Profiles]** resource. Therefore, you cannot use an **[!UICONTROL Unsubscription link]** block in an [event transactional message](../../channels/using/event-transactional-messages.md), because the targeting dimension of that type of message is **[!UICONTROL Real-time events]**. However, you can use the **Unsubscription link** block in a [profile transactional message](../../channels/using/profile-transactional-messages.md), because the targeting dimension of that type of message is **Profiles**. Finally, the **[!UICONTROL Link to mirror page]** block does not have a targeting dimension, so you can use it in any message.

如果将此字段留空，内容块将与所有消息兼容，无论定位维度是什么。如果设置定位维度，该块将仅与具有相同定位维度的消息兼容。

For more on this, refer to [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
