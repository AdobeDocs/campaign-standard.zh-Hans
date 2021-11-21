---
title: 了解Campaign Standard推送通知有效载荷结构
description: 本文档旨在描述在移动应用程序中接收的有效载荷的结构。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: a6515795-1006-4f27-bc44-5ae8b8edc018
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '1141'
ht-degree: 3%

---

# 了解推送通知有效载荷结构 {#push-payload}

Adobe Campaign允许您在iOS和Android移动设备上向移动应用程序（移动应用程序）发送个性化的分段推送通知。

在移动设备应用程序上收到的每个推送通知都会携带一些信息，在发送警报推送通知时，应用程序会使用这些信息来显示推送通知，并且很可能还会进行一些进一步的计算，尤其是在发送无提示推送通知时。

该信息由移动设备应用程序代码在事件处理程序中接收，该事件处理程序指示已收到推送通知。 在从Adobe Campaign Standard发送推送通知时，在移动设备应用程序中收到的信息也可能包含Campaign Standard特定信息，这些信息可用于利用Campaign Standard提供的某些功能。 此外，有效负载还可以包含可由移动设备应用程序使用的自定义数据。

本文档介绍成功从Adobe Campaign Standard将推送通知发送到应用程序时，移动设备应用程序中收到的有效负载的结构。

>[!NOTE]
>
>有效负载结构因移动设备应用程序类型(例如，iOS应用程序、启用了FCM的Android应用程序)而异。

## 推送有效载荷结构 {#push-payload-structure}

本节详细介绍各种移动平台的有效负载示例结构，并描述其中包含的主要属性。 这是事件处理程序中移动设备应用程序代码中接收的有效载荷的结构，指示已接收推送通知。

有效负载属性及其值将因推送通知高级选项中提供的配置而异。 此部分还提供了Campaign StandardUI中这些配置与有效负载中的属性之间的映射，以阐明在Campaign Standard中配置选项时有效负载将如何更改。

### 对于iOS移动设备应用程序 {#payload-structure-ios}

**从Adobe Campaign发送到iOS应用程序的有效负载示例：**

```
{

    "aps":{

            "alert":{

                    "body":"This is the content of my push notification",

                    "title":"Push Notification Title"

            },

            "content-available":1,

            "category":"NEW_MESSAGE_CATEGORY",

            "badge":2,

            "mutable-content":1,

            "sound":"default"

        },

    "custom_field1":"custom_value1",

    "custom_field2":"custom_value2",

    "media-attachment-url":"https://2.img-dpreview.com/files/p/articles/9440145363/Creative_Cloud.jpeg",

    "uri":"https://mydeeplinkurl.com",

    "_dId":"56c4",

    "_mId":"h138a"} 
```

