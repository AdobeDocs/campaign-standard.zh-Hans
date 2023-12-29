---
title: 推送通知渠道即将发生的变化
description: 推送通知渠道即将发生的变化
audience: channels
feature: Push
role: Admin
level: Experienced
exl-id: e273b443-7c43-482b-8f86-60ada4b57cbf
source-git-commit: 1d8baca669235be10d373d985ea62f6f014c16f8
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 12%

---

# 推送通知渠道即将发生的变化 {#push-upgrade}

您可以使用Campaign在Android和iOS设备上发送推送通知。 要执行此操作，Campaign需要依赖特定的订阅服务。 Android Firebase Cloud Messaging (FCM) 服务的一些重要更改将于 2024 年发布，并将影响您的 Adobe Campaign 实施。此外，对于iOS应用程序，Adobe正在更改允许管理员配置证书的方式。

## 更改了哪些内容？ {#push-changes}

### Android {#push-android}

作为Google持续努力改进其服务的一部分，旧版FCM API将在以下日期停用 **2024年6月20日**. 在中了解有关Firebase云消息HTTP协议的更多信息 [Google Firebase文档](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

目前Adobe Campaign Standard正在使用HTTP旧版API发送Android推送通知消息，并将在未来几个月内进行更改以升级到HTTP v1 API。

### iOS {#push-ios}

Adobe还将为iOS推送通知渠道升级Adobe Campaign Standard，并更改我们允许管理员为其iOS应用程序配置证书的方式。 管理员现在需要通过iOS的用户界面上传Adobe Campaign Standard证书。

## 您是否受影响？ {#push-impact}

作为Campaign Standard用户，如果您向受众发送推送通知消息，则会受到影响。

## 如何迁移？ {#push-migration}

这些更新要求升级Campaign Standard版本，因为它们会影响移动渠道配置和权限管理。

为了促进顺利过渡进程，将很快提供详细指示。

我们的客户支持团队将在整个过渡过程中为您提供帮助。 我们还可能主办网络研讨会和支持会议，以涵盖过渡的技术方面和最佳实践。

同时，建议花些时间审查您在Adobe Campaign Standard中的当前配置和自定义，以便您准备在需要时进行任何必要的更改。

如果您有任何直接的顾虑或问题，请随时联系我们的支持团队。
