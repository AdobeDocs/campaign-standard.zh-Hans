---
title: 推送通知报告
description: 通过现成的推送通知报告，了解推送通知的成功性。
page-status-flag: 从未激活
uuid: 5b121a37-1c09-4749-a409-698978ddc4c
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 报告
content-type: 参考
topic-tags: 报告列表
discoiquuid: a425cd59-edfd-42c5-a6bd-38773c353ff0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 推送通知报告{#push-notification-report}

>[!CAUTION]
>
>请注意，您必须将量度拖放到表中，以 **[!UICONTROL Message type]** 根据您的交付类型分割数据，在这种情况下，推送通知将提交。

推送 **通知报表提供** Adobe Campaign中推送通知的营销效果的详细信息。 此现成报告将帮助您了解用户如何与推送通知、移动应用程序和交付交互。

移动应用程序中需要一些配置才能实现推送跟踪，有关详细 [步骤](https://helpx.adobe.com/campaign/kb/push-tracking.html) ，请参阅此页。

![](assets/dynamic_report_push.png)

每个表由摘要编号和图表表示。 您可以更改详细信息在各自的可视化设置中的显示方式。

第一个表“推 **送通知参与摘要** ”分为三个类别：按日、按移动App和按交付分发。 它包含接收方对交付反应的可用数据：

* **[!UICONTROL Processed/sent]**:发送的推送通知总数。
* **[!UICONTROL Delivered]**:成功发送的推送通知数（与已发送的推送通知总数相关）。
* **[!UICONTROL Impressions]**:推送通知已发送到设备且未在通知中心更改的次数。 在大多数情况下，展示次数应与已交付的数字相似。 这确保设备获得消息并将该信息转发回服务器。
* **[!UICONTROL Unique impressions]**:按收件人显示次数。
* **[!UICONTROL Click through rate]**:与推送通知交互的用户百分比。
* **[!UICONTROL Open rate]**:已打开推送通知的百分比。

![](assets/dynamic_report_push_2.png)

第二个表“推 **送通知单击和打开** ”被分为三个类别：按日、按移动App和按交付分发。 它包含每个交付的收件人行为的可用数据：

* **[!UICONTROL Impressions]**:接收方看到的推送通知总数。
* **[!UICONTROL Unique impressions]**:按收件人显示次数。
* **[!UICONTROL Click]**:推送通知被交付到设备并被用户单击的次数。 用户要么要查看通知，然后将其移至“推送打开”跟踪，要么将其关闭。
* **[!UICONTROL Unique clicks]**:唯一用户与推送通知交互的次数，例如单击通知或按钮。
* **[!UICONTROL Open]**:交付到设备并由用户点击以打开应用程序的推送通知总数。 这与推送单击类似，但如果通知被取消，则不会触发推送打开。
* **[!UICONTROL Unique Opens]**:打开分发的收件人数。

