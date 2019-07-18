---
title: 应用程序内交付
seo-title: 应用程序内交付
description: 应用程序内交付
seo-description: 应用程序内交付活动允许您配置在工作流中发送应用程序内消息。
page-status-flag: 从未激活
uuid: 528d9472-e447-47af-a6 b2-3181aa5 fb广告
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 渠道活动
discoiquuid: 19796aca-6e9e-4d3a-8917-ba660 ec7993 c
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# In-App delivery{#in-app-delivery}

## Description {#description}

![](assets/wkf_in_app_1.png)

**应用程序内交付** 活动允许您配置在工作流中发送应用程序内消息。应用程序内消息传递允许您在用户在应用程序中处于活动状态时显示消息。For more information concerning the In-App delivery, refer to this [section](../../channels/using/about-in-app-messaging.md).

## Context of use {#context-of-use}

**[!UICONTROL In-App delivery]** 该活动通常用于自动向在同一工作流中计算的目标受众发送应用程序内消息。

收件人通过诸如查询、交叉点等定位活动在同一工作流程中定义活动上游。

消息准备会根据工作流执行参数触发。在消息仪表板中，您可以选择是请求还是不需要手动确认发送消息(默认情况下需要)。您可以手动启动工作流或在工作流中放置调度程序活动以自动执行执行。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Query]** activity to your workflow. Please note that the **[!UICONTROL Query]** activity targeting dimension in the **[!UICONTROL Properties]** tab needs to be updated according to the template chosen in Step 4:

   * Targeting dimension should be set to **[!UICONTROL mobileApp (mobileAppV5)]** for the **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]** template.
   * Targeting dimension should be set to **[!UICONTROL profile (profile)]** for the **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** template.
   * Targeting dimension should be set to **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** for the **[!UICONTROL Target users based on their Mobile profile (inApp)]** template.

1. Drag and drop a **[!UICONTROL In-App delivery]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button from the activity's quick actions.

   ![](assets/wkf_in_app_3.png)

1. 选择应用程序内消息类型。This will depend on the data targeted in your **[!UICONTROL Query]** activity.

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**：通过此消息类型，您可以定位已订阅移动应用程序的Adobe Campaign配置文件，以及使用Campaign中提供的配置文件属性个性化应用程序内消息。
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**：此消息类型允许您向移动应用程序的所有用户发送消息，即使在Campaign中没有现有配置文件也是如此。
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**：此消息类型允许您定位移动应用程序的所有用户，该应用程序在Campaign中具有移动配置文件，无论已知或未知，以及用移动设备获取的任何配置文件属性个性化应用程序内消息。
   ![](assets/wkf_in_app_4.png)

1. Enter your In-App message properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.
1. **[!UICONTROL Triggers]** 在选项卡中，拖放将触发消息的事件。提供三类活动：
1. 定义应用程序内内容。Refer to the section concerning [In-App customization](../../channels/using/customizing-an-in-app-message.md).
1. By default, the **[!UICONTROL In-App delivery]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL In-App delivery]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**：这使您能够生成包含与入站过渡相同的相同人群的出站过渡。
   * **[!UICONTROL Add outbound transition with the population]**：这使您能够生成包含消息发送人群的出站过渡。分发准备过程中排除的目标成员将从该过渡中排除。
   ![](assets/wkf_in_app_5.png)

1. 确认活动的配置并保存工作流。

重新打开活动时，您会直接转到应用程序内仪表板。只能编辑其内容。

默认情况下，启动交付工作流只会触发消息准备。在启动工作流之后，仍需要确认从工作流创建的消息的发送。But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. 通过取消选中此选项，准备完成后无需进一步通知即可发送消息。

## Remarks {#remarks}

在工作流中创建的分发可以在应用程序的营销活动列表中访问。您可以使用仪表板查看工作流的执行状态。推送通知摘要窗格中的链接允许您直接访问链接的元素(工作流、营销活动等)。

In the parent deliveries, which can be accessed from the marketing activity list, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL In-App delivery]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).
