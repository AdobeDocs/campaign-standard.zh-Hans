---
title: 创建多语言模板
seo-title: 创建多语言模板
description: 创建多语言模板
seo-description: 了解如何根据自动细分客户的首选语言通过单次交付定义和执行多语言电子邮件/SMS交付。报告每个分发的效果，涵盖语言和各个级别。
page-status-flag: 从未激活
uuid: 7a2cd5f7-c0 fc-4825-a770-a62816 c66 b3 f
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: 管理模板
discoiquuid: 064c5c4a-f579-4bab-adf3-51c92 eb4518 f
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Creating a multilingual template{#creating-a-multilingual-template}

多语言模板是用于管理多语言消息的特定模板。

This kind of template is available for **Email and SMS messages** and useable in standalone mode, within a workflow or in a recurring delivery.

在多语言功能模板中，语言管理基于变体。**每个变体表示一种语言。**

Adobe Campaign Standard最多可设置40种变体。

Adobe Campaign附带的默认语言设置为EN。默认语言可能会更改为其他变体，但绝不应删除。

在模板创建过程中，您可以添加与消息中所需语言数量对应的变体数。

要执行SMS或电子邮件模板的创建，请执行以下步骤：

1. 复制现有的多语言模板(SMS或电子邮件)。

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >You can also modify an existing standard template in a multilingual template by clicking on the **[!UICONTROL Initialize content variant]** button in the template properties.

1. 修改属性以自定义标签、跟踪等。
1. 通过单击变体拼贴修改所需变体的数量。此时会显示变体窗口

   ![](assets/multi_template_variants.png)

   您可以添加或删除变体。To add a variant, complete the **[!UICONTROL New content variant]** window.

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >请勿删除“default”变体，因为它是发送到配置文件的变体，而不是已完成的首选语言参数。

1. 根据需要自定义标签变体，然后单击确认。
1. 您还可以直接为每个变体添加内容。

您现在可以根据此多语言模板创建电子邮件或SMS消息。

**相关主题：**

* [创建多语言电子邮件](../../channels/using/creating-a-multilingual-email.md)
* [创建配置文件](../../audiences/using/creating-profiles.md)

