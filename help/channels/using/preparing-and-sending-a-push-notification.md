---
solution: Campaign Standard
product: campaign
title: 创建和发送推送通知
description: 请按照以下步骤在Adobe Campaign中创建单发推送通知。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
feature: 推送
role: 业务从业者
level: 中间
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '861'
ht-degree: 4%

---


# 准备和发送推送通知{#preparing-and-sending-a-push-notification}

## 准备通知{#preparing-the-notification}

创建具有Adobe Campaign的推送通知的步骤有：

1. 在&#x200B;**[!UICONTROL Marketing activities]**&#x200B;窗口中，[创建新的营销活动](../../start/using/marketing-activities.md#creating-a-marketing-activity)。

   请注意，也可以从[活动](../../start/using/marketing-activities.md#creating-a-marketing-activity)或Adobe Campaign[主页](../../start/using/interface-description.md#home-page)创建单个推送通知。

   您还可以在工作流中使用推送通知投放活动。 此活动显示在[推送通知投放](../../automating/using/push-notification-delivery.md)部分。

1. 选择 **[!UICONTROL Push notification]**。
1. 选择模板。

   ![](assets/push_notif_type.png)

   默认情况下，您可以选择以下两个模板之一：

   * **[!UICONTROL Send push to Campaign profiles]**:使用此模板目标已订阅您的移动应用程序并已选择接收推送通知的Adobe Campaign CRM用户档案。您可以将[personalization](../../designing/using/personalization.md#inserting-a-personalization-field)字段插入推送通知中，如收件人的名字。
   * **[!UICONTROL Send push to app subscribers]**:使用此模板向所有已选择接收来自您的应用程序的通知的已知和匿名移动应用程序用户发送推送通知。您可以使用从移动应用程序收集的数据个性化这些信息。

   您还可以选择多语言模板。 有关详细信息，请参阅[创建多语言推送通知](../../channels/using/creating-a-multilingual-push-notification.md)。

   有关模板的详细信息，请参阅[管理模板](../../start/using/marketing-activity-templates.md)部分。

1. 输入您的推送通知属性，并在&#x200B;**[!UICONTROL Associate a Mobile App to a delivery]**&#x200B;字段中选择您的移动应用程序。

   请注意，下拉列表将同时显示SDK V4和Experience Platform SDK应用程序。

   ![](assets/push_notif_properties.png)

   您可以将推送通知链接到活动。 为此，请从已创建的活动中选择它。

1. 在下面的屏幕中，您可以指定受众，例如您所有订阅特定移动应用程序的VIP客户。 有关详细信息，请参阅[创建受众](../../audiences/using/creating-audiences.md)。

   您的受众将根据在上一步中选择的移动应用程序自动过滤。

   ![](assets/push_notif_audience.png)

1. 您现在可以自定义推送通知。 首先，选择消息样式：**[!UICONTROL Alert/Message/Badge]**&#x200B;或&#x200B;**[!UICONTROL Silent push]**。 [关于推送通知](../../channels/using/about-push-notifications.md)部分介绍了推送通知类型。

   编辑推送通知的内容并定义高级选项。 请参阅[自定义推送通知](../../channels/using/customizing-a-push-notification.md)。

   ![](assets/push_notif_content.png)

   此处配置的推送通知内容和选项将以有效负荷的形式传递到您的移动应用程序。 [了解Campaign Standard推送通知有效负荷结构](https://helpx.adobe.com/cn/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html)技术说明中介绍了有效负荷的详细结构。

1. 单击 **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. 在发送通知之前，您可以使用测试用户档案对其进行测试，然后在发送投放之前准确了解收件人将看到的内容。 从投放摘要中选择&#x200B;**[!UICONTROL Audiences]**，然后单击&#x200B;**[!UICONTROL Test profiles]**&#x200B;选项卡。

   有关发送测试的详细信息，请参阅[测试用户档案](../../sending/using/sending-proofs.md)。

1. 选择测试用户档案并单击&#x200B;**[!UICONTROL Preview]**&#x200B;以显示通知：内容通过测试用户档案数据实现个性化。
1. 检查不同设备上的推送通知布局：选择iPhone、Android手机、iPad或Android平板电脑进行预览渲染。

   ![](assets/push_notif_preview.png)

1. **[!UICONTROL Estimated Payload Size]**&#x200B;是基于测试用户档案数据的估计。 实际有效负荷大小可能不同。 消息的限制为4KB。

   >[!CAUTION]
   >
   >如果有效负荷大小超过4KB限制，则不会传递消息。

请注意，个性化数据会影响消息的大小。

## 发送通知{#sending-the-notification}

通过定义受众条件，可将推送通知发送到Adobe Campaign中的选定受众。 对于以下示例，我们选定的受众由4个目标移动应用程序订阅者组成。

1. 单击&#x200B;**[!UICONTROL Prepare]**&#x200B;计算目标并生成通知。

   ![](assets/push_send_1.png)

1. 准备成功完成后，**[!UICONTROL Deployment]**&#x200B;窗口将显示以下KPI:**[!UICONTROL Target]**&#x200B;和&#x200B;**[!UICONTROL To deliver]**。 请注意，由于排除项，**[!UICONTROL To deliver]**&#x200B;计数低于&#x200B;**[!UICONTROL Targeted]**&#x200B;计数，可单击&#x200B;**[!UICONTROL Deployment]**&#x200B;窗口底部的![](assets/lp_link_properties.png)按钮查看这些排除项。

   ![](assets/push_send_2.png)

1. 在&#x200B;**[!UICONTROL Exclusion logs]**&#x200B;选项卡中，可以找到从发送的目标中排除的所有消息的列表以及此排除的原因。

   在此，我们可以看到我们的移动应用程序用户中有一个被排除，因为该地址在阻止列表上，而其他用户档案是重复。

   ![](assets/push_send_5.png)

1. 单击&#x200B;**[!UICONTROL Exclusion causes]**&#x200B;选项卡以显示被排除消息的卷。

   ![](assets/push_send_7.png)

1. 您现在可以单击&#x200B;**[!UICONTROL Confirm]**&#x200B;以开始发送推送通知。
1. 通过消息仪表板和日志，检查投放的状态。有关详细信息，请参阅[发送消息](../../sending/using/confirming-the-send.md)和[投放日志](../../sending/using/monitoring-a-delivery.md#delivery-logs)。

   在此示例中，消息仪表板显示Adobe Campaign尝试发送两个推送通知：一个已成功传送到设备，另一个失败。 要了解投放为何有错误，请单击&#x200B;**[!UICONTROL Deployment]**&#x200B;窗口底部的![](assets/lp_link_properties.png)按钮。

   ![](assets/push_send_4.png)

1. 在&#x200B;**[!UICONTROL Deployment]**&#x200B;窗口中，单击&#x200B;**[!UICONTROL Sending logs]**&#x200B;选项卡以访问已发送推送通知的列表及其状态。 对于此投放，成功发送了一个推送通知，而另一个由于设备令牌错误而失败。 然后，将从更多投放将此订阻止列表阅者添加到。

   >[!NOTE]
   >
   >原因可能是下游到Adobe Campaign的故障。 如果apns和fcm等提供商出现故障，原因也将反映出来。 有关提供商故障的详细信息，请参阅[Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html)和[Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref)文档。

   ![](assets/push_send_6.png)

您现在可以通过动态报表衡量推送通知投放的影响。

**相关主题：**

* [推送通知报告](../../reporting/using/push-notification-report.md)
* [在工作流中发送推送通知](../../automating/using/push-notification-delivery.md)
