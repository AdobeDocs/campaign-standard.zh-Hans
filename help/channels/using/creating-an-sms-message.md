---
title: 创建短信消息
description: 请按照以下步骤在Adobe Campaign中创建单发SMS消息。
page-status-flag: 从未激活
uuid: 591ae97e-2d19-4f93-be4b-d8d20f1d2d12
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 频道
content-type: 参考
topic-tags: sms消息
discoiquuid: b27381a9-19e5-4b65-b194-c72f475ba54d
delivercontext-tags: deliveryCreation，向导
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 创建短信消息{#creating-an-sms-message}

创建SMS交付与创建常规电子邮件非常相似。 以下步骤介绍了特定于此渠道的配置。 有关其他 [选项的更多信息](../../channels/using/creating-an-email.md) ，请参阅创建电子邮件。

高级SMS参数在 [SMS配置部分有详细介绍](../../administration/using/configuring-sms-channel.md) 。

要创建SMS消息并将其发送到手机，您需要：

* 在渠 **[!UICONTROL Routing]** 道上使用该模式配 **[!UICONTROL Mobile (SMS)]** 置的外部帐 **[!UICONTROL Bulk delivery]** 户。 For more on this, refer to the [Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) section.
* 正确链接到此外部帐户的分发模板。

1. 创建SMS交付。 您可以从Adobe Campaign主页、营销活 [动中](../../start/using/interface-description.md#home-page)，或营销活 [动列表](../../start/using/marketing-activities.md#creating-a-marketing-activity)[中执行此操作](../../start/using/programs-and-campaigns.md#creating-a-campaign)。

   您还可以在工作流中添加SMS活动。 有关详细信息，请参阅工作 [流指南](../../automating/using/sms-delivery.md) 。

   创建消息时，将显示向导，指导您完成最重要的步骤。 通过向导定义的内容在之后仍可从消息功能板进行编辑。

1. 选择要使用的模板。 您可以选择现成的SMS模板或您自己的模板之一。

   ![](assets/sms_creation_1.png)

   要传送到移动电话，传送模板必须正确链接到SMS路由外部帐户。

1. 输入SMS的常规属性。

   ![](assets/sms_creation_2.png)

   活动标签及其ID都显示在界面中，但邮件收件人看不到它们。

1. 指定要定位的受众。 您可以选择现有受众，或通过定义和组合规则直接定位受众。

   ![](assets/sms_creation_3.png)

1. 将内容添加到SMS 在SMS创建完成后，您还可以通 **[!UICONTROL Content]** 过单击交付仪表板的部分来定义内容。 请参 [阅关于SMS内容设计](../../channels/using/about-sms-and-push-content-design.md)。

   如果您已经将个性化字段或条件文本插入到SMS消息的内容中，则消息的长度可能因收件人而异。 事实上，这些因素可能会引入GSM编码中未考虑的字符。 这就是在个性化实施后必须评估消息长度的原因。 See [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_creation_4.png)

1. 确认创建消息。 随后将显示其功能板。
1. 计划发送。 短消息可以在消息准备之后立即手动发送，也可以在预定日期自动发送。 请参 [阅计划消息](../../sending/using/about-scheduling-messages.md)。
1. 准备消息以分析其有效性、个性化和目标。

   ![](assets/sms_creation_6.png)

   >[!NOTE]
   >
   >您可以设置全局跨渠道疲劳规则，这些规则将自动从营销活动中排除过度征求的档案。 请参阅 [疲劳规则](../../administration/using/fatigue-rules.md)。

1. 发送校样以检查和验证您的邮件并监控其收件箱呈现。 请参阅发 [送证明](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) 。
1. 确认消息的发送。 发送将相应地开始到您定义的计划。

   ![](assets/sms_creation_7.png)

消息将发送。 您可以通过消息仪表板和日志检查其传送。

发送完成后，您可以开始使用内置或自定义交付报告衡量消息的影响。

**相关主题：**

* [关于SMS和推送内容版](../../channels/using/about-sms-and-push-content-design.md)
* [管理模板](../../start/using/about-templates.md)
* [创建SMS交付视频](https://helpx.adobe.com/campaign/kt/acs/using/acs-creating-a-sms-delivery-feature-video-use.html)

