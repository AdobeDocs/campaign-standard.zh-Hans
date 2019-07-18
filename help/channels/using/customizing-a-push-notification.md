---
title: 自定义推送通知
seo-title: 自定义推送通知
description: 自定义推送通知
seo-description: 了解如何使用各种高级选项自定义推送通知。
page-status-flag: 从未激活
uuid: 8cf74design-b1 ba-4aad-83bd-7289cb22 d5 f4
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: 推送通知
discoiquuid: dc944c85-2059-46df-b396-676fe3617 dd1
context-tags: delivery，mobileAppContent，返回
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Customizing a push notification{#customizing-a-push-notification}

为了微调推送通知，Adobe Campaign允许您在设计推送通知时访问一组高级选项。

As an expert user, to configure mobile applications in Adobe Campaign, refer to the following technote [Understanding Campaign Standard Push Notifications Payload Structure](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html).

![](assets/push_notif_advanced.png)

**相关内容：**

* [推送通知报告](../../reporting/using/push-notification-report.md)
* [在工作流中发送推送通知](../../automating/using/push-notification-delivery.md)

## Play a sound {#play-a-sound}

The function **[!UICONTROL Play a sound]** gives the application the ability to play sounds on your device with the delivery of a push notification, when the app isn't running.

音效将提醒推送通知用户，从而使其可见性更高。要在移动应用程序中包含声音，请执行以下操作：

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. **[!UICONTROL Play a sound]** 在字段中输入接收通知时移动设备播放的声音文件的文件名。

   For more information on supported media formats, refer to [Apple](https://support.apple.com/kb/PH16864?locale=en_US) and [Android](https://developer.android.com/guide/topics/media/media-formats.html) documentations.

   ![](assets/push_notif_advanced_7.png)

1. 如果在手机应用程序的包中定义了该文件，则声音文件在发送通知时播放。否则，将播放设备的默认声音。

用户随后将收到推送通知和音效(仅当电话未设静音时)。

## Refresh the badge value {#refresh-the-badge-value}

徽章用于直接在应用程序图标上显示新的未读信息数。用户打开或读取应用程序中的新内容后，徽章值将消失。

在设备上收到通知时，它可以刷新或添加相关应用程序的徽章值。要从服务器端发送徽章值，请执行以下操作：

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. 徽章值必须为整数，并可以更新不同的方法：

   * To refresh the badge, enter 0 in the **[!UICONTROL Value of the badge]** field. 这将从应用程序图标中删除徽章。
   * To add a badge value, enter any number in the **[!UICONTROL Value of the badge]** field. 用户收到推送通知后，此号码将自动显示在徽章中。
   * 如果字段为空或不包含整数，则徽章值将不会更改。
   Here, we entered 1 in the **[!UICONTROL Value of the badge]** field to let the users know that they have a new information in their application.

   ![](assets/push_notif_advanced_8.png)

1. 发送消息后，用户将收到推送通知，应用程序将自动显示新的徽章值。

   ![](assets/push_notif_advanced_1.png)

## Add a deeplink {#add-a-deeplink}

使用取消链接可使用户直接将用户带到应用程序内的内容(而不是打开Web浏览器页面)。

取消链接可包括个性化的应用程序内体验数据。例如，收件人的名字会自动填充应用程序指引到的页面上。

在推送通知中添加取消链接：

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. Enter the link in the **[!UICONTROL Add a deeplink]** field.

   ![](assets/push_notif_advanced_3.png)

1. 发送消息后，用户将收到推送通知，并通过与通知交互来访问应用程序中的特定页面，例如点按或单击行动动员按钮。

   ![](assets/push_notif_advanced_4.png)

## Define an action {#define-an-action}

您可以添加类别ID(如果在移动应用程序中可用)，然后显示操作按钮。这些通知为用户提供了一种更快地执行不同任务以响应通知的方法，而无需在应用程序中打开或导航。

用户手机上显示的对话框需要决定继续。当用户选择某个操作时，系统会通知应用程序，以便它能够执行任何关联的任务。

要在推送通知中添加类别，请执行以下操作：

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. Enter a predefined category name in the **[!UICONTROL Category]** field to display actionable buttons when the push notification is received.

   移动应用程序开发人员必须在应用程序中定义类别ID和按钮的预期行为。For more on this, refer to the [Apple Developer documentation](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/SupportingNotificationsinYourApp.html) (**Configuring Categories and Actionable Notifications** section) or the [Android Developer documentation](https://developer.android.com/guide/topics/ui/notifiers/notifications.html).

   ![](assets/push_notif_advanced_9.png)

1. 发送推送通知后，用户收到它并必须使用以前配置的可操作按钮采取操作。

   ![](assets/push_notif_actionable_buttons.png)

根据用户的操作，将通知应用程序以执行任何关联的任务。

## Add custom fields {#add-custom-fields}

自定义字段允许您以关键值对的形式传递有效负荷中的自定义数据。此选项可用于将其他数据传递到应用程序之外的预定义键之外。

要执行此操作，请执行以下操作：

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. **[!UICONTROL Custom fields]** 在类别中，单击 **[!UICONTROL Add an element]** 按钮。
1. Enter your **[!UICONTROL Keys]** then the **[!UICONTROL Values]** associated with each key.

   ![](assets/push_notif_advanced_10.png)

1. 自定义字段的处理和目的完全由移动应用程序完成。在下面的推送通知中，应用程序已使用自定义字段显示推送通知的按钮标签。

   ![](assets/push_notif_actionable_buttons.png)

## Add rich media content {#add-rich-media-content}

多媒体内容使您能够更好地参与用户互动，从而更好地打开推送通知。

您可以包含将在通知本身中播放或显示的图像、gif、音频或视频文件。应用程序用户将不必打开应用程序来查看它。

要在推送通知中包含富媒体，请执行以下操作：

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. Enter the URL of your file in the **[!UICONTROL Rich media content URL]** field for each format: iOS and Android.

   对于iOS10或更高版本，您可以插入图像、gif、音频和视频文件。对于早期的iOS版本，无需丰富的内容即可显示推送通知。For detailed steps on how to display an image from an Adobe Campaign push notification on an iOS device, refer to this [page](https://helpx.adobe.com/campaign/kb/display-image-push.html).

   对于Android，您只能包含图像。

   ![](assets/push_notif_advanced_6.png)

1. 发送消息后，用户将收到推送通知并可以查看富媒体内容。

   ![](assets/push_notif_advanced_2.png)

## Change the notification behavior for iOS {#change-the-notification-behavior-for-ios}

![](assets/push_notif_advanced_5.png)

For iOS 10 or higher, two additional options are available in the **[!UICONTROL Advanced options]** section of push notifications: **[!UICONTROL Mutable content]** and **[!UICONTROL Content available]**.

When the **[!UICONTROL Mutable content]** option is checked and/or a Rich media content URL is added, the mutable-content flag will be sent in the push payload and will allow the push notification content to be modified by a notification service application extension provided in iOS SDK. For more on this, refer to [Apple developer documentation](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html).

然后，您可以利用移动应用程序扩展进一步修改从Adobe Campaign发送的推送通知的内容或演示。例如，用户可以使用此选项来：

* 解密以加密格式传送的数据
* 下载图像或其他媒体文件，并将其作为附件添加到通知
* 更改通知的正文或标题文本
* 向通知中添加线程标识符

When **[!UICONTROL Content available]** is checked, the content available flag will be sent in the push payload to ensure that the app is woken up as soon as it receives the push notification, meaning that the app will be able to access the payload data. 即使应用程序在后台运行并且不需要任何用户交互(例如点击推送通知)，这种情况仍然有效，但如果应用程序未运行，则此操作不适用。For more on this, refer to the [Apple developer documentation](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html).

## Change the notification behavior for Android {#change-the-notification-behavior-for-android}

For Android, you can enter the URL of your file in the **Rich media content URL** field. 而对于iOS版本，对于Android，您只能包含图像，而不能包括gif、音频或视频文件。

The **[!UICONTROL High priority]** checkbox allows you to set up a high or normal priority for your push notifications. For more information on message priority, refer to the [Google developer documentation](https://firebase.google.com/docs/cloud-messaging/concept-options#setting-the-priority-of-a-message).

![](assets/push_notif_advanced_11.png)

