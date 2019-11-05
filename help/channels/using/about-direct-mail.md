---
title: 关于直邮
description: 了解Adobe Campaign中直邮渠道的主要特性。
page-status-flag: 从未激活
uuid: 24add992-2efe-4b73-81c9-cda3e921ab16
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 频道
content-type: 参考
topic-tags: 直邮
discoiquuid: e1fbf39c-9c30-493c-8322-9c71e18ce98c
context-tags: delivery,directMailContent,back;deliveryCreation，向导
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 关于直邮{#about-direct-mail}

直邮是一个脱机渠道，允许您个性化和生成直邮提供商所需的文件。 它使您能够在客户旅程中混合使用线上和线下渠道。

>[!NOTE]
>
>此功能是可选的。 请检查您的许可协议。 使 **[!UICONTROL Export]** 用直邮需要角色。 请联系您的管理员。

在线渠道允许您创建消息（电子邮件、短信、移动应用交付等）并直接从Adobe Campaign将其发送给您的受众。 离线渠道则有所不同。 在准备直邮递送时，Adobe Campaign会生成一个文件，其中包含所有目标配置文件和选定的联系信息（例如邮政地址）。 然后，您可以将此文件发送给直接邮件提供商，由其负责实际发送。

以下部分介绍如何创建和生成一次性直接邮寄服务。 您还可以在工作流中包含直接邮件活动，以编排将线上和线下渠道组合在一起的营销活动。 有关详细信息，请参阅工作 [流指南](../../automating/using/workflow-data-and-processes.md) 。

Adobe Campaign中的用户流程如下：

1. 创建交付
1. 选择受众
1. 定义内容
1. 设置联系日期
1. 生成文件

## 建议 {#recommendations}

### 直邮提供商 {#direct-mail-providers}

首先，您需要联系直邮提供商并收集其推荐。 确定提取文件中需要包含哪些档案信息，以便他们能够个性化通信并将其发送给受众。 例如，名字和姓氏、邮政地址、促销代码等。 这些字段是您要在直接邮件内容的“定 [义提取](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) ”选项卡中添加的字段。

确保选中了配置 **[!UICONTROL Address specified]** 文件信息中的框。 如果激活了此选项，则配置文件将添加到目标。 它不是，它将在准备阶段被一个排版规则排除(请参阅 [创建直邮](../../channels/using/creating-the-direct-mail.md))。 在导入配置文件时，请勿忘记更新此字段。

![](assets/direct_mail_22.png)

### 邮政地址 {#postal-addresses}

在添加要包含在提取文件中的字段时，节点中会显示邮政地址字 **[!UICONTROL Location]** 段。

Adobe Campaign为您提供一组预定义的计算字段，这些字段遵循最常见的邮政地址标准化。 这些字段在节点中可 **[!UICONTROL Postal address]** 用。

默认情况下，地址最多可包含六行：第一个计算的字 **[!UICONTROL Line 1]** 段(包含名字和姓氏，下一行包含邮政地址（公路等），最后一行包含邮政编码和城镇。

![](assets/direct_mail_23.png)

