---
title: 关于推送通知
description: 了解 Adobe Campaign 中推送通知渠道的主要特性。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Push
role: User
level: Intermediate
exl-id: e61daed6-a0ec-49d8-b1ad-77590fafb496
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '1239'
ht-degree: 40%

---

# 关于推送通知{#about-push-notifications}

>[!CAUTION]
>
>必须由专家用户执行推送通知的实施。如果需要协助，请与您的 Adobe 客户经理或专业服务合作伙伴联系。推送通知属于可选功能。请核实您的许可协议并联系您的帐户管理员以将其激活。

利用 Adobe Campaign，可向 iOS 和 Android 移动设备发送个性化的分段推送通知。

通过利用 Experience Platform SDK 在 Adobe Campaign 中设置的移动应用程序，可接收此类消息。有关此功能的详细信息，请参阅[使用 Adobe Experience Platform SDK 配置移动应用程序](../../administration/using/configuring-a-mobile-application.md)。

在 Adobe Campaign 中，由移动设备发出的移动配置文件属性数据存储在 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** 资源中，利用该资源，您可定义要从应用程序的订阅者那里收集的数据。

需要扩展此资源，才能收集您打算从移动设备发送到 Adobe Campaign 的数据。要实现此目的，请参阅此[页面](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)以了解详细步骤。

Adobe Campaign 提供两种类型的推送通知：

* **[!UICONTROL Alert/Message/Badge]** 类型通知允许您发送基于文本的标准消息，其中可包含在 **[!UICONTROL Advanced options]** 部分中定义的附加内容（声音、徽章、深度连接等）。

   此通知类型允许您在个性化字段中添加标题和消息。要个性化您的消息，请确保选择 **[!UICONTROL Send push on profiles]** 模板。

* **[!UICONTROL Silent push]** 类型通知用于静默通知应用程序，不会向最终用户发送任何消息或内容。此类消息的典型用例，是让应用程序知道服务器上有可供下载的内容。

可以设置某些特定配置来定义通知行为。有关更多信息，请参阅[此章节](../../channels/using/customizing-a-push-notification.md)。

>[!NOTE]
>
>有关隐私的法律因国家/地区而异。有些国家/地区要求您向用户告知移动应用所收集的数据类型。请查看您所在国家/地区与移动应用相关的法律。确保发送到移动应用的推送通知符合 Apple（Apple 推送通知服务）和 Google（Google Cloud Messaging 或 Firebase Cloud Messaging）指定的先决条件和条件。

**相关内容：**

* [准备和发送推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)
* [创建多语言推送通知](../../channels/using/creating-a-multilingual-push-notification.md)
* [推送通知报告](../../reporting/using/push-notification-report.md)
* [Campaign Standard Mobile 指南](../../channels/using/get-started-communication-channels.md)

## 先决条件 {#prerequisites}

>[!NOTE]
>要利用 Campaign 的推送通知功能，您需要提供没有密码的、.pem 格式的有效推送证书。

>
>如果您拥有有效的 p12 证书，则可以使用联机资源轻松将其转换为 .pem 文件。

在发送推送通知之前，您应：

1. 在 Adobe Campaign 中，确保可以访问 **[!UICONTROL Push notification]** 渠道。如果您无法访问这些渠道，请与帐户管理团队联系。

1. 確認您的使用者擁有Adobe Campaign Standard的必要許可權和Adobe Experience Platform的標籤。

1. 在資料收集UI中，建立行動屬性。 有关更多信息，请参阅[设置移动属性](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/)。

1. 在資料收集UI中，安裝 **[!UICONTROL Adobe Campaign Standard]** 副檔名。

