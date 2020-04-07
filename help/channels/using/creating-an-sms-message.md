---
title: 创建短信消息
description: 按照以下步骤在Adobe Campaign中创建单发SMS消息。
page-status-flag: never-activated
uuid: 591ae97e-2d19-4f93-be4b-d8d20f1d2d12
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: b27381a9-19e5-4b65-b194-c72f475ba54d
delivercontext-tags: deliveryCreation,wizard
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 155ed7e50e207e4c4dc0569e5e96b24e712e4be8

---


# 创建短信消息{#creating-an-sms-message}

创建SMS投放与创建常规电子邮件非常相似。 以下步骤介绍了特定于此渠道的配置。 有关其他 [选项的更多信息](../../channels/using/creating-an-email.md) ，请参阅创建电子邮件。

高级SMS参数在 [SMS配置部分有详细介绍](../../administration/using/configuring-sms-channel.md) 。

要创建SMS消息并将其发送到手机，您需要：

* 在 **[!UICONTROL Routing]** 渠道上用该模式 **[!UICONTROL Mobile (SMS)]** 配置的 **[!UICONTROL Bulk delivery]** 外部帐户。 For more on this, refer to the [Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) section.
* 正确链接到此投放模板的外部帐户。

1. 创建SMS投放。 您可以从Adobe Campaign [主页](../../start/using/interface-description.md#home-page)、 [活动](../../start/using/marketing-activities.md#creating-a-marketing-activity) 或营销 [活动列表](../../start/using/programs-and-campaigns.md#creating-a-campaign)中执行此操作。

   您还可以在工作流中添加SMS活动。 有关详细信息，请参阅 [工作流](../../automating/using/sms-delivery.md) 。

   创建消息时，将显示向导，指导您完成最重要的步骤。 通过向导定义的内容在之后仍可从消息仪表板进行编辑。

1. 选择要使用的模板。 您可以选择现成的SMS模板或您自己的模板之一。

   ![](assets/sms_creation_1.png)

   要传送到移动电话，投放模板必须正确地链接到SMS路由外部帐户。

1. 输入SMS的常规属性。

   ![](assets/sms_creation_2.png)

   活动标签及其ID都显示在界面中，但消息收件人看不到它们。

1. 指定要目标的受众。 您可以选择现有受众，或通过定义和组合规则直接目标人群。

   ![](assets/sms_creation_3.png)

1. 将内容添加到SMS 在SMS创建完成后，您还可以通 **[!UICONTROL Content]** 过单击投放仪表板的部分来定义内容。 请参 [阅关于SMS内容设计](../../channels/using/about-sms-and-push-content-design.md)。

   如果您已将个性化字段或条件文本插入SMS消息的内容，则消息的长度可能因收件人而异。 事实上，这些因素可能会引入GSM编码中未考虑的字符。 这就是在个性化实施后必须评估消息长度的原因。 See [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_creation_4.png)

1. 确认创建消息。 然后显示其仪表板。
1. 计划发送。 短消息可以在消息准备之后立即手动发送，也可以在预定日期自动发送。 请参 [阅计划消息](../../sending/using/about-scheduling-messages.md)。
1. 准备消息以分析其有效性、个性化和目标。

   ![](assets/sms_creation_6.png)

   >[!NOTE]
   >
   >您可以设置全局交叉渠道疲劳规则，该规则将自动从活动中排除过度激励的用户档案。 请参阅 [疲劳规则](../../sending/using/fatigue-rules.md)。

1. 发送验证以检查和验证您的邮件并监控其收件箱呈现。 请参阅发 [送验证](../../sending/using/sending-proofs.md) 。
1. 确认消息的发送。 发送将相应地开始到您定义的计划。

   ![](assets/sms_creation_7.png)

消息将发送。 您可以通过消息投放和日志检查其仪表板。

发送完成后，您可以使用内置或自定义开始来评估消息的影响。

**相关主题：**

* [关于SMS和推送内容版](../../channels/using/about-sms-and-push-content-design.md)
* [管理模板](../../start/using/marketing-activity-templates.md)
* [创建SMS投放视频](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/sms/sms-delivery.html)

