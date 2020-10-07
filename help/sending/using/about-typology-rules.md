---
title: 关于分类和分类规则
description: 了解 Adobe Campaign 中分类和分类规则的工作方式。
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 关于分类和分类规则{#about-typology-rules}

通过 Campaign Standard 可将消息链接到&#x200B;**分类**，以检查消息是否有效且符合质量标准。

分类是在消息分析阶段执行的一系列&#x200B;**分类规则**。利用分类，可确保电子邮件始终包含特定元素（如退订链接或主题行）或用于从预期目标中排除分组（如未订阅者、竞争对手或不忠诚客户）的筛选规则。

![](assets/typology_messagelink.png)

Campaign Standard 中提供了现成的分类和分类规则。您也可以根据需要创建新规则，并将它们添加到现有分类或新分类以链接到消息。

创建分类并将其应用到消息的步骤如下：

1. 创建分类规则（请参阅[此章节](../../sending/using/managing-typology-rules.md#creating-a-typology-rule)）。
1. 创建分类并在其中引用之前创建的规则（请参阅[此章节](../../sending/using/managing-typologies.md#creating-a-typology)）。
1. 配置投放以使用创建的分类（请参阅[此章节](../../sending/using/managing-typologies.md#applying-typologies-to-messages)）。
1. 在消息准备期间，可排除满足相关条件的用户档案。您可以检查日志以监视排除情况。
