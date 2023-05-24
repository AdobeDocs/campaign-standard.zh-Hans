---
title: 应用程序内投放
description: 應用程式內傳送活動可讓您在工作流程中設定傳送應用程式內訊息。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8d5a35c4-e22b-498e-b71c-c5922cf8c2fd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 43%

---

# 应用程序内投放{#in-app-delivery}

## 说明 {#description}

![](assets/wkf_in_app_1.png)

此 **應用程式內傳遞** 活動可讓您在工作流程中設定傳送應用程式內訊息。 應用程式內傳訊功能可讓您在使用者於應用程式內活動時顯示訊息。 如需應用程式內傳送的詳細資訊，請參閱此 [區段](../../channels/using/about-in-app-messaging.md).

## 使用环境 {#context-of-use}

此 **[!UICONTROL In-App delivery]** 活動通常用於自動傳送應用程式內訊息給在相同工作流程中計算的目標對象。

收件者是透過查詢、交叉點等定位活動，在相同工作流程中定義活動上游的活動。

根据工作流执行参数，触发消息准备。在消息仪表板中，您可以选择是否请求手动确认以发送消息（默认要求）。您可以手动启动工作流，或在工作流中放置调度程序活动以自动执行。

## 配置 {#configuration}

1. 拖放 **[!UICONTROL Query]** 活動至您的工作流程。 請注意 **[!UICONTROL Query]** 中的活動目標維度 **[!UICONTROL Properties]** 標籤需要根據在步驟4中選擇的範本更新：

   * 目標維度應設為 **[!UICONTROL mobileApp (mobileAppV5)]** 的 **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]** 範本。
   * 目標維度應設為 **[!UICONTROL profile (profile)]** 的 **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** 範本。
   * 目標維度應設為 **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** 的 **[!UICONTROL Target users based on their Mobile profile (inApp)]** 範本。

1. 将 **[!UICONTROL In-App delivery]** 活动拖放到工作流中。
1. 选择活动，然后使用所显示快捷操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。

   >[!NOTE]
   >
   >您可以通过活动快捷操作中的 ![](assets/dlv_activity_params-24px.png) 按钮，访问活动的常规属性和高级选项（而非投放本身）。

   ![](assets/wkf_in_app_3.png)

1. 選取應用程式內訊息型別。 這將取決於以下專案的目標資料： **[!UICONTROL Query]** 活動。

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**：此訊息型別可讓您鎖定已訂閱您行動應用程式的Adobe Campaign設定檔，並使用Campaign提供的設定檔屬性個人化應用程式內訊息。
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**：此訊息型別可讓您傳送訊息給行動應用程式的所有使用者，即使他們在Campaign中沒有現有的設定檔亦然。
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**：此訊息型別可讓您鎖定在Campaign中具有行動設定檔的所有行動應用程式使用者（無論已知或未知），並使用從行動裝置取得的任何設定檔屬性個人化應用程式內訊息。

   ![](assets/wkf_in_app_4.png)

1. 輸入您的應用程式內訊息屬性，然後在以下位置選取您的行動應用程式： **[!UICONTROL Associate a Mobile App to a delivery]** 欄位。
1. 在 **[!UICONTROL Triggers]** 选项卡中，拖放触发消息的事件。提供三種類別的事件：
1. 定義您的應用程式內內容。 請參閱以下章節： [應用程式內自訂](../../channels/using/customizing-an-in-app-message.md).
1. 默认情况下，**[!UICONTROL In-App delivery]** 活动不包含任何叫客过渡。如果要向 **[!UICONTROL In-App delivery]** 互动添加叫客过渡，请转到高级活动选项的 **[!UICONTROL General]** 选项卡（活动快捷操作中的 ![](assets/dlv_activity_params-24px.png) 按钮），然后选中以下选项之一：

   * **[!UICONTROL Add outbound transition without the population]**：通过此选项可生成叫客过渡，其中包含的群体与集客过渡完全相同。
   * **[!UICONTROL Add outbound transition with the population]**：這可讓您產生出站轉變，其中包含傳送訊息的母體。 傳遞準備期間排除的目標成員會從此轉變中排除。

   ![](assets/wkf_in_app_5.png)

1. 确认活动的配置并保存工作流。

當您重新開啟活動時，會直接帶您至應用程式內控制面板。 只能编辑其内容。

默认情况下，启动投放工作流只会触发消息准备。在工作流启动后，发送从工作流创建的消息，仍需要确认。但是在消息仪表板中，仅当通过工作流创建消息时，才能禁用 **[!UICONTROL Request confirmation before sending messages]** 选项。取消选中此选项后，消息在准备完成后即发送，不会进一步通知。

## 备注 {#remarks}

可以在应用程序的营销活动列表中，访问在工作流中创建的投放。您可以使用仪表板查看工作流的执行状态。推播通知摘要窗格中的連結可讓您直接存取連結的元素（工作流程、行銷活動等）。

在可從行銷活動清單存取的父傳送中，您可以檢視已處理的傳送總數(根據 **[!UICONTROL In-App delivery]** 活動已設定)。 要执行此操作，请通过选择 **[!UICONTROL Deployment]** 以打开父投放 ![](assets/wkf_dlv_detail_button.png) 块的详细视图。
