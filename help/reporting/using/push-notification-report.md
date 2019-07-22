---
title: 推送通知报告
seo-title: 推送通知报告
description: 推送通知报告
seo-description: 通过推送通知现成报告，了解推送通知的成功情况。
page-status-flag: 从未激活
uuid: 5b121a37-1c09-4749-a409-6989978ddc4 c
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 报告报告
content-type: reference
topic-tags: 报告列表
discoiquuid: a425cd59-edfd-42c5-a6 bd-38773c353 ff0
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 7102ed308f94985f8924a13aab2583e50b6c68e4

---


# Push notification report{#push-notification-report}

>[!CAUTION]
>
>Please note that you have to drag and drop the **[!UICONTROL Message type]** metrics to your tables to split your data depending on your delivery types, in this case push notification deliveries.

**推送通知** 报告提供Adobe Campaign中推送通知的营销效果的详细信息。此现成报告将帮助您了解用户如何与推送通知、移动应用程序和交付进行互动。

Some configuration is required in the mobile application to implement push tracking, refer to this [page](https://helpx.adobe.com/campaign/kb/push-tracking.html) for the detailed steps.

![](assets/dynamic_report_push.png)

每个表由摘要编号和图表表示。您可以更改详细信息在其各自的可视化设置中的显示方式。

The first table **Push notification Engagement Summary** is split into three categories: by day, by mobile app and by delivery. 它包含接收人重新激活的可用数据：

* **[!UICONTROL Processed/sent]**：发送的推送通知总数。
* **[!UICONTROL Delivered]**：成功发送的推送通知数量，与发送的推送通知的总数相关。
* **[!UICONTROL Impressions]**：推送通知已发送到设备并在通知中心未更改的次数。在大多数情况下，展示次数应类似于交付的数字。这可确保设备获得消息，并将该信息rela回服务器。
* **[!UICONTROL Unique impressions]**：收件人数量。
* **[!UICONTROL Click through rate]**：与推送通知交互的用户百分比。
* **[!UICONTROL Open rate]**：打开的推送通知百分比。

![](assets/dynamic_report_push_2.png)

The second table **Push notification Clicks &amp; opens** is split into three categories: by day, by mobile app and by delivery. 它包含每个交付的收件人行为的可用数据：

* **[!UICONTROL Impressions]**：收件人看到的推送通知总数。
* **[!UICONTROL Unique impressions]**：收件人数量。
* **[!UICONTROL Click]**：推送通知已发送到设备并由用户单击的次数。用户希望查看通知，随后将移至推送打开跟踪或取消通知。
* **[!UICONTROL Unique clicks]**：唯一用户与推送通知交互的次数，例如，单击通知或按钮。
* **[!UICONTROL Open]**：向设备发送的推送通知总数，并由用户单击打开应用程序。这与“推送单击”类似，但如果通知被忽略，则不会触发推送打开。
* **[!UICONTROL Unique Opens]**：打开分发的收件人数量。

