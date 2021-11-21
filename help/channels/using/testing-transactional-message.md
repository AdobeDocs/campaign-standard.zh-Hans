---
title: 测试事务性消息
description: 了解如何在Adobe Campaign中测试事务型消息。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 5138826d-ae08-403b-91ef-91027ef6e78e
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 36%

---

# 测试事务性消息 {#testing-a-transactional-message}

在发布事务型消息之前，您可以创建特定的测试用户档案，以便正确检查消息。

## 定义特定测试用户档案 {#defining-specific-test-profile}

定义将链接到事件的测试用户档案，以便预览消息并发送相关校样。

1. 从 [事务性消息仪表板](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)，请单击 **[!UICONTROL Create test profile]** 按钮。

   ![](assets/message-center_test-profile.png)

1. 在 **[!UICONTROL Event data used for personalization]** 部分中，指定要以 JSON 格式发送的信息。预览消息和测试用户档案接收校样时，将使用此内容。

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >如果您扩充了消息，则还可以输入与其他表格相关的信息，例如 **[!UICONTROL Profile]**. 请参阅 [丰富活动内容](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) 和 [个性化事务型消息](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

1. 创建后，将在事务型消息中预先指定测试用户档案。 单击消息的 **[!UICONTROL Test profiles]** 块，可查看校样的目标。

   ![](assets/message-center_5.png)

您还可以创建新的测试用户档案，或使用 **[!UICONTROL Test profiles]** 菜单中已存在的测试用户档案。操作步骤：

1. 单击 **Adobe** 徽标，然后选择 **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. 在 **[!UICONTROL Event]** 部分，选择之前创建的事件。 在本例中，选择“购物车放弃 (EVTcartAbandonment)”。
1. 在 **[!UICONTROL Event data]** 文本框中指定要以 JSON 格式发送的信息。

   ![](assets/message-center_3.png)

1. 保存更改。
1. [访问消息](../../channels/using/editing-transactional-message.md#accessing-transactional-messages) 创建的测试用户档案，然后选择更新的测试用户档案。

**相关主题：**

* [管理测试用户档案](../../audiences/using/managing-test-profiles.md)
* [创建受众](../../audiences/using/creating-audiences.md)

## 发送校样 {#sending-proof}

创建一个或多个特定测试用户档案并保存事务型消息后，即可发送校样以对其进行测试。

![](assets/message-center_10.png)

有关发送校样的详细步骤，请参见 [发送校样](../../sending/using/sending-proofs.md) 中。
