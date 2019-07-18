---
title: 跟踪消息
seo-title: 跟踪消息
description: 跟踪消息
seo-description: 了解如何跟踪交付收件人的行为。
page-status-flag: 从未激活
uuid: c3721647-0663-4614-a9 c9-3b3 a40 af328 a
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 发送
content-type: reference
topic-tags: 发送和跟踪消息
discoiquuid: fa50f0d-3dcf-4a9e-bcc-1eca2 bfc449
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Tracking messages{#tracking-messages}

## About tracking {#about-tracking}

凭借Adobe Campaign的跟踪功能，您可以跟踪交付收件人的行为。为此，Adobe Campaign使用会话cookie和永久性cookie。

您可以通知用户，您的站点通过授权请求(例如，在页面上出现)和一个复选框(例如，在页面上出现)提供Web跟踪工具，或在登录的第一页顶部添加横幅等。应避免弹出窗口，因为它们通常被浏览器阻止。

Adobe Campaign使用两种类型的cookies：

* 会话cookie(nld)。这包含发送到联系人(BroadlogID)的电子邮件的标识符和消息模板(DeliyID)的标识符。当联系人单击由Adobe Campaign发送的电子邮件中包含的URL并使您能够跟踪其在Web上的行为时，将添加该URL。关闭浏览器时，将自动删除此会话cookie。联系人可以配置其浏览器以拒绝cookies。
* Adobe Experience Cloud解决方案之间共享的Cookie。这使您能够识别在访问网站时与Experience Cloud解决方案交互的用户。The description of this cookie is available here: [https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html).

Tracking information are available for each contact of your database into **[!UICONTROL integrated customer profiles]**. For more on this, refer to [this section](../../audiences/using/integrated-customer-profile.md).

## Tracking logs {#tracking-logs}

**[!UICONTROL Tracking logs]** 此选项卡列出此交付的跟踪历史记录。此选项卡显示已发送消息的跟踪信息，如Adobe Campaign跟踪的所有URL。此选项卡中的跟踪信息每10分钟更新一次。

>[!NOTE]
>
>如果未为分发启用跟踪功能，则不显示此选项卡。Tracking logs are available for the **email** and **push notification** channels only.

![](assets/tracking_logs.png)

在上面的示例中，收件人：

* 打开了消息。
* 单击“了解更多”自定义链接。
* 单击取消订阅和镜像页面链接。

**[!UICONTROL Type]** 在列中，可能的值有：

* **[!UICONTROL Email click]**：收件人单击了自定义链接。
* **[!UICONTROL Mirror page]**：收件人单击了指向镜像页面的链接。
* **[!UICONTROL Open]**：收件人打开了电子邮件。
* **[!UICONTROL Opt-out]**：收件人单击了取消订阅链接。

>[!NOTE]
>
>**对于推送通知** 渠道，只跟踪移动通知的单击。In that case, the value will be **[!UICONTROL Click on mobile notification]**.

For more on how to insert tracking links, refer to [this page](../../designing/using/inserting-a-link.md).

## Tracked URLs {#tracked-urls}

**[!UICONTROL Tracked URLs]** 此选项卡将重新排列所发送消息中包含的URL，包括其URL类型及其源URL。

![](assets/sending_delivery6.png)

For more on tracking links, refer to [this section](../../designing/using/about-tracked-urls.md).
