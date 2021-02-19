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

**应用程序内投放**&#x200B;活动允许您配置在工作流中发送应用程序内消息。 应用程序内消息传递允许您在用户在应用程序中处于活动状态时显示消息。 有关应用程序内投放的详细信息，请参阅此[部分](../../channels/using/about-in-app-messaging.md)。

## 使用环境{#context-of-use}

**[!UICONTROL In-App delivery]**&#x200B;活动通常用于自动将应用程序内消息发送到在同一工作流中计算的目标受众。

这些收件人通过查询、交叉点等定位活动在同一工作流中定义在活动的上游。

根据工作流执行参数，触发消息准备。在消息仪表板中，您可以选择是否请求手动确认以发送消息（默认要求）。您可以手动启动工作流，或在工作流中放置调度程序活动以自动执行。

## 配置{#configuration}

1. 将&#x200B;**[!UICONTROL Query]**&#x200B;活动拖放到工作流中。 请注意，**[!UICONTROL Properties]**&#x200B;选项卡中的&#x200B;**[!UICONTROL Query]**&#x200B;活动定位维度需要根据步骤4中选择的模板进行更新：

   * 定位维度应设置为&#x200B;**[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**&#x200B;模板的&#x200B;**[!UICONTROL mobileApp (mobileAppV5)]**。
   * 定位维度应设置为&#x200B;**[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**&#x200B;模板的&#x200B;**[!UICONTROL profile (profile)]**。
   * 定位维度应设置为&#x200B;**[!UICONTROL Target users based on their Mobile profile (inApp)]**&#x200B;模板的&#x200B;**[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]**。

1. 将 **[!UICONTROL In-App delivery]** 活动拖放到工作流中。
1. 选择活动，然后使用所显示快捷操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。

   >[!NOTE]
   >
   >您可以通过活动快捷操作中的 ![](assets/dlv_activity_params-24px.png) 按钮，访问活动的常规属性和高级选项（而非投放本身）。

   ![](assets/wkf_in_app_3.png)

1. 选择应用程序内消息类型。 这取决于&#x200B;**[!UICONTROL Query]**&#x200B;活动中的目标数据。

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**:此消息类型使您能够目标订阅了您的移动应用程序的Adobe Campaign用户档案，并利用活动中提供的用户档案属性个性化应用程序内消息。
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**:此消息类型允许您向移动应用程序的所有用户发送消息，即使他们没有活动中的现有用户档案。
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**:此消息类型使您能够目标具有活动移动用户档案（无论已知或未知）的移动应用程序的所有用户，并使用从移动设备获取的任何用户档案属性个性化应用程序内消息。

   ![](assets/wkf_in_app_4.png)

1. 输入您的应用程序内消息属性，并在&#x200B;**[!UICONTROL Associate a Mobile App to a delivery]**&#x200B;字段中选择您的移动应用程序。
1. 在 **[!UICONTROL Triggers]** 选项卡中，拖放触发消息的事件。提供三类别事件:
1. 定义您的应用程序内内容。 请参阅有关[应用程序内自定义](../../channels/using/customizing-an-in-app-message.md)的部分。
1. 默认情况下，**[!UICONTROL In-App delivery]** 活动不包含任何叫客过渡。如果要向 **[!UICONTROL In-App delivery]** 互动添加叫客过渡，请转到高级活动选项的 **[!UICONTROL General]** 选项卡（活动快捷操作中的 ![](assets/dlv_activity_params-24px.png) 按钮），然后选中以下选项之一：

   * **[!UICONTROL Add outbound transition without the population]**：通过此选项可生成叫客过渡，其中包含的群体与集客过渡完全相同。
   * **[!UICONTROL Add outbound transition with the population]**:这样，您就可以生成一个出站过渡，其中包含将消息发送到的人口。在准备目标时排除的投放成员不在此过渡中。

   ![](assets/wkf_in_app_5.png)

1. 确认活动的配置并保存工作流。

重新打开活动时，您将直接转到应用程序内仪表板。 只能编辑其内容。

默认情况下，启动投放工作流只会触发消息准备。在工作流启动后，发送从工作流创建的消息，仍需要确认。但是在消息仪表板中，仅当通过工作流创建消息时，才能禁用 **[!UICONTROL Request confirmation before sending messages]** 选项。取消选中此选项后，消息在准备完成后即发送，不会进一步通知。

## 备注{#remarks}

可以在应用程序的营销活动列表中，访问在工作流中创建的投放。您可以使用仪表板查看工作流的执行状态。推送通知摘要窗格中的链接允许您直接访问链接的元素(工作流、活动等)。

在可从营销投放列表访问的父活动中，您可以视图已处理的发送总数(根据在配置&#x200B;**[!UICONTROL In-App delivery]**&#x200B;活动时指定的汇总期间)。 要执行此操作，请通过选择 **[!UICONTROL Deployment]** 以打开父投放 ![](assets/wkf_dlv_detail_button.png) 块的详细视图。
