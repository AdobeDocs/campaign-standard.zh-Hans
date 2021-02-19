---
solution: Campaign Standard
product: campaign
title: 返回发件人
description: 了解如何收到地址不正确的通知并将其排除在将来的通信之外。
audience: channels
content-type: reference
topic-tags: direct-mail
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---


# 返回发件人{#return-to-sender}

支持与包含“返回给发件人”信息的直邮提供商的平面文件交换。 这允许将相应的邮政地址排除在将来的通信之外。 这还允许您收到地址不正确的通知，并通过其他渠道与客户联系或鼓励他更新其邮政地址。

例如，联系人已移到新位置，但未向您提供其新的邮政地址。 提供者检索错误地址的列表，并将此信息发送给自动错阻止列表误地址的Adobe Campaign。

为了使此功能正常工作，直邮默认投放模板在内容中包括投放日志ID。 因此，Adobe Campaign将能够使用户档案和投放数据与提供程序返回的信息同步。

![](assets/direct_mail_return_sender_1.png)

**[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**&#x200B;下有导入模板。 重复此模板以创建您自己的模板。 有关使用导入模板的详细信息，请参阅[使用导入模板](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)。

![](assets/direct_mail_return_sender_2.png)

完成导入后，Adobe Campaign会自动执行以下操作：

* 在用户档案级别添加阻止列表了不正确的地址以
* 投放主要指标(KPI)已更新
* 投放日志将更新
