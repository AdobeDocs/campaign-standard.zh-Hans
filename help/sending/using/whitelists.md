---
title: Adobe Campaign standard中的白名单
description: 了解如何使用Adobe Campaign Standard优化白名单。
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44049443f8028ed26089ee0d49944ebac6a62111

---


# 白名单{#whitelists}

主要互联网服务提供商(ISP)和Web邮件提供商管理公认电子邮件发送方的白名单。 Adobe Campaign可帮助您通过最佳白名单进行认证。

电子邮件白名单是电子邮件地址或域名的列表，电子邮件阻止程序将允许从中接收邮件。

白名单有两种类型：
* 非商业白名单
* 商业白名单

## 非商业白名单 {#non-commercial-whitelists}

要被这些白名单接受，发送方必须通过一系列基于技术验证的测试（其电子邮件服务器不得是开放式中继，但应具有静态IP），以验证基础架构或其活动（传送频率、数量、投诉数量）。

如果发送方未遵循以下任一规则，则可能会从白名单中删除该规则。 在其 **Adobe Campaign电子邮件交付能力包中** ,Adobe Campaign为非商业白名单的认证流程提供了附带的专家咨询服务。

## 商业白名单 {#commercial-whitelists}

商业白名单基于允许发送方完全绕过防垃圾邮件过滤器的系统，或在发送方进入系统时分配增量点。 这些付费白名单（CPT或按年提供）由诸如返回路径发送者得分等系统提供。

ISP可免费使用这些服务，ISP的数量可能因白名单而异。 因此，发送者在通过具有发送保证来发送其消息时可以更加自信。 某些白名单还提供打开图像和激活链接的功能。

在白名单中显示是任何电子邮件营销活动的不可否认的资产。 在其 **Adobe Campaign电子邮件交付能力包中** ,Adobe Campaign提供商业白名单认证服务，如CSA和Return Path Sender Score。