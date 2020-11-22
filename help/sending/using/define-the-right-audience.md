---
solution: Campaign Standard
product: campaign
title: 定义正确的受众
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
translation-type: tm+mt
source-git-commit: a7300666587362048431d0bafacc317170b317aa
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 11%

---


# 定义正确的受众 {#define-the-right-audience}

目标人口是关键：仔细构建列表，在流行的电子邮件客户端和移动设备上测试电子邮件，并确保电子邮件列表始终处于最新状态（没有未知或过时的地址）。 您还可以发送帮助设置完整验证周期的验证。

在本节中进一步了 [解目标群](../../audiences/using/selecting-an-audience-in-a-message.md)

## 目标正确的受众 {#target-the-right-audience}

当您的内容准备就绪后，您需要仔细定义将收到您的消息的人。

为了使投放成功，您希望将最相关的个性化内容发送给正确的收件人。 Adobe Campaign使您能够构建最准确的目标:您可以根据收件人的年龄、本地化、他们购买的商品，如果他们点击了先前投放中的链接，等等。 使用Adobe Campaign，您还可以定义测试用户档案、对照组和种子地址，以确保目标正确。

## 目标映射 {#target-mappings}

默认情况下，投放模板用户档案 **目标**。 Adobe Campaign为投放优惠其他目标映射，您可以根据需要进行更改。

本节将介绍这 [些映射](../../automating/using/query.md#targeting-dimensions-and-resources)。

您还可以创建和使用自定义目标映射。 如需详细信息，请参阅[此部分](../../administration/using/target-mappings-in-campaign.md)。

## 外部数据 {#external-data}

您可以将存储在外部文件而非保存在收件人库中的传送到数据库。 为此，设计一个工作流将从文件将数据加载到数据库中并创建一个关联的受众。  通过此用 [例了解更多信息](../../automating/using/use-case-calling-workflow.md)。 另请参阅 [使用参数调用工作流](../../automating/using/calling-a-workflow-with-external-parameters.md)。

## 发送给您的订阅者 {#send-to-subscribers}

要向新闻稿的订阅者发送消息，您可以直接将订阅者目标到相应的信息服务。 在本节 [中了解更多](../../audiences/using/about-subscriptions.md)。

**提示** -您可以创建列表受众，该使用工作流将订阅者目标到您的新闻稿。 然后，您可以在受众中选择此投放。 有关此内容的详细信息，请参 [阅创建列表受众](../../audiences/using/creating-audiences.md#creating-list-audiences)。

## 验证、测试用户档案和对照组 {#proofs-test-control-groups}

要测试投放，请在发送到主目标前使用验证。
请确保您选择适当的验证收件人，因为它们会验证表单和消息的内容。 本节介绍了发送验证 [的步骤](../../sending/using/sending-proofs.md)。

在本节中进一步了 [解测试用户档案](../../audiences/using/managing-test-profiles.md)。

You can use [Control groups](../../sending/using/control-group.md) to measure the impact of your campaigns by excluding a portion of their audience. 然后，便能够将收到消息的目标群体的行为与非目标联系人的行为进行比较。根据发送日志，还可以在将来活动中以控制组为目标。

## 消除重复地址 {#deduplicate-addresses}

请务必避免重复电子邮件地址，因为这可能会影响您的目标:

* 在拆分目标时，可以多次发送同一消息。

* 如果收件人在收到消息后取消订阅，其重复用户档案仍将收到将来的消息。

消除重复地址可保护您的发送信誉并确保良好的隔离管理。

通过此用 [例了解更多信息](../../automating/using/deduplicating-data-imported-file.md)。
