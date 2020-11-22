---
solution: Campaign Standard
product: campaign
title: 创建和发送推送通知
description: 按照以下步骤创建Adobe Campaign的单发推送通知。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 4%

---


# 准备和发送推送通知{#preparing-and-sending-a-push-notification}

## 准备通知 {#preparing-the-notification}

创建具有Adobe Campaign的推送通知的步骤有：

1. 从窗 **[!UICONTROL Marketing activities]** 口创 [建新的营销活动](../../start/using/marketing-activities.md#creating-a-marketing-activity)。

   请注意，也可以从活动或Adobe Campaign [主页](../../start/using/marketing-activities.md#creating-a-marketing-activity) 创建单个推 [送通知](../../start/using/interface-description.md#home-page)。

   您还可以在工作流中使用推送通知投放活动。 此活动显示在推送 [通知投放部分](../../automating/using/push-notification-delivery.md) 。

1. 选择 **[!UICONTROL Push notification]**。
1. 选择模板。

   ![](assets/push_notif_type.png)

   默认情况下，您可以选择以下两个模板之一：

   * **[!UICONTROL Send push to Campaign profiles]**:使用此模板目标订阅了您的移动应用程序并选择接收推送通知的Adobe CampaignCRM用户档案。 您可以在 [推送通知](../../designing/using/personalization.md#inserting-a-personalization-field) (如收件人的名字)中插入个性化字段。
   * **[!UICONTROL Send push to app subscribers]**:使用此模板向所有已选择接收来自您的应用程序的通知的已知和匿名移动应用程序用户发送推送通知。 您可以使用从移动应用程序收集的数据个性化这些信息。

   您还可以选择多语言模板。 有关详细信息，请参 [阅创建多语言推送通知](../../channels/using/creating-a-multilingual-push-notification.md)。

   For more on templates, refer to the [Managing templates](../../start/using/marketing-activity-templates.md) section.

1. Enter your push notification properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.

   请注意，下拉框将同时显示SDK V4和Experience PlatformSDK应用程序。

   ![](assets/push_notif_properties.png)

   您可以将推送通知链接到活动。 为此，请从已创建的活动中选择它。

1. 在下面的屏幕中，您可以指定受众，例如，所有订阅特定移动应用程序的VIP客户。 有关此方面的详细信息，请参 [阅创建受众](../../audiences/using/creating-audiences.md)。

   您的受众将根据上一步中选择的移动应用程序自动过滤。

   ![](assets/push_notif_audience.png)

1. 您现在可以自定义推送通知。 首先，选择消息样式： **[!UICONTROL Alert/Message/Badge]** 或 **[!UICONTROL Silent push]**&#x200B;者 有关推送通知的类型，请参阅“关 [于推送通知](../../channels/using/about-push-notifications.md) ”部分。

   编辑推送通知的内容并定义高级选项。 See [Customizing a push notification](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   此处配置的推送通知内容和选项将以有效负荷的形式传递到您的移动应用程序。 有关有效负荷的详细结构，请参阅了解ACS [推送通知有效负荷结构](https://helpx.adobe.com/cn/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html) 技术说明。

1. 单击 **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. 在发送通知之前，您可以使用测试用户档案测试通知，然后在发送投放之前准确查看收件人将看到的内容。 从投放 **[!UICONTROL Audiences]** 摘要中进行选择，然后单击该 **[!UICONTROL Test profiles]** 选项卡。

   有关发送测试的详细信息，请参阅 [测试用户档案](../../sending/using/sending-proofs.md)。

1. 选择测试用户档案并单击 **[!UICONTROL Preview]** 以显示通知：内容通过测试用户档案数据进行个性化。
1. 检查不同设备上的推送通知布局：选择iPhone、Android手机、iPad或Android平板电脑进行预览渲染。

   ![](assets/push_notif_preview.png)

1. 是 **[!UICONTROL Estimated Payload Size]** 基于测试用户档案数据的估计。 实际有效负荷大小可能不同。 消息的限制为4KB。

   >[!CAUTION]
   >
   >如果有效负荷大小超过4KB限制，则不会传递消息。

请注意，个性化数据会影响消息的大小。

## 发送通知 {#sending-the-notification}

通过定义受众条件，可将推送通知发送到Adobe Campaign中的选定受众。 对于以下示例，我们选定的受众由4个目标移动应用程序订阅者组成。

1. Click **[!UICONTROL Prepare]** to compute the target and generate the notifications.

   ![](assets/push_send_1.png)

1. Once the preparation has finished successfully, the **[!UICONTROL Deployment]** window presents the following KPIs: **[!UICONTROL Target]** and **[!UICONTROL To deliver]**. Note that the **[!UICONTROL To deliver]** count is lower than the **[!UICONTROL Targeted]** one due to exclusions which can be viewed by clicking ![](assets/lp_link_properties.png) button at the bottom of the **[!UICONTROL Deployment]** window.

   ![](assets/push_send_2.png)

1. 在选 **[!UICONTROL Exclusion logs]** 项卡中，您可以找到所有从发送的目标中排除的消息的列表以及此排除的原因。

   在此，我们可以看到我们的移动App订户被排除，因为该地址在阻止列表器上，而其他订户被排除，因为用户档案是重复。

   ![](assets/push_send_5.png)

1. 单击选 **[!UICONTROL Exclusion causes]** 项卡以显示被排除消息的卷。

   ![](assets/push_send_7.png)

1. 您现在可以单击 **[!UICONTROL Confirm]** 以开始发送推送通知。
1. 通过消息仪表板和日志，检查投放的状态。有关此方面的详细信息，请 [参阅发送消息](../../sending/using/confirming-the-send.md) 和 [投放日志](../../sending/using/monitoring-a-delivery.md#delivery-logs)。

   在此示例中，消息仪表板显示Adobe Campaign尝试发送两个推送通知：一个已成功交付到设备，另一个失败。 要了解投放出错的原因，请 ![](assets/lp_link_properties.png) 单击窗口底部的按 **[!UICONTROL Deployment]** 钮。

   ![](assets/push_send_4.png)

1. 在窗口 **[!UICONTROL Deployment]** 中，单击选 **[!UICONTROL Sending logs]** 项卡以访问已发送推送通知的列表及其状态。 对于此投放，成功发送了一个推送通知，而另一个由于设备令牌错误而失败。 此订户随后将被添加到该阻止列表中，以免更多投放。

   >[!NOTE]
   >
   >原因可能是Adobe Campaign下游的故障。 如果apns和fcm等提供商出现故障，原因也将反映出这一点。 有关提供程序故障的详细信息，请参阅 [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) 和 [Android文档](https://firebase.google.com/docs/cloud-messaging/http-server-ref) 。

   ![](assets/push_send_6.png)

您现在可以使用动态报告衡量推送通知投放的影响。

**相关主题：**

* [推送通知报告](../../reporting/using/push-notification-report.md)
* [在工作流中发送推送通知](../../automating/using/push-notification-delivery.md)
