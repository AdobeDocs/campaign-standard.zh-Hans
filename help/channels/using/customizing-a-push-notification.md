---
title: 自定义推送通知
description: 了解如何使用各种高级选项自定义推送通知。
page-status-flag: 从未激活
uuid: 8cf74cad-b1ba-4aad-83bd-7289cb22d5f4
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 频道
content-type: 参考
topic-tags: 推送通知
discoiquuid: dc944c85-2059-46df-b396-676fe3617dd1
context-tags: delivery,mobileAppContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 自定义推送通知{#customizing-a-push-notification}

为了微调推送通知，Adobe Campaign允许您在设计推送通知时访问一组高级选项。

作为专家用户，要在Adobe Campaign中配置移动应用程序，请参阅以下技术说明了 [解Campaign标准推送通知有效负荷结构](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html)。

![](assets/push_notif_advanced.png)

**相关内容：**

* [推送通知报告](../../reporting/using/push-notification-report.md)
* [在工作流中发送推送通知](../../automating/using/push-notification-delivery.md)

## 播放声音 {#play-a-sound}

该功 **[!UICONTROL Play a sound]** 能使应用程序能够在应用程序未运行时通过推送通知的发送在设备上播放声音。

音效将提醒用户推送通知，使其更加可见。 要在移动应用程序中包含声音，请执行以下操作：

1. 打开推送通知并访问该 **[!UICONTROL Advanced options]** 部分。
1. 在字 **[!UICONTROL Play a sound]** 段中，输入在收到通知时由移动设备播放的声音文件的文件名（不带扩展名）。

   有关支持的媒体格式的详细信息，请参 [阅Apple](https://support.apple.com/kb/PH16864?locale=en_US) 和 [Android文档](https://developer.android.com/guide/topics/media/media-formats.html) 。

   ![](assets/push_notif_advanced_7.png)

1. 如果文件是在手机应用程序包中定义的，则在发送通知时播放声音文件。 否则，将播放设备的默认音效。

然后，用户将收到推送通知和声音，只有在手机未静音时。

## 刷新标记值 {#refresh-the-badge-value}

徽章用于直接在应用程序图标上显示新的未读信息的数量。 当用户从应用程序打开或读取新内容时，徽章值将消失。

在设备上收到通知后，它可以刷新或添加相关应用程序的标记值。 要从服务器端发送标记值，请执行以下操作：

1. 打开推送通知并访问该 **[!UICONTROL Advanced options]** 部分。
1. 徽章值必须是整数，可以通过以下不同方式进行更新：

   * 要刷新标记，请在字段中输入0 **[!UICONTROL Value of the badge]** 。 这将从应用程序图标中删除该徽章。
   * 要添加徽章值，请在字段中输入任意 **[!UICONTROL Value of the badge]** 数字。 用户收到推送通知后，此号码将自动显示在徽章中。
   * 如果字段为空或不包含整数，则标记值不会更改。
   在此，我们在字段中输入了1, **[!UICONTROL Value of the badge]** 以便让用户知道他们的应用程序中有一个新信息。

   ![](assets/push_notif_advanced_8.png)

1. 发送消息后，用户将收到推送通知，其应用程序将自动显示新的徽章值。

   ![](assets/push_notif_advanced_1.png)

## 添加深层链接 {#add-a-deeplink}

利用Develink，您可以直接将用户带到应用程序内的内容（而不是打开Web浏览器页面）。

开发人员可以包含个性化数据，以获得自定义的应用程序内体验。 例如，收件人的名字会自动填写在应用程序将其定向到的页面上。

在推送通知中添加深层链接：

1. 打开推送通知并访问该 **[!UICONTROL Advanced options]** 部分。
1. 在字段中输入链 **[!UICONTROL Add a deeplink]** 接。

   ![](assets/push_notif_advanced_3.png)

1. 发送消息后，用户将收到推送通知并通过与通知交互（例如点击或单击行动动员按钮）访问应用程序中的特定页面。

   ![](assets/push_notif_advanced_4.png)

## 定义操作 {#define-an-action}

您可以添加类别ID（如果在移动应用程序中可用），然后显示操作按钮。 这些通知为用户提供了一种更快的方式，无需在应用程序中打开或导航即可响应通知执行不同的任务。

用户电话上显示的对话框需要决定继续。 当用户选择其中一个操作时，系统会通知应用程序，以便它能够执行任何关联的任务。

在推送通知中添加类别：

1. 打开推送通知并访问该 **[!UICONTROL Advanced options]** 部分。
1. 在字段中输入预定义的类别名 **[!UICONTROL Category]** 称，以在收到推送通知时显示可操作的按钮。

   移动应用程序开发人员必须定义类别ID和按钮在应用程序中的预期行为。 有关详细信息，请参阅 [Apple Developer文档](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/SupportingNotificationsinYourApp.html) (配置类&#x200B;**别和可操作通知部分** )或 [Android开发人员文档](https://developer.android.com/guide/topics/ui/notifiers/notifications.html)。

   ![](assets/push_notif_advanced_9.png)

1. 发送推送通知后，用户会收到该通知，并必须使用之前配置的可操作按钮执行操作。

   ![](assets/push_notif_actionable_buttons.png)

根据用户的操作，应用程序将收到通知，以便它能够执行任何相关任务。

## 添加到期日期 {#add-expiration-date}

>[!NOTE]
>
>这些更改仅适用于Campaign Standard 19.4的起始版本。

通过为推送通知设置到期日期，您可以设置特定的到期日期，在该日期，Apple([APNS](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/sending_notification_requests_to_apns))或Android([FCM](https://firebase.google.com/docs/cloud-messaging/concept-options))将不再发送消息。

要向推送通知添加到期日，请执行以下操作：

1. 选中该 **[!UICONTROL Expire message]** 选项。

   >[!NOTE]
   >
   >通过选 **[!UICONTROL Expire message]** 择选项，持续时间将自动设置为0。 如果不更改值，APNS和FCM将尝试立即发送消息。 如果失败，则不会重新发送消息。

1. 在字段 **[!UICONTROL Duration]** 中，选择推送通知的有效性。

   ![](assets/push_expiration.png)

1. 在发送推送通知后，如果用户由于电话未打开或没有信号而未立即收到推送通知，则推送仍将在过期日期时隙内发送。

请注意，如果推送通知在到期日期之前尚未发送，则将丢弃该通知。

## 添加自定义字段 {#add-custom-fields}

自定义字段允许您以键值对的形式在有效负荷中传递自定义数据。 此选项可用于向应用程序传递超出预定义密钥的其他数据。

为此，请执行以下操作：

1. 打开推送通知并访问该 **[!UICONTROL Advanced options]** 部分。
1. 在类 **[!UICONTROL Custom fields]** 别中，单击按 **[!UICONTROL Add an element]** 钮。
1. 然后输 **[!UICONTROL Keys]** 入与每 **[!UICONTROL Values]** 个键关联的键。

   ![](assets/push_notif_advanced_10.png)

1. 自定义字段的处理和用途完全取决于移动应用程序。 在以下推送通知中，应用程序已使用自定义字段显示推送通知的按钮标签。

   ![](assets/push_notif_actionable_buttons.png)

## 添加富媒体内容 {#add-rich-media-content}

富媒体内容使您能够更好地参与用户活动，这意味着您的用户更倾向于打开您的推送通知。

您可以包括将在通知本身中播放或显示的图像、gif、音频或视频文件。 您的应用程序用户无需打开应用程序即可查看它。

要在推送通知中包含富媒体，请执行以下操作：

1. 打开推送通知并访问该 **[!UICONTROL Advanced options]** 部分。
1. 在每种格式的字段中输入 **[!UICONTROL Rich media content URL]** 文件的URL:iOS和Android。

   对于iOS 10或更高版本，可插入图像、gif、音频和视频文件。 对于早期的iOS版本，将显示推送通知而不显示丰富内容。 有关如何在iOS设备上显示Adobe Campaign推送通知中的图像的详细步骤，请参阅此 [页](https://helpx.adobe.com/campaign/kb/display-image-push.html)。

   对于Android，只能包含图像。

   ![](assets/push_notif_advanced_6.png)

1. 发送消息后，用户将收到您的推送通知并可以查看富媒体内容。

   ![](assets/push_notif_advanced_2.png)

## 更改iOS的通知行为 {#change-the-notification-behavior-for-ios}

![](assets/push_notif_advanced_5.png)

对于iOS 10或更高版本，推送通知部分还提供 **[!UICONTROL Advanced options]** 两个其他选项： **[!UICONTROL Mutable content]** 和 **[!UICONTROL Content available]**。

当选 **[!UICONTROL Mutable content]** 中该选项和／或添加富媒体内容URL时，可变内容标志将在推送有效负荷中发送，并且将允许由iOS SDK中提供的通知服务应用程序扩展修改推送通知内容。 有关详细信息，请参阅 [Apple开发人员文档](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html)。

然后，您可以利用移动应用程序扩展进一步修改从Adobe Campaign发送的推送通知的内容或演示文稿。 例如，用户可以利用此选项：

* 解密以加密格式传送的数据
* 下载图像或其他媒体文件，并将它们作为附件添加到通知中
* 更改通知的正文或标题文本
* 向通知添加线程标识符

选中 **[!UICONTROL Content available]** 后，将在推送有效负荷中发送可用内容标志，以确保应用程序在收到推送通知后立即唤醒，这意味着应用程序将能够访问有效负荷数据。 即使应用程序在后台运行并且无需任何用户交互（例如点击推送通知），这也会起作用，但是，如果应用程序未运行，则这不适用。 有关详细信息，请参阅 [Apple开发人员文档](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html)。

## 更改Android的通知行为 {#change-the-notification-behavior-for-android}

对于Android，您可以在富媒体内容URL字段中输入 **文件的URL** 。 而对于iOS版本，对于Android，您只能包含图像，而不能包含gif、音频或视频文件。

通过 **[!UICONTROL High priority]** 此复选框，您可以设置推送通知的高优先级或正常优先级。 有关消息优先级的详细信息，请参阅 [Google开发人员文档](https://firebase.google.com/docs/cloud-messaging/concept-options#setting-the-priority-of-a-message)。

![](assets/push_notif_advanced_11.png)

