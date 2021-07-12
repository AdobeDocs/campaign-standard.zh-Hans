---
solution: Campaign Standard
product: campaign
title: 定义电子邮件的主题行和发件人
description: 了解如何在Email Designer中定义电子邮件的主题行和发件人。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: 电子邮件设计
role: User
level: Beginner
exl-id: 22112517-40f7-4966-84bf-40794e5d0f79
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 2%

---

# 定义电子邮件的主题行和发件人{#defining-the-subject-line-of-an-email}

## 定义电子邮件的主题行 {#subject-line}

消息主体必须准备和发送消息。

>[!NOTE]
>
>如果主题行为空，则消息仪表板和Email Designer中会显示警告。

1. 创建电子邮件.
1. 转到Email Designer主页的&#x200B;**[!UICONTROL Properties]**&#x200B;选项卡（可通过主页图标访问）。
1. 填写&#x200B;**[!UICONTROL Subject]**&#x200B;部分。

   ![](assets/email_designer_subject.png)

1. 您还可以通过单击相应的图标，将个性化字段、内容块和动态内容添加到主题行。 有关更多信息，请参阅[个性化](../../designing/using/personalization.md)。

## 定义电子邮件的电子邮件发送者 {#email-sender}

要定义将显示在发送邮件标题中的发件人名称，请转到Email Designer主页的&#x200B;**[!UICONTROL Properties]**&#x200B;选项卡（可通过主页图标访问）。

![](assets/delivery_content_edition16.png)

* **[!UICONTROL From: name]**&#x200B;字段允许您输入发件人名称。 默认情况下，默认的&#x200B;**发件人名称**&#x200B;块会自动输入到字段中。 默认的发件人电子邮件地址和发件人姓名在&#x200B;**[!UICONTROL Brands]**&#x200B;中定义，可通过高级菜单&#x200B;**[!UICONTROL Administration > Instance settings > Brand configuration]**&#x200B;下的Adobe Campaign徽标访问。

   您可以通过单击&#x200B;**发件人名称**&#x200B;块来更改发件人名称。 然后，该字段将变得可编辑，您可以输入要使用的名称。

   此字段可以个性化。 为此，您可以单击发件人名称下方的图标，添加个性化字段、内容块和动态内容。 有关更多信息，请参阅[个性化](../../designing/using/personalization.md)。

* 无法从此部分编辑&#x200B;**[!UICONTROL From: email address]**&#x200B;字段。 您可以通过从电子邮件的功能板编辑其属性来更改电子邮件。 有关更多信息，请参阅[电子邮件高级参数列表](../../administration/using/configuring-email-channel.md#advanced-parameters)。

>[!NOTE]
>
>标头参数不得为空。 发送者的地址是允许发送电子邮件的强制地址（RFC标准）。 Adobe Campaign检查输入的电子邮件地址的语法。

**相关主题：**

* [插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)
* [添加内容块](../../designing/using/personalization.md#adding-a-content-block)
* [在电子邮件中定义动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
