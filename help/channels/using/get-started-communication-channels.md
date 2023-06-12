---
title: 通信渠道入门
description: 在各种渠道上创建个性化信息，使用模板，创建登陆页，以及查看最佳实践。
audience: channels
content-type: reference
topic-tags: about-communication-channels
feature: Overview
role: User
level: Beginner
exl-id: 4ea5b0eb-35da-4db6-a529-ba636be7825f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 23%

---

# 通信渠道入门 {#discovering-communication-channels}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_concepts.svg" width="60px"><p><a href="#global-concepts">全局概念</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#available-communication-channels">通信渠道</a></p></td>
<td><img src="assets/do-not-localize/icon_transactional.svg" width="60px"><p><a href="#transactional-messages">事务性消息</a></p></td>
<td><img src="assets/do-not-localize/icon_landing.svg" width="60px"><p><a href="#landing-pages">登陆页面</a></p></td></tr>
</table>

通过Adobe Campaign，您可以跨每个渠道启动、衡量和自动化营销活动。
协调所有营销渠道并不是一项不可能的任务。 借助Adobe Campaign，您可以将来自不同系统、设备和渠道的客户数据整合到单个配置文件中。 然后，提供及时且相关的营销活动，在客户历程的适当位置和适当方式与客户见面。

## 全局概念 {#global-concepts}

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

**利用Campaign消息仪表板** 从单一位置配置和发送报文，并访问各种功能，如时间安排、多语言报文传送……

**管理模板** 以配置消息属性，并让您获得时间以及消息传递策略的一致性。 例如，对于电子邮件，负责配置模板的功能管理员可以定义电子邮件的标准参数，如受众、计划或内容，与发送相关的高级参数，有效性、跟踪等，或者与定位和个性化（定位上下文）相关的预配置参数。

了解更多信息:

* [发送消息的关键步骤](../../channels/using/key-steps-to-send-a-message.md)
* [访问消息](../../channels/using/accessing-messages.md)
* [消息仪表板](../../channels/using/message-dashboard.md)
* [多语言消息模板](../../channels/using/multilingual-messages-template.md)
* [营销活动模板](../../start/using/marketing-activity-templates.md)

## 通信渠道 {#available-communication-channels}

<img src="assets/do-not-localize/icon_channels.svg"  width="60px">

**五个通信渠道** 在Adobe Campaign中提供：电子邮件、短信消息、推送通知、应用程序内消息和直邮投放。

对于每个渠道，都提供了特定功能。 例如，电子邮件渠道允许您执行A/B测试，以测试最多3个版本的电子邮件。 通过SMS渠道，管理STOP SMS消息并将来自收件人的传入SMS存储到数据库中。

此外，还可以利用Campaign Standard **个性化和动态内容功能** 以吸引受众的兴趣。

了解更多信息:

* [创建电子邮件](../../channels/using/about-emails.md)
* [创建短信消息](../../channels/using/about-sms-messages.md)
* [创建推送通知](../../channels/using/about-push-notifications.md)
* [创建应用程序内消息](../../channels/using/about-in-app-messaging.md)
* [创建直邮投放](../../channels/using/about-direct-mail.md)

## 事务性消息 {#transactional-messages}

<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

**发送单个和唯一消息** 对您的客户实时：欢迎邮件、订单送货确认、密码修改等。

事务型消息可用于电子邮件、短信和推送通知渠道，具体取决于您的选项。 有两种类型的消息： **事件事务型消息** 在没有用户档案信息的情况下定位事件，以及 **用户档案事务型消息** 从数据库定向用户档案。

了解更多信息:

* [事务性消息传递入门](../../channels/using/getting-started-with-transactional-msg.md)
* [配置事务性事件](../../channels/using/configuring-transactional-event.md)
* [发布事务性事件](../../channels/using/publishing-transactional-event.md)
* [编辑事务性消息](../../channels/using/editing-transactional-message.md)
* [发布事务型消息](../../channels/using/publishing-transactional-message.md)
* [事务性推送通知](../../channels/using/transactional-push-notifications.md)
* [跟进消息](../../channels/using/follow-up-messages.md)

## 登陆页面 {#landing-pages}

<img src="assets/do-not-localize/icon_landing.svg" width="60px">

Campaign附带登陆页面，这些登陆页面是可用于 **捕获受众信息**，提供服务的订阅、显示数据并扩展数据库。

登陆页面还可用于 **获取或更新现有用户档案**，并设置双重选择加入机制，以便保护平台免受错误或无效的电子邮件地址或垃圾邮件机器人的侵扰。

了解更多信息:

* [登陆页面快速入门](../../channels/using/getting-started-with-landing-pages.md)
* [登陆页面模板](../../channels/using/landing-page-templates.md)
* [管理登陆页面表单数据](../../channels/using/managing-landing-page-form-data.md)
* [设置双重选择加入流程](../../channels/using/setting-up-a-double-opt-in-process.md)

## 其他资源

* [优化可投放性](../../sending/using/about-deliverability.md)
* [投放最佳实践](../../sending/using/delivery-best-practices.md)
* [设计电子邮件内容](../../designing/using/designing-content-in-adobe-campaign.md)
* [导入AEM内容](../../integrating/using/creating-email-experience-manager.md)
* [使用工作流发送消息](../../automating/using/about-channel-activities.md)
* [通信渠道教程视频](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/create-email-from-homepage.html?lang=zh-Hans)
* [用例：创建跨渠道投放](../../automating/using/workflow-cross-channel-delivery.md)
