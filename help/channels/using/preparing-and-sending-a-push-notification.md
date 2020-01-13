---
title: 准备和发送推送通知
description: 请按照以下步骤在Adobe Campaign中创建单发推送通知。
page-status-flag: never-activated
uuid: 01997725-ca0a-420c-9e81-5ea801652f87
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: ec930cd4-6365-4e54-babe-9dc2eed041fc
context-tags: delivery,mobileAppContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c26f98c8edd832beeedfedafb8ad27730cc30d25

---


# 准备和发送推送通知{#preparing-and-sending-a-push-notification}

## 准备通知 {#preparing-the-notification}

使用Adobe Campaign创建推送通知的步骤有：

1. 从窗口 **[!UICONTROL Marketing activities]** 中，创[建新的营销活动](../../start/using/marketing-activities.md#creating-a-marketing-activity)。

   请注意，也可以从营销活动或Adobe Campaign主页 [创建](../../start/using/marketing-activities.md#creating-a-marketing-activity) 单个推 [送通知](../../start/using/interface-description.md#home-page)。

   您还可以在工作流中使用推送通知交付活动。 此活动显示在推送通 [知传送部分](../../automating/using/push-notification-delivery.md) 。

1. Select **[!UICONTROL Push notification]**.
1. 选择模板。

   ![](assets/push_notif_type.png)

   默认情况下，您可以选择以下两个模板之一：

   * **[!UICONTROL Send push to Campaign profiles]**:使用此模板可定位已订阅您的移动应用程序并选择接收推送通知的Adobe Campaign CRM配置文件。 您可以将个[性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)（如收件人的名字）插入推送通知中。
   * **[!UICONTROL Send push to app subscribers]**:使用此模板向所有已选择接收应用程序通知的已知和匿名移动应用程序用户发送推送通知。 您可以使用从移动应用程序收集的数据个性化这些消息。
   您还可以选择多语言模板。 有关详细信息，请参阅 [创建多语言推送通知](../../channels/using/creating-a-multilingual-push-notification.md)。

   有关模板的详细信息，请参阅管理模 [板一节](../../start/using/marketing-activity-templates.md) 。

1. 输入您的推送通知属性，然后在字段中选择您的移动应用 **[!UICONTROL Associate a Mobile App to a delivery]** 程序。

   请注意，下拉列表将同时显示SDK V4和Experience Platform SDK应用程序。

   ![](assets/push_notif_properties.png)

   您可以将推送通知链接到营销活动。 为此，请从已创建的营销活动中选择它。

1. 在以下屏幕中，您可以指定受众，例如订阅特定移动应用程序的所有VIP客户。 有关此方面的详细信息，请参阅 [创建受众](../../audiences/using/creating-audiences.md)。

   将根据上一步中选择的移动应用程序自动过滤受众。

   ![](assets/push_notif_audience.png)

1. 您现在可以自定义推送通知。 首先，选择消息样式：或 **[!UICONTROL Alert/Message/Badge]** 者 **[!UICONTROL Silent push]** 。 “关于推送通知”部分中介绍了 [推送通知类型](../../channels/using/about-push-notifications.md) 。

   编辑推送通知的内容并定义高级选项。 See [Customizing a push notification](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   此处配置的推送通知内容和选项将以有效负荷的形式传递给您的移动应用程序。 有效负荷的详细结构在了解ACS推送通知有效 [负荷结构技术中有介绍](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html) 。

1. 单击 **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. 在发送通知之前，您可以使用测试配置文件对通知进行测试，然后在发送发送通知之前准确查看收件人将看到的内容。 从交 **[!UICONTROL Audiences]** 付摘要中进行选择，然后单击选 **[!UICONTROL Test profiles]** 项卡。

   有关发送测试的详细信息，请参阅测 [试配置文件](../../sending/using/managing-test-profiles-and-sending-proofs.md)。

1. 选择测试配置文件，然 **[!UICONTROL Preview]** 后单击以显示通知：内容通过测试配置文件数据个性化。
1. 检查不同设备上的推送通知布局：选择iPhone、Android手机、iPad或Android平板电脑以预览渲染。

   ![](assets/push_notif_preview.png)

1. 这 **[!UICONTROL Estimated Payload Size]** 是基于测试简档数据的估计。 实际有效负荷大小可能不同。 消息的限制为4KB。

   >[!CAUTION]
   >
   >如果有效负荷大小超过4KB限制，则不会传送消息。 个性化数据会影响消息的大小。

## 发送通知 {#sending-the-notification}

通过定义受众标准，可将推送通知发送到Adobe Campaign中的选定受众。 对于以下示例，我们的选定受众包括4个目标移动App订阅者。

1. 单击 **[!UICONTROL Prepare]** 以计算目标并生成通知。

   ![](assets/push_send_1.png)

1. 准备成功完成后，窗口 **[!UICONTROL Deployment]** 将显示以下KPI:**[!UICONTROL Target]** 和 **[!UICONTROL To deliver]** 。 Note that the **[!UICONTROL To deliver]** count is lower than the **[!UICONTROL Targeted]** one due to exclusions which can be viewed by clicking![](assets/lp_link_properties.png)button at the bottom of the **[!UICONTROL Deployment]** window.

   ![](assets/push_send_2.png)

1. 在该选 **[!UICONTROL Exclusion logs]** 项卡中，您可以找到从已发送的目标中排除的所有消息的列表以及排除的原因。

   在此，我们可以看到我们的一个移动App订阅者被排除，因为地址被列入黑名单，而其他订阅者则因为配置文件重复。

   ![](assets/push_send_5.png)

1. 单击该 **[!UICONTROL Exclusion causes]** 选项卡以显示被排除消息的卷。

   ![](assets/push_send_7.png)

1. 您现在可以单击 **[!UICONTROL Confirm]** 开始发送推送通知。
1. 通过消息仪表板和日志检查您的交付状态。 有关此方面的详细信息，请参 [阅发送消息](../../sending/using/confirming-the-send.md) 和 [交付日志](../../sending/using/monitoring-a-delivery.md#delivery-logs)。

   在此示例中，消息功能板显示Adobe Campaign尝试发送两个推送通知：一个已成功交付到设备，另一个未成功。 要了解传送有错误的原因，请单 ![](assets/lp_link_properties.png) 击窗口底部的按 **[!UICONTROL Deployment]** 钮。

   ![](assets/push_send_4.png)

1. 在窗口 **[!UICONTROL Deployment]** 中，单击选项卡 **[!UICONTROL Sending logs]** 以访问已发送的推送通知列表及其状态。 对于此交付，成功发送了一个推送通知，而另一个由于设备令牌错误而失败。 然后，此订阅者将在进一步分发中列入黑名单。

   >[!NOTE]
   >
   >原因可能是Adobe Campaign下游的任何故障。 如果apns和fcm等供应商出现故障，原因也将反映出这一点。 有关提供商故障的详细信息，请参阅 [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) 和 [Android文档](https://firebase.google.com/docs/cloud-messaging/http-server-ref) 。

   ![](assets/push_send_6.png)

您现在可以使用动态报告衡量推送通知交付的影响。

**相关主题：**

* [推送通知报告](../../reporting/using/push-notification-report.md)
* [在工作流中发送推送通知](../../automating/using/push-notification-delivery.md)

