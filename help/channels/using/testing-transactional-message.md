---
solution: Campaign Standard
product: campaign
title: 测试事务型消息
description: 了解如何在Adobe Campaign中测试事务性消息。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: f19d4b5c1837f3f03789958abb1539d4edea0744
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 39%

---


# 测试事务型消息{#testing-a-transactional-message}

在发布事务性消息之前，您可以创建特定的测试用户档案，以便正确检查消息。

## 定义特定测试用户档案{#defining-specific-test-profile}

定义将链接到事件的测试用户档案，这样您就可以预览消息并发送相关验证。

1. 在[事务性消息仪表板](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)中，单击&#x200B;**[!UICONTROL Create test profile]**&#x200B;按钮。

   ![](assets/message-center_test-profile.png)

1. 在 **[!UICONTROL Event data used for personalization]** 部分中，指定要以 JSON 格式发送的信息。预览消息和测试用户档案接收校样时，将使用此内容。

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >如果您对消息进行了详细说明，则还可以输入与其他表相关的信息，如&#x200B;**[!UICONTROL Profile]**。 请参阅[丰富事件](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)和[个性化事务性消息](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)。

1. 创建后，将在事务性消息中预先指定测试用户档案。 单击消息的 **[!UICONTROL Test profiles]** 块，可查看校样的目标。

   ![](assets/message-center_5.png)

您还可以创建新的测试用户档案，或使用 **[!UICONTROL Test profiles]** 菜单中已存在的测试用户档案。操作步骤：

1. 单击左上角的 **[!UICONTROL Adobe Campaign]** 徽标，然后选择 **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**。
1. 在&#x200B;**[!UICONTROL Event]**&#x200B;部分，选择您刚刚创建的事件。 在本例中，选择“购物车放弃 (EVTcartAbandonment)”。
1. 在 **[!UICONTROL Event data]** 文本框中指定要以 JSON 格式发送的信息。

   ![](assets/message-center_3.png)

1. 保存更改。
1. [访问您](../../channels/using/editing-transactional-message.md#accessing-transactional-messages) 创建的消息并选择更新的测试用户档案。

**相关主题：**

* [管理测试用户档案](../../audiences/using/managing-test-profiles.md)
* [创建受众](../../audiences/using/creating-audiences.md)

## 发送验证{#sending-proof}

创建一个或多个特定测试用户档案并保存事务性消息后，可以发送验证进行测试。

![](assets/message-center_10.png)

发送验证的步骤详见[发送验证](../../sending/using/sending-proofs.md)部分。
