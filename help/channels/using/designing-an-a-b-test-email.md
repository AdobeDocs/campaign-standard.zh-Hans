---
solution: Campaign Standard
product: campaign
title: 设计 A/B 测试电子邮件
description: 了解 A/B 测试功能，并按照以下步骤进行操作，以在 Adobe Campaign 中使用 A/B 测试模板创建电子邮件。
audience: channels
content-type: reference
topic-tags: email-messages
context-tags: delivery,abTesting,back;deliveryCreation,wizard;delivery,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 100%

---


# 设计 A/B 测试电子邮件{#designing-an-a-b-test-email}

利用 Adobe Campaign 中的 A/B 测试功能，可定义两到三个电子邮件变体。每个变体都会被发送到群体样本，以确定哪个变体效果最好。确定之后，会将入选的变体发送给其余群体。

您可以选择更改电子邮件的内容、主题或发件人。

>[!NOTE]
>
>无法对 Adobe Experience Manager 中创建的电子邮件进行 A/B 测试。

## 创建 A/B 测试电子邮件{#creating-an-a-b-test-email}

可以使用标准电子邮件创建向导创建 A/B 测试，该向导中添加了 A/B 测试配置步骤。有关创建标准电子邮件的详情，请参见[创建电子邮件](../../channels/using/creating-an-email.md)一节。

在 A/B 测试的特定环境中：

1. 根据要更改的元素，使用三个 A/B 测试特定模板之一创建新电子邮件：

   * 关于发件人的 A/B 测试
   * 关于内容的 A/B 测试
   * 关于主题的 A/B 测试

   ![](assets/create_ab_testing.png)

   >[!NOTE]
   >
   >跟进和 A/B 测试模板默认隐藏。勾选左侧的 A/B 测试框（**[!UICONTROL Filter]** 侧面板）可显示模板。

1. 定义电子邮件的常规属性和目标受众，操作方式与标准电子邮件类似。请参阅[创建受众](../../audiences/using/creating-audiences.md)一节。
1. 在创建向导的第四步，定义 A/B 测试参数：

   * **[!UICONTROL Number of variants]**：您可以选择使用两个或三个变体。如果选择了三个变体，则在向导中确认此步骤后，将无法修改此选择。
   * **[!UICONTROL Winning strategy]**：选择用于确定入选变量的标准。
   * **[!UICONTROL Target breakdown]**：选择接收每种变体的目标百分比。确定后，剩余的百分比将接收入选的变体。随机选择定向用户档案。
   * **[!UICONTROL Winner sending method]**：选择是否在确定入选变体后自动发送该变体，并选择是否手动确认发送给剩余群体。
   * **[!UICONTROL Test duration]**：指定测试的持续时间。经过此持续时间后，将自动确定入选变量。您可以在测试结束前，从电子邮件仪表板手动选择入选变体。

      要收集所有跟踪数据并正确考虑以选择入选变量，测试必须至少持续 1 小时。
   ![](assets/ab_parameters.png)

1. 定义 A/B 测试参数后，请转到向导的下一步并定义电子邮件的内容。根据您选择的模板，您可以定义多个主题、多个发件人名称或多个不同的内容。使用轮盘可在元素的不同变体之间导航。有关更多信息，请参阅[内容编辑器](../../designing/using/designing-content-in-adobe-campaign.md)一节。

   ![](assets/create_ab_testing2.png)

1. 确认创建电子邮件。随后将显示电子邮件仪表板
1. 计划发送所定义的日期代表 A/B 测试的开始日期。
1. 检查 **[!UICONTROL A/B test parameters]** 块中显示的 A/B 测试参数。在确认发送测试（第 9 步）之前，您可以通过选择该块来修改这些参数。

   ![](assets/create_ab_testing3.png)

1. 准备电子邮件发送，以分析消息发送的目标和数量。请参阅[准备发送](../../sending/using/preparing-the-send.md)一节。
1. 在发送 A/B 测试之前，通过发送校样来检查电子邮件。
1. 准备完成后，确认发送测试。确认后，无法修改 A/B 测试参数。

   在 **[!UICONTROL Schedule]** 中规定的日期开始 A/B 测试。您可以使用 **[!UICONTROL A/B test]** 和 **[!UICONTROL Deployment]** 块跟踪其进度。

   如果您想要缩短测试持续时间，可以随时手动选择入选变体。

   测试完成后，将在 **[!UICONTROL A/B Test]** 块中显示摘要表格，以便您查看各种不同受测变体的各项指标。

1. 如果已选择 **[!UICONTROL Send after confirmation]** 作为发送方法，则必须手动选择入选变体以将其发送至其余群体。如果已选择 **[!UICONTROL Automatic]**，则系统一旦确定入选变体就会立即将其发给其余群体。

   >[!NOTE]
   >
   >如果存在关联，则必须手动选择入选变体。您可以通知电子邮件创建者和修改者，已选中或需要选择某个变体。请参阅 [Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)。

现在，您的电子邮件已经定义并发送。您可以访问其日志和报告来衡量活动是否成功。

**相关主题**：

[创建电子邮件](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/create-email-from-homepage.html)视频

## 关于 A/B 测试指标{#about-a-b-test-indicators}

电子邮件仪表板中提供了一些有助于评估 A/B 测试的指标：单击次数、打开次数、退回次数等。

请注意，**[!UICONTROL Estimated recipient reactivity]** 指标是进行了点击的收件人数目与打开了电子邮件的收件人数目之间的比值。例如，如果有 10 位收件人打开了电子邮件，并有 5 位收件人点击了该电子邮件。则反应性比率为50%。
