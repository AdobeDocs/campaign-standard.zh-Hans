---
title: 个性化发送方
seo-title: 个性化发送方
description: 个性化发送方
seo-description: 了解如何个性化消息发送方的姓名或地址。
page-status-flag: 从未激活
uuid: 7aa08d5d-9e6c-4dac-bff8-6fde85368 c2 d
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 设计
content-type: reference
topic-tags: 个性化内容
discoiquuid: 49532f6b-3cd0-4d03-932e-bcb7 d05 c74 d4
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Personalizing the sender{#personalizing-the-sender}

## Email sender {#email-sender}

To define the name of the sender which will appear in the header of messages sent, go the **[!UICONTROL Properties]** tab of the Email Designer home page (accessible through the home icon).

![](assets/delivery_content_edition16.png)

* **[!UICONTROL From: name]** 字段允许您输入发送者姓名。By default, the default **Sender name** block is automatically entered in the field. Adobe Campaign refers to the email channel configuration (from the advanced menu **[!UICONTROL Administration > Channels > Email > Email accounts]** via the Adobe Campaign logo) to designate this sender.

   You can change the sender name by clicking the **Sender name** block. 该字段随后变为可编辑，您可以输入要使用的名称。

   此字段可个性化。为此，您可以单击发送者姓名下方的图标，添加个性化字段、内容块和动态内容。

* **[!UICONTROL From: email address]** 此字段无法从此部分进行编辑。您可以通过从其仪表板编辑电子邮件的属性来更改它。For more on this, see [List of email advanced parameters](../../administration/using/configuring-email-channel.md#advanced-parameters).

>[!NOTE]
>
>标题参数不能为空。发送方地址必须允许发送电子邮件(RFC标准)。Adobe Campaign会检查输入的电子邮件地址的语法。

**相关主题：**

* [插入个性化字段](../../designing/using/inserting-a-personalization-field.md)
* [添加内容块](../../designing/using/adding-a-content-block.md)
* [在电子邮件中定义动态内容](../../designing/using/defining-dynamic-content-in-an-email.md)

## SMS sender {#sms-sender}

您可以个性化SMS发送方的姓名。For more on this, refer to the [SMS configuration](../../administration/using/configuring-sms-channel.md#configuring-sms-properties) section.
