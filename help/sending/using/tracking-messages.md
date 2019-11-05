---
title: 跟踪消息
description: 了解如何跟踪送达收件人的行为。
page-status-flag: 从未激活
uuid: c3721647-0663-4614-a9c9-3b3a40af328a
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 发送
content-type: 参考
topic-tags: 发送和跟踪消息
discoiquuid: 6fa50f0d-3dcf-4a9e-bcc-1ecda2bfb449
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 跟踪消息{#tracking-messages}

## 关于跟踪 {#about-tracking}

借助Adobe Campaign的跟踪功能，您可以跟踪交付收件人的行为。 Adobe Campaign 使用会话 Cookie 和永久性 Cookie 实现上述功能。

您可以通过授权请求（例如，页面上出现的请求）通知用户您的站点已装备有Web跟踪工具，该请求带有一个复选框以授权使用Cookie，或在他们登录的第一页的顶部添加一个横幅，等等。 应避免弹出窗口，因为它们经常被浏览器阻止。

Adobe Campaign 使用两种类型的 Cookie：

* 会话Cookie(nlid)。 其中包含发送给联系人的电子邮件标识符(broadlogId)和消息模板的标识符(deliveryId)。 联系人单击由 Adobe Campaign 发送的电子邮件中包含的 URL 后即可添加标识符，让您能够跟踪他们在网络上的行为。关闭浏览器时，将自动擦除会话 Cookie。联系人可以将浏览器配置为拒绝 Cookie。
* 在Adobe Experience cloud解决方案之间共享的Cookie。 这使您能够识别在访问网站时与Experience cloud解决方案交互的用户。 此Cookie的说明可从以下网页获取： [https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html)。

跟踪信息可用于数据库的每个联系人 **[!UICONTROL integrated customer profiles]**。 如需详细信息，请参阅[此部分](../../audiences/using/integrated-customer-profile.md)。

## 跟踪日志 {#tracking-logs}

该选 **[!UICONTROL Tracking logs]** 项卡列出了此交付的跟踪历史记录。 此选项卡显示已发送消息的跟踪信息，如Adobe Campaign跟踪的所有URL。 此选项卡中的跟踪信息每10分钟更新一次。

>[!NOTE]
>
>如果未为分发启用跟踪，则不显示此选项卡。 跟踪日志仅可用于电 **子邮件****和推送通知渠道** 。

![](assets/tracking_logs.png)

在以上示例中，收件人：

* 已打开消息。
* 单击“了解更多”自定义链接。
* 单击了取消订阅和镜像页面链接。

在该列 **[!UICONTROL Type]** 中，可能的值为：

* **[!UICONTROL Email click]**:收件人单击了自定义链接。
* **[!UICONTROL Mirror page]**:收件人单击了指向镜像页面的链接。
* **[!UICONTROL Open]**:收件人打开了电子邮件。
* **[!UICONTROL Opt-out]**:收件人单击了取消订阅链接。

>[!NOTE]
>
>对于推 **送通知渠道** ，只跟踪移动通知的点击。 在这种情况下，值将为 **[!UICONTROL Click on mobile notification]**。

有关如何插入跟踪链接的详细信息，请参 [阅此页](../../designing/using/links.md#inserting-a-link)。

## 跟踪的URL {#tracked-urls}

该选 **[!UICONTROL Tracked URLs]** 项卡重新分组已发送消息中包含的URL，包括其URL类型和源URL。

![](assets/sending_delivery6.png)

For more on tracking links, refer to [this section](../../designing/using/links.md#about-tracked-urls).
