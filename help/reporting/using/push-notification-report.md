---
title: 推送通知报告
description: 使用推送通知现成报告，了解推送通知是否成功。
audience: reporting
content-type: reference
topic-tags: list-of-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: acfe0b9c-77a4-46ad-8151-7bf9c21fa4b0
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 1%

---

# 推送通知报告{#push-notification-report}

>[!CAUTION]
>
>请注意，您必须拖放 **[!UICONTROL Message type]** 量度到您的表中，以根据投放类型拆分数据，在本例中是推送通知投放。

此 **推送通知** 报表提供了Adobe Campaign中推送通知营销绩效的详细信息。 此开箱即用的报表可帮助您了解用户如何与推送通知、移动应用程序和投放进行交互。

在移动应用程序中需要进行一些配置才能实施推送跟踪，请参阅此 [页面](../../administration/using/push-tracking.md) 以了解详细步骤。

![](assets/dynamic_report_push.png)

每个表格都由摘要数字和图表表示。 您可以更改详细信息在其各自可视化图表设置中的显示方式。

第一个表 **推送通知参与摘要** 分为三类：按日、按移动应用程序和按投放。 它包含可用于收件人对投放的反应性的数据：

* **[!UICONTROL Processed/sent]**：发送的推送通知总数。
* **[!UICONTROL Delivered]**：成功发送的推送通知数，与已发送推送通知的总数相关。
* **[!UICONTROL Impressions]**：将推送通知发送到设备并在通知中心保持不接触的次数。 在大多数情况下，展示次数应与交付次数相似。 这可确保设备收到消息并将该信息中继回服务器。
* **[!UICONTROL Unique impressions]**：收件人展示的次数。
* **[!UICONTROL Click through rate]**：与推送通知交互的用户百分比。
* **[!UICONTROL Open rate]**：已打开推送通知的百分比。

![](assets/dynamic_report_push_2.png)

第二张表 **推送通知点击次数和打开次数** 分为三类：按日、按移动应用程序和按投放。 它包含每次投放的收件人行为可用数据：

* **[!UICONTROL Impressions]**：收件人看到的推送通知总数。
* **[!UICONTROL Unique impressions]**：收件人展示的次数。
* **[!UICONTROL Click]**：推送通知送达设备并被用户单击的次数。 用户希望查看通知（通知随后将被移动到推送打开跟踪），或者关闭它。
* **[!UICONTROL Unique clicks]**：独特用户与推送通知进行交互（例如单击通知或按钮）的次数。
* **[!UICONTROL Open]**：发送到设备并由用户单击从而打开应用程序的推送通知总数。 这与推送点击类似，不同之处在于，如果取消通知，则不会触发推送打开。
* **[!UICONTROL Unique Opens]**：打开投放的收件人数量。
