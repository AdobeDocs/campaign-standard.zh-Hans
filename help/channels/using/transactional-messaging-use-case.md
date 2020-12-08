---
title: 配置事务型消息传递
description: 了解如何配置事务消息传递。
page-status-flag: never-activated
uuid: 4caeadbe-f4a7-43ce-986d-e99fa9ca0d0d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 3f968556-e774-43dc-a0b8-7188d7665fbc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: caa41d6c727385bd6e77f64750872f191a5ad040
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 3%

---


# 事务消息使用案例{#transactional-messaging-use-case}

在此示例中，您希望使用Adobe Campaign事务消息传递功能在您网站上的每次购买后发送确认电子邮件，通过客户的CRM ID识别客户。

先决条件如下：

* 确保&#x200B;**[!UICONTROL Profile]**&#x200B;资源已扩展，并且新字段与CRM ID对应。

* 创建并发布与购买对应的自定义资源，并将其链接到&#x200B;**[!UICONTROL Profile]**&#x200B;资源。 这样，您将能够从此资源检索信息以丰富消息内容。

有关扩展、创建和发布资源的详细信息，请参阅[此部分](../../developing/using/key-steps-to-add-a-resource.md)。

实施此用例的主要步骤如下。

>[!NOTE]
>
>有关事务消息传递一般进程的图形表示，请参阅[此模式](../../channels/using/getting-started-with-transactional-msg.md#key-steps)。

## 第1步——创建并发布事件配置{#create-event-configuration}

1. 使用&#x200B;**[!UICONTROL Email]**&#x200B;事件创建新渠道。 请参阅[创建事件](../../channels/using/configuring-transactional-event.md#creating-an-event)。

1. 选择&#x200B;**[!UICONTROL Profile]**&#x200B;定位维度以创建基于[用户档案的事务性消息](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages)。

1. 定义可用于个性化事务性消息的属性。 在此示例中，添加“CRM ID”和“产品标识符”字段。 请参阅[定义事件属性](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)。

   ![](assets/message-center_usecase1.png)

1. 要用客户购买的相关信息丰富消息内容，请创建一个面向&#x200B;**[!UICONTROL Purchase]**&#x200B;资源的扩充。 请参阅[丰富事件](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)。

   ![](assets/message-center_usecase2.png)

1. 在以前添加到事件的“产品标识符”字段与&#x200B;**[!UICONTROL Purchase]**&#x200B;资源中的相应字段之间创建连接条件。

   ![](assets/message-center_usecase3.png)

1. 由于这对于基于用户档案的事件是必备的，因此您还必须创建一个扩充，以&#x200B;**[!UICONTROL Profile]**&#x200B;资源为目标。

1. 在以前添加到消息的“CRM ID”字段和您扩展的&#x200B;**[!UICONTROL Profile]**&#x200B;资源中的相应字段之间创建连接条件。<!--What's the purpose to have created a CRM ID for this event and to have the CRM ID as a join condition? could it be any other field provided you created it in the event?-->

   ![](assets/message-center_usecase4.png)

1. 在&#x200B;**[!UICONTROL Targeting enrichment]**&#x200B;部分，选择&#x200B;**[!UICONTROL Profile]**&#x200B;资源上的扩充，该目标将在投放执行期间用作消息。

   ![](assets/message-center_usecase5.png)

1. 预览并发布事件。 请参阅[预览和发布事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

## 第2步——编辑并发布事务性消息{#create-transactional-message}

1. 转到发布事务性消息时自动创建的事件。 请参阅[访问事务性消息](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)。

1. 编辑并个性化信息。 请参阅[编辑用户档案事务性消息](../../channels/using/editing-transactional-message.md#editing-profile-transactional-message)。

1. 通过与您添加到&#x200B;**[!UICONTROL Profile]**&#x200B;资源的“CRM ID”字段进行协调，您可以直接访问所有用户档案信息，将消息发送到[个性化](../../designing/using/personalization.md#inserting-a-personalization-field)。

   ![](assets/message-center_usecase6.png)

1. 通过与“产品标识符”字段进行对帐，您可以通过添加&#x200B;**[!UICONTROL Purchase]**&#x200B;资源中的任何字段，以丰富有关客户购买的信息的消息内容。

   ![](assets/message-center_usecase7.png)

   为此，请从上下文工具栏中选择&#x200B;**[!UICONTROL Insert personalization field]**。 从&#x200B;**[!UICONTROL Context]** > **[!UICONTROL Transactional event]** > **[!UICONTROL Event context]**&#x200B;节点中，打开与&#x200B;**[!UICONTROL Purchase]**&#x200B;自定义资源对应的节点，然后选择任意字段。

1. 您可以使用特定的测试用户档案测试消息。 请参阅[测试事务性消息](../../channels/using/testing-transactional-message.md#testing-a-transactional-message)。

1. 内容准备就绪后，保存更改并发布消息。 请参阅[发布事务型消息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)。

## 第3步——集成触发{#integrate-event-trigger}的事件

将事件集成到您的网站中。 请参阅[集成触发事件](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)。

## 第4步——消息投放{#message-delivery}

执行所有这些步骤后，一旦客户从您的网站购买产品，他们就会收到一封个性化的确认电子邮件，其中包含有关其购买的信息。