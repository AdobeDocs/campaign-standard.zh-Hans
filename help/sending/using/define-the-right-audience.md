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

了解有关目标群体的更多信息 [在此部分中](../../audiences/using/selecting-an-audience-in-a-message.md)

## 定位正确的受众 {#target-the-right-audience}

准备好内容后，您需要仔细定义接收消息的人员。

为了成功交付，您需要将最相关的个性化内容发送给正确的收件人。 Adobe Campaign使您能够构建最准确的目标：您可以根据收件人的年龄、本地化、购买内容、是否在上一次投放中单击链接等选择收件人。 通过Adobe Campaign，您还可以定义测试用户档案、控制组和种子地址，以确保您的目标正确。

## 目标映射 {#target-mappings}

默认情况下，投放模板目标 **配置文件**. Adobe Campaign为您的投放提供了其他目标映射，您可以根据需要更改这些映射。

这些映射将呈现 [在此部分中](../../automating/using/query.md#targeting-dimensions-and-resources).

您还可以创建和使用自定义的目标映射。 如需详细信息，请参阅[此部分](../../administration/using/target-mappings-in-campaign.md)。

## 外部数据 {#external-data}

您可以向存储在外部文件中而不是数据库中保存的收件人投放。 要实现此目的，设计工作流会将数据从文件加载到数据库中，并创建关联受众。  了解详情 [在此用例中](../../automating/using/use-case-calling-workflow.md). 另请参阅 [使用参数调用工作流](../../automating/using/calling-a-workflow-with-external-parameters.md).

## 发送给订阅者 {#send-to-subscribers}

要向新闻稿的订阅者发送消息，可以直接将订阅者定位到相应的信息服务。 了解详情 [在此部分中](../../audiences/using/about-subscriptions.md).

**提示**  — 您可以创建列表受众，该受众使用工作流定向新闻稿的订阅者。 然后，您可以在投放中选择此受众。 有关此内容的更多信息，请参阅 [创建列表受众](../../audiences/using/creating-audiences.md#creating-list-audiences).

## 验证、测试用户档案和控制组 {#proofs-test-control-groups}

要测试您的投放，请在发送到主目标之前使用验证。
确保选择适当的校样收件人，因为他们验证消息的表单和内容。 给出了发送校样的步骤 [在此部分中](../../sending/using/sending-proofs.md).

了解有关测试用户档案的更多信息 [在此部分中](../../audiences/using/managing-test-profiles.md).

您可以使用 [对照组](../../sending/using/control-group.md) 用于通过排除部分营销活动受众来衡量其影响。 然后，便能够将收到消息的目标群体的行为与非目标联系人的行为进行比较。根据发送日志，还可以在将来活动中以控制组为目标。

## 删除重复地址 {#deduplicate-addresses}

请务必避免电子邮件地址重复，因为这可能会对目标产生影响：

* 分割目标时，同一消息可能会发送多次。

* 如果收件人在收到消息后取消订阅，则其重复的用户档案仍会收到未来的消息。

对地址进行重复数据删除可保护您的发送信誉并确保良好的隔离管理。

了解详情 [在此用例中](../../automating/using/deduplicating-data-imported-file.md).
