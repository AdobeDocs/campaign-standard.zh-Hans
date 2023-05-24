---
title: 推送通知投放
description: 推播通知傳送活動可讓您在工作流程中設定傳送單一傳送推播通知或循環推播通知。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: b6a43d51-32d4-4806-b4e4-33236f1e27f5
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 47%

---

# 推送通知投放{#push-notification-delivery}

## 说明 {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

此 **[!UICONTROL Push notification]** 活動可讓您在工作流程中設定傳送推播通知。 這可以是單一傳送通知，只傳送一次，或是重複通知。

* **單一** 傳送通知是標準的行動應用程式推播通知傳送，只傳送一次。
* **週期性** 通知可讓您在定義的時段內，多次傳送相同的行動應用程式推播通知傳送至不同的目標。 您可以按时段聚合投放，以获得对应于您需求的报告。

## 使用环境 {#context-of-use}

此 **[!UICONTROL Push notification]** 活動通常用於自動傳送通知至在相同工作流程中計算的目標。

連結至排程器時，您可以定義循環推播通知。

收件者是透過查詢、交叉點等定位活動，在相同工作流程中定義活動上游的活動。

根据工作流执行参数，触发消息准备。在消息仪表板中，您可以选择是否请求手动确认以发送消息（默认要求）。您可以手动启动工作流，或在工作流中放置调度程序活动以自动执行。

**相关主题**

* [使用工作流程傳送循環推播通知](../../automating/using/recurring-push-notifications.md)

## 配置 {#configuration}

1. 将 **[!UICONTROL Push notification]** 活动拖放到工作流中。
1. 选择活动，然后使用所显示快捷操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。

   >[!NOTE]
   >
   >您可以通过活动快捷操作中的 ![](assets/dlv_activity_params-24px.png) 按钮，访问活动的常规属性和高级选项（而非投放本身）。此按钮专用于 **[!UICONTROL Push notification]** 活动。您可以透過推播控制面板中的動作列存取推播通知的屬性。

1. 選取推播通知傳送模式：

   * **[!UICONTROL Single notification]**：推播通知只會傳送一次。 您可以在此处指定是否向活动添加叫客过渡。此程序的第 7 步详细介绍了各种过渡类型。
   * **[!UICONTROL Recurring notification]**：根據()中定義的頻率，推播通知會傳送多次 **[!UICONTROL Scheduler]** 活動。 选择发送的聚合期。這可讓您將定義期間發生的所有傳送重新分組，並透過也稱為的單一推播通知進行 **循環執行** 並可從應用程式的行銷活動清單存取。

      例如，對於每日傳送的循環生日通知，您可以選擇彙總每月的傳送。 這可讓您每月收到傳送的報告，不過通知會每天傳送。

1. 選取通知型別。 這些型別來自在中定義的推播通知範本 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** 功能表。
1. 輸入推播通知的一般屬性。 您还可以将其连接到现有营销策划。工作流程傳送活動的標籤會以推播通知標籤更新。
1. 定義推播通知內容。 另請參閱 [建立推播通知](../../channels/using/preparing-and-sending-a-push-notification.md)
1. 默认情况下，**[!UICONTROL Push notification]** 活动不包含任何叫客过渡。如果要向 **[!UICONTROL Push Notification]** 互动添加叫客过渡，请转到高级活动选项的 **[!UICONTROL General]** 选项卡（活动快捷操作中的 ![](assets/dlv_activity_params-24px.png) 按钮），然后选中以下选项之一：

   * **[!UICONTROL Add outbound transition without the population]**：通过此选项可生成叫客过渡，其中包含的群体与集客过渡完全相同。
   * **[!UICONTROL Add outbound transition with the population]**：這可讓您產生一個外站轉變，其中包含接收通知的母體。 傳遞準備期間排除的目標成員會從此轉變中排除。

1. 确认活动的配置并保存工作流。

當您重新開啟活動時，會直接帶您至推播通知控制面板。 只能编辑其内容。

默认情况下，启动投放工作流只会触发消息准备。在工作流启动后，发送从工作流创建的消息，仍需要确认。但是在消息仪表板中，仅当通过工作流创建消息时，才能禁用 **[!UICONTROL Request confirmation before sending messages]** 选项。取消选中此选项后，消息在准备完成后即发送，不会进一步通知。

## 备注 {#remarks}

可以在应用程序的营销活动列表中，访问在工作流中创建的投放。您可以使用仪表板查看工作流的执行状态。推播通知摘要窗格中的連結可讓您直接存取連結的元素（工作流程、行銷活動等）。

在可從行銷活動清單存取的父傳送中，您可以檢視已處理的傳送總數(根據 **[!UICONTROL Push notification]** 活動已設定)。 要执行此操作，请通过选择 **[!UICONTROL Deployment]** 以打开父投放 ![](assets/wkf_dlv_detail_button.png) 块的详细视图。
