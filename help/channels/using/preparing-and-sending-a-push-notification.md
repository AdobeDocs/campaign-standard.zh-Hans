---
title: 创建和发送推送通知
description: 执行以下步骤，在Adobe Campaign中创建单次发送的推送通知。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
feature: Push
role: User
level: Intermediate
exl-id: 41b83014-aea9-4ec2-b20e-c0a05bcad503
source-git-commit: affd4f9716235a283df20de5539e43c4832762f7
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 3%

---

# 准备和发送推送通知{#preparing-and-sending-a-push-notification}

## 准备通知 {#preparing-the-notification}

使用Adobe Campaign创建推送通知的步骤如下：

1. 从 **[!UICONTROL Marketing activities]** 窗口， [创建新的营销活动](../../start/using/marketing-activities.md#creating-a-marketing-activity).

   请注意，还可以从创建单个推送通知 [营销活动](../../start/using/marketing-activities.md#creating-a-marketing-activity) 或从Adobe Campaign [主页](../../start/using/interface-description.md#home-page).

   您还可以在工作流中使用推送通知投放活动。 本活动将在以下位置中介绍 [推送通知投放](../../automating/using/push-notification-delivery.md) 部分。

1. 选择 **[!UICONTROL Push notification]**。
1. 选择模板。

   ![](assets/push_notif_type.png)

   默认情况下，您可以选择以下两个模板之一：

   * **[!UICONTROL Send push to Campaign profiles]**：使用此模板定位已订阅您的移动应用程序并选择接收推送通知的Adobe Campaign CRM用户档案。 您可以插入 [个性化](../../designing/using/personalization.md#inserting-a-personalization-field) 推送通知中的字段，例如收件人的名字。
   * **[!UICONTROL Send push to app subscribers]**：使用此模板向所有选择从您的应用程序接收通知的已知和匿名移动应用程序用户发送推送通知。 您可以使用从移动应用程序收集的数据对这些消息进行个性化设置。

   您还可以选择多语言模板。 有关更多信息，请参阅 [创建多语言推送通知](../../channels/using/creating-a-multilingual-push-notification.md).

   有关模板的更多信息，请参阅 [管理模板](../../start/using/marketing-activity-templates.md) 部分。

1. 输入推送通知属性，然后在以下位置选择您的移动应用程序： **[!UICONTROL Associate a Mobile App to a delivery]** 字段。

   请注意，下拉菜单将同时显示SDK V4和Experience PlatformSDK应用程序。

   ![](assets/push_notif_properties.png)

   您可以将推送通知链接到营销策划。 要实现此目的，请从已创建的营销策划中选择它。

1. 在以下屏幕中，您可以指定受众，例如订阅了特定移动应用程序的所有VIP客户。 有关此内容的更多信息，请参阅 [创建受众](../../audiences/using/creating-audiences.md).

   系统将根据上一步骤中选择的移动应用程序自动过滤受众。

   ![](assets/push_notif_audience.png)

1. 您现在可以自定义推送通知。 首先，选择消息样式： **[!UICONTROL Alert/Message/Badge]** 或 **[!UICONTROL Silent push]**. 有关推送通知类型的说明，请参见 [关于推送通知](../../channels/using/about-push-notifications.md) 部分。

   编辑推送通知的内容并定义高级选项。 请参阅 [自定义推送通知](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   此处配置的推送通知内容和选项将以有效负荷的形式传递到您的移动应用程序。 有关有效载荷的详细结构，请参见 [了解Campaign Standard推送通知有效载荷结构](../../administration/using/push-payload.md) 技术说明。

1. 单击 **[!UICONTROL Create]**。

   ![](assets/push_notif_content_2.png)

1. 在发送通知之前，您可以使用测试用户档案对其进行测试，然后在发送投放之前查看收件人将看到的确切内容。 选择 **[!UICONTROL Audiences]** 在投放摘要中单击 **[!UICONTROL Test profiles]** 选项卡。

   有关发送测试的更多信息，请参阅 [测试用户档案](../../sending/using/sending-proofs.md).

1. 选择测试用户档案并单击 **[!UICONTROL Preview]** 显示通知：使用测试用户档案数据对内容进行个性化。
1. 检查不同设备上的推送通知布局：选择iPhone、Android手机、iPad或Android平板电脑以预览渲染。

   ![](assets/push_notif_preview.png)

1. 此 **[!UICONTROL Estimated Payload Size]** 是基于测试用户档案数据的估计值。 实际有效负载大小可能有所不同。 消息的限制为4KB。

   >[!CAUTION]
   >
   >如果有效负载大小超过4 KB限制，则无法投放消息。

请注意，个性化数据会影响消息的大小。

## 发送通知 {#sending-the-notification}

通过定义受众条件，可以将推送通知发送给Adobe Campaign中的选定受众。 以下示例中，我们选择的受众包含4个目标移动应用程序订阅者。

1. 单击 **[!UICONTROL Prepare]** 计算目标并生成通知。

   ![](assets/push_send_1.png)

1. 成功完成准备工作后， **[!UICONTROL Deployment]** 窗口将显示以下KPI： **[!UICONTROL Target]** 和 **[!UICONTROL To deliver]**. 请注意 **[!UICONTROL To deliver]** 计数小于 **[!UICONTROL Targeted]** 一个因排除项产生，可通过单击 ![](assets/lp_link_properties.png) 按钮底部的 **[!UICONTROL Deployment]** 窗口。

   ![](assets/push_send_2.png)

1. 在 **[!UICONTROL Exclusion logs]** 选项卡，您可以找到从发送的目标中排除的所有消息的列表以及此排除背后的原因。

   列入阻止列表在此，我们可以看到我们的一个移动应用程序订阅者已被排除，因为该地址在上，而其他订阅者因用户档案重复而被排除。

   ![](assets/push_send_5.png)

1. 单击 **[!UICONTROL Exclusion causes]** 选项卡，显示已排除的消息量。

   ![](assets/push_send_7.png)

1. 您现在可以单击 **[!UICONTROL Confirm]** 以开始发送推送通知。
1. 通过消息仪表板和日志，检查投放的状态。有关此内容的更多信息，请参阅 [发送消息](../../sending/using/confirming-the-send.md) 和 [投放日志](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   在此示例中，消息仪表板显示Adobe Campaign尝试发送两个推送通知：一个已成功交付到设备，另一个失败。 要了解投放有错误的原因，请单击 ![](assets/lp_link_properties.png) 按钮底部的 **[!UICONTROL Deployment]** 窗口。

   ![](assets/push_send_4.png)

1. 从 **[!UICONTROL Deployment]** 窗口中，单击 **[!UICONTROL Sending logs]** 选项卡，用于访问已发送推送通知的列表及其状态。 对于此投放，一个推送通知已成功发送，而另一个由于设备令牌错误而失败。 然后，此订阅者将被添加到该阻止列表，以防止进一步的投放。

   >[!NOTE]
   >
   >原因可能是Adobe Campaign下游的任何故障。 如果apns和fcm等提供程序出现故障，原因也会反映出来。 有关提供程序故障的详细信息，您可以参阅 [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) 和 [Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref) 文档。

   ![](assets/push_send_6.png)

您现在可以使用动态报告衡量推送通知投放的影响。

**相关主题：**

* [推送通知报告](../../reporting/using/push-notification-report.md)
* [在工作流中发送推送通知](../../automating/using/push-notification-delivery.md)
