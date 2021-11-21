---
title: 创建短信消息
description: 按照以下步骤在 Adobe Campaign 中创建单次发送的短信消息。
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard
feature: SMS
role: User
level: Beginner
exl-id: 36442480-c6b6-4b7d-b566-40169a7c8544
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 96%

---

# 创建短信消息{#creating-an-sms-message}

创建短信投放与创建常规电子邮件非常相似。以下步骤描述了特定于此渠道的配置。有关其他选项的更多信息，请参阅[创建电子邮件](../../channels/using/creating-an-email.md)。

有关高级短信参数的详情，请参见[短信配置](../../administration/using/configuring-sms-channel.md)一节。

![](assets/do-not-localize/how-to-video.png) [在视频中发现此功能](#video)

要创建短信消息并将其发送到手机，您需要：

* 在 **[!UICONTROL Mobile (SMS)]** 渠道上使用 **[!UICONTROL Bulk delivery]** 模式配置的 **[!UICONTROL Routing]** 外部帐户。有关更多信息，请参阅[路由](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)一节。
* 正确链接到此外部帐户的投放模板。

1. 创建短信投放。您可以在 Adobe Campaign [主页](../../start/using/interface-description.md#home-page)的[营销策划](../../start/using/marketing-activities.md#creating-a-marketing-activity)或[营销活动列表](../../start/using/programs-and-campaigns.md#creating-a-campaign)中执行此操作。

   您还可以在工作流中添加短信活动。有关更多信息，请参阅[工作流](../../automating/using/sms-delivery.md)指南。

   创建消息时，会显示向导以逐步指导您完成最重要的步骤。通过向导定义的内容，未来仍可通过消息仪表板进行编辑。

1. 选择要使用的模板。您可以选择现成的短信模板或自己拥有的模板之一。

   ![](assets/sms_creation_1.png)

   要传送到手机，投放模板必须正确地链接到短信路由外部帐户。

1. 输入短信的常规属性。

   ![](assets/sms_creation_2.png)

   界面中会显示活动标签及其 ID，但消息收件人看不到它们。

1. 指定要定向的受众。您可以选择现有受众，也可以通过定义和组合规则直接定向群体。

   ![](assets/sms_creation_3.png)

1. 向短信添加内容。在短信创建完成后，您还可以单击投放仪表板的 **[!UICONTROL Content]** 部分以定义内容。请参阅[关于短信内容设计](../../channels/using/about-sms-and-push-content-design.md)。

   如果在短信消息内容中插入了个性化字段或条件文本，则消息的长度可能会因收件人而异。事实上，这可能是因为短信消息中带有 GSM 编码无法识别的字符。这就是实施个性化后必须评估消息长度的原因。请参阅[个性化短信消息](../../channels/using/personalizing-sms-messages.md)。

   ![](assets/sms_creation_4.png)

1. 确认创建消息。随后将显示其仪表板。
1. 安排发送。短信可以在消息准备之后手动发送，也可以在安排的日期自动发送。请参阅[计划消息发送](../../sending/using/about-scheduling-messages.md)。
1. 准备消息以分析其有效性、个性化和目标。

   ![](assets/sms_creation_6.png)

   >[!NOTE]
   >
   >您可以设置全局跨渠道疲劳规则，以便自动从营销方案中排除过度投放的用户档案。请参阅[疲劳规则](../../sending/using/fatigue-rules.md)。

1. 发送校样以检查和验证您的消息并监视其收件箱呈现。请参阅[发送校样](../../sending/using/sending-proofs.md)一节。
1. 确认消息的发送。将根据您定义的日程表启动发送。

   ![](assets/sms_creation_7.png)

消息已发送。您可以通过消息仪表板和日志检查其投放情况。

发送完成后，您就可以使用内置或自定义投放报告以评估消息的影响。

**相关主题：**

* [关于短信和推送内容编辑](../../channels/using/about-sms-and-push-content-design.md)
* [管理模板](../../start/using/marketing-activity-templates.md)

## 教程视频 {#video}

以下视频演示了如何创建短信投放。

>[!VIDEO](https://video.tv.adobe.com/v/25265/?quality=12)

提供了其他Campaign Standard操作方法视频 [此处](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hans).