1. 在Adobe Campaign Standard中，設定您在資料收集UI中建立的行動屬性。 如需詳細資訊，請參閱 [在Adobe Campaign中設定標籤應用程式](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. 将特定于渠道的配置添加到您的移动应用设置中。有关更多信息，请参阅 [Adobe Campaign 中特定于渠道的应用程序配置](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)。

1. 若要支援行動使用案例實作，請參閱中有關擴充功能、標籤規則和SDK實作的詳細指示 [使用Adobe Experience Platform SDK在Adobe Campaign Standard中支援的行動使用案例](../../administration/using/configuring-rules-launch.md).

## 推播通知常見問題集 {#push-faq}

### 若要進一步瞭解推播頻道，有哪些實用的資源建議？ {#resource-push}

檢視下列資源：

* [视频教程](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/push/creating-a-push-notification.html)
* [產品檔案](../../channels/using/about-push-notifications.md)
* 使用AEP SDK進行設定 [檔案](../../administration/using/configuring-a-mobile-application.md)
* [社群頁面](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

### 在Campaign中取得推播權杖需要做什麼？ {#push-token-acquisition}

確保布建團隊已完成Adobe Campaign Standard中推播頻道的布建。 從SDK實作setPushIdentifier API。 有关详细信息，请参见此 [ 页面](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#set-up-push-messaging)。

### 在Campaign中擁有推播權杖和ECID後，還需要傳送哪些其他專案？ {#sending-push}

客戶需要提供.pem格式的有效推播憑證才能傳送推播通知。 此憑證不需要密碼。

### 如果我有.p12憑證，而不是.pem憑證，該怎麼辦？ {#certificates}

您可以在terminal中執行下列命令，將.p12憑證轉換為.pem憑證。 也有數個線上資源可供轉換指示使用。

```
openssl pkcs12 -in pushcert.p12 -out pushcert.pem -nodes -clcerts
```

### 如何知道憑證上傳是否成功？ {#certificate-upload}

您會看到下列訊息。

![](assets/faq_2.png)

### 我可以同時為iOS應用程式上傳生產憑證和沙箱憑證嗎（Android不適用）？ {#prod-sandbox-certificate}

否，應用程式將在沙箱或生產模式中運作，並且一旦設定後無法變更為另一個（即沙箱至生產應用程式）。 建議您先在沙箱模式下測試應用程式，然後轉換為生產模式。

若要變更為生產模式，您必須建立另一個應用程式。 也請務必不要勾選「沙箱」核取方塊及上傳生產憑證。

### 我可以同時上傳iOS和Android憑證嗎？ {#ios-android-credentials}

是，Campaign會同時支援兩個平台，並允許您上傳兩個平台的認證。

### 我已成功上傳推送憑證，但未傳送任何推送訊息。 {#push-certificates-upload}

請透過測試推播憑證來確認其有效 [此處](https://pushtry.com/).

### 我可以從pushtry.com成功傳送推播通知，但無法透過Campaign。 {#push-not-sending}

請確定您遵循提供的推送裝載指示 [此處](../../administration/using/push-payload.md).

請注意，對於Android，Campaign僅支援資料裝載，不支援通知裝載

### 我已在Adobe Campaign Standard的「管理」區段中設定應用程式，但「傳送」屬性中無法使用行動應用程式。 {#mobile-app-unavailable}

應用程式必須先上傳有效的推送憑證，才能在傳送屬性中使用。

### 我已嘗試此頁面上的所有指示，但我無法從Campaign傳送推播。 {#push-troubleshoot}

請開啟客戶服務票證。

### 推播通知已從Campaign傳送，但媒體檔案未顯示。{#media-file-unavailable}

行動應用程式開發人員需要處理應用程式中媒體檔案的支援。 有時網路頻寬也會使媒體檔案無法呈現。 請參閱此 [頁面](../../administration/using/image-push-notification.md) 其他指標。

### 在Campaign中啟用推播報告需要做什麼？ {#push-reporting-enable}

按照下面的步骤进行操作：

* 設定推播追蹤回傳。 您可以找到指示 [此處](../../administration/using/configuring-a-mobile-application.md).
* 從行動核心實作trackAction API。 請參閱此 [頁面](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/) 以取得詳細資訊。

如需更詳細的指示，請參閱此 [頁面](../../administration/using/push-tracking.md).

### 哪些報表適用於推播頻道？ {#push-report-available}

Adobe Campaign中針對推播頻道提供了現成可用的報表。 請參閱此 [檔案](../../reporting/using/push-notification-report.md).

檢視此 [頁面](../../reporting/using/indicator-calculation.md#push-notification-delivery) 以瞭解每個推送量度的計算方式。

### 推送和應用程式內訊息是否支援深層連結？ {#deeplink-push}

是，推送訊息支援深層連結。 深層連結應包括：

* 指出必須停用傳遞追蹤才能讓深層連結運作的語言。
* 將Branch作為可執行深層連結追蹤之合作夥伴的應用程式傳單。 如需Branch和Adobe Campaign Standard整合的詳細資訊，請參閱此 [頁面](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).
