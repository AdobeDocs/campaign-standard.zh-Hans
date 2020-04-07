---
title: 关于类型和类型规则
description: 了解Adobe Campaign中的类型和类型规则如何工作。
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a9c0e3cc4609e747bbfebeb90049862f29c9d8d9

---


# 关于类型和类型规则{#about-typology-rules}

Campaign Standard允许您将消息链接到 **类型**，以检查消息是否有效并符合质量标准。

类型是在消 **息类型规则**&#x200B;阶段执行的分析集。 它们允许您确保电子邮件始终包含某些元素(如退订链接或主题行)或筛选规则，以从您的预期目标中排除组(如未订阅者、竞争对手或非忠诚度客户)。

![](assets/typology_messagelink.png)

可在Campaign Standard中使用现成的字体和类型规则。 根据您的需求，您还可以创建新规则，并将它们添加到现有或新的类型以链接到您的消息。

创建消息并将类型学应用到消息的步骤有：

1. 创建类型规则(请参 [阅此部分](../../sending/using/managing-typology-rules.md#creating-a-typology-rule))。
1. 创建一种类型学，并参考您在其中创建的规则(请参 [阅本节](../../sending/using/managing-typologies.md#creating-a-typology))。
1. 配置投放以使用您创建的排版(请参 [阅本节](../../sending/using/managing-typologies.md#applying-typologies-to-messages))。
1. 在消息准备过程中，当满足标准时，用户档案将被排除。 您可以检查日志以监视排除。
