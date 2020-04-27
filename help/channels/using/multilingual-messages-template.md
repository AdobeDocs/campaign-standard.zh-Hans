---
title: 多语言消息模板
description: 了解如何根据自动细分的客户首选语言通过单一投放定义和执行多语言电子邮件／短信投放。 报告每个投放的性能，包括语言和各个级别。
page-status-flag: never-activated
uuid: 7a2cd5f7-c0fc-4825-a770-a62816c66b3f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: managing-templates
discoiquuid: 064c5c4a-f579-4bab-adf3-51c92eb4518f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# 多语言消息模板 {#multilingual-messages-template}

多语言模板是用于管理多语言消息的特定模板。 此类模板可用于 **Email** **SMS消息和SMS消息** ，并可在独立模式、工作流程或循环投放中使用。

在多语言功能模板中，语言管理基于变体。 **每个变体都表示一种语言**。 Adobe Campaign标准版最多可设置40个变体。

Adobe Campaign附带设置为 **EN的默认语言**。 默认语言可以更改为其他变体，但不应删除。

在模板创建过程中，您可以在消息中添加与所需语言数量相对应的变体数量。

要创建SMS或电子邮件模板，请执行以下步骤：

1. 重复现有的多语言模板（SMS或电子邮件）。

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >您还可以通过单击模板属性中的按钮来修改多语言模板中 **[!UICONTROL Initialize content variant]** 的现有标准模板。

1. 修改属性以自定义标签、跟踪等。
1. 单击变体拼贴可修改所需变体的数量。 随即会显示变体窗口

   ![](assets/multi_template_variants.png)

   您可以添加或删除变体。 要添加变体，请完成该 **[!UICONTROL New content variant]** 窗口。

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >请勿删除“default”变体，因为它是发送到用户档案的变体，但没有完整的首选语言参数。

1. 根据需要自定义标签变体，然后单击 **[!UICONTROL Confirm]**。
1. 您还可以直接为每个变体添加内容。

您现在可以基于此多语言模板创建电子邮件或SMS消息。

**相关主题：**

* [创建多语言电子邮件](../../channels/using/creating-a-multilingual-email.md)
* [创建用户档案](../../audiences/using/creating-profiles.md)
