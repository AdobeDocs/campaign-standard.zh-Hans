---
title: 返回发件人
description: 了解如何收到地址错误的通知并将其排除在将来的通信之外。
page-status-flag: 从未激活
uuid: 11981c2f-0b7f-4166-9daa-ec6a6b4d5367
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 频道
content-type: 参考
topic-tags: 直邮
discoiquuid: 5f20ff3f-8242-4735-8c60-c57610edff52
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 返回发件人{#return-to-sender}

支持与直接邮件提供商进行平面文件交换，并包含“返回给发送者”信息。 这允许将相应的邮政地址排除在将来的通信之外。 这还允许您收到地址错误的通知并通过其他渠道与客户联系或鼓励他更新其邮政地址。

例如，联系人已移到新位置，但未向您提供他的新邮政地址。 提供商会检索错误地址列表，并将此信息发送到Adobe Campaign,Adobe Campaign会自动将错误地址列入黑名单。

为了使此功能正常工作，直邮默认分发模板在内容中包括分发日志ID。 因此，Adobe Campaign将能够将配置文件和交付数据与提供商返回的信息同步。

![](assets/direct_mail_return_sender_1.png)

导入模板位于下 **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**。 复制此模板以创建您自己的模板。 有关使用导入模板的详细信息，请参阅 [使用导入模板](../../automating/using/defining-import-templates.md)。

![](assets/direct_mail_return_sender_2.png)

完成导入后，Adobe Campaign会自动执行以下操作：

* 配置文件级别的黑名单中列出地址不正确
* 更新交付主要指标(KPI)
* 更新了交付日志

