---
title: 个性化SMS消息
seo-title: 个性化SMS消息
description: 个性化SMS消息
seo-description: 在个性化SMS消息时发现翻译选项的特殊性。
page-status-flag: 从未激活
uuid: 123fe70c-c279-40a3-88b6-6bfb2453 ec83
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: sms-messages
discoiquuid: 7c6485c-e3 c2-4caa-a547-002990ae3 f9
delivercontext-tags: DeliquyCreate，向导；交付，smsContent，back；交付，SMSContent，返回
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Personalizing SMS messages{#personalizing-sms-messages}

The principles for personalizing SMS messages are the same as those for [emails](../../designing/using/inserting-a-personalization-field.md). 但是，您必须了解转换选项，因为这些选项可能会影响编码，因此需要发送SMS消息。For more on this, refer to the [Transliteration and SMS length](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

这里我们会采用一个示例SMS消息，其中包含个性化字段，根据是否选择了翻译，将不会生成相同数量的发送：

**&lt; firstName&gt;&lt; LastName&gt;，新产品现已可用。Come and check them out in store!**

* 对于名为“John Smith”的收件人，因为它不包含特殊字符，Adobe Campaign将选择GSM编码，以每SMS短消息授权最多160个字符。因此，消息将发送到单个部分。
* 对于名为“raphaël Forêt”的收件人，字符'ë'和'force'无法在GSM中进行编码。根据是否启用了翻译，Adobe Campaign可以在以下两种行为之间进行选择：

   * 如果translation is authorized'ë'and'force'will replace by'e'，即可使用GSM编码，因此最多可在SMS中使用160个字符。此消息将作为单个SMS消息发送，但会略有改动。
   * 如果未授权翻译，Adobe Campaign将选择以二进制格式(Unicode)发送消息：因此，所有字符都将因此发送。由于Unicode中的SMS消息仅限于70个字符，Adobe Campaign将必须以两部分发送消息。

>[!NOTE]
>
>根据每个消息自动选择最佳编码的算法会按情况单独执行。这样，只能在Unicode中发送需要Unicode编码的个性化消息；所有其他人都将使用GSM编码。

