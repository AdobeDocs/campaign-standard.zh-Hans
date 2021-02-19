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

目标人口是关键：仔细构建列表，在流行的电子邮件客户端和移动设备上测试电子邮件，并确保您的电子邮件列表始终处于最新状态（没有未知或过时的地址）。 您还可以发送有助于设置完整验证周期的验证。

在本节](../../audiences/using/selecting-an-audience-in-a-message.md)中了解关于目标群[的更多信息

## 目标正确的受众{#target-the-right-audience}

当您的内容准备就绪后，您需要仔细定义将收到您的消息的用户。

为了使您的投放成功，您需要将最相关的个性化内容发送给正确的收件人。 Adobe Campaign使您能够构建最准确的目标:您可以根据收件人的年龄、本地化、购买的商品，如果他们单击了上一个投放中的链接，等等。 使用Adobe Campaign，您还可以定义测试用户档案、对照组和种子地址，以确保目标正确。

## 目标映射{#target-mappings}

默认情况下，投放模板目标&#x200B;**用户档案**。 Adobe Campaign会优惠其他目标映射，您可以根据自己的需求进行更改。

这些映射在本节](../../automating/using/query.md#targeting-dimensions-and-resources)中显示。[

您还可以创建和使用自定义目标映射。 如需详细信息，请参阅[此部分](../../administration/using/target-mappings-in-campaign.md)。

## 外部数据{#external-data}

您可以向存储在外部文件而不是保存在收件人库中的客户传送。 为此，设计一个工作流将从文件将数据加载到数据库并创建关联受众。  了解此用例中的更多[信息](../../automating/using/use-case-calling-workflow.md)。 另请参阅[使用参数](../../automating/using/calling-a-workflow-with-external-parameters.md)调用工作流。

## 发送给您的订阅者{#send-to-subscribers}

要向新闻稿的订阅者发送消息，您可以直接将订阅者目标到相应的信息服务。 请阅读本节](../../audiences/using/about-subscriptions.md)了解更多信息。[

**提示**  — 您可以创建一个列表受众，使用工作流将订阅者目标到您的新闻稿。然后，您可以在投放中选择此受众。 有关详细信息，请参阅[创建列表受众](../../audiences/using/creating-audiences.md#creating-list-audiences)。

## 验证、测试用户档案和对照组{#proofs-test-control-groups}

要测试投放，请在发送到主目标之前使用验证。
请确保您选择适当的验证收件人，因为它们会验证表单和消息的内容。 发送验证的步骤在本节](../../sending/using/sending-proofs.md)中介绍。[

了解有关测试用户档案[的详细信息，请参阅本节](../../audiences/using/managing-test-profiles.md)。

您可以使用[对照组](../../sending/using/control-group.md)来通过排除活动的一部分来衡量其影响。 然后，便能够将收到消息的目标群体的行为与非目标联系人的行为进行比较。根据发送日志，还可以在将来活动中以控制组为目标。

## 消除地址重复{#deduplicate-addresses}

请务必避免拥有重复电子邮件地址，因为这可能会影响您的目标:

* 在拆分目标时，可以多次发送同一消息。

* 如果收件人在收到消息后取消订阅，其重复用户档案仍将接收将来的消息。

消除地址重复可保护您的发送信誉并确保良好的隔离管理。

了解此用例中的更多[信息](../../automating/using/deduplicating-data-imported-file.md)。
