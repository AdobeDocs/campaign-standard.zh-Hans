---
title: 创建电子邮件
description: 请按照以下步骤Adobe Campaign创建单发电子邮件。
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
source-git-commit: 155ed7e50e207e4c4dc0569e5e96b24e712e4be8

---


# 创建电子邮件{#creating-an-email}

您可以从活动、 [Adobe Campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity)[主页或营销](../../start/using/interface-description.md#home-page)活动列表创建电 [子邮件](../../start/using/marketing-activities.md#about-marketing-activities)。 您还可以从工作流创建单发和重复发送的电子邮件。

1. 开始创建电子邮件营销活动后，请选择要使用的模板。

   默认情况下，您可以从多个模板中为每个营销活动进行选择。 这允许您根据需要预配置某些参数，并为投放分配品牌。 有关此内容的详细信息，请参阅 [管理模板](../../start/using/marketing-activity-templates.md)。

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >默认情况下，后续和A/B测试模板是隐藏的。 如果要显示左侧(侧 **[!UICONTROL Filter]** 面板)的框，请选中它们。

1. 输入电子邮件的常规属性。 您可以在“标签”字段中输入 **名称** ，然后编辑ID。 活动名称及其ID都显示在界面中，但消息收件人看不到它们。

   您可以添加用户可在活动内容中看到的描述。

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >您可以在父活动中从主页或营销活动的列表创建电子邮件。 从已创建的活动中选择它。

1. 根据您的业务标准定义消息的目标。 请参阅 [管理用户档案](../../audiences/using/about-profiles.md)。

   您还可以定义将验证消息的测试用户档案。 请参阅 [管理测试用户档案](../../audiences/using/managing-test-profiles.md)。

   ![](assets/email_creation_3.png)

1. 使用电子邮件设计器定义消息内容、发送者姓名和主题并实现 [个性化](../../designing/using/designing-content-in-adobe-campaign.md)。 有关此方面的详细信息，请参阅关 [于电子邮件内容设计](../../designing/using/designing-content-in-adobe-campaign.md)。

   ![](assets/email_creation_4.png)

   您可以使用预定义的内容模板或Dreamweaver或Adobe Experience Manager直接设计消息。 如果您不喜欢设计人员，还可以上传为您准备的内容，或从URL导入现有内容。 请参 [阅选择现有内容](../../designing/using/using-existing-content.md)。

1. 预览您的消息。 请参阅 [预览消息](../../sending/using/previewing-messages.md)。
1. 确认创建电子邮件。

   >[!NOTE]
   >
   >要保存电子邮件，您首先需要对内容进行一些编辑。 如果单击 **[!UICONTROL Cancel]** 此时，您将无法完成向导，并且将不会创建您的电子邮件。

   随后将显示电子邮件仪表板。 它允许您检查消息并准 [备发送](../../sending/using/preparing-the-send.md)。

   使用 **[!UICONTROL Edit properties]** 右上角的按钮可以编辑电子邮件的属性。 例如，您可以配置电子邮件，以便在投放准备时计算其标签。  本节中列出了可用 [的参数](../../administration/using/configuring-email-channel.md#list-of-email-properties)。

   ![](assets/delivery_dashboard_2.png)

1. 计划发送。 请参 [阅计划消息](../../sending/using/about-scheduling-messages.md)。

   ![](assets/delivery_planning.png)

1. 准备消息以分析其目标。 See [Preparing the send](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >您可以设置全局交叉渠道疲劳规则，该规则将自动从活动中排除过度激励的用户档案。 有关此问题的详细信息，请参阅 [疲劳规则](../../sending/using/fatigue-rules.md)。

1. 发送验证以检查和验证您的邮件并监控其收件箱呈现。 请参阅 [发送验证](../../sending/using/sending-proofs.md)。

   ![](assets/bat_select.png)

1. 发送消息并通过消息仪表板和日志检查其投放。 请参阅 [发送消息](../../sending/using/confirming-the-send.md)。

   ![](assets/confirm_delivery.png)

1. 用投放报告衡量您的消息的影响。 有关报告的详细信息，请参 [阅此部分](../../reporting/using/about-dynamic-reports.md)。

**相关主题**:

* [创建电子邮件视频](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/create-email-from-homepage.html)
* [创建个性化的电子邮件](https://helpx.adobe.com/campaign/kb/acs-get-started-with-emails.html) -分步指南
* [Adobe Campaign与Dreamweaver集成](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html) 视频
* [与Adobe Experience Manager集成](../../integrating/using/integrating-with-experience-manager.md)
