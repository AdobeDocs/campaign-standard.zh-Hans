---
title: 定义正确的受众
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: “当您的内容准备就绪后，了解如何仔细定义接收您消息的人。”
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

目标群体是关键：仔细构建列表，在流行的电子邮件客户端和移动设备上测试电子邮件，并确保电子邮件列表是最新的（地址不未知或过时）。 您还可以发送校样，以帮助设置完整的验证周期。

进一步了解目标群体 [在此部分中](../../audiences/using/selecting-an-audience-in-a-message.md)

## 定位正确的受众 {#target-the-right-audience}

当您的内容准备就绪后，您需要仔细定义接收消息的人员。

为了使交付成功，您需要将最相关的个性化内容发送给适当的收件人。 Adobe Campaign使您能够构建最准确的目标：您可以根据收件人的年龄、本地化、购买的内容、他们单击了先前投放中的链接等内容来选择收件人。 通过Adobe Campaign，您还可以定义测试用户档案、控制组和种子地址，以确保目标正确。

## 目标映射 {#target-mappings}

默认情况下，投放模板定位 **用户档案**. Adobe Campaign为您的投放提供了其他目标映射，您可以根据自己的需求进行更改。

这些映射将呈现 [在此部分中](../../automating/using/query.md#targeting-dimensions-and-resources).

您还可以创建和使用自定义目标映射。 如需详细信息，请参阅[此部分](../../administration/using/target-mappings-in-campaign.md)。

## 外部数据 {#external-data}

您可以将内容发送给存储在外部文件中而不是保存在数据库中的收件人。 为此，设计一个工作流将从文件将数据加载到数据库中，并创建关联的受众。  了解更多 [在此用例中](../../automating/using/use-case-calling-workflow.md). 另请参阅 [使用参数调用工作流](../../automating/using/calling-a-workflow-with-external-parameters.md).

## 发送给订阅者 {#send-to-subscribers}

要向新闻稿的订阅者发送消息，您可以直接将订阅者定位到相应的信息服务。 了解更多 [在此部分中](../../audiences/using/about-subscriptions.md).

**笔尖**  — 您可以使用工作流创建列表受众，以定向新闻稿的订阅者。 然后，您可以在投放中选择此受众。 有关此内容的更多信息，请参阅 [创建列表受众](../../audiences/using/creating-audiences.md#creating-list-audiences).

## 校样、测试用户档案和控制组 {#proofs-test-control-groups}

要测试投放，请在发送到主目标之前使用校样。
请确保选择适当的校样收件人，因为他们会验证消息的表单和内容。 介绍了发送校样的步骤 [在此部分中](../../sending/using/sending-proofs.md).

进一步了解测试用户档案 [在此部分中](../../audiences/using/managing-test-profiles.md).

您可以使用 [控制组](../../sending/using/control-group.md) 可通过排除部分受众来衡量活动的影响。 然后，便能够将收到消息的目标群体的行为与非目标联系人的行为进行比较。根据发送日志，还可以在将来活动中以控制组为目标。

## 删除重复地址 {#deduplicate-addresses}

请务必避免使用重复的电子邮件地址，因为这可能会对您的目标产生影响：

* 在拆分目标时，可以多次发送同一消息。

* 如果收件人在收到消息后取消订阅，则其重复的用户档案仍将收到将来的消息。

删除地址重复项可保护您的发送信誉，并确保良好的隔离管理。

了解更多 [在此用例中](../../automating/using/deduplicating-data-imported-file.md).
