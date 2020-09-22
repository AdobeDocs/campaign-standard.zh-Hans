---
title: 创建电子邮件
description: 按照以下步骤创建Adobe Campaign的单发电子邮件。
page-status-flag: never-activated
uuid: 74c7ef35-82c0-4bc4-b1f6-8e74fdcaea3c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: b27e0170-e73f-4782-8568-02927fb374f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e1e092249a447039c0d845f143be532f845ca1dc
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 18%

---


# 创建电子邮件{#creating-an-email}

您可以从活动、 [](../../start/using/marketing-activities.md#creating-a-marketing-activity)、Adobe Campaign [主页](../../start/using/interface-description.md#home-page)或营销 [活动列表创](../../start/using/marketing-activities.md#about-marketing-activities)建电子邮件。 您还可以从工作流创建单发送和重复发送的电子邮件。

1. 开始创建电子邮件营销活动后，请选择要使用的模板。

   默认情况下，您可以从多个模板中为每个营销活动进行选择。 这允许您根据需要预配置某些参数，并为投放分配品牌。 For more on this, see [Managing templates](../../start/using/marketing-activity-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >跟进和 A/B 测试模板默认隐藏。如果要显示左侧的框( **[!UICONTROL Filter]** 侧面板)，请选中它们。

1. 输入电子邮件的常规属性。 You can enter a name in the **Label** field and edit the ID. 活动名和其ID都显示在接口中，但消息收件人看不到。

   您可以添加用户会在营销策划内容中看到的描述。

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >您可以在父活动中从营销活动的主页或列表创建电子邮件。 从已创建的活动中选择它。

1. 根据您的业务标准定义消息的目标。 See [About profiles](../../audiences/using/about-profiles.md).

   您还可以定义将验证消息的测试用户档案。 请参阅[管理测试用户档案](../../audiences/using/managing-test-profiles.md)。

   ![](assets/email_creation_3.png)

1. 使用电子邮件设计器定义和个性化邮件内容、发件人 [姓名和主题](../../designing/using/designing-content-in-adobe-campaign.md)。 有关此方面的详细信息，请参 [阅关于电子邮件内容设计](../../designing/using/designing-content-in-adobe-campaign.md)。

   ![](assets/email_creation_4.png)

   您可以使用预定义的内容模板或Dreamweaver或Adobe Experience Manager直接设计消息。 如果您不喜欢设计人员，还可以上传为您准备的内容，或从URL导入现有内容。 请参 [阅选择现有内容](../../designing/using/using-existing-content.md)。

1. 预览您的消息。 请参阅[预览消息](../../sending/using/previewing-messages.md)。
1. 确认创建电子邮件。

   >[!NOTE]
   >
   >要保存电子邮件，您首先需要对内容进行一些编辑。 如果此 **[!UICONTROL Cancel]** 时单击，将无法完成向导，并且将不会创建电子邮件。

   随后将显示电子邮件仪表板。 它允许您检查消息并准 [备发送](../../sending/using/preparing-the-send.md)。

   右 **[!UICONTROL Edit properties]** 上角的按钮允许您编辑电子邮件的属性。 例如，您可以配置电子邮件，以便在投放准备时计算其标签。  本节中列出了可 [用参数](../../administration/using/configuring-email-channel.md#list-of-email-properties)。

   ![](assets/delivery_dashboard_2.png)

1. 安排发送。请参阅[计划消息发送](../../sending/using/about-scheduling-messages.md)。

   ![](assets/delivery_planning.png)

1. 准备消息以分析其目标。 See [Preparing the send](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >您可以设置全局跨渠道疲劳规则，以便自动从营销方案中排除过度投放的用户档案。有关此方面的详细信息，请参 [阅疲劳规则](../../sending/using/fatigue-rules.md)。

1. 发送校样以检查和验证您的消息并监视其收件箱呈现。请参阅 [发送验证](../../sending/using/sending-proofs.md)。

   ![](assets/bat_select.png)

1. 发送消息并通过消息投放和日志检查其仪表板。 请参阅 [发送消息](../../sending/using/confirming-the-send.md)。

   ![](assets/confirm_delivery.png)

1. 通过投放报告衡量您的消息的影响。 For more on reporting, see [this section](../../reporting/using/about-dynamic-reports.md).

**相关主题**：

* [创建电子邮件](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/create-email-from-homepage.html) 视频
* [创建个性化的](https://helpx.adobe.com/cn/campaign/kb/acs-get-started-with-emails.html) 电子邮件分步指南
* [Adobe Campaign和Dreamweaver集成](https://docs.adobe.com/content/help/zh-Hans/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.translate.html) 视频
* [与Adobe Experience Manager集成](../../integrating/using/integrating-with-experience-manager.md)
