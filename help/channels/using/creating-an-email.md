---
title: 创建电子邮件
description: 按照以下步骤在Adobe Campaign中创建单次发送的电子邮件。
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Beginner
exl-id: 4483e469-0a2b-494d-b768-950168759727
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 15%

---

# 创建电子邮件{#creating-an-email}

您可以从[营销活动](../../start/using/marketing-activities.md#creating-a-marketing-activity)、Adobe Campaign [主页](../../start/using/interface-description.md#home-page)或[营销活动列表](../../start/using/marketing-activities.md#about-marketing-activities)创建电子邮件。 您还可以根据工作流创建单一发送和重复发送的电子邮件。

![](assets/do-not-localize/how-to-video.png) [通过观看视频了解此功能](#video)

1. 开始创建电子邮件营销活动后，请选择要使用的模板。

   默认情况下，您可以为每个营销活动从多个模板中进行选择。 这样，您就可以根据需要预配置某些参数，还可以为投放分配品牌。 有关此内容的详细信息，请参阅[管理模板](../../start/using/marketing-activity-templates.md)。

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >跟进和 A/B 测试模板默认隐藏。如果要显示左侧框（**[!UICONTROL Filter]**&#x200B;侧面板），请选中这些框。

1. 输入电子邮件的常规属性。 您可以在&#x200B;**标签**&#x200B;字段中输入名称并编辑ID。

   >[!NOTE]
   >
   >界面中会显示活动名称及其ID，但消息收件人看不到它们。
   >
   >确保ID字段不包含任何空格以避免出现任何差异，例如，在与Adobe Analytics集成时。

   您可以添加用户会在营销策划内容中看到的描述。

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >您可以从主页或营销活动列表在父营销策划中创建电子邮件。 从已创建的营销策划中选择它。

1. 根据业务标准定义消息的目标。 查看[关于用户档案](../../audiences/using/about-profiles.md)。

   您还可以定义将验证消息的测试用户档案。 请参阅[管理测试用户档案](../../audiences/using/managing-test-profiles.md)。

   ![](assets/email_creation_3.png)

1. 使用[电子邮件Designer](../../designing/using/designing-content-in-adobe-campaign.md)定义并个性化邮件内容、发件人姓名和主题。 有关此内容的详细信息，请参阅[关于电子邮件内容设计](../../designing/using/designing-content-in-adobe-campaign.md)。

   ![](assets/email_creation_4.png)

   您可以使用预定义的内容模板，或使用Dreamweaver或Adobe Experience Manager直接设计消息。 如果您不觉得自己是设计者，则还可以上传已为您准备的内容，或从URL导入现有内容。 请参阅[选择现有内容](../../designing/using/using-existing-content.md)。

1. 预览您的消息。 请参阅[预览消息](../../sending/using/previewing-messages.md)。
1. 确认创建电子邮件。

   >[!NOTE]
   >
   >为了能够保存电子邮件，您首先需要对内容进行一些编辑。 如果此时单击&#x200B;**[!UICONTROL Cancel]**，您将无法完成向导，并且不会创建电子邮件。

   随后将显示电子邮件仪表板。 它允许您检查消息并[准备发送](../../sending/using/preparing-the-send.md)。

   通过右上角的&#x200B;**[!UICONTROL Edit properties]**&#x200B;按钮，可编辑电子邮件的属性。 例如，您可以配置电子邮件，以便在投放准备时计算其标签。  [此部分](../../administration/using/configuring-email-channel.md#list-of-email-properties)中列出了可用的参数。

   ![](assets/delivery_dashboard_2.png)

1. 安排发送。请参阅[计划消息发送](../../sending/using/about-scheduling-messages.md)。

   ![](assets/delivery_planning.png)

1. 准备消息以分析其目标。 请参阅[准备发送](../../sending/using/confirming-the-send.md)。

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >您可以设置全局跨渠道疲劳规则，以便自动从营销方案中排除过度投放的用户档案。有关详细信息，请参阅[疲劳规则](../../sending/using/fatigue-rules.md)。

1. 发送校样以检查和验证您的消息并监视其收件箱呈现。请参阅[发送校样](../../sending/using/sending-proofs.md)。

   ![](assets/bat_select.png)

1. 通过消息仪表板和日志，发送消息并检查其投放。 请参阅[发送邮件](../../sending/using/confirming-the-send.md)。

   ![](assets/confirm_delivery.png)

1. 使用投放报告衡量消息的影响。 有关报告的详细信息，请参阅[此部分](../../reporting/using/about-dynamic-reports.md)。

**相关主题**：

* [创建个性化电子邮件](../../channels/using/key-steps-to-send-a-message.md)分步指南
* [Adobe Campaign与Dreamweaver集成](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)
* [与Adobe Experience Manager集成](../../integrating/using/integrating-with-experience-manager.md)

## 教程视频 {#video}

本视频说明如何创建电子邮件。

>[!VIDEO](https://video.tv.adobe.com/v/29752?quality=12&captions=chi_hans)

[此处](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hans)提供了其他Campaign Standard操作方法视频。
