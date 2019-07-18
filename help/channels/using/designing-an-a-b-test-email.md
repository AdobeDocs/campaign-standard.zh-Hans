---
title: 设计A/B测试电子邮件
seo-title: 设计A/B测试电子邮件
description: 设计A/B测试电子邮件
seo-description: 发现A/B测试功能，然后按照以下步骤从Adobe Campaign中的A/B测试模板创建电子邮件。
page-status-flag: 从未激活
uuid: 104f6973-68a7-4692-a90 a-a5570 a980 ec7
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: 电子邮件消息
discoiquuid: e249ba70-90d0-43f2-868c-ce9 fdc7 e642 d
context-tags: 交付，测试，返回；DeliquyCreate，向导；交付，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: d50d486ed77cb7989df47133bb49fde3227ae3a5

---


# Designing an A/B test email{#designing-an-a-b-test-email}

Adobe Campaign中的A/B测试功能允许您定义到三个电子邮件变体。每个变体都会发送到人口样本，以确定最佳结果。确定后，入选变量会发送给剩余的用户。

您可以选择更改电子邮件的内容、主题或发送方。

>[!NOTE]
>
>不可能对在Adobe Experience Manager中创建的电子邮件进行A/B测试。

## Creating an A/B test email {#creating-an-a-b-test-email}

A/B测试可使用标准电子邮件创建向导创建，该向导将添加A/B测试配置步骤。Creating a standard email is detailed in the [Creating an email](../../channels/using/creating-an-email.md) section.

在A/B测试的特定上下文中：

1. 根据您要更改的元素，从三个A/B测试特定模板之一中创建新电子邮件：

   * 对发送方进行A/B测试
   * 内容上的A/B测试
   * 主题A/B测试
   ![](assets/create_ab_testing.png)

   >[!NOTE]
   >
   >默认情况下，跟踪和A/B测试模板处于隐藏状态。Check the A/B test box on the left side ( **[!UICONTROL Filter]** lateral panel) to display them.

1. 定义电子邮件的一般属性和目标受众，就像标准电子邮件一样。Refer to the [Creating audiences](../../audiences/using/creating-audiences.md) section.
1. 在创建向导的第四步，定义A/B测试参数：

   * **[!UICONTROL Number of variants]**：您可以选择使用两种或三种变体。如果您选择三个变体，则在向导中确认此步骤后，无法修改此选项。
   * **[!UICONTROL Winning strategy]**：选择要用于确定入选变体的标准。
   * **[!UICONTROL Target breakdown]**：选择目标将接收每个变体的百分比。剩余百分比在确定后将收到入选变量。将随机选择目标配置文件。
   * **[!UICONTROL Winner sending method]**：选择您是否希望入选变量在确定后自动发送，还是希望手动确认发送给剩余的用户。
   * **[!UICONTROL Test duration]**：指定测试的持续时间。入选变量在此持续时间后自动确定。您可以在电子邮件仪表板的测试结束前手动选择入选变量。

      测试必须至少为一小时，以便收集所有跟踪数据并正确考虑入选变量。
   ![](assets/ab_parameters.png)

1. 定义A/B测试参数后，请传递到向导中的下一步，并定义电子邮件内容。根据您选择的模板，您可以定义多个主题、多个发送者名称或多个不同的内容。使用转盘在元素的不同变体之间导航。For more information, consult the [content editor](../../designing/using/about-email-content-design.md) section.

   ![](assets/create_ab_testing2.png)

1. 确认创建电子邮件。随后将显示电子邮件仪表板。
1. 计划发送。定义的日期表示A/B测试开始。
1. Check the A/B test parameters displayed in the **[!UICONTROL A/B test parameters]** block. 您可以对其进行修改，直到您通过选择块来确认发送测试(步骤9)。

   ![](assets/create_ab_testing3.png)

1. 准备电子邮件发送以分析目标和要发送的消息数。Consult the [Preparing the send](../../sending/using/preparing-the-send.md) section.
1. 在发送A/B测试之前，请通过发送校样来检查您的电子邮件。
1. 准备完毕后，确认发送测试。一旦确认，A/B测试参数将无法修改。

   The A/B test starts on the date defined in the **[!UICONTROL Schedule]**.You can track its progress using the **[!UICONTROL A/B test]** and **[!UICONTROL Deployment]** blocks.

   如果您希望将测试持续时间缩短，可以随时手动选择入选变体。

   Once testing has finished, a summary table is displayed in the **[!UICONTROL A/B Test]** block and this allows you to view the various indicators for the different variants that were tested.

1. If you have selected **[!UICONTROL Send after confirmation]** as the sending method, you have to manually select the winning variant to start sending it to the remaining population. If you have selected **[!UICONTROL Automatic]**, the winning variant is automatically sent to the remaining population as soon as it has been determined by the system.

   >[!NOTE]
   >
   >如果存在绑定，则必须手动选择入选变体。您可以通知电子邮件创建者和修改人已选择变体或需要选择变体。See [Adobe Campaign notifications](../../administration/using/sending-internal-notifications.md).

您的电子邮件现在已定义并发送。您可以访问其日志和报告来评估营销活动的成功与否。

**相关主题**：

[创建电子邮件](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-email-from-homepage-feature-video-use.html) 视频

## About A/B test indicators {#about-a-b-test-indicators}

在电子邮件仪表板中，有几个指示器可帮助您测量A/B测试：单击次数、打开次数、弹回次数等。

Note that the **[!UICONTROL Estimated recipient reactivity]** indicator is a rate comparing the number of recipients who clicked against the number of recipients who opened the email. 例如，如果10个收件人打开了电子邮件和被点击的收件人。重新激活率为50%。
