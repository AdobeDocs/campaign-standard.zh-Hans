---
solution: Campaign Standard
product: campaign
title: 推送通知报告
description: 通过现成的推送通知报告，了解推送通知的成功性。
audience: reporting
content-type: reference
topic-tags: list-of-reports
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 1%

---


# 推送通知报告{#push-notification-report}

>[!CAUTION]
>
>请注意，您必须将度量拖放到表 **[!UICONTROL Message type]** 中，以根据投放类型(在此例中为推送通知投放)拆分数据。

推送 **通知报表提供** “Adobe Campaign”中推送通知的营销效果的详细信息。 此现成报告将帮助您了解用户如何与推送通知、移动应用程序和投放交互。

移动应用程序中需要进行一些配置才能实现推送跟踪，请参 [阅本页](../../administration/using/push-tracking.md) ，了解详细步骤。

![](assets/dynamic_report_push.png)

每个表由摘要编号和图表表示。 您可以更改详细信息在其各自的可视化设置中的显示方式。

第一个表“ **推送通知参与摘要** ”分为三个类别:按日、按移动App和按投放。 它包含收件人对投放反应的可用数据：

* **[!UICONTROL Processed/sent]**:发送的推送通知总数。
* **[!UICONTROL Delivered]**:成功发送的推送通知数（与已发送的推送通知总数相关）。
* **[!UICONTROL Impressions]**:推送通知已发送到设备且未在通知中心更改的次数。 在大多数情况下，展示次数应与已交付数目相似。 这确保设备收到消息并将该信息转发回服务器。
* **[!UICONTROL Unique impressions]**:按收件人显示次数。
* **[!UICONTROL Click through rate]**:与推送通知交互的用户百分比。
* **[!UICONTROL Open rate]**:已打开的推送通知的百分比。

![](assets/dynamic_report_push_2.png)

第二个表“ **推送通知单击和打开** ”分为三个类别:按日、按移动App和按投放。 它包含每个收件人的可用投放行为数据：

* **[!UICONTROL Impressions]**:收件人看到的推送通知总数。
* **[!UICONTROL Unique impressions]**:按收件人显示次数。
* **[!UICONTROL Click]**:推送通知被交付到设备并被用户单击的次数。 用户要么希望视图通知，然后将其移至“推送打开”跟踪，要么将其关闭。
* **[!UICONTROL Unique clicks]**:唯一用户与推送通知交互的次数，例如单击通知或按钮。
* **[!UICONTROL Open]**:用户点击的推送通知总数，从而打开应用程序。 这与推送单击类似，但如果通知消失，则不会触发推送打开。
* **[!UICONTROL Unique Opens]**:打开收件人的投放数。

