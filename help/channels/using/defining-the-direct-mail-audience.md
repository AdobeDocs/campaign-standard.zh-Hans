---
title: 定义直接邮寄受众
seo-title: 定义直接邮寄受众
description: 定义直接邮寄受众
seo-description: 了解如何定义直接邮寄投递目标。
page-status-flag: 从未激活
uuid: f843e368-5c07-4b53-8943-46f7bf45b62b
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: 直邮
discoiquuid: f993d1b6-4b9a-4f95-81fc-60c126211bd2
context-tags: delivery，directmailContent，返回
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Defining the direct mail audience{#defining-the-direct-mail-audience}

You can either define the audience in the creation wizard or by clicking on the **Audience** section of the delivery dashboard.

![](assets/direct_mail_15.png)

## Defining the main target {#defining-the-main-target}

对于直接邮件，目标档案是包含在提取文件中的目标档案，您将发送给直接邮寄提供商。

对于每个目标配置文件，新行都会添加到提取文件中。The amount of profile information that will be included for each recipient is defined in the [Defining the extraction](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) screen.

>[!CAUTION]
>
>请确保您的配置文件包含邮寄地址，因为此信息对于直接邮件提供商至关重要。Also make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information. See [Recommendations](../../channels/using/about-direct-mail.md#recommendations).

## Adding test and trap profiles {#adding-test-and-trap-profiles}

添加测试配置文件，以便用少量配置文件测试文件。它允许您快速创建文件示例，在准备实际文件之前测试和验证结构。Refer to [Managing test profiles and sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md).

使用陷印对于直接发送邮件是必需的。例如，它们允许您验证直接邮件提供商是否确实发送了通信，并且他们没有向其他提供商发送您的客户端列表。

对于直接邮件递送，在提取过程中添加陷印并混入输出文档中。By default, they are inserted in the sorting order of the output file, but you can choose to insert them at the end or the beginning of the file ( **[!UICONTROL Trap insertion mode]** tab).
