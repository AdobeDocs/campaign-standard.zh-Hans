---
title: 应用程序内投放
description: 利用应用程序内投放活动，可在工作流中配置发送应用程序内消息。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8d5a35c4-e22b-498e-b71c-c5922cf8c2fd
source-git-commit: 21bcc9818b881212985988ef3377687069a1dbea
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 39%

---

# 应用程序内投放{#in-app-delivery}

## 说明 {#description}

![](assets/wkf_in_app_1.png)

**应用程序内投放**&#x200B;活动允许您在工作流中配置发送应用程序内消息。 通过应用程序内消息传送，可显示用户在应用程序内处于活动状态的消息。 有关应用程序内投放的更多信息，请参阅此[部分](../../channels/using/about-in-app-messaging.md)。

## 使用环境 {#context-of-use}

**[!UICONTROL In-App delivery]**&#x200B;活动通常用于向在同一工作流中计算的目标受众自动发送应用程序内消息。

同一工作流中的上游活动，通过查询、交集之类的定向活动，定义了收件人。

根据工作流执行参数，触发消息准备。在消息仪表板中，您可以选择是否请求手动确认以发送消息（默认要求）。您可以手动启动工作流，或在工作流中放置调度程序活动以自动执行。

## 配置 {#configuration}

1. 将&#x200B;**[!UICONTROL Query]**&#x200B;活动拖放到您的工作流。 请注意，需要根据在步骤4中选择的模板更新&#x200B;**[!UICONTROL Properties]**&#x200B;选项卡中的&#x200B;**[!UICONTROL Query]**&#x200B;活动定向维度：

   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**&#x200B;模板的定向维度应设置为&#x200B;**[!UICONTROL mobileApp (mobileAppV5)]**。
   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**&#x200B;模板的定向维度应设置为&#x200B;**[!UICONTROL profile (profile)]**。
   * 对于&#x200B;**[!UICONTROL Target users based on their Mobile profile (inApp)]**&#x200B;模板，目标维度应设置为&#x200B;**[!UICONTROL subscriptions to an application (`nms:appSubscriptionRcp:appSubscriptionRcpDetail`)]**。

1. 将 **[!UICONTROL In-App delivery]** 活动拖放到工作流中。
1. 选择活动，然后使用所显示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。

   >[!NOTE]
   >
   >您可以通过活动快捷操作中的![](assets/dlv_activity_params-24px.png)按钮，访问活动（而非投放本身）的常规属性和高级选项。

   ![](assets/wkf_in_app_3.png)

1. 选择应用程序内消息类型。 这将取决于您的&#x200B;**[!UICONTROL Query]**&#x200B;活动中定向的数据。

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**：利用此消息类型，可定向订阅了移动应用程序的Adobe Campaign用户档案，并使用Campaign中提供的用户档案属性对应用程序内消息进行个性化设置。
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**：利用此消息类型，可向移动应用程序的所有用户发送消息，即使他们在Campaign中没有现有的用户档案。
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**：利用此消息类型，可定向在Campaign中具有移动用户档案（无论已知还是未知）的移动应用程序的所有用户，并使用从移动设备获取的任何用户档案属性对应用程序内消息进行个性化。

   ![](assets/wkf_in_app_4.png)

1. 输入应用程序内消息属性，然后在&#x200B;**[!UICONTROL Associate a Mobile App to a delivery]**&#x200B;字段中选择您的移动应用程序。
1. 在 **[!UICONTROL Triggers]** 选项卡中，拖放触发消息的事件。提供了三类事件：
1. 定义应用程序内内容。 请参阅有关[应用程序内自定义](../../channels/using/customizing-an-in-app-message.md)的章节。
1. 默认情况下，**[!UICONTROL In-App delivery]** 活动不包含任何叫客过渡。如果要向 **[!UICONTROL In-App delivery]** 互动添加叫客过渡，请转到高级活动选项的 **[!UICONTROL General]** 选项卡（活动快速操作中的 ![](assets/dlv_activity_params-24px.png) 按钮），然后选中以下选项之一：

   * **[!UICONTROL Add outbound transition without the population]**：通过此选项可生成叫客过渡，其中包含的群体与集客过渡完全相同。
   * **[!UICONTROL Add outbound transition with the population]**：通过此选项可生成叫客过渡，其中包含接收消息的群体。 在投放准备期间被排除的目标成员将从此过渡中排除。

   ![](assets/wkf_in_app_5.png)

1. 确认活动的配置并保存工作流。

重新打开活动时，您将直接转到应用程序内仪表板。 只能编辑其内容。

默认情况下，启动投放工作流只会触发消息准备。在工作流启动后，发送从工作流创建的消息，仍需要确认。但是在消息仪表板中，仅当通过工作流创建消息时，才能禁用 **[!UICONTROL Request confirmation before sending messages]** 选项。取消选中此选项后，消息在准备完成后即发送，不会进一步通知。

## 备注 {#remarks}

可以在应用程序的营销活动列表中，访问在工作流中创建的投放。您可以使用仪表板查看工作流的执行状态。利用推送通知摘要窗格中的链接，可直接访问链接的元素（工作流、活动等）。

在可从营销活动列表访问的父投放中，您可以查看已处理的发送总数（基于配置&#x200B;**[!UICONTROL In-App delivery]**&#x200B;活动时指定的聚合期）。 要执行此操作，请通过选择 **[!UICONTROL Deployment]** 以打开父投放 ![](assets/wkf_dlv_detail_button.png) 块的详细视图。
