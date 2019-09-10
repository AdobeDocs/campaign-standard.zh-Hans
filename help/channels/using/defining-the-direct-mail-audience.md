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
source-git-commit: 27447db9ee0dd387c39976c7bd4e157a4b7899b8

---


# 定义直接邮寄受众{#defining-the-direct-mail-audience}

您可以在创建向导中定义受众，也可以单击交付功能板的 **“受众”** 部分。

![](assets/direct_mail_15.png)

## 定义主目标 {#defining-the-main-target}

对于直接邮件，目标档案是包含在提取文件中的目标档案，您将发送给直接邮寄提供商。

对于每个目标配置文件，新行都会添加到提取文件中。将在 [定义提取](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) 屏幕中定义每个收件人所包含的配置文件信息量。

>[!CAUTION]
>
>请确保您的配置文件包含邮寄地址，因为此信息对于直接邮件提供商至关重要。同时确保已选中配置文件信息 **[!UICONTROL Address specified]** 中的复选框。请参阅 [推荐](../../channels/using/about-direct-mail.md#recommendations)。

## 添加测试和陷印配置文件 {#adding-test-and-trap-profiles}

添加测试配置文件，以便用少量配置文件测试文件。它允许您快速创建文件示例，在准备实际文件之前测试和验证结构。请参阅 [管理测试配置文件和发送校样](../../sending/using/managing-test-profiles-and-sending-proofs.md)。

使用陷印对于直接发送邮件是必需的。它们允许您验证直接邮件提供商是否确实发送了通信，并且他们没有向其他提供商发送您的客户端列表。请参阅 [使用陷印](../../sending/using/managing-test-profiles-and-sending-proofs.md#using-traps)。

对于直接邮件递送，在提取过程中添加陷印并混入输出文档中。默认情况下，它们会插入输出文件的排序顺序，但您可以选择在文件的结尾或开头插入它们。定义受众时，从 **[!UICONTROL Trap insertion mode]** 选项卡中选择所需的选项。

![](assets/direct_mail_trap_insertion_mode.png)
