---
title: 设计 A/B 测试电子邮件
description: 发现A/B测试功能，然后按照以下步骤从Adobe Campaign中的A/B测试模板创建电子邮件。
page-status-flag: never-activated
uuid: 104f6973-68a7-4692-a90a-a5570a980ec7
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: e249ba70-90d0-43f2-868c-ce9fdc7e642d
context-tags: delivery,abTesting,back;deliveryCreation,wizard;delivery,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d8a46a53f2abd453aaf0ff8322b7f9b942ec1c6

---


# 设计 A/B 测试电子邮件{#designing-an-a-b-test-email}

Adobe Campaign中的A/B测试功能允许您定义两到三个电子邮件变体。 每个变体被发送到群体样本以确定哪个具有最佳结果。 一旦确定，则将获胜变体发送到剩余人群。

您可以选择更改电子邮件的内容、主题或发件人。

>[!NOTE]
>
>无法对在Adobe Experience manager中创建的电子邮件进行A/B测试。

## Creating an A/B test email {#creating-an-a-b-test-email}

可以使用标准电子邮件创建向导创建A/B测试，并向其添加A/B测试配置步骤。 创建标准电子邮件在创建电子邮 [件部分有详细介绍](../../channels/using/creating-an-email.md) 。

在A/B测试的特定上下文中：

1. 根据您要更改的元素，从三个A/B测试特定模板之一创建新电子邮件：

   * 发送者的A/B测试
   * 内容A/B测试
   * 主题A/B测试
   ![](assets/create_ab_testing.png)

   >[!NOTE]
   >
   >默认情况下，后续和A/B测试模板是隐藏的。 选中左侧（侧面板）的A/B测试 **[!UICONTROL Filter]**框以显示它们。

1. 定义电子邮件的一般属性和目标受众，就像标准电子邮件一样。 请参阅创 [建受众](../../audiences/using/creating-audiences.md) 。
1. 在创建向导的第四步中，定义A/B测试参数：

   * **[!UICONTROL Number of variants]**:您可以选择使用两、三种变体。 如果您选择了三个变体，则在向导中确认此步骤后，无法修改此选择。
   * **[!UICONTROL Winning strategy]**:选择要用于确定入选变体的标准。
   * **[!UICONTROL Target breakdown]**:选择目标将接收每个变体的百分比。 确定后，剩余百分比将接收入选变体。 目标配置文件会随机选择。
   * **[!UICONTROL Winner sending method]**:选择您是希望在确定入选变体后自动发送变体，还是希望手动确认发送到剩余人群。
   * **[!UICONTROL Test duration]**:指定测试的持续时间。 在此持续时间后，将自动确定入选变体。 您可以在电子邮件仪表板中测试结束之前手动选择入选变体。

      要收集所有跟踪数据并正确考虑以选择入选变体，测试必须至少为1小时。
   ![](assets/ab_parameters.png)

1. 定义A/B测试参数后，请转到向导中的下一步，然后定义电子邮件内容。 根据您选择的模板，您可以定义多个主题、多个发件人姓名或多个不同的内容。 使用轮盘在元素的不同变体之间导航。 有关详细信息，请参阅内 [容编辑器](../../designing/using/designing-content-in-adobe-campaign.md) 部分。

   ![](assets/create_ab_testing2.png)

1. 确认创建电子邮件。 随后将显示电子邮件功能板。
1. 计划发送。 定义的日期指示A/B测试的开始。
1. 检查块中显示的A/B测试参 **[!UICONTROL A/B test parameters]**数。 在通过选择块确认发送测试（步骤9）之前，您可以修改测试。

   ![](assets/create_ab_testing3.png)

1. 准备电子邮件发送以分析目标和要发送的消息数。 请参阅 [准备发送部分](../../sending/using/preparing-the-send.md) 。
1. 在发送A/B测试之前，请通过发送校样来检查您的电子邮件。
1. 准备完成后，确认发送测试。 确认后，将无法修改A/B测试参数。

   A/B测试从中定义的日期开始。您 **[!UICONTROL Schedule]**可以使用和块跟踪其进**[!UICONTROL A/B test]** 度 **[!UICONTROL Deployment]**。

   如果您希望将测试持续时间缩短，则可以随时手动选择入选变体。

   测试完成后，块中会显示摘要表 **[!UICONTROL A/B Test]**格，这允许您查看测试的不同变体的各种指示符。

1. 如果您选择了 **[!UICONTROL Send after confirmation]**作为发送方法，则必须手动选择入选变体以开始将其发送到剩余人群。 如果您选择了**[!UICONTROL Automatic]**&#x200B;该选项，则入选变体将在系统确定后立即自动发送到剩余人群。

   >[!NOTE]
   >
   >如果存在绑定，则必须手动选择入选变体。 您可以通知电子邮件创建者和修改者已选择变体或需要选择变体。 请参 [阅Adobe Campaign通知](../../administration/using/sending-internal-notifications.md)。

您的电子邮件现已定义并发送。 您可以访问其日志和报告来衡量营销活动的成功程度。

**相关主题**:

[创建电子邮件视频](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/create-email-from-homepage.html)

## 关于A/B测试指示器 {#about-a-b-test-indicators}

在电子邮件功能板中，有几个指示器可帮助您测量A/B测试：单击次数、打开次数、弹回次数等。

请注意，该指 **[!UICONTROL Estimated recipient reactivity]**示器是比较单击的收件人数量与打开电子邮件的收件人数量的比率。 例如，如果有10个收件人打开了电子邮件，而有5个收件人单击了该电子邮件。 反应性率为50%。
