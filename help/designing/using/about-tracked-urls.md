---
title: 关于跟踪的URL
seo-title: 关于跟踪的URL
description: 关于跟踪的URL
seo-description: 了解如何管理将跟踪的内容的所有URL。
page-status-flag: 从未激活
uuid: dfe5146b-5256-431c-87b3-3c54817eba36
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 设计
content-type: reference
topic-tags: 管理链接
discoiquuid: d9b0b3c2-874b-4cb4-bce9-c0194 a19 f25 f
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# About tracked URLs{#about-tracked-urls}

Adobe Campaign使您能够跟踪收件人单击电子邮件中包含的URL时的行为。For more on tracking, see [this section](../../sending/using/tracking-messages.md#about-tracking).

The **[!UICONTROL Links]** icon in the action bar automatically displays the list of all the URLs of your content that will be tracked.

![](assets/des_links.png)

>[!NOTE]
>
>默认情况下，跟踪处于激活状态。只有在Adobe Campaign中激活了跟踪功能后，此功能才可用于电子邮件。For more on the tracking parameters, refer to [this section](../../administration/using/configuring-email-channel.md#tracking-parameters).

可以从此列表修改每个链接的URL、类别、标签和跟踪类型。要编辑链接，请单击相应的铅笔图标。

![](assets/des_links_tracking.png)

对于每个跟踪的URL，您可以将跟踪模式设置为以下值之一：

* **跟踪**：在此URL上激活跟踪。
* **Mirror页面**：认为此URL是一个镜像页面URL。
* **从不**：从不激活此URL的跟踪。保存此信息：如果URL中再次出现该URL，则会自动取消激活其跟踪。
* **选择退出**：将此URL视为选择退出或取消订阅URL。

![](assets/des_link_tracking_type.png)

您还可以取消激活或激活每个URL的跟踪。

>[!NOTE]
>
>By default in Adobe Campaign, all content URLs are tracked except **Mirror page URL** and **Unsubscription** link.

You can regroup your URLs by editing the **[!UICONTROL Category]** field, depending on the URLs used in the message. These categories can be displayed reports, as for example in [URLs and click streams](../../reporting/using/urls-and-click-streams.md).

![](assets/des_link_tracking_category.png)

When building a report, from the **[!UICONTROL Components]** tab, select **[!UICONTROL Dimension]** and scroll down the list to access the tracking components. For example, drag and drop **[!UICONTROL Tracking URL Category]** into the workspace to display results according to the tracking category of each clicked URL.

![](assets/des_link_tracking_report.png)

For more on building customized reports, see [this section](../../reporting/using/about-dynamic-reports.md).
