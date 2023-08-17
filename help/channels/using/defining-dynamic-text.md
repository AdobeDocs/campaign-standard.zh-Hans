---
title: 定义动态文本
description: 了解如何根据Adobe Campaign中定义的条件向用户动态显示各种文本。
audience: designing
content-type: reference
topic-tags: defining-conditional-content
feature: SMS
role: User
level: Beginner
exl-id: 649e3428-a3bf-470f-923c-04d9a57a208f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 3%

---

# 定义动态文本{#defining-dynamic-text}

动态文本的定义方式与动态内容相同。 请参阅 [定义动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) 部分。

>[!NOTE]
>
>对于短信和推送，您只能定义动态文本。 您可以在登陆页面中定义动态内容和文本。 如果要使用定义动态文本 [电子邮件设计工具](../../designing/using/designing-content-in-adobe-campaign.md)，请参见 [定义电子邮件中的动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

请注意，替代对（未包含在Unicode字符集的基本多语言平面中的字符）不能以2字节（16位）存储，并且需要编码为2个UTF-16字符。 这些字符包括一些CJK表意文字，大多数表情符号和一些语言。
<br>这些字符可能会导致动态文本中存在某些不兼容问题。 在发送消息之前，您需要执行强有力的测试。


以下示例说明如何在短信消息中定义动态文本。

1. 在消息正文或登陆页面中选择文本。
1. 单击 **[!UICONTROL Enable dynamic text]**。

   ![](assets/dynamic_text_sms_1.png)

   此 **[!UICONTROL Dynamic text]** 选项将显示在面板中。 它的配置方式与动态内容相同。

1. 选择变体。

   ![](assets/dynamic_text_sms_2.png)

1. 为此变量定义条件。

   ![](assets/dynamic_text_sms_4.png)

为至少一个变体定义条件后，动态文本周围会显示一个紫色框架。

![](assets/dynamic_text_sms_3.png)
