---
solution: Campaign Standard
product: campaign
title: 应用程序内投放
description: 应用程序内投放活动允许您配置在工作流中发送应用程序内消息。
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 43%

---


# 应用程序内投放{#in-app-delivery}

## 说明{#description}

![](assets/wkf_in_app_1.png)

应 **用程序内投放** 活动允许您配置在工作流中发送应用程序内消息。 当用户在应用程序中处于活动状态时，应用程序内消息允许您显示消息。 有关应用程序内投放的详细信息，请参阅此 [部分](../../channels/using/about-in-app-messaging.md)。

## 使用环境{#context-of-use}

The **[!UICONTROL In-App delivery]** activity is generally used to automate sending an In-App message to a target audience calculated in the same workflow.

收件人是在同一工作流中通过活动、交叉点等定位活动在查询上游定义的。

根据工作流执行参数，触发消息准备。在消息仪表板中，您可以选择是否请求手动确认以发送消息（默认要求）。您可以手动启动工作流，或在工作流中放置调度程序活动以自动执行。

## 配置{#configuration}

1. Drag and drop a **[!UICONTROL Query]** activity to your workflow. 请注意，标 **[!UICONTROL Query]** 签中的活动 **[!UICONTROL Properties]** 定位维度需要根据步骤4中选择的模板进行更新：

   * 定位维度应设置 **[!UICONTROL mobileApp (mobileAppV5)]** 为模 **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]** 板。
   * 定位维度应设置 **[!UICONTROL profile (profile)]** 为模 **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** 板。
   * 定位维度应设置 **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** 为模 **[!UICONTROL Target users based on their Mobile profile (inApp)]** 板。

1. 将 **[!UICONTROL In-App delivery]** 活动拖放到工作流中。
1. 选择活动，然后使用所显示快捷操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。

   >[!NOTE]
   >
   >您可以通过活动快捷操作中的 ![](assets/dlv_activity_params-24px.png) 按钮，访问活动的常规属性和高级选项（而非投放本身）。

   ![](assets/wkf_in_app_3.png)

1. 选择应用程序内消息类型。 这取决于活动中的目标数 **[!UICONTROL Query]** 据。

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**:此消息类型使您能够目标订阅了您的移动应用程序的Adobe Campaign用户档案，并利用活动中可用的用户档案属性个性化应用程序内消息。
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**:此消息类型允许您向移动应用程序的所有用户发送消息，即使他们没有活动用户档案。
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**:此消息类型允许您目标具有移动用户档案（无论已知或未知）的移动应用的所有用户，并使用从移动设备获取的任何用户档案属性个性化应用内消息。

   ![](assets/wkf_in_app_4.png)

1. Enter your In-App message properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.
1. 在 **[!UICONTROL Triggers]** 选项卡中，拖放触发消息的事件。提供三类别事件:
1. 定义您的应用程序内内容。 请参阅有关应用程序 [内自定义的部分](../../channels/using/customizing-an-in-app-message.md)。
1. 默认情况下，**[!UICONTROL In-App delivery]** 活动不包含任何叫客过渡。如果要向 **[!UICONTROL In-App delivery]** 互动添加叫客过渡，请转到高级活动选项的 **[!UICONTROL General]** 选项卡（活动快捷操作中的 ![](assets/dlv_activity_params-24px.png) 按钮），然后选中以下选项之一：

   * **[!UICONTROL Add outbound transition without the population]**：通过此选项可生成叫客过渡，其中包含的群体与集客过渡完全相同。
   * **[!UICONTROL Add outbound transition with the population]**:这样，您就可以生成一个出站过渡，其中包含将消息发送到的人群。 在准备目标时排除的投放成员不在此过渡中。

   ![](assets/wkf_in_app_5.png)

1. 确认活动的配置并保存工作流。

重新打开活动时，您将直接转到应用程序内仪表板。 只能编辑其内容。

默认情况下，启动投放工作流只会触发消息准备。在工作流启动后，发送从工作流创建的消息，仍需要确认。但是在消息仪表板中，仅当通过工作流创建消息时，才能禁用 **[!UICONTROL Request confirmation before sending messages]** 选项。取消选中此选项后，消息在准备完成后即发送，不会进一步通知。

## 备注{#remarks}

可以在应用程序的营销活动列表中，访问在工作流中创建的投放。您可以使用仪表板查看工作流的执行状态。推送通知摘要窗格中的链接允许您直接访问链接的元素(工作流、活动等)。

In the parent deliveries, which can be accessed from the marketing activity list, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL In-App delivery]** activity was configured). 要执行此操作，请通过选择 **[!UICONTROL Deployment]** 以打开父投放 ![](assets/wkf_dlv_detail_button.png) 块的详细视图。
