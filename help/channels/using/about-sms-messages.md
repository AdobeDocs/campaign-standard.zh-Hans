---
title: 关于SMS消息
seo-title: 关于SMS消息
description: 关于SMS消息
seo-description: 发现Adobe Campaign中SMS频道的主要特殊性。
page-status-flag: 从未激活
uuid: 14dc7434-8171-4ad1-9540-52ca637659a9
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: sms-messages
discoiquuid: 6134fe72-77de-4fd0-b794-4d966 efaccf
delivercontext-tags: DeliquyCreate，向导；交付，SMSContent，返回
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# About SMS messages{#about-sms-messages}

Adobe Campaign允许您提供SMS(短消息服务)消息。

>[!NOTE]
>
>SMS频道是加载项。请检查您的许可协议。

对于SMS消息，您只能以文本格式创建、修改和个性化消息。您还可以在发送SMS消息之前进行预览。

如果SMS消息处于GSM编码中，则限制为160个字符；如果在Unicode中，则仅限70个字符。但是，某些特殊字符可能会影响消息的长度。For more on this, refer to the [SMS encoding](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

SMS messages can be created from the **[!UICONTROL Marketing activities]** menu, from a campaign, or in a workflow, see [Creating an SMS message](../../channels/using/creating-an-sms-message.md).

要向手机发送SMS消息，您需要：

* **[!UICONTROL Routing]****[!UICONTROL Mobile (SMS)]** 在渠道中配置 **[!UICONTROL Bulk delivery]** 了模式的外部帐户。For more on this, refer to the [Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) section.
* 正确链接到此外部帐户的交付模板。

**相关主题：**

* [管理模板](../../start/using/about-templates.md)
* [SMS配置](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)

## SMS delivery template {#sms-delivery-template}

Adobe Campaign为移动设备提供了一个交付模板。This template must be correctly linked to the external account used for the **[!UICONTROL Mobile (SMS)]** channel. 要访问和修改它，请执行以下操作：

1. Select **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** from the advanced menu.
1. Hover over the **[!UICONTROL Send via SMS]** template with the mouse and select the **Duplicate element** option.
1. 选择新模板。
1. Click the **[!UICONTROL Edit properties]** button.
1. In the **[!UICONTROL Advanced parameters]** section of the template properties, make sure that the template is linked to the external account to be used for delivering SMS.

   ![](assets/sms_template.png)

**相关主题：**

* [管理模板](../../start/using/about-templates.md)

