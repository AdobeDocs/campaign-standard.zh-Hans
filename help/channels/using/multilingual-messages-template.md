---
solution: Campaign Standard
product: campaign
title: 多语言消息模板
description: 了解如何根据自动分段客户的首选语言，通过单次投放定义和执行多语言电子邮件/短信投放。关于每次投放之绩效的报告，可以细分到语言和各个级别。
audience: start
content-type: reference
topic-tags: managing-templates
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 100%

---


# 多语言消息模板{#multilingual-messages-template}

多语言模板是用于管理多语言消息的特定模板。此类模板可用于&#x200B;**电子邮件和****短信消息**，并可用在独立模式、工作流或定期投放中。

在多语言功能模板中，语言的管理基于变体。**每个变体表示一种语言**。Adobe Campaign Standard 最多可设置 40 个变体。

Adobe Campaign 提供的默认语言设置为 **EN**。默认语言可以更改为其他变体，但不得删除。

在模板创建过程中，您可以在消息中添加与所需语言数量对应的变体数量。

要创建短信或电子邮件模板，请执行以下步骤：

1. 复制现有的多语言模板（短信或电子邮件）。

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >您也可通过单击模板属性中的 **[!UICONTROL Initialize content variant]** 按钮，修改多语言模板中的现有标准模板。

1. 修改属性以自定义标签、跟踪等。

1. 单击变体拼贴，可修改所需变体的数量。随即会显示变体窗口。

   ![](assets/multi_template_variants.png)

   您可以添加或删除变体。要添加变体，请填写 **[!UICONTROL New content variant]** 窗口。

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >请勿删除“default”变体，因为该变体将被发送到没有填写首选语言参数的用户档案。

1. 根据需要自定义标签变体，然后单击 **[!UICONTROL Confirm]**。

1. 您还可以直接为每个变体添加内容。

现在，即可根据此多语言模板创建电子邮件或短信。

**相关主题：**

* [创建多语言电子邮件](../../channels/using/creating-a-multilingual-email.md)
* [创建用户档案](../../audiences/using/creating-profiles.md)
