---
title: 推广服务
description: 使用Adobe Campaign通过专用登陆页面、电子邮件或直接在您的网站上推广服务并吸引客户。
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
feature: Audiences
role: User
level: Intermediate
exl-id: c1f8770a-8b25-41db-aa52-828e181a563d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 3%

---

# 推广服务{#promoting-a-service}

您可以通过多种方式提供服务订阅，并让访客能够管理其订阅。

您可以使用Campaign通过以下方式推广服务：

* [在电子邮件中插入服务订阅或退订链接](../../designing/using/links.md#inserting-a-link).

* [在电子邮件中插入指向订阅或退订登陆页面的链接](../../designing/using/links.md). 在这种情况下，必须在相关登陆页面的属性中直接引用服务(请参阅 [将登陆页面链接到服务](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service))。

   >[!NOTE]
   >
   >还必须让订阅者能够取消订阅。 为此，请插入服务 <b>退订链接</b> 在自动发送给新订阅者的确认电子邮件（在服务属性中定义）中，以及在将来的新闻稿电子邮件中。

* 在网站上提供订阅或退订登陆页面。 授予您访问登陆页面的权限的URL必须指定相关服务等参数以及访问该页面的配置文件ID。 此ID可在登陆页面参数中定义(请参阅 [配置登陆页面](../../channels/using/configuring-landing-page.md))。
