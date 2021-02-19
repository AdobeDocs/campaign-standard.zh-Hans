---
solution: Campaign Standard
product: campaign
title: 定义电子邮件的主题行和发件人
description: 了解如何在电子邮件设计器中定义电子邮件的主题行和发件人。
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 1e7359db2de1a9c420af33ac85c0597c098ae3f8
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 2%

---


# 定义电子邮件的主题行和发件人{#defining-the-subject-line-of-an-email}

## 定义电子邮件{#subject-line}的主题行

邮件主题是准备和发送邮件的必填项。

>[!NOTE]
>
>如果主题行为空，则消息仪表板和电子邮件设计器中会显示警告。

1. 创建电子邮件.
1. 转到“电子邮件设计器”主页的&#x200B;**[!UICONTROL Properties]**&#x200B;选项卡（可通过主页图标访问）。
1. 填写&#x200B;**[!UICONTROL Subject]**&#x200B;部分。

   ![](assets/email_designer_subject.png)

1. 您还可以通过单击相应的图标将个性化字段、内容块和动态内容添加到主题行。 有关详细信息，请参阅[个性化](../../designing/using/personalization.md)。

## 定义电子邮件{#email-sender}的电子邮件发件人

要定义将显示在所发送邮件标头中的发件人姓名，请转到“电子邮件设计器”主页的&#x200B;**[!UICONTROL Properties]**&#x200B;选项卡（可通过主页图标访问）。

![](assets/delivery_content_edition16.png)

* **[!UICONTROL From: name]**&#x200B;字段允许您输入发件人名称。 默认情况下，默认的&#x200B;**发件人名称**&#x200B;块会自动输入到字段中。 默认发件人电子邮件地址和发件人姓名在&#x200B;**[!UICONTROL Brands]**&#x200B;中定义，可通过高级菜单&#x200B;**[!UICONTROL Administration > Instance settings > Brand configuration]**&#x200B;下的Adobe Campaign徽标访问。

   单击&#x200B;**发件人姓名**&#x200B;块可以更改发件人姓名。 然后，该字段将变为可编辑，您可以输入要使用的名称。

   这个领域可以个性化。 为此，您可以单击发件人姓名下方的图标，添加个性化字段、内容块和动态内容。 有关详细信息，请参阅[个性化](../../designing/using/personalization.md)。

* 无法从此部分编辑&#x200B;**[!UICONTROL From: email address]**&#x200B;字段。 您可以通过编辑电子邮件仪表板的属性来更改它。 有关详细信息，请参阅[电子邮件高级参数列表](../../administration/using/configuring-email-channel.md#advanced-parameters)。

>[!NOTE]
>
>标题参数不得为空。 发送者的地址是允许发送电子邮件的必填地址（RFC标准）。 Adobe Campaign检查输入的电子邮件地址的语法。

**相关主题：**

* [插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)
* [添加内容块](../../designing/using/personalization.md#adding-a-content-block)
* [在电子邮件中定义动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
