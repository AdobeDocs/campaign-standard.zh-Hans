---
title: 定义直邮受众
description: 了解如何定义直邮递送的目标。
page-status-flag: 从未激活
uuid: f843e368-5c07-4b53-8943-46f7bf45b62b
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 频道
content-type: 参考
topic-tags: 直邮
discoiquuid: f993d1b6-4b9a-4f95-81fc-60c126211bd2
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 定义直邮受众{#defining-the-direct-mail-audience}

您可以在创建向导中定义受众，也可以通过单击交付仪表板的“ **受众** ”部分来定义受众。

![](assets/direct_mail_15.png)

## 定义主目标 {#defining-the-main-target}

对于直邮，目标配置文件是将包含在提取文件中的配置文件，您会将其发送给直邮提供商。

对于每个目标配置文件，提取文件中会添加一个新行。 定义提取屏幕中定义了将包括给每个收件人的配置文件 [信息的数量](#defining-the-extraction) 。

>[!CAUTION]
>
>确保您的配置文件包含邮政地址，因为这些信息对直邮提供商至关重要。 另外，请确保已选中配 **[!UICONTROL Address specified]** 置文件信息中的复选框。 请参阅 [推荐](../../channels/using/about-direct-mail.md#recommendations)。

## 添加测试和陷印配置文件 {#adding-test-and-trap-profiles}

添加测试配置文件，以便使用少量配置文件测试文件。 它允许您在准备实际文件之前快速创建一个文件范例以测试和验证结构。 See [Managing test profiles and sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md).

使用陷阱是直接发送邮件的关键。 它们允许您验证您的直邮提供商是否确实在发送通信，以及他们是否没有将您的客户列表发送给其他提供商。 请参阅 [使用陷印](../../sending/using/managing-test-profiles-and-sending-proofs.md#using-traps)。

对于直接邮件发送，在提取过程中添加陷印并混合在输出文档中。 默认情况下，它们按输出文件的排序顺序插入，但您可以选择在文件的结尾或开头插入。 定义受众时，从选项卡中选择所需的 **[!UICONTROL Trap insertion mode]** 选项。

![](assets/direct_mail_trap_insertion_mode.png)
