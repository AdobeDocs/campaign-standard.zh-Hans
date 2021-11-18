---
title: 返回发件人
description: 了解如何收到地址不正确的通知，并将其排除在将来的通信之外。
audience: channels
content-type: reference
topic-tags: direct-mail
feature: Direct Mail
role: User
level: Intermediate
exl-id: 6783aa68-7fd7-4f53-86bf-853c0fea5899
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---

# 返回发件人{#return-to-sender}

支持与直邮提供商的平面文件交换，其中包含“退回发件人”信息。 这允许将相应的邮政地址排除在未来通信之外。 这还允许您收到地址不正确的通知，并通过其他渠道与客户联系或鼓励他们更新其邮政地址。

例如，联系人已移至新位置，但未向您提供其新邮政地址。 提供商检索错误地址的列表，并将此信息发送到Adobe Campaign，会自阻止列表动错误地址。

为了使此功能正常工作，直邮默认投放模板在内容中包含投放日志ID。 因此，Adobe Campaign将能够将用户档案和投放数据与提供商返回的信息同步。

![](assets/direct_mail_return_sender_1.png)

导入模板位于 **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. 复制此模板以创建您自己的模板。 有关使用导入模板的更多信息，请参阅 [使用导入模板](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates).

![](assets/direct_mail_return_sender_2.png)

完成导入后，Adobe Campaign会自动执行以下操作：

* 在用户档案级别添加阻止列表的地址不正确
* 投放主要指标(KPI)已更新
* 投放日志已更新
