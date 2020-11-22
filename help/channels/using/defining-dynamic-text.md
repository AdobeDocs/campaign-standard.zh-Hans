---
solution: Campaign Standard
product: campaign
title: 定义动态文本
description: 了解如何根据Adobe Campaign中定义的条件向用户动态显示不同的文本。
audience: designing
content-type: reference
topic-tags: defining-conditional-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 3%

---


# 定义动态文本{#defining-dynamic-text}

动态文本的定义方式与动态内容相同。 请参阅定 [义动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) 。

>[!NOTE]
>
>对于SMS和推送，您只能定义动态文本。 您可以在登陆页中定义动态内容和文本。 如果要使用电子邮件设计器定义 [动态文本](../../designing/using/designing-content-in-adobe-campaign.md)，请 [参阅定义电子邮件中的动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。

请注意，替代对（Unicode字符集的基本多语言平面中未包含的字符）不能以2字节（16位）存储，需要将其编码为2个UTF-16字符。 这些字符包括一些CJK表意文字、大多数表情符号和一些语言。
<br>这些字符可能会导致动态文本中出现一些不兼容问题。 在发送消息之前，您需要执行强测试。


以下示例演示如何定义SMS消息中的动态文本。

1. 在邮件或登陆页正文中选择文本。
1. 单击 **[!UICONTROL Enable dynamic text]**.

   ![](assets/dynamic_text_sms_1.png)

   该选 **[!UICONTROL Dynamic text]** 项将显示在调色板中。 其配置方式与动态内容相同。

1. 选择变体。

   ![](assets/dynamic_text_sms_2.png)

1. 定义此变体的条件。

   ![](assets/dynamic_text_sms_4.png)

为至少一个变体定义条件后，动态文本周围将显示紫色框架。

![](assets/dynamic_text_sms_3.png)
