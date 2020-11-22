---
solution: Campaign Standard
product: campaign
title: 定义电子邮件的主题行和发件人
description: 了解如何在电子邮件设计器中定义电子邮件的主题行和发件人。
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 2%

---


# 定义电子邮件的主题行和发件人{#defining-the-subject-line-of-an-email}

## Defining the subject line of an email {#subject-line}

邮件主题必须准备并发送邮件。

>[!NOTE]
>
>如果主题行为空，则消息仪表板和电子邮件设计器中会显示一条警告消息。

1. 创建电子邮件.
1. 转到“电 **[!UICONTROL Properties]** 子邮件设计器”主页卡（可通过主页图标访问）。
1. Fill in the **[!UICONTROL Subject]** section.

   ![](assets/email_designer_subject.png)

1. 您还可以通过单击相应的图标向主题行添加个性化字段、内容块和动态内容。 For more on this, see [Personalization](../../designing/using/personalization.md).
1. 您可以尝试不同的主题行，以在发送电子邮件之前获得其打开率的估计值。 有关此方面的详细信息， [请参阅测试电子邮件的主题行](../../sending/using/testing-subject-line-email.md)。

## 定义电子邮件的电子邮件发件人 {#email-sender}

要定义将显示在所发送邮件标头中的发件人姓名，请转至“电子邮件设计 **[!UICONTROL Properties]** 器”主页卡（可通过主页图标访问）。

![](assets/delivery_content_edition16.png)

* 该 **[!UICONTROL From: name]** 字段允许您输入发件人姓名。 默认情况下，默认 **发件人姓名** 块会自动输入该字段。 默认的发件人电子邮件地址和发件人姓名可 **[!UICONTROL Brands]** 通过高级菜单下的Adobe Campaign标志进行定义 **[!UICONTROL Administration > Instance settings > Brand configuration]** 。

   您可以单击“发件人姓名”块来更 **改发件人** 姓名。 然后，该字段将变为可编辑字段，您可以输入要使用的名称。

   这个领域可以个性化。 为此，您可以单击发件人姓名下方的图标，添加个性化字段、内容块和动态内容。 For more on this, see [Personalization](../../designing/using/personalization.md).

* 无法 **[!UICONTROL From: email address]** 从此部分编辑该字段。 您可以通过编辑电子邮件仪表板的属性来更改它。 有关详细信息，请参 [阅电子邮件高级参数列表](../../administration/using/configuring-email-channel.md#advanced-parameters)。

>[!NOTE]
>
>标题参数不得为空。 发送者的地址是允许发送电子邮件的必填地址（RFC标准）。 Adobe Campaign检查输入的电子邮件地址的语法。

**相关主题：**

* [插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)
* [添加内容块](../../designing/using/personalization.md#adding-a-content-block)
* [在电子邮件中定义动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
