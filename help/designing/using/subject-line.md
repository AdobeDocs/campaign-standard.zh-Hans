---
title: 定义电子邮件的主题行和发件人
description: 了解如何在Email Designer中定义电子邮件的主题行和发件人。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Beginner
exl-id: 22112517-40f7-4966-84bf-40794e5d0f79
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 2%

---

# 定义电子邮件的主题行和发件人{#defining-the-subject-line-of-an-email}

## 定义电子邮件的主题行 {#subject-line}

消息主体必须准备和发送消息。

>[!NOTE]
>
>如果主题行为空，则消息仪表板和Email Designer中会显示警告。

1. 创建电子邮件.
1. 转到 **[!UICONTROL Properties]** （可通过主页图标访问）。
1. 填写 **[!UICONTROL Subject]** 中。

   ![](assets/email_designer_subject.png)

1. 您还可以通过单击相应的图标，将个性化字段、内容块和动态内容添加到主题行。 有关此内容的更多信息，请参阅 [个性化](../../designing/using/personalization.md).

## 定义电子邮件的电子邮件发送者 {#email-sender}

要定义将显示在发送邮件标题中的发件人名称，请转到 **[!UICONTROL Properties]** （可通过主页图标访问）。

![](assets/delivery_content_edition16.png)

* 的 **[!UICONTROL From: name]** 字段，可输入发件人名称。 默认情况下， **发件人名称** 块。 默认发件人电子邮件地址和发件人名称在 **[!UICONTROL Brands]** 可通过高级菜单下的Adobe Campaign徽标访问 **[!UICONTROL Administration > Instance settings > Brand configuration]** .

   您可以通过单击 **发件人名称** 块。 然后，该字段将变得可编辑，您可以输入要使用的名称。

   此字段可以个性化。 为此，您可以单击发件人名称下方的图标，添加个性化字段、内容块和动态内容。 有关此内容的更多信息，请参阅 [个性化](../../designing/using/personalization.md).

* 的 **[!UICONTROL From: email address]** 字段。 您可以通过从电子邮件的功能板编辑其属性来更改电子邮件。 有关更多信息，请参阅 [电子邮件高级参数列表](../../administration/using/configuring-email-channel.md#advanced-parameters).

>[!NOTE]
>
>标头参数不得为空。 发送者的地址是允许发送电子邮件的强制地址（RFC标准）。 Adobe Campaign检查输入的电子邮件地址的语法。

**相关主题：**

* [插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)
* [添加内容块](../../designing/using/personalization.md#adding-a-content-block)
* [在电子邮件中定义动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
