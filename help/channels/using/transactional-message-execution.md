---
title: 異動訊息執行與監控
description: 瞭解異動訊息執行，並探索如何監控異動訊息。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 4cea7207-469c-46c5-9921-ae2f8f12d141
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 62%

---

# 異動訊息執行與監控 {#transactional-messaging-execution}

## 異動訊息執行傳送 {#transactional-message-execution-delivery}

訊息發佈並完成網站整合後，觸發事件時，即會指派給執行傳送。

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

一個 **執行傳送** 是無法操作且無法使用的技術訊息，每個月會針對每個交易式訊息建立一次，且每次都會編輯並再次發佈交易式訊息。

**相关主题**：
* [发布事务型消息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)
* [整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)

## 異動訊息重試過程 {#transactional-message-retry-process}

临时未投放的事务型消息将会自动重试，一直执行到投放过期为止。有关投放持续时间的更多信息，请参阅[有效性参数](../../administration/using/configuring-email-channel.md#validity-period-parameters)。

发送事务型消息失败时，可使用以下两个重试系统：

* 在事务型消息传递级别，如果将事务型消息放在分配给执行投放的事件之前，有可能会失败，这意味着，应放在事件接收和投放准备之间。请参阅[事件处理重试流程](#event-processing-retry-process)。
* 在发送流程级别，一旦将事件分配给执行投放，则事务型消息可能因临时错误而失败。请参阅[消息发送重试流程](#message-sending-retry-process)。

### 事件处理重试流程 {#event-processing-retry-process}

觸發事件時，會將其指派給執行傳送。 如果无法将事件分配给执行投放，则延迟事件处理。随后执行重试，直到将其分配给新的执行投放为止。

>[!NOTE]
>
>延迟的事件不会显示在事务型消息发送日志中，因为并未将其分配给执行投放。

例如，无法将事件分配给执行投放，因为其内容不正确、存在访问权限或品牌策略问题，在应用类型规则时检测到错误等。在这种情况下，您可以暂停消息，编辑该消息以修复问题，然后再次发布。然后，重试系统会将其分配给新的执行投放。

### 消息发送重试流程 {#message-sending-retry-process}

一旦将事件分配给执行投放，事务型消息就可能因临时错误而失败，例如，如果收件人邮箱已满。有关更多信息，请参阅[投放临时失败后重试](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)。

>[!NOTE]
>
>将事件分配给执行投放后，该执行投放的发送日志中会显示该事件，并且仅在此时显示。失敗的傳送會顯示在 **[!UICONTROL Execution list]** 異動訊息傳送記錄的索引標籤。

### 重試程式限制 {#limitations}

**发送日志更新**

在重试流程中，不会立即更新新执行投放的发送日志（通过计划的工作流执行的更新）。这意味着即使新的执行投放已经处理了事务型事件，该消息仍然处于 **[!UICONTROL Pending]** 状态。

**失败的执行投放**

无法停止执行投放。但是，如果当前执行投放失败，则会在收到新事件后立即创建新执行投放，所有新事件都由此新执行投放进行处理。失败的执行投放不会处理任何新事件。

如果某些已指派給執行傳送的事件在重試過程中被延遲，並且該執行傳送失敗，重試系統不會將延遲的事件指派給新的執行傳送，這意味著這些事件會遺失。 檢查 [傳遞記錄](#monitoring-transactional-message-delivery) 檢視可能受影響的收件者。

## 監控異動訊息 {#monitoring-transactional-message-delivery}

若要監控異動訊息，您必須存取對應訊息的 [執行傳遞](#transactional-message-execution-delivery).

1. 要查看消息投放日志，请单击 **[!UICONTROL Deployment]** 块右下方的图标。

   ![](assets/message-center_access_logs.png)

1. 按一下 **[!UICONTROL Execution list]** 標籤。

   ![](assets/message-center_execution_tab.png)

1. 選取您選擇的執行傳送。

   ![](assets/message-center_execution_delivery.png)

1. 再按一下右下方的圖示 **[!UICONTROL Deployment]** 區塊。

   ![](assets/message-center_execution_access_logs.png)

   對於每個執行傳送，您可以像檢視標準傳送一樣檢視傳送記錄。 如需存取和使用記錄檔的詳細資訊，請參閱 [監控傳遞](../../sending/using/monitoring-a-delivery.md).

### 設定檔交易式訊息特性 {#profile-transactional-message-monitoring}

對於設定檔交易式訊息，您可以監控以下設定檔資訊。

选择 **[!UICONTROL Sending logs]** 选项卡。在 **[!UICONTROL Status]** 列中，**[!UICONTROL Sent]** 表示用户档案已选择加入。

![](assets/message-center_marketing_sending_logs.png)

選取 **[!UICONTROL Exclusions logs]** 索引標籤來檢視已從訊息目標（例如封鎖清單上的地址）中排除的收件者。

![](assets/message-center_marketing_exclusion_logs.png)

对于选择退出的任何用户档案，**[!UICONTROL Address on denylist]** 分类规则将排除对应的收件人。

此规则属于特定分类的一部分，该特定分类会基于 **[!UICONTROL Profile]** 表应用到所有事务型消息。

![](assets/message-center_marketing_typology.png)

**相关主题**：

* [关于类型和类型规则](../../sending/using/about-typology-rules.md)
* [监测投放](../../sending/using/monitoring-a-delivery.md)
