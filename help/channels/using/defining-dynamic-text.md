---
title: 定义动态文本
description: 了解如何根据Adobe Campaign中定义的条件向用户动态显示不同的文本。
page-status-flag: never-activated
uuid: bbcd200c-4fb4-467b-ba39-09b8bee9bcaa
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: defining-conditional-content
discoiquuid: 6bb6cee3-5674-4113-8073-5a9572b3e830
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b70e18be29fd48d102313f6d741e9ffe053cc34

---


# 定义动态文本{#defining-dynamic-text}

动态文本的定义方式与动态内容相同。 请参阅定义 [动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) 。

>[!NOTE]
>
>对于SMS和推送，您只能定义动态文本。 您可以在登录页面中定义动态内容和文本。 如果要使用电子邮件设计器定义动态文 [本](../../designing/using/designing-content-in-adobe-campaign.md)，请参阅 [在电子邮件中定义动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。

以下示例演示如何定义SMS消息中的动态文本。

1. 在消息或登录页面的正文中选择文本。
1. Click **[!UICONTROL Enable dynamic text]**.

   ![](assets/dynamic_text_sms_1.png)

   该选 **[!UICONTROL Dynamic text]** 项显示在调色板中。 它的配置方式与动态内容相同。

1. 选择变体。

   ![](assets/dynamic_text_sms_2.png)

1. 为此变体定义一个条件。

   ![](assets/dynamic_text_sms_4.png)

为至少一个变体定义条件后，动态文本周围将显示紫色框架。

![](assets/dynamic_text_sms_3.png)

