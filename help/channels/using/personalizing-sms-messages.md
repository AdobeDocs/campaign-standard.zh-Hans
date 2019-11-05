---
title: 个性化短信消息
description: 发现个性化SMS消息时音译选项的特异性。
page-status-flag: 从未激活
uuid: 123fe70c-c279-40a3-88b6-6bfb2453ec83
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 频道
content-type: 参考
topic-tags: sms消息
discoiquuid: 7c64785c-e3c2-4caa-a547-002990ae3f9
delivercontext-tags: deliveryCreation，向导；delivery,smsContent,back;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 个性化短信消息{#personalizing-sms-messages}

个性化SMS消息的原则与电子邮件的原 [则相同](../../designing/using/personalization.md#inserting-a-personalization-field)。 但是，您必须注意音译选项，因为这些选项会影响编码，因此也会影响要发送的SMS消息数。 有关详细信息，请参阅音 [译和SMS长度部分](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) 。

这里，我们采集一个包含个性化字段的SMS短消息示例，根据是否已选择音译，这些字段将不会生成相同数量的发送：

**&lt; FirstName &gt; &lt; lastName &gt;，新产品现已推出。 来店里看看！**

* 对于名为“John Smith”的收件人，由于其中不包含特殊字符，Adobe Campaign将选择GSM编码，该编码将对每条SMS消息最多160个字符进行授权。 因此，消息将通过单个部分发送。
* 对于名为“Raphaël Forêt”的接收者，字符“ë”和“ê”不能用GSM编码。 根据是否启用了音译，Adobe Campaign可以在两种行为之间进行选择：

   * 如果音译被授权为“ë”,“ê”将被“e”取代，这意味着可以使用GSM编码，因此在SMS中最多可使用160个字符。 此消息将作为单条SMS消息发送，但稍作更改。
   * 如果音译未获得授权，Adobe Campaign将选择以二进制格式(Unicode)发送消息：因此，将按此发送所有字符。 由于Unicode中的SMS消息仅限70个字符，Adobe Campaign将必须分两部分发送消息。

>[!NOTE]
>
>自动选择最佳编码的算法是针对每条消息逐个执行的。 这样，只有需要Unicode编码的个性化消息才会以Unicode发送；其他所有人都将使用GSM编码。

## SMS发送方 {#sms-sender}

您可以个性化SMS发送者的姓名。 有关详细信息，请参阅 [SMS配置部分](../../administration/using/configuring-sms-channel.md#configuring-sms-properties) 。
