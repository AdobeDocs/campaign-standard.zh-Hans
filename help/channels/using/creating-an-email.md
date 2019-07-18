---
title: 创建电子邮件
seo-title: 创建电子邮件
description: 创建电子邮件
seo-description: 按照以下步骤在Adobe Campaign中创建单发送电子邮件。
page-status-flag: 从未激活
uuid: 74c7ef35-82c0-4bc4-b1 f6-8e74 dfcaua3 c
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: 电子邮件消息
discoiquuid: b27e0170-e73 f-4782-8568-02927fb374 f4
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Creating an email{#creating-an-email}

You can create an email from a [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity), from the Adobe Campaign [home page](../../start/using/interface-description.md#home-page), or in the [marketing activity list](../../start/using/marketing-activities.md#about-marketing-activities). 您还可以从工作流中创建单发送和重复电子邮件。

1. 开始创建电子邮件营销活动后，请选择要使用的模板。

   默认情况下，您可以为每个营销活动选择多个模板。这允许您根据需要预配置某些参数，并为您的交付分配品牌。For more on this, see [Managing templates](../../start/using/about-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >默认情况下，跟踪和A/B测试模板处于隐藏状态。Check the boxes on the left side ( **[!UICONTROL Filter]** lateral panel) if you want to display them.

1. 输入电子邮件的常规属性。You can enter a name in the **Label** field and edit the ID. 活动名称及其ID显示在界面中，但消息收件人不可见。

   您可以添加用户可在营销活动内容中看到的描述。

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >您可以在主页上的父营销活动或营销活动列表中创建您的电子邮件。从已经创建的营销活动中选择它。

1. 根据您的业务标准定义消息的目标。See [Managing profiles](../../audiences/using/about-profiles.md).

   您还可以定义将验证消息的测试配置文件。See [Managing test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles).

   ![](assets/email_creation_3.png)

1. Define and personalize the message content, sender name and subject using the [Email Designer](../../designing/using/about-email-content-design.md#about-the-email-designer). For more on this, see [About email content design](../../designing/using/about-email-content-design.md).

   ![](assets/email_creation_4.png)

   您可以使用预定义的内容模板或使用Dreamweaver或Adobe Experience Manager直接设计消息。如果您不像设计人员一样，您还可以上传为您准备的内容，或从URL导入现有内容。See [Selecting an existing content](../../designing/using/selecting-an-existing-content.md).

1. 预览消息。See [Previewing messages](../../sending/using/previewing-messages.md).
1. 确认创建电子邮件。

   >[!NOTE]
   >
   >要保存电子邮件，您首先需要对内容进行一些编辑。If you click **[!UICONTROL Cancel]** at this point, you will not complete the wizard and your email will not be created.

   随后会显示电子邮件仪表板。For more on this, see [Approving messages](../../sending/using/preparing-the-send.md).

   ![](assets/delivery_dashboard_2.png)

1. 计划发送。See [Scheduling messages](../../sending/using/about-scheduling-messages.md).

   ![](assets/delivery_planning.png)

1. 准备消息以分析其目标。See [Preparing the send](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >您可以设置全局跨渠道疲劳规则，它们会自动排除营销活动中已被过度授权的配置文件。For more on this, see [Fatigue rules](../../administration/using/fatigue-rules.md).

1. 发送证明以检查和验证您的消息并监控其收件箱渲染。See [Sending proof](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).

   ![](assets/bat_select.png)

1. 发送消息并通过消息仪表板和日志检查其交付。See [Sending messages](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. 利用交付报告衡量消息的影响力。For more on reporting, see [this section](../../reporting/using/about-dynamic-reports.md).

**相关主题**：

* [创建电子邮件](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-email-from-homepage-feature-video-use.html) 视频
* [创建个性化的电子邮件](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GettingStartedEmail.html) 分步指南
* [Adobe Campaign和Dreamweaver集成](https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html) 视频
* [与Adobe Experience Manager集成](../../integrating/using/integrating-with-experience-manager.md)