**要与一起使用的JSON有效负载示例 [iOS APNS测试程序](https://pushtry.com/)**

```
{

  "aps": {

    "alert": {

      "title": "Push Notification Title",

      "body": "body of push"

    },

    "badge": 33,

    "sound": "default"

  },

  "custom_field1": "custom_value1",

  "uri": "https://mydeeplinkurl.com"

}
```

有效负载中最重要的部分是aps词典，其中包含Apple定义的键值，用于确定接收通知的系统应如何向用户发出警报（如果有）。 此部分包含预定义键，移动设备应用程序使用这些键来构建推送通知的行为。

有关aps中属性的详细信息，请参阅Apple开发人员文档： [创建远程通知有效负载](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1).

### 对于Android应用程序 {#payload-structure-android}

**从Adobe Campaign发送到Android应用程序的有效负载示例**

```
{

  "collapseKey": "1476005",

  "priority": "high",

  "data": {

    "_dId": "d57fd6",

    "_mId": "h1685a5",

    "body": "adobe body 123",

    "category": "adobe category 123",

    "custom key 1": "value 1",

    "custom key 2": "test value 2",

    "custom key 3": "foo bar android",

    "media-attachment-url": "http://adobegiphy.com?test=123",

    "sound": "http://testcampaign.instance.com/r/?id=s1685a5,d57fd6,d57ff5",

    "title": "adobe title 123",

    "uri": "http://testcampaign.instance.com/r/?id=d1685a5,d57fd6,d57ff6",

    "badge": 1817

  }

}
```

**要使用的JSON有效负载示例 [Google FCM测试器](https://pushtry.com/)**

```
{

  "to": "<==========ENTER your device token==============>",

  "collapseKey": "1476005",

  "priority": "high",

  "data": {

    "_dId": "d57fd6",

    "_mId": "h1685a5",

    "title": "adobe title 123",

    "body": "adobe body 123",

    "category": "adobe category 123",

    "custom key 1": "value 1",

    "custom key 2": "test value 2",

    "custom key 3": "foo bar android",

    "media-attachment-url": "http://adobegiphy.com?test=123",

    "sound": "http://testcampaign.instance.com/r/?id=s1685a5,d57fd6,d57ff5",

    "uri": "http://testcampaign.instance.com/r/?id=d1685a5,d57fd6,d57ff6",

    "badge": 1817

  }

}
```

有效负载包含包含所有推送通知投放内容（包括自定义键/值对）的数据消息，客户端应用程序必须处理该消息以构建和显示推送通知（如果需要），或添加任何其他业务逻辑。

要了解Android有效负载的各个方面，请参阅 [消息传送概念和选项(fcm)](https://firebase.google.com/docs/cloud-messaging/concept-options).

>[!NOTE]
>
>自2018年1月起，Android有效负载中对通知消息的支持已移除，以便能够唤醒应用程序并将控制权传递到移动设备应用程序，而无需用户与应用程序交互。

### Campaign Standard配置和负载属性之间的映射 {#mapping-payload}

| 营销活动配置 | iOS中受影响的属性 | Android中受影响的属性 | 说明 |
|:-:|:-:|:-:|:-:|
| 消息标题 <br>消息正文 | 警报→标题 <br> 警报→主体 | 标题 <br>身体 | 此数据包含警报消息的特定信息。<br>标题和正文键提供警报的内容。 |
| 播放提示音 | 声音 | 声音 | 要与警报一起播放的自定义声音。 |
| 标记的值 | 徽章 | 徽章 | 用于标记应用程序图标的整数值。 |
| 添加深层链接 | uri | NA | 利用深层链接，您可以直接将用户导向应用程序内的内容（而不是打开 Web 浏览器页面）。 |
| 类别 | 类别 | 类别 | 显示带有远程通知的自定义操作。 <br>类别键有助于系统在警报界面中将该类别的操作显示为按钮。 |
| 自定义字段 | custom_field1、custom_field2... | custom_field1、custom_field2... | 要发送到应用程序的任何自定义数据。 |
| 富媒体内容URL（图像、GIF动图、音频和视频文件）<br>(仅适用于iOS 10或更高版本) | media-attachment-url | NA | 用于向通知添加富内容的媒体文件URL。 <br>为此URL提供值时，可变内容标记会自动发送到有效负载中。 <br> (仅适用于iOS 10或更高版本) |
| 可变内容 <br> (仅适用于iOS 10或更高版本) | 可变内容 | NA | 您的应用程序中的通知服务扩展将使用可变内容键“截获”所有远程通知，并允许您处理/处理请求有效负载的内容，该内容随后可用于自定义通知。 此功能的用例包括下载和显示多个媒体，解密推送有效载荷中存在的任何加密数据。 有关详细信息，请参阅 [修改远程通知的有效负载](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html). <br>(仅适用于iOS 10或更高版本) |
| 可用内容 | 内容可用 | NA | 选择此选项后，可在iOS应用程序处于后台/暂停状态时唤醒应用程序。 唤醒意味着应用程序在后台运行，而负责接收推送通知数据有效负载的相应事件处理程序将获得控制，并可以使用数据进行任何计算，包括但不限于构建自定义推送通知并显示相同内容。 有关详细信息，请参阅 [通过通知投放唤醒应用程序](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html). |
| 富媒体内容URL（图像文件）<br>（仅适用于Android） | NA | media-attachment-url | 用于向通知添加富内容的图像文件的URL。 |
| NA | _mId<br>_dId | _mId <br>_dId | broadlogId和deliveryId的值。<br>如果您的应用程序希望调用跟踪回发以跟踪何时单击/打开推送通知，则需要这些属性。 此信息由应用程序服务器在内部计算并发送，无需用户干预。<br>有关回发的信息，请参阅 [页面](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback). |

### 如何在移动设备应用程序代码中检索有效负载信息 {#payload-information}

应用程序服务器发送的有效负荷信息由事件处理程序中的移动设备应用程序代码接收，该事件处理程序指示已收到推送通知。 此事件将因所处理的移动设备平台而异，也因应用程序是在前台还是后台运行而异。 以下文档可帮助您根据用例确定要处理的事件处理程序。

* iOS应用程序： **处理远程通知** 部分 [远程通知](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html).
* Android应用程序： [在Android客户端应用程序上接收消息](https://firebase.google.com/docs/cloud-messaging/android/receive)

**iOS移动设备应用程序示例**

```
 - (void)application:(UIApplication *)application

didReceiveRemoteNotification:(NSDictionary *)userInfo {

    

    NSDictionary *apsDict = [userInfo objectForKey:@"aps"];

    NSDictionary *alertDict = [apsDict objectForKey:@"alert"];

    NSString *title = [alertDict objectForKey:@"title"];

    NSString *body = [alertDict objectForKey:@"body"];

    NSString *category = [apsDict objectForKey:@"category"];

    NSString *deliveryId = userInfo[@"_dId"];

    NSString *broadlogId = userInfo[@"_mId"];

    NSString *mediaAttachmentURL = userInfo[@"media-attachment-url"];

    NSString *deeplinkURL = userInfo[@"uri"];

    NSString *customValue1 = userInfo[@"custom_field1"];   

}
```

**Android Mobile FCM应用程序示例**

```
public void onMessageReceived(RemoteMessage message) {

    Map<String, String> dataMap = message.getData();

     

    String title = dataMap.get("title");

    String body = dataMap.get("body");

    String category = dataMap.get("category");

    String deliveryId = dataMap.get("_dId");

    String broadlogId = dataMap.get("_mId");

    String mediaAttachmentURL = dataMap.get("media-attachment-url");

    String deeplinkURL = dataMap.get("uri");

    String customValue1 = dataMap.get("custom_field1");

}
```
