---
solution: Campaign Standard
product: campaign
title: 跟踪消息
description: 了解如何跟踪投放收件人的行为。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 17%

---


# 跟踪消息{#tracking-messages}

## 关于跟踪 {#about-tracking}

凭借其跟踪功能，Adobe Campaign使您能够跟踪投放收件人的行为。 Adobe Campaign 使用会话 Cookie 和永久性 Cookie 实现上述功能。

您可以通过授权请求（例如，页面上出现的请求）通知用户您的站点已配备Web跟踪工具，该请求中带有一个复选框，用于授权使用cookie，或在他们登录的第一页顶部添加一个横幅，等等。 弹出窗口应避免出现，因为它们经常被浏览器阻止。

可以为数据库的每个联系人获取跟踪信息 **[!UICONTROL integrated customer profiles]**。 如需详细信息，请参阅[此部分](../../audiences/using/integrated-customer-profile.md)。

Adobe Campaign 使用两种类型的 Cookie：

* 会话Cookie(nid)。 它包含发送给联系人的电子邮件标识符(broadlogId)和邮件模板的标识符(deliveryId)。 联系人单击由 Adobe Campaign 发送的电子邮件中包含的 URL 后即可添加标识符，让您能够跟踪他们在网络上的行为。关闭浏览器时，将自动擦除会话 Cookie。联系人可以将浏览器配置为拒绝 Cookie。
* 在Adobe Experience Cloud解决方案之间共享的Cookie。 这使您能够识别访问网站时与Experience Cloud解决方案交互的用户。 此处提供此Cookie的说 [明](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-mc.html)。

通过Adobe Campaign Standard跟踪，您可以访问以下功能：

<table>
<tr>
    <td valign="top">
        <a href="../../administration/using/configuring-email-channel.md#tracking-parameters"><img width="60px" alt="条件" src="assets/icon_email_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="https://helpx.adobe.com/campaign/kb/push-tracking.html"><img width="60px" alt="条件" src="assets/icon_push_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="../../designing/using/links.md#about-tracked-urls"><img width="60px" alt="条件" src="assets/icon_url.png"/></a>
    </td>
        <td valign="top">
          <a href="../../sending/using/tracking-messages.md#tracking-logs"><img width="60px" alt="条件" src="assets/icon_log.png"/></a>
    </td>
    </td>
    <td valign="top">
          <a href="../../reporting/using/tracking-indicators.md"><img width="60px" alt="条件" src="assets/icon_report.png"/></a>
</tr>
<tr>
<td>电子邮件跟踪</td>
<td>推送跟踪</td>
<td>跟踪的URL</td>
<td>跟踪日志</td>
<td>跟踪报告</td>
</tr>
</table>

## Tracking logs {#tracking-logs}

该选 **[!UICONTROL Tracking logs]** 项卡列表此投放的跟踪历史记录。 此选项卡显示已发送消息的跟踪信息，如Adobe Campaign跟踪的所有URL。 此选项卡中的跟踪信息每10分钟更新一次。

>[!NOTE]
>
>如果未为投放启用跟踪，则不显示此选项卡。 跟踪日志仅可用于电 **子邮件****和推送通** 知渠道。

![](assets/tracking_logs.png)

在以上示例中，收件人:

* 已打开消息。
* 单击了“了解更多”自定义链接。
* 单击退订和镜像页面链接。

在该列 **[!UICONTROL Type]** 中，可能的值为：

* **[!UICONTROL Email click]**:收件人单击了自定义链接。
* **[!UICONTROL Mirror page]**:收件人单击了指向镜像页面的链接。
* **[!UICONTROL Open]**:收件人打开了电子邮件。
* **[!UICONTROL Opt-out]**:收件人单击了退订链接。

>[!NOTE]
>
>对于推 **送通知渠道** ，只跟踪移动通知的单击。 在这种情况下，值将为 **[!UICONTROL Click on mobile notification]**。

有关如何插入跟踪链接的详细信息，请参 [阅此页](../../designing/using/links.md#inserting-a-link)。

## 跟踪的URL {#tracked-urls}

该选 **[!UICONTROL Tracked URLs]** 项卡重新分组已发送邮件中包含的URL，包括其URL类型和源URL。

![](assets/sending_delivery6.png)

For more on tracking links, refer to [this section](../../designing/using/links.md#about-tracked-urls).
