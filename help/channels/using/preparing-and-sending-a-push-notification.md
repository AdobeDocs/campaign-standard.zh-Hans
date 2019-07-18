---
title: 准备和发送推送通知
seo-title: 准备和发送推送通知
description: 准备和发送推送通知
seo-description: 按照以下步骤在Adobe Campaign中创建单发送推送通知。
page-status-flag: 从未激活
uuid: 01997725-ca0 a-420c-9e81-5ea801652 f87
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: 推送通知
discoiquuid: ec930cd4-6365-4e54-babe-9dc2 et041 fc
context-tags: delivery，mobileAppContent，返回
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Preparing and sending a push notification{#preparing-and-sending-a-push-notification}

## Preparing the notification {#preparing-the-notification}

使用Adobe Campaign创建推送通知的步骤有：

1. From the **[!UICONTROL Marketing activities]** window, [create a new marketing activity](../../start/using/marketing-activities.md#creating-a-marketing-activity).

   Note that a single push notification can also be created from a [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity) or from the Adobe Campaign [home page](../../start/using/interface-description.md#home-page).

   您还可以在工作流中使用推送通知交付活动。This activity is presented in the [Push notification delivery](../../automating/using/push-notification-delivery.md) section.

1. Select **[!UICONTROL Push notification]**.
1. 选择模板。

   ![](assets/push_notif_type.png)

   默认情况下，您可以选择以下两个模板之一：

   * **[!UICONTROL Send push to Campaign profiles]**：使用此模板定位已订阅移动应用程序并选择接收推送通知的Adobe Campaign CRM配置文件。You can insert [personalization](../../designing/using/inserting-a-personalization-field.md) fields into your push notification, such as the recipient's first name.
   * **[!UICONTROL Send push to app subscribers]**：使用此模板向已选择接收来自应用程序通知的所有已知和匿名移动应用程序用户发送推送通知。您可以使用从移动应用程序收集的数据个性化这些消息。
   您还可以选择多语言模板。For more information, refer to [Creating a multilingual push notification](../../channels/using/creating-a-multilingual-push-notification.md).

   For more on templates, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. Enter your push notification properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.

   请注意，下拉菜单将显示SDK V和Experience Platform SDK应用程序。

   ![](assets/push_notif_properties.png)

   您可以将推送通知链接到营销活动。为此，请从已创建的营销活动中选择它。

1. 在以下屏幕中，您可以指定受众，例如订阅特定移动应用程序的所有VIP客户。For more on this, see [Creating audiences](../../audiences/using/creating-audiences.md).

   将根据上一步中选定的移动应用程序自动过滤受众。

   ![](assets/push_notif_audience.png)

1. 您现在可以自定义推送通知。First, choose the message style: **[!UICONTROL Alert/Message/Badge]** or **[!UICONTROL Silent push]**. The push notification types are described in the [About push notifications](../../channels/using/about-push-notifications.md) section.

   编辑推送通知的内容并定义高级选项。See [Customizing a push notification](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   此处配置的推送通知内容和选项以负载形式传递到您的移动应用程序。The detailed structure of the payload is described in the [Understanding ACS push notifications payload structure](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html) technote.

1. Click **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. 在发送通知之前，您可以使用测试配置文件对其进行测试，然后准确查看收件人在发送交付之前将看到的内容。Select **[!UICONTROL Audiences]** from your delivery summary and click the **[!UICONTROL Test profiles]** tab.

   For more on sending tests, refer to [Test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md).

1. Select your test profiles and click **[!UICONTROL Preview]** to display the notification: content is personalized with the test profile data.
1. 在不同设备上检查推送通知布局：选择iPhone、Android手机、iPad或Android平板电脑以预览渲染。

   ![](assets/push_notif_preview.png)

1. The **[!UICONTROL Estimated Payload Size]** is an estimate based on test profile data. 实际有效负荷大小可能有所不同。消息的限制为4KB。

   >[!CAUTION]
   >
   >如果有效负荷大小超过4KB限制，则不会发送消息。个性化数据会影响消息的大小。

## Sending the notification {#sending-the-notification}

通过定义受众条件，可以将推送通知发送到Adobe Campaign中的选定受众。对于以下示例，我们所选的受众由个目标移动应用用户组成。

1. Click **[!UICONTROL Prepare]** to compute the target and generate the notifications.

   ![](assets/push_send_1.png)

1. Once the preparation has finished successfully, the **[!UICONTROL Deployment]** window presents the following KPIs: **[!UICONTROL Target]** and **[!UICONTROL To deliver]**. Note that the **[!UICONTROL To deliver]** count is lower than the **[!UICONTROL Targeted]** one due to exclusions which can be viewed by clicking ![](assets/lp_link_properties.png) button at the bottom of the **[!UICONTROL Deployment]** window.

   ![](assets/push_send_2.png)

1. **[!UICONTROL Exclusion logs]** 在选项卡中，您可以找到从目标发送的所有消息的列表以及此排除的原因。

   此处，我们可以看到我们的一个移动应用程序用户被排除，因为该地址被列入黑名单并且其他订阅者是因为配置文件重复。

   ![](assets/push_send_5.png)

1. Click the **[!UICONTROL Exclusion causes]** tab to display the volume of excluded messages.

   ![](assets/push_send_7.png)

1. You can now click **[!UICONTROL Confirm]** to start sending push notifications.
1. 通过消息仪表板和日志检查您的交付状态。For more on this, see [Sending messages](../../sending/using/confirming-the-send.md) and [Delivery logs](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   在此示例中，消息仪表板会显示Adobe Campaign尝试发送两个推送通知：其中一个成功交付到设备，另一个失败。To know why the delivery has errors, click the ![](assets/lp_link_properties.png) button at the bottom of the **[!UICONTROL Deployment]** window.

   ![](assets/push_send_4.png)

1. From the **[!UICONTROL Deployment]** window, click the **[!UICONTROL Sending logs]** tab to access the list of sent push notifications and their statuses. 对于此交付，成功发送一个推送通知，而另一个推送通知由于设备令牌不佳而失败。之后，此订阅者将从进一步交付中列入黑名单。

   >[!NOTE]
   >
   >Adobe Campaign下游可能出现任何故障。如提供商和fcm等提供商失败，原因也会反映出来。For more information on provider failures, you can refer to the [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) and [Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref) documentation.

   ![](assets/push_send_6.png)

您现在可以通过动态报告衡量推送通知交付的影响。

**相关主题：**

* [推送通知报告](../../reporting/using/push-notification-report.md)
* [在工作流中发送推送通知](../../automating/using/push-notification-delivery.md)

