---
title: 返回发送方
seo-title: 返回发送方
description: 返回发送方
seo-description: 了解如何收到错误地址的通知并将其排除在将来的通信中。
page-status-flag: 从未激活
uuid: 11981c2f-4166-9daa-ec6 a6 b4 d5 b4 d5367
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: 直邮
discoiquuid: 5f20ff3f-8242-4735-8c60-c57610 edff52
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Return to sender{#return-to-sender}

支持与发送到发送者信息的直接邮件提供商进行平面文件交换。这允许将相应的邮件排除在将来的通信中。这还允许您收到不正确地址的通知并通过其他渠道与客户互动，或鼓励他更新其邮寄地址。

例如，联系人已迁到新位置，但没有为您提供新的邮政地址。提供商检索错误地址的列表，并将此信息发送到自动黑名单中列出错误地址的Adobe Campaign。

为了使此功能正常工作，直接邮件默认交付模板包括内容传递日志ID。因此，Adobe Campaign将能够将配置文件和交付数据与提供商返回的信息同步。

![](assets/direct_mail_return_sender_1.png)

An import template is available under **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. 复制此模板以创建自己的模板。For more on using import templates, refer to [Using import templates](../../automating/using/defining-import-templates.md).

![](assets/direct_mail_return_sender_2.png)

完成导入后，Adobe Campaign会自动执行以下操作：

* 配置文件级别列入黑名单，地址不正确
* 交付主要指示器(KPI)已更新
* 交付日志已更新

