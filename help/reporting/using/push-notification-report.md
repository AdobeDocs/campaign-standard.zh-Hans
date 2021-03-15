---
solution: Campaign Standard
product: campaign
title: 推送通知报告
description: 通过现成的推送通知报告，了解推送通知的成功性。
audience: reporting
content-type: reference
topic-tags: list-of-reports
feature: 报告
role: 领导者
level: 中间
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 1%

---


# 推送通知报告{#push-notification-report}

>[!CAUTION]
>
>请注意，您必须将&#x200B;**[!UICONTROL Message type]**&#x200B;量度拖放到表中，才能根据投放类型(本例中为推送通知投放)拆分数据。

**推送通知**&#x200B;报表提供Adobe Campaign中推送通知营销效果的详细信息。 此现成报告将帮助您了解用户如何与推送通知、移动应用程序和投放交互。

移动应用程序中需要一些配置来实现推送跟踪，有关详细步骤，请参阅此[页面](../../administration/using/push-tracking.md)。

![](assets/dynamic_report_push.png)

每个表都由摘要编号和图表表示。 您可以更改详细信息在各自的可视化设置中的显示方式。

第一个表&#x200B;**推送通知参与摘要**&#x200B;分为三个类别:按日、按移动App和按投放。 它包含收件人对投放反应的可用数据：

* **[!UICONTROL Processed/sent]**:发送的推送通知总数。
* **[!UICONTROL Delivered]**:成功发送的推送通知数（与已发送的推送通知总数相关）。
* **[!UICONTROL Impressions]**:推送通知已发送到设备且未在通知中心中更改的次数。在大多数情况下，展示次数应与已交付数目类似。 这可确保设备收到消息并将该信息转发回服务器。
* **[!UICONTROL Unique impressions]**:按收件人显示次数。
* **[!UICONTROL Click through rate]**:与推送通知交互的用户百分比。
* **[!UICONTROL Open rate]**:已打开的推送通知的百分比。

![](assets/dynamic_report_push_2.png)

第二个表&#x200B;**推送通知单击和打开**&#x200B;被拆分为三个类别:按日、按移动App和按投放。 它包含每个收件人的可用投放:

* **[!UICONTROL Impressions]**:收件人查看的推送通知总数。
* **[!UICONTROL Unique impressions]**:按收件人显示次数。
* **[!UICONTROL Click]**:推送通知被交付到设备并被用户单击的次数。用户要么希望视图通知，然后将通知移至“推送打开”跟踪，要么取消通知。
* **[!UICONTROL Unique clicks]**:唯一用户与推送通知交互的次数，例如单击通知或按钮。
* **[!UICONTROL Open]**:用户通过点击将推送通知交付到设备以打开应用程序的总数。这与“推送单击”类似，但如果通知被关闭，则不会触发“推送打开”。
* **[!UICONTROL Unique Opens]**:打开投放的收件人数。

