---
title: 关于直邮
seo-title: 关于直邮
description: 关于直邮
seo-description: 了解Adobe Campaign中直接邮寄渠道的主要特殊性。
page-status-flag: 从未激活
uuid: 24add992-2fe-4b73-81c9-cda3 e921 ab16
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: 直邮
discoiquuid: e1fbf39c-9c30-493c-8322-9c71e18ce98c
context-tags: delivery，directmailContent，back；Delivery创建，向导
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# About direct mail{#about-direct-mail}

直邮是一个线下渠道，允许您个性化并生成直邮提供商所需的文件。它使您能够在客户旅程中混合线上和线下渠道。

>[!NOTE]
>
>此功能为可选功能。请检查您的许可协议。**[!UICONTROL Export]** 使用直接邮件需要角色。请联系您的管理员。

在线渠道允许您创建消息(电子邮件、短信、移动应用程序交付等)并直接从Adobe Campaign发送给受众。线下渠道不同，准备直接邮寄邮件时，Adobe Campaign会生成一个文件，其中包括所有目标档案和所选的联系信息(例如，邮政地址)。然后，您可以将此文件发送给将负责处理实际发送的直接邮件提供商。

下节介绍如何创建和生成单镜头直接邮件传送。您还可以在工作流程中包含直接邮寄活动，以编排线上和线下渠道的营销活动。For more on this, refer to the [Workflows](../../automating/using/workflow-data-and-processes.md) guide.

Adobe Campaign中的用户流程如下：

1. 创建交付
1. 选择受众
1. 定义内容
1. 设置联系日期
1. 生成文件

## Recommendations {#recommendations}

### Direct mail providers {#direct-mail-providers}

首先，您需要联系直接邮件提供商并收集他们的建议。确定需要包含在提取文件中的配置文件信息，以便他们能够个性化通信并将其发送给受众。例如，名字、姓氏、促销代码等。These fields are the ones that you will add in the [Defining the extraction](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) tab of the direct mail's content.

Make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information. 如果激活此选项，则配置文件将添加到目标。It is not, it will excluded by a typology rule during the preparation phase (see [Creating the direct mail](../../channels/using/creating-the-direct-mail.md)). 在配置文件导入过程中，请勿忘记更新此字段。

![](assets/direct_mail_22.png)

### Postal addresses {#postal-addresses}

When you add the fields to include in the extraction file, the postal address fields are available in the **[!UICONTROL Location]** node.

Adobe Campaign为您提供了一套预定义的计算字段，这些字段遵循了最常见的邮政编码标准化。The fields are available in the **[!UICONTROL Postal address]** node.

An address can contain up to six lines by default: the first calculated field ( **[!UICONTROL Line 1]** contains the first name and last name, the next lines contain the postal address (road etc.), and the last line contains the ZIP/Postal code and town or city.

![](assets/direct_mail_23.png)

