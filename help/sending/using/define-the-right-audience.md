---
title: 定义正确的受众
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: “准备好内容后，了解如何仔细定义接收消息的人员。”
feature: Deliverability
role: User
level: Intermediate
exl-id: 1e06fd9d-e850-4856-8f7b-b581dbe157df
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 11%

---

# 定义正确的受众 {#define-the-right-audience}

目标群体是关键：仔细构建列表，在常用的电子邮件客户端和移动设备上测试电子邮件，并确保电子邮件列表是最新的（不含未知或过时的地址）。 您还可以发送校样来帮助设置完整的验证周期。

在本节[&#128279;](../../audiences/using/selecting-an-audience-in-a-message.md)中了解有关目标群体的更多信息

## 定位正确的受众 {#target-the-right-audience}

准备好内容后，您需要仔细定义接收消息的人员。

为了成功交付，您需要将最相关的个性化内容发送给正确的收件人。 Adobe Campaign使您能够构建最准确的目标：您可以根据收件人的年龄、本地化、购买内容、是否在上一次投放中单击链接等选择收件人。 通过Adobe Campaign，您还可以定义测试用户档案、控制组和种子地址，以确保您的目标正确。

## 目标映射 {#target-mappings}

默认情况下，投放模板以&#x200B;**用户档案**&#x200B;为目标。 Adobe Campaign为您的投放提供了其他目标映射，您可以根据需要更改这些映射。

此部分[&#128279;](../../automating/using/query.md#targeting-dimensions-and-resources)中提供了这些映射。

您还可以创建和使用自定义的目标映射。 如需详细信息，请参阅[此小节](../../administration/using/target-mappings-in-campaign.md)。

## 外部数据 {#external-data}

您可以向存储在外部文件中而不是数据库中保存的收件人投放。 要实现此目的，设计工作流会将数据从文件加载到数据库中，并创建关联受众。  在此用例[&#128279;](../../automating/using/use-case-calling-workflow.md)中了解更多。 另请参阅[使用参数](../../automating/using/calling-a-workflow-with-external-parameters.md)调用工作流。

## 发送给订阅者 {#send-to-subscribers}

要向新闻稿的订阅者发送消息，可以直接将订阅者定位到相应的信息服务。 在本节[&#128279;](../../audiences/using/about-subscriptions.md)中了解更多。

**提示** — 您可以使用工作流创建以新闻稿订阅者为目标的“列表”受众。 然后，您可以在投放中选择此受众。 有关详细信息，请参阅[创建列表受众](../../audiences/using/creating-audiences.md#creating-list-audiences)。

## 验证、测试用户档案和控制组 {#proofs-test-control-groups}

要测试您的投放，请在发送到主目标之前使用验证。
确保选择适当的校样收件人，因为他们验证消息的表单和内容。 在此部分[&#128279;](../../sending/using/sending-proofs.md)中介绍了发送校样的步骤。

在本节[&#128279;](../../audiences/using/managing-test-profiles.md)中了解有关测试用户档案的更多信息。

您可以使用[控制组](../../sending/using/control-group.md)通过排除部分控制组受众来衡量营销活动的影响。 然后，便能够将收到消息的目标群体的行为与非目标联系人的行为进行比较。根据发送日志，还可以在将来活动中以对照组为目标。

## 删除重复地址 {#deduplicate-addresses}

请务必避免电子邮件地址重复，因为这可能会对目标产生影响：

* 分割目标时，同一消息可能会发送多次。

* 如果收件人在收到消息后取消订阅，则其重复的用户档案仍会收到未来的消息。

对地址进行重复数据删除可保护您的发送信誉并确保良好的隔离管理。

在此用例[&#128279;](../../automating/using/deduplicating-data-imported-file.md)中了解更多。
