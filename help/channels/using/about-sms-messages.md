---
solution: Campaign Standard
product: campaign
title: 关于短信消息
description: 了解Adobe Campaign中SMS渠道的主要特性。
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 23%

---


# 关于短信消息{#about-sms-messages}

Adobe Campaign允许您传送SMS（短消息服务）消息。

>[!NOTE]
>
>SMS渠道是一个附加组件。 请核实您的许可协议。

对于SMS消息，您只能以文本格式创建、修改和个性化消息。 您还可以在发送SMS消息之前预览这些消息。

如果SMS消息采用GSM编码，则其长度限制为160个字符；如果SMS消息采用Unicode，则长度限制为70个字符。 但是，某些特殊字符会影响消息的长度。 For more on this, refer to the [SMS encoding](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

可以从菜单、活动 **[!UICONTROL Marketing activities]** 或工作流中创建SMS消息，请参 [阅创建SMS消息](../../channels/using/creating-an-sms-message.md)。

要将SMS消息传送到移动电话，您需要：

* 在 **[!UICONTROL Mobile (SMS)]** 渠道上使用 **[!UICONTROL Bulk delivery]** 模式配置的 **[!UICONTROL Routing]** 外部帐户。有关更多信息，请参阅[路由](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)一节。
* 正确链接到此外部帐户的投放模板。

**相关主题：**

* [管理模板](../../start/using/marketing-activity-templates.md)
* [SMS配置](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [短信报告](../../reporting/using/sms-report.md)
* [Campaign Standard Mobile 指南](https://helpx.adobe.com/cn/campaign/kb/acs-mobile.html)

## SMS投放模板 {#sms-delivery-template}

Adobe Campaign优惠移动设备的投放模板。 此模板必须正确链接到用于外部帐户的 **[!UICONTROL Mobile (SMS)]** 渠道。 要访问和修改它：

1. 从高 **[!UICONTROL Resources]** 级 **[!UICONTROL Templates]** 菜单 **[!UICONTROL Delivery templates]** 中选择> >。
1. 将鼠标悬 **[!UICONTROL Send via SMS]** 停在模板上，然后选择 **重复元素** 选项。
1. 选择新模板。
1. 单击 **[!UICONTROL Edit properties]** 按钮。
1. 在模 **[!UICONTROL Advanced parameters]** 板属性的一节中，确保模板已链接到用于传送SMS的外部帐户。

   ![](assets/sms_template.png)

**相关主题：**

* [管理模板](../../start/using/marketing-activity-templates.md)
