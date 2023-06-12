---
title: 跟踪消息
description: 了解如何跟踪投放收件人的行为。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: fac29bc2-57fa-40f9-a160-cd75f695b91e
source-git-commit: affd4f9716235a283df20de5539e43c4832762f7
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 29%

---

# 跟踪消息{#tracking-messages}

## 关于跟踪 {#about-tracking}

借助其跟踪功能，Adobe Campaign使您能够跟踪投放收件人的行为。 Adobe Campaign 使用会话 Cookie 和永久性 Cookie 实现上述功能。

您可以通过授权请求（有时出现在页面上方）告知用户，您的网站配备了Web跟踪工具并要求用户选中复选框来授权使用Cookie，或者在用户登陆的首页顶部添加横幅等。 应避免使用弹出窗口，因为浏览器通常会拦截此类窗口。

跟踪信息适用于数据库中的每个联系人 **[!UICONTROL integrated customer profiles]**. 如需详细信息，请参阅[此部分](../../audiences/using/integrated-customer-profile.md)。

Adobe Campaign 使用两种类型的 Cookie：

* 会话Cookie (nlid)。 其中包含发送给联系人的电子邮件的标识符(broadlogId)，以及消息模板的标识符(deliveryId)。 联系人单击由 Adobe Campaign 发送的电子邮件中包含的 URL 后即可添加标识符，让您能够跟踪他们在网络上的行为。关闭浏览器时，将自动擦除会话 Cookie。联系人可以将浏览器配置为拒绝 Cookie。
* Adobe Experience Cloud解决方案之间共享的Cookie。 通过使用这种 ，您可以识别访问网站时与 Experience Cloud 解决方案发生交互的用户。此Cookie的描述可用 [此处](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-mc.html).

通过Adobe Campaign Standard进行跟踪，可访问以下功能：

<table>
<tr>
    <td valign="top">
        <a href="../../administration/using/configuring-email-channel.md#tracking-parameters"><img width="60px" alt="条件" src="assets/icon_email_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="../../administration/using/push-tracking.md"><img width="60px" alt="条件" src="assets/icon_push_parameters.png"/></a>
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
<td>跟踪的 URL</td>
<td>跟踪日志</td>
<td>跟踪报告</td>
</tr>
</table>

## 跟踪日志 {#tracking-logs}

此 **[!UICONTROL Tracking logs]** 选项卡列出了此投放的跟踪历史记录。 此选项卡显示已发送消息的跟踪信息，例如Adobe Campaign已跟踪的所有URL。 此选项卡中的跟踪信息每10分钟更新一次。

>[!NOTE]
>
>如果未为投放启用跟踪，则不会显示此选项卡。跟踪日志可用于 **电子邮件** 和 **推送通知** 仅限渠道。

![](assets/tracking_logs.png)

在上面的示例中，收件人：

* 已打开消息。
* 已单击镜像页面链接。
* 已单击“了解详情”自定义链接。

在 **[!UICONTROL Type]** 列中，可能的值包括：

* **[!UICONTROL Email click]**：收件人单击了自定义链接。
* **[!UICONTROL Mirror page]**：收件人单击了指向镜像页面的链接。
* **[!UICONTROL Open]**：收件人已打开电子邮件。
* **[!UICONTROL Opt-out]**：收件人单击了退订链接。

>[!NOTE]
>
>对于 **推送通知** 渠道，则仅跟踪对移动通知的点击。 在这种情况下，值将为 **[!UICONTROL Click on mobile notification]**.

有关如何插入跟踪链接的更多信息，请参阅 [此页面](../../designing/using/links.md#inserting-a-link).

此 **[!UICONTROL Tracking indicators]** 报告包含用于在收到电子邮件后跟踪行为的关键指标。 有关详细信息，请参见此 [ 页面](../../reporting/using/tracking-indicators.md)。

## 跟踪的 URL {#tracked-urls}

此 **[!UICONTROL Tracked URLs]** Tab对已发送消息中包含的URL进行重组，包括它们的URL类型和源URL。

![](assets/sending_delivery6.png)

有关跟踪链接的更多信息，请参阅 [本节](../../designing/using/links.md#about-tracked-urls).
