---
title: 发送内部通知
seo-title: 发送内部通知
description: 发送内部通知
seo-description: 了解如何向Adobe Campaign用户发送实时系统通知。
page-status-flag: 从未激活
uuid: f196f025-dbb9-4268-9d7 d-ff626994 b447
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: 应用程序设置
discoiquuid: 4d51229a-745a-4f24-b1 c2-22fa203 b499 c
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Sending internal notifications{#sending-internal-notifications}

Adobe Campaign允许您在应用程序内直接接收有关重要系统活动的通知。实时通知可让相关利益相关者知晓并为用户提供即时、直接在应用程序中采取活动通知的能力。团队的结果是灵活性、效率和更顺畅地执行营销活动。

![](assets/pulse_3.png)

您可以为以下对象配置通知：

* **[!UICONTROL A/B Test emails]**：系统会通知电子邮件创建者和修饰符已选择变体(自动模式)或需要选择变体(手动模式)。单击通知将显示相应的电子邮件。默认情况下，通知在现成A/B测试模板中处于激活状态。If you want to deactivate them, edit the properties of the email or the email template and uncheck the box located under **General &gt; Notifications**. For more information on A/B Test emails, refer to [Creating an AB Test](../../channels/using/designing-an-a-b-test-email.md). For more on email properties, refer to [List of email properties](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**：每当工作流出错时，都会通知选定安全组的每个成员(电子邮件和应用程序内通知)。单击通知或电子邮件链接将显示相应的工作流。默认情况下，在现成的工作流模板中取消激活通知。If you want to activate them, edit the properties of the workflow or workflow template and add a security group under **General &gt; Execution &gt; Error management &gt; Supervisors**. For more information on security groups, refer to [Managing groups and users](../../administration/using/managing-groups-and-users.md). For more on workflow properties, refer to [Workflow properties](../../automating/using/executing-a-workflow.md#workflow-properties).

   ![](assets/pulse_1.png)

