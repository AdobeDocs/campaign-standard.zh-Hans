---
title: 关于短信消息
description: 了解Adobe Campaign中短信渠道的主要特性。
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
feature: SMS
role: User
level: Beginner
exl-id: a7f22d92-dbf9-4c2b-8fc1-1e31d1e5e79c
TQID: https://experienceleague.adobe.com/d0IcWAf5j-JUAKKeC84Fxm-mZsfuMJ2k6GmhQfdQeFk
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 267
ht-degree: 29%

---

# 关于短信消息{#about-sms-messages}

Adobe Campaign允许您投放短信（短信服务）消息。

>[!NOTE]
>
>短信渠道是一个加载项。 请核实您的许可协议。

对于短信消息，您可以仅以文本格式创建、修改和个性化消息。 您还可以在发送短信消息之前进行预览。

如果短信消息采用GSM编码，则长度限制为160个字符；如果短信消息采用Unicode，则长度限制为70个字符。 但是，某些特殊字符会影响消息的长度。 有关更多信息，请参阅[短信编码](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)部分。

可从&#x200B;**[!UICONTROL Marketing activities]**&#x200B;菜单、营销策划或工作流创建短信消息，请参阅[创建短信消息](../../channels/using/creating-an-sms-message.md)。

要将短信消息发送到手机，您需要：

* 在 **[!UICONTROL Mobile (SMS)]** 渠道上使用 **[!UICONTROL Bulk delivery]** 模式配置的 **[!UICONTROL Routing]** 外部帐户。 有关更多信息，请参阅[路由](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)一节。
* 正确链接到此外部帐户的投放模板。

**相关主题：**

* [管理模板](../../start/using/marketing-activity-templates.md)
* [短信配置](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [短信报告](../../reporting/using/sms-report.md)
* [Campaign Standard Mobile指南](../../channels/using/get-started-communication-channels.md)

## 短信投放模板 {#sms-delivery-template}

Adobe Campaign提供了用于移动设备的投放模板。 此模板必须正确链接到用于&#x200B;**[!UICONTROL Mobile (SMS)]**&#x200B;渠道的外部帐户。 要访问和修改它，请执行以下操作：

1. 从高级菜单中选择&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**。
1. 将鼠标悬停在&#x200B;**[!UICONTROL Send via SMS]**&#x200B;模板上并选择&#x200B;**重复元素**&#x200B;选项。
1. 选择新模板。
1. 单击 **[!UICONTROL Edit properties]** 按钮。
1. 在模板属性的&#x200B;**[!UICONTROL Advanced parameters]**&#x200B;部分中，确保模板已链接到用于传递短信的外部帐户。

   ![](assets/sms_template.png)

**相关主题：**

* [管理模板](../../start/using/marketing-activity-templates.md)
