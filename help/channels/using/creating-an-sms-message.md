---
title: 创建SMS消息
seo-title: 创建SMS消息
description: 创建SMS消息
seo-description: 按照以下步骤在Adobe Campaign中创建单发送SMS消息。
page-status-flag: 从未激活
uuid: 591ae97e-2d19-4f93be-be4 b-d8 d20 f1 d12 d12
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: sms-messages
discoiquuid: b27381a9-19e5-4b65-b485-c72 f475 ba54 d
delivercontext-tags: Delivery创建，向导
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: d50d486ed77cb7989df47133bb49fde3227ae3a5

---


# Creating an SMS message{#creating-an-sms-message}

创建SMS分发与创建常规电子邮件非常相似。以下步骤描述了特定于此渠道的配置。Refer to [Creating an email](../../channels/using/creating-an-email.md) for more information on other options.

Advanced SMS parameters are detailed in the [SMS configuration](../../administration/using/configuring-sms-channel.md) section.

要创建SMS消息并将其发送到手机，您需要：

* **[!UICONTROL Routing]****[!UICONTROL Mobile (SMS)]** 在渠道中配置 **[!UICONTROL Bulk delivery]** 了模式的外部帐户。For more on this, refer to the [Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) section.
* 正确链接到此外部帐户的交付模板。

1. 创建SMS交付。You can do it from the Adobe Campaign [home page](../../start/using/interface-description.md#home-page), in a [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity) or in the [marketing activity list](../../start/using/programs-and-campaigns.md#creating-a-campaign).

   您还可以在工作流中添加SMS活动。For more on this, refer to the [Workflows](../../automating/using/sms-delivery.md) guide.

   创建消息时，将显示一个向导，以指导您完成最重要的步骤。通过向导定义的内容仍然可以在消息仪表板中进行编辑。

1. 选择要使用的模板。您可以选择现成的SMS模板或自己的模板之一。

   ![](assets/sms_creation_1.png)

   要交付到手机，交付模板必须正确链接到SMS路由外部帐户。

1. 输入SMS的常规属性。

   ![](assets/sms_creation_2.png)

   活动标签及其ID显示在界面中，但消息收件人不可见。

1. 指定要定位的受众。您可以通过定义和合并规则来选择现有受众或直接定位某个人群。

   ![](assets/sms_creation_3.png)

1. 将内容添加到SMS。You can also define the content by clicking the **[!UICONTROL Content]** section of the delivery dashboard, once the SMS creation is finalized. See [About SMS content design](../../designing/using/about-sms-and-push-content-design.md).

   如果您在SMS消息内容中插入了个性化字段或条件文本，则消息的长度可能因一个收件人而异。事实上，这些因素可能引入不考虑GSM编码的字符。这就是为什么在执行个性化之后，必须评估消息长度的原因。See [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_creation_4.png)

1. 确认创建消息。随后会显示其仪表板。
1. 计划发送。SMS可以在消息准备之后手动发送，也可以在预定的日期自动发送。See [Scheduling messages](../../sending/using/about-scheduling-messages.md).
1. 准备消息以分析其有效性、个性化和目标。

   ![](assets/sms_creation_6.png)

   >[!NOTE]
   >
   >您可以设置全局跨渠道疲劳规则，它们会自动排除营销活动中已被过度授权的配置文件。See [Fatigue rules](../../administration/using/fatigue-rules.md).

1. 发送证明以检查和验证您的消息并监控其收件箱渲染。See the [Sending proof](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) section.
1. 确认发送消息。发送将相应地开始为您定义的计划。

   ![](assets/sms_creation_7.png)

消息将发送。您可以通过消息仪表板和日志检查其交付。

发送完成后，您可以通过内置的或自定义的交付报表开始测量消息的影响。

**相关主题：**

* [关于SMS和推送内容版本](../../designing/using/about-sms-and-push-content-design.md)
* [管理模板](../../start/using/about-templates.md)
* [创建SMS交付](https://helpx.adobe.com/campaign/kt/acs/using/acs-creating-a-sms-delivery-feature-video-use.html) 视频

