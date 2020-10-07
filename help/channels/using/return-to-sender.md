---
title: 返回发件人
description: 了解如何收到地址错误的通知并将其排除在将来的通信之外。
page-status-flag: never-activated
uuid: 11981c2f-0b7f-4166-9daa-ec6a6b4d5367
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: 5f20ff3f-8242-4735-8c60-c57610edff52
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 返回发件人{#return-to-sender}

支持与直接邮件提供商进行包含“返回给发件人”信息的平面文件交换。 这允许将来的通信中排除相应的邮政地址。 这还允许您收到地址不正确的通知，并通过其他渠道与客户联系，或鼓励他更新其邮政地址。

例如，联系人已移到新位置，但未向您提供其新的邮政地址。 提供者检索错误地址的列表，并将此信息发送给自动错误地阻止列表址的Adobe Campaign。

为了使此功能正常工作，直邮默认投放模板在内容中包括投放日志ID。 因此，Adobe Campaign将能够将用户档案和投放数据与提供程序返回的信息同步。

![](assets/direct_mail_return_sender_1.png)

导入模板位于 **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**。 重复此模板以创建您自己的模板。 有关使用导入模板的详细信息，请参阅 [使用导入模板](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)。

![](assets/direct_mail_return_sender_2.png)

完成导入后，Adobe Campaign会自动执行以下操作：

* 在用户档案级别将不阻止列表正确的地址添加到
* 投放主要指标(KPI)已更新
* 投放日志更新
