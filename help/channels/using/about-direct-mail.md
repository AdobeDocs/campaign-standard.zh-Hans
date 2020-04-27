---
title: 关于直邮
description: 了解Adobe Campaign直邮渠道的主要特点。
page-status-flag: never-activated
uuid: 24add992-2efe-4b73-81c9-cda3e921ab16
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: e1fbf39c-9c30-493c-8322-9c71e18ce98c
context-tags: delivery,directMailContent,back;deliveryCreation,wizard
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# 关于直邮{#about-direct-mail}

直邮是一种脱机渠道，允许您个性化和生成直邮提供商所需的文件。 它使您能够在客户旅程中混合使用线上和线下渠道。

>[!NOTE]
>
>此功能是可选的。 请检查您的许可协议。 使 **[!UICONTROL Export]** 用直邮需要角色。 请联系您的管理员。

在线渠道允许您创建消息(电子邮件、SMS、移动应用投放等)直接从Adobe Campaign寄到受众。 离线渠道则不同。 当您准备直邮投放时，Adobe Campaign会生成一个文件，其中包含所有目标用户档案和所选联系信息（例如，邮政地址）。 然后，您可以将此文件发送给直接邮件提供商，由其负责实际发送。

以下部分介绍如何创建和生成一次性直接邮寄投放。 您还可以在工作流中包含直接邮件活动，以编排将联机和脱机渠道组合在一起的活动。 有关详细信息，请参阅 [工作流](../../automating/using/workflow-data-and-processes.md) 。

Adobe Campaign中的用户进程如下：

1. 创建投放
1. 选择受众
1. 定义内容
1. 设置联系日期
1. 生成文件

## 建议 {#recommendations}

### 直邮提供商 {#direct-mail-providers}

首先，您需要联系直邮提供商并收集其推荐。 确定哪些用户档案信息需要包含在提取文件中，以便他们能够个性化通信并将其发送给受众。 例如，名字和姓氏、邮政地址、促销代码等。 这些字段是您要在直邮内容的“定 [义提取](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) ”选项卡中添加的字段。

确保选中了用户档案信 **[!UICONTROL Address specified]** 息中的框。 如果激活了此选项，用户档案将添加到目标。 不是，它将在准备阶段被类型规则排除(请参阅创 [建直邮](../../channels/using/creating-the-direct-mail.md))。 在用户档案导入过程中，请勿忘记更新此字段。

![](assets/direct_mail_22.png)

### 邮政地址 {#postal-addresses}

添加要包含在提取文件中的字段时，节点中会显示邮政地址字 **[!UICONTROL Location]** 段。

Adobe Campaign优惠一组遵循最常见的邮政地址标准化的预定义计算字段。 这些字段在节点中可 **[!UICONTROL Postal address]** 用。

默认情况下，地址最多可包含六行：第一个计算字段&#x200B;**[!UICONTROL Line 1]** (包含名字和姓氏，下一行包含邮政地址（路等），最后一行包含邮政编码和城镇。

![](assets/direct_mail_23.png)

