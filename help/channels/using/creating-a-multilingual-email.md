---
title: 创建多语言电子邮件
description: 请按照以下步骤创建一封以不同首选语言为目标的多语言电子邮件。
page-status-flag: never-activated
uuid: e90f4ec8-14e3-4304-b5fc-bce0ba08a4ef
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: 79231445-1d51-499a-adcf-0c0f6db1cfa3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb5cc55c431cbe6050699a35ef2fff270f869dee

---


# 创建多语言电子邮件{#creating-a-multilingual-email}

您可以向使用不同首选语言的档案发送多语言电子邮件：每个配置文件都将收到电子邮件的变体，其语言为其首选语言。

为此，请检查您是否提供了多语言电子邮件模板。 如果没有，请在本节中了解如何创 [建一个](../../channels/using/multilingual-messages-template.md)。

受众基于具有完整首选语言信息的档案。

1. 根据多语言模板创建新的 [电子邮件](../../channels/using/multilingual-messages-template.md)。

   ![](assets/multi_create1.png)

1. 定义电子邮件的一般属性和目标受众，就像标准电子邮件一样。 请参阅创 [建受众](../../audiences/using/creating-audiences.md) 。
1. 在创建向导的第四步中，定义变体选项。 如果多语 [言模板](../../channels/using/multilingual-messages-template.md) 已包含所有正确的参数，您可以直接单击该按 **[!UICONTROL Create]**钮。

   ![](assets/multi_create4.png)

   如果需要，请使用按钮添加变 **[!UICONTROL Add an element]**体。**[!UICONTROL Default]** 不得删除变体。 设置为时， **[!UICONTROL default]**将[使用配置文件的首选语言](../../audiences/using/creating-profiles.md)，来选择变体。 您还可以将变体设**[!UICONTROL Default]** 置为任何其他语言。

1. 确认创建电子邮件：随后将显示电子邮件功能板。
1. 为每个变体定义电子邮件内容。 根据您选择的模板，您可以定义多个主题、多个发件人姓名或多个不同的内容。 使用下拉菜单在元素的不同变体之间导航。 有关详细信息，请参阅内 [容编辑器](../../designing/using/designing-content-in-adobe-campaign.md) 部分。

   ![](assets/multi_selectcontent.png)

1. 测试和验证您的消息。 请参阅发送 [证明部分](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) 。
1. 安排发送 **[!UICONTROL Send after confirmation option]**。
1. 发送电子邮件后，您可以访问其日志和报告来衡量营销活动的成功程度。 For more on reporting, refer to [this section](../../reporting/using/about-dynamic-reports.md).

**相关主题：**

* [使用一个工作流程触及多语言受众](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
