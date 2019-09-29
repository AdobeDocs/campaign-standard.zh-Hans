---
title: 定义电子邮件的主题行和发送者
seo-title: 定义电子邮件的主题行和发送者
description: 定义电子邮件的主题行和发送者
seo-description: 了解如何在电子邮件设计器中定义电子邮件的主题行和发件人。
page-status-flag: 从未激活
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0cf4807fc3d617b0c5ca33705b6344d1f3994ab3

---


# Defining the subject line and the sender of an email{#defining-the-subject-line-of-an-email}

The message subject is mandatory to prepare and send the message.

>[!NOTE]
>
>如果主题行为空，则消息功能板和电子邮件设计器中会显示一条警告消息。

要配置电子邮件主题，请转 **[!UICONTROL Properties]** 到“电子邮件设计器”主页的选项卡（可通过主页图标访问）并填写该部 **[!UICONTROL Subject]** 分。

**要定义电子邮件的主题行，请执行以下操作**:

1. 创建电子邮件。
1. 关闭主页。
1. 转到“电 **[!UICONTROL Properties]** 子邮件设计器”主页的选项卡（可通过主页图标访问）并填写该 **[!UICONTROL Subject]** 部分。

![](assets/email_designer_subject.png)

您还可以通过单击相应的图标将个性化字段、内容块和动态内容添加到主题行。

**相关主题：**

* [插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)
* [添加内容块](../../designing/using/personalization.md#adding-a-content-block)
* [在电子邮件中定义动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## 预测主题行 {#predictive-subject-line}

在编辑电子邮件时，您可以尝试不同的主题行并在发送电子邮件之前获得其打开率的估计。

默认情况下，此功能处于禁用状态。 在导入第一个模型时启用它。 模型是特定于特定行业的培训数据集的结果。 Models allow the system to predict the open rate of the email when a new subject line is submitted.

>[!NOTE]
>
>此功能适用于电子邮件和仅包含英语内容的数据库。 如果您的实例包含其他语言的电子邮件，则经过培训的模型将不一致，并会导致错误的结果。 仅当实例上已有模型可用时，才会显示用于测试主题的选项。

**相关主题**

* [测试主题行](../../sending/using/testing-subject-line-email.md)

## 电子邮件发送者 {#email-sender}

To define the name of the sender which will appear in the header of messages sent, go the  tab of the Email Designer home page (accessible through the home icon).**[!UICONTROL Properties]**

![](assets/delivery_content_edition16.png)

* The  field allows you to enter the sender name. **[!UICONTROL From: name]**&#x200B;默认情况下，默认的 **发件人姓名块** ，会自动输入该字段。 Adobe Campaign refers to the email channel configuration (from the advanced menu  via the Adobe Campaign logo) to designate this sender.**[!UICONTROL Administration > Channels > Email > Email accounts]**

   You can change the sender name by clicking the Sender name block. **** The field then becomes editable and you can enter the name you would like to use.

   这个领域可以个性化。 为此，您可以通过单击发件人姓名下方的图标来添加个性化字段、内容块和动态内容。

* 无法 **[!UICONTROL From: email address]** 从此部分编辑该字段。 您可以通过从电子邮件的功能板中编辑电子邮件的属性来更改它。 有关详细信息，请参 [阅电子邮件高级参数列表](../../administration/using/configuring-email-channel.md#advanced-parameters)。

>[!NOTE]
>
>标题参数不得为空。 The sender's address is mandatory to allow an email to be sent (RFC standard). Adobe Campaign检查输入的电子邮件地址的语法。

**相关主题：**

* [插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)
* [添加内容块](../../designing/using/personalization.md#adding-a-content-block)
* [在电子邮件中定义动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)