---
title: 跟踪消息
description: 瞭解如何追蹤傳遞收件者的行為。
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

## 關於追蹤 {#about-tracking}

藉由Adobe Campaign的追蹤功能，您可以追蹤傳送收件者的行為。 Adobe Campaign 使用会话 Cookie 和永久性 Cookie 实现上述功能。

您可以透過授權請求（有時出現在網站頁面中）告知使用者，網站已配備網路追蹤工具並要求使用者選中核取方塊授權使用Cookie，或在使用者登陸的首頁頂端新增橫幅等。 应避免使用弹出窗口，因为浏览器通常会拦截此类窗口。

資料庫中每個連絡人的追蹤資訊都可供使用 **[!UICONTROL integrated customer profiles]**. 如需详细信息，请参阅[此部分](../../audiences/using/integrated-customer-profile.md)。

Adobe Campaign 使用两种类型的 Cookie：

* 工作階段Cookie (nlid)。 這包含傳送給連絡人的電子郵件識別碼(broadlogId)和訊息範本識別碼(deliveryId)。 联系人单击由 Adobe Campaign 发送的电子邮件中包含的 URL 后即可添加标识符，让您能够跟踪他们在网络上的行为。关闭浏览器时，将自动擦除会话 Cookie。联系人可以将浏览器配置为拒绝 Cookie。
* Adobe Experience Cloud解決方案之間共用的Cookie。 通过使用这种 ，您可以识别访问网站时与 Experience Cloud 解决方案发生交互的用户。此Cookie的說明可供使用 [此處](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-mc.html).

透過Adobe Campaign Standard進行追蹤可讓您存取下列功能：

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
<td>電子郵件追蹤</td>
<td>推播追蹤</td>
<td>跟踪的 URL</td>
<td>跟踪日志</td>
<td>追蹤報告</td>
</tr>
</table>

## 跟踪日志 {#tracking-logs}

此 **[!UICONTROL Tracking logs]** 索引標籤會列出此傳送的追蹤記錄。 此標籤會顯示已傳送訊息的追蹤資訊，例如Adobe Campaign已追蹤的所有URL。 此標籤中的追蹤資訊每10分鐘更新一次。

>[!NOTE]
>
>如果未为投放启用跟踪，则不会显示此选项卡。追蹤記錄可用於 **電子郵件** 和 **推播通知** 僅限管道。

![](assets/tracking_logs.png)

在上述範例中，收件者：

* 已開啟訊息。
* 已按一下映象頁面連結。
* 已按一下「瞭解更多」自訂連結。

在 **[!UICONTROL Type]** 欄，可能的值包括：

* **[!UICONTROL Email click]**：收件者按一下自訂連結。
* **[!UICONTROL Mirror page]**：收件者按一下映象頁面的連結。
* **[!UICONTROL Open]**：收件者已開啟電子郵件。
* **[!UICONTROL Opt-out]**：收件者已按一下取消訂閱連結。

>[!NOTE]
>
>對於 **推播通知** 通道，則只會追蹤行動通知的點按。 在此情況下，值將會是 **[!UICONTROL Click on mobile notification]**.

如需如何插入追蹤連結的詳細資訊，請參閱 [此頁面](../../designing/using/links.md#inserting-a-link).

此 **[!UICONTROL Tracking indicators]** 報告包含接收電子郵件訊息後追蹤行為的關鍵指標。 有关详细信息，请参见此 [ 页面](../../reporting/using/tracking-indicators.md)。

## 跟踪的 URL {#tracked-urls}

此 **[!UICONTROL Tracked URLs]** 索引標籤會重新分組已傳送訊息中包含的URL，包括其URL型別和來源URL。

![](assets/sending_delivery6.png)

如需追蹤連結的詳細資訊，請參閱 [本節](../../designing/using/links.md#about-tracked-urls).
