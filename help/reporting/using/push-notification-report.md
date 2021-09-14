---
title: 推送通知报告
description: 通过现成的推送通知报表，了解推送通知是否成功。
audience: reporting
content-type: reference
topic-tags: list-of-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: acfe0b9c-77a4-46ad-8151-7bf9c21fa4b0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 1%

---

# 推送通知报告{#push-notification-report}

>[!CAUTION]
>
>请注意，您必须将&#x200B;**[!UICONTROL Message type]**&#x200B;量度拖放到表中，才能根据投放类型（在本例中为推送通知投放）拆分数据。

**推送通知**&#x200B;报表提供推送通知在Adobe Campaign中的营销效果的详细信息。 此开箱即用的报表将帮助您了解用户如何与推送通知、移动应用程序和投放进行交互。

移动应用程序中需要一些配置才能实施推送跟踪，有关详细步骤，请参阅此[页面](../../administration/using/push-tracking.md)。

![](assets/dynamic_report_push.png)

每个表都由概要数字和图表表示。 您可以更改详细信息在各自的可视化设置中的显示方式。

第一个表&#x200B;**推送通知参与度摘要**&#x200B;分为三个类别：按日、按移动应用程序和按投放。 它包含接收人对投放的反应的可用数据：

* **[!UICONTROL Processed/sent]**:发送的推送通知总数。
* **[!UICONTROL Delivered]**:成功发送的推送通知数，与已发送的推送通知总数有关。
* **[!UICONTROL Impressions]**:将推送通知发送到设备且未在通知中心受到影响的次数。在大多数情况下，展示次数数应与已交付的数量相似。 这可确保设备收到消息并将该信息转发回服务器。
* **[!UICONTROL Unique impressions]**:收件人的展示次数。
* **[!UICONTROL Click through rate]**:与推送通知交互的用户百分比。
* **[!UICONTROL Open rate]**:打开的推送通知的百分比。

![](assets/dynamic_report_push_2.png)

第二个表&#x200B;**推送通知点击次数和打开次数**&#x200B;分为三类：按日、按移动应用程序和按投放。 其中包含每个投放的收件人行为的可用数据：

* **[!UICONTROL Impressions]**:收件人可看到的推送通知总数。
* **[!UICONTROL Unique impressions]**:收件人的展示次数。
* **[!UICONTROL Click]**:将推送通知发送到设备并由用户单击的次数。用户要么想要查看通知（该通知随后将被移至推送打开跟踪），要么就将其关闭。
* **[!UICONTROL Unique clicks]**:独特用户与推送通知交互的次数，例如单击通知或按钮。
* **[!UICONTROL Open]**:用户交付到设备并点击的推送通知总数，从而打开应用程序。这类似于推送点击，除非取消通知后不会触发推送打开。
* **[!UICONTROL Unique Opens]**:打开投放的收件人数。
