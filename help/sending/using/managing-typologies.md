---
title: 管理类型
description: 了解如何使用类型。
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ec0af8c06e36f51ddaf6e3d4190fa6acd56d2da6

---


# 管理类型 {#managing-typologies}

## 关于类型 {#about-typologies}

类型是一组规则，允许您在发送邮件之前检查邮件的有效性。 例如：消息内容不为空、存在退订、排除重复等。

可通过> **[!UICONTROL Administration]** >菜单访 **[!UICONTROL Channels]** 问 **[!UICONTROL Typologies]** 字体。 默认情况下，应用程序中有默认的类型。 根据您的需求，您可以创建自己的字体或修改现有的字体。

![](assets/typologies-list.png)

对于每种类型， **[!UICONTROL Typology rules]** 该部分列表在使用带有消息的类型时执行的规则集。

![](assets/typology_typo-rule-list.png)

>[!NOTE]
>
>要获取有关某个类型规则的更多详细信息，请多次单击它。 规则将以只读模式显示。

## 创建类型学 {#creating-a-typology}

要创建新的排版，请按照以下步骤操作：

1. 访问 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** >菜 **[!UICONTROL Typologies]** 单。

1. 此时将显示列表。 Click the **[!UICONTROL Create]** button.

   ![](assets/typologies-list.png)

1. 定义类 **[!UICONTROL Label]**&#x200B;型，然后单 **[!UICONTROL Add an element]** 击按钮以选择要包含在其中的类型规则。 For more on typology rules, refer to [this section](../../sending/using/managing-typology-rules.md).

   ![](assets/typology_addrules.png)

   >[!NOTE]
   >
   >该 **[!UICONTROL IP affinity]** 字段允许您根据配置管理关联。 它们在实例的配置文件中定义。 如果要使用关联，请与管理员联系。

1. 单击 **[!UICONTROL Create]** 以确认您的选择。 您的排版现已准备好用于消息。

## 对消息应用类型 {#applying-typologies-to-messages}

将排版学与消息或消息模板关联时，将执行排版学中包含的类型规则以检查消息的有效性。

>[!NOTE]
>
>每个消息或消息模板只能分配一个类型学。

要将类型学链接到消息，请执行以下步骤：

1. 访问消息属性。 请注意，消息模板可从 **[!UICONTROL Resources]** >导航菜 **[!UICONTROL Templates]** 单访问。

1. 在 **[!UICONTROL Advanced parameters]** >部 **[!UICONTROL Prearation]** 分中，选择要链接到消息的类型学。

   ![](assets/typology_message.png)

1. 单击 **[!UICONTROL Confirm]**.

   现在，选定的类型学已链接到消息。 将执行其所有关联类型规则以检查消息的有效性。
