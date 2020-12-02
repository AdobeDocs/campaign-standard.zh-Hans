---
solution: Campaign Standard
product: campaign
title: 事件事务型消息
description: 了解如何创建和发布事件事务型消息。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: 4e157a582de836fa325d95593491c756209b205e
workflow-type: tm+mt
source-wordcount: '1352'
ht-degree: 77%

---


# 事务性消息生命周期{#publishing-transactional-message}

当[事务性消息](../../channels/using/editing-transactional-message.md)准备好发送时，可以发布它。

测试、发布、暂停、取消发布和删除事件的步骤详述如下。 本节还介绍事务消息重试过程。

## 事务型消息传递发布流程 {#transactional-messaging-pub-process}

下图说明了整个交易消息发布流程。

![](assets/message-center_pub-process.png)

有关发布事务性消息的详细信息，请参阅[此部分](#publishing-a-transactional-message)。
有关暂停事务性消息的详细信息，请参阅[此部分](#suspending-a-transactional-message-publication)。
有关取消发布事务性消息的详细信息，请参阅[此部分](#unpublishing-a-transactional-message)。

有关发布和取消发布事件的详细信息，请参阅[此部分](../../channels/using/publishing-transactional-event.md)。

## 测试事务型消息{#testing-a-transactional-message}

您首先需要创建特定的测试用户档案，以便能够正确检查事务性消息。

### 定义特定测试用户档案{#defining-specific-test-profile}

定义将链接到事件的测试用户档案，以便预览消息并发送相关验证。

1. 在事务性消息仪表板中，单击&#x200B;**[!UICONTROL Create test profile]**&#x200B;按钮。

   ![](assets/message-center_test-profile.png)

1. 在 **[!UICONTROL Event data used for personalization]** 部分中，指定要以 JSON 格式发送的信息。预览消息和测试用户档案接收校样时，将使用此内容。

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >您还可以输入与用户档案表格有关的信息。请参阅[丰富事件](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)<!--and [Personalizing a transactional message](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)-->。

1. 创建后，将在用户档案中预指定测试事务性消息。 单击消息的 **[!UICONTROL Test profiles]** 块，可查看校样的目标。

   ![](assets/message-center_5.png)

您还可以创建新的测试用户档案，或使用 **[!UICONTROL Test profiles]** 菜单中已存在的测试用户档案。操作步骤：

1. 单击左上角的 **[!UICONTROL Adobe Campaign]** 徽标，然后选择 **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**。
1. 在&#x200B;**[!UICONTROL Event]**&#x200B;部分，选择您刚刚创建的事件。 在本例中，选择“购物车放弃 (EVTcartAbandonment)”。
1. 在 **[!UICONTROL Event data]** 文本框中指定要以 JSON 格式发送的信息。

   ![](assets/message-center_3.png)

1. 保存更改。
1. 访问您创建的消息并选择更新的测试用户档案。

**相关主题：**

* [管理测试用户档案](../../audiences/using/managing-test-profiles.md)
* [创建受众](../../audiences/using/creating-audiences.md)

### 发送验证{#sending-proof}

创建一个或多个特定测试用户档案并保存事务性消息后，可以发送验证进行测试。

![](assets/message-center_10.png)

发送验证的步骤详见[发送验证](../../sending/using/sending-proofs.md)一节。

## 发布事务型消息{#publishing-a-transactional-message}

检查事务型消息后，即可进行发布。

![](assets/message-center_12.png)

现在，一旦触发“购物车废弃”事件，就会自动提示发送消息，其中包含收件人的头衔和姓氏、购物车 URL、查看的最后一个产品或产品清单（如果您定义了产品清单）以及购物车总金额。

要访问有关事务型消息的报告，请使用 **[!UICONTROL Reports]** 按钮。请参阅[动态报告](../../reporting/using/about-dynamic-reports.md)。

![](assets/message-center_13.png)

### 暂停事务型消息发布{#suspending-a-transactional-message-publication}

例如，可以使用 **[!UICONTROL Pause]** 按钮暂停发布事务型消息，以修改消息中包含的数据。这样，就不会再处理事件，而是将其保留在 Adobe Campaign 数据库的队列中。

排队的事件在REST API中定义的时间段内保留(请参阅[REST API文档](../../api/using/managing-transactional-messages.md)或在使用触发器核心服务时的触发器事件中保留(请参阅[关于Adobe Experience Cloud触发器](../../integrating/using/about-adobe-experience-cloud-triggers.md))。

![](assets/message-center_pause.png)

单击 **[!UICONTROL Resume]** 后，将继续处理所有排队的事件（前提是它们未过期）。现在，它们包含暂停模板发布时执行的所有修改。

### 取消发布事务型消息{#unpublishing-a-transactional-message}

单击 **[!UICONTROL Unpublish]** 可取消事务型消息发布，但也会取消相应事件的发布，从 REST API 中删除与之前创建的事件对应的资源。

![](assets/message-center_unpublish-template.png)

现在，即使是通过您的网站触发了事件，也不再发送相应的消息，也不会将消息存储在数据库中。

>[!NOTE]
>
>要再次发布消息，您需要返回相应的事件配置[发布事件](../../channels/using/publishing-transactional-event.md)，然后[发布消息](#publishing-a-transactional-message)。

如果取消发布已暂停的事务型消息，则可能需要等待最多 24 小时，才能再次发布该消息。这是为了让 **[!UICONTROL Database cleanup]** 工作流清理发送到队列的所有事件。

有关暂停消息的详细步骤，请参阅[暂停事务型消息发布](#suspending-a-transactional-message-publication)一节。

**[!UICONTROL Database cleanup]** 工作流每天凌晨 4 点运行，可通过 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Workflows]** 访问。

### 删除事务型消息{#deleting-a-transactional-message}

取消发布某条事务型消息后，或尚未发布该事务型消息时，可以从事务型消息列表中删除该消息。操作步骤：

1. 单击左上角的 **[!UICONTROL Adobe Campaign]** 徽标，然后选择 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**。
1. 将鼠标指针悬停在您选择的消息上。
1. 单击 **[!UICONTROL Delete element]** 按钮。

![](assets/message-center_delete-template.png)

但是，删除事务型消息只能在特定条件下完成：

* 确保事务型消息具有 **[!UICONTROL Draft]** 状态，否则您将无法删除它。**[!UICONTROL Draft]** 状态适用于尚未发布或[已取消发布](#unpublishing-a-transactional-message)（且[未暂停](#suspending-a-transactional-message-publication)）的消息。

* **事务型消息**：除非将其他事务型消息链接到相应的事件，否则如果事务型消息已取消发布，则还需要取消发布事件配置才能成功删除事务型消息。有关更多信息，请参阅[取消发布事件](../../channels/using/publishing-transactional-event.md#unpublishing-an-event)。

   >[!IMPORTANT]
   >
   >删除已发送通知的事务型消息，也会删除其发送和跟踪日志。

* **来自现成事件模板的事务型消息（内部事务型消息）**：如果内部事务型消息是唯一与相应内部事件关联的消息，则无法删除该消息。首先必须复制事务型消息或通过 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Transactional message templates]** 菜单创建另一个事务型消息。

## 事务型消息重试流程{#transactional-message-retry-process}

临时未投放的事务型消息将会自动重试，一直执行到投放过期为止。有关投放持续时间的更多信息，请参阅[有效性参数](../../administration/using/configuring-email-channel.md#validity-period-parameters)。

发送事务型消息失败时，可使用以下两个重试系统：

* 在事务型消息传递级别，如果将事务型消息放在分配给执行投放的事件之前，有可能会失败，这意味着，应放在事件接收和投放准备之间。请参阅[事件处理重试流程](#event-processing-retry-process)。
* 在发送流程级别，一旦将事件分配给执行投放，则事务型消息可能因临时错误而失败。请参阅[消息发送重试流程](#message-sending-retry-process)。

### 事件处理重试流程{#event-processing-retry-process}

如果无法将事件分配给执行投放，则延迟事件处理。随后执行重试，直到将其分配给新的执行投放为止。

>[!NOTE]
>
>延迟的事件不会显示在事务型消息发送日志中，因为并未将其分配给执行投放。

例如，无法将事件分配给执行投放，因为其内容不正确、存在访问权限或品牌策略问题，在应用类型规则时检测到错误等。在这种情况下，您可以暂停消息，编辑该消息以修复问题，然后再次发布。然后，重试系统会将其分配给新的执行投放。

### 消息发送重试流程{#message-sending-retry-process}

一旦将事件分配给执行投放，事务型消息就可能因临时错误而失败，例如，如果收件人邮箱已满。有关更多信息，请参阅[投放临时失败后重试](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)。

>[!NOTE]
>
>将事件分配给执行投放后，该执行投放的发送日志中会显示该事件，并且仅在此时显示。失败的投放显示在事务性消息发送日志的&#x200B;**[!UICONTROL Execution list]**&#x200B;选项卡中。

### 重试进程限制{#limitations}

**发送日志更新**

在重试流程中，不会立即更新新执行投放的发送日志（通过计划的工作流执行的更新）。这意味着即使新的执行投放已经处理了事务型事件，该消息仍然处于 **[!UICONTROL Pending]** 状态。

**失败的执行投放**

无法停止执行投放。但是，如果当前执行投放失败，则会在收到新事件后立即创建新执行投放，所有新事件都由此新执行投放进行处理。失败的执行投放不会处理任何新事件。

如果分配给执行投放的部分事件已延迟，并且该执行投放失败，则重试系统不会为新的执行投放分配延迟事件，这意味着这些事件丢失。
