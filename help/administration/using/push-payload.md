---
title: 了解Campaign Standard推送通知有效负荷结构
description: 了解在移动应用程序中接收的有效载荷的结构
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: a6515795-1006-4f27-bc44-5ae8b8edc018
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 3%

---

# 了解推送通知有效载荷结构 {#push-payload}

通过Adobe Campaign，您可以在iOS和Android移动设备上向移动应用程序（移动应用程序）发送个性化的分段推送通知。

在移动应用程序上收到的每个推送通知都会携带一些信息，在发送警报推送通知时，应用程序会使用这些信息显示推送通知，并且很可能还会进行一些进一步计算，尤其是在发送静默推送通知时。

移动设备应用程序代码会在事件处理程序中接收此信息，以指示已收到推送通知。 从Adobe Campaign Standard发送推送通知时，在移动应用程序中接收的信息也可能包含特定Campaign Standard的信息，这些信息可用于利用Campaign Standard提供的某些功能。 此外，有效负载可以包含可由移动设备应用程序使用的自定义数据。

本文档介绍了当推送通知成功从Adobe Campaign Standard发送到应用程序时，在移动应用程序中接收的有效负载的结构。

>[!NOTE]
>
>有效负载结构因移动设备应用程序(即iOS应用程序、支持FCM的Android应用程序)的类型而异。

## 推送有效负荷结构 {#push-payload-structure}

此部分详细介绍适用于各种移动平台的示例有效载荷的结构，并描述其中包含的主要属性。 这是事件处理程序中的移动设备应用程序代码中接收的有效负荷的结构，指示已收到推送通知。

有效负载属性及其值将因推送通知高级选项中提供的配置而异。 此部分还提供了Campaign StandardUI中的这些配置与有效负载中的属性之间的映射，以阐明在Campaign Standard中配置选项时有效负载会发生什么变化。

### 适用于iOS移动设备应用程序的 {#payload-structure-ios}

**从Adobe Campaign发送到iOS应用程序的示例有效负载：**

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

**要与结合使用的JSON示例有效负载 [iOS APNS Tester](https://pushtry.com/)**

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

有效负载中最重要的部分是aps词典，它包含Apple定义的键，用于确定接收通知的系统应如何提醒用户（如果有的话）。 此部分包含移动应用程序用来制定推送通知行为的预定义键。

可以在Apple开发人员文档中找到有关aps中属性的深入详细信息： [创建远程通知有效负载](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1).

### 适用于Android应用程序 {#payload-structure-android}

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

**要使用的JSON示例有效负载 [Google FCM测试器](https://pushtry.com/)**

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

有效负载包含数据消息，其中包含所有推送通知投放内容，包括自定义键/值对，如果需要，客户端应用程序必须处理该消息以构建和显示推送通知，否则必须添加任何其他业务逻辑。

要了解Android有效负载的各个方面，请参阅 [消息传送概念和选项(fcm)](https://firebase.google.com/docs/cloud-messaging/concept-options).

>[!NOTE]
>
>自2018年1月起，将不再支持Android有效负载中的通知消息，以便能够唤醒应用程序，并将控制权传递到移动设备应用程序，而无需用户与应用程序交互。

### Campaign Standard配置和有效负载属性之间的映射 {#mapping-payload}

| Campaign配置 | iOS中受影响的属性 | Android中受影响的属性 | 说明 |
|:-:|:-:|:-:|:-:|
| 消息标题 <br>消息正文 | 警报→标题 <br> 警报→正文 | 标题 <br>正文 | 此数据包含警报消息的详情。<br>标题和正文键提供警报的内容。 |
| 播放提示音 | 声音 | 声音 | 用于播放警报的自定义声音。 |
| 徽章的值 | 徽章 | 徽章 | 用于标记应用程序图标的整数值。 |
| 添加深层链接 | uri | 无 | 利用深层链接，您可以直接将用户导向应用程序内的内容（而不是打开 Web 浏览器页面）。 |
| 类别 | 类别 | 类别 | 显示带有远程通知的自定义操作。 <br>类别键可帮助系统将此类别的操作显示为警报界面中的按钮。 |
| 自定义字段 | custom_field1， custom_field2 ... | custom_field1， custom_field2 ... | 您希望发送到应用程序的任何自定义数据。 |
| 富媒体内容URL（图像、gif、音频和视频文件）<br>(仅适用于iOS 10或更高版本) | media-attachment-url | 无 | 用于将丰富内容添加到通知的媒体文件的URL。 <br>在提供此URL的值时，可变内容标志将自动发送到有效负载中。 <br> (仅适用于iOS 10或更高版本) |
| 可变内容 <br> (仅适用于iOS 10或更高版本) | 可变内容 | 无 | 应用程序中的Notification Service扩展将使用可变内容键“截取”所有远程通知，并将允许您处理/处理请求有效负载的内容，然后可以使用这些内容自定义通知。 此功能的用例包括下载和显示多个媒体，解密推送有效负载中存在的任何加密数据。 欲知更多信息，请访问 [修改远程通知的有效负载](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html). <br>(仅适用于iOS 10或更高版本) |
| 可用内容 | content-available | 无 | 选择此选项可在iOS应用程序处于后台/暂停状态时唤醒该应用程序。 唤醒意味着应用程序在后台运行，负责接收推送通知数据有效负载的相应事件处理程序将获得控制并且可以使用数据执行任何计算，包括但不限于构建自定义推送通知并显示该通知。 欲知更多信息，请访问 [使用通知投放唤醒应用程序](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html). |
| 富媒体内容URL（图像文件）<br>（仅适用于Android） | 无 | media-attachment-url | 用于向通知添加丰富内容的图像文件的URL。 |
| 无 | _mId<br>_dId | _mId <br>_dId | broadlogId和deliveryId的值。<br>如果您的应用程序希望调用跟踪回发以跟踪何时单击/打开推送通知，则需要这些属性。 此信息由应用服务器在内部计算和发送，无需用户干预。<br>有关回发的信息，请参阅 [页面](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback). |

### 如何在移动应用程序代码中检索有效负荷信息 {#payload-information}

应用程序服务器发送的有效负载信息由移动设备应用程序代码在事件处理程序中接收，该事件处理程序指示已收到推送通知。 此事件会因正在处理的移动设备平台以及应用程序是在前台还是后台运行而有所不同。 以下文档可帮助您根据用例识别要处理的事件处理程序。

* iOS应用程序： **处理远程通知** 中的部分 [远程通知](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html).
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

**Android移动设备FCM应用程序示例**

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
