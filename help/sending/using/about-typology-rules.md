---
title: 关于分类和分类规则
description: 了解 Adobe Campaign 中分类和分类规则的工作方式。
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
context-tags: typology,overview;typologyRule,main;typologyRule,overview
feature: Typology Rules
role: User
level: Intermediate
exl-id: dff72856-d28c-45c4-a073-12cc25f51f23
TQID: https://experienceleague.adobe.com/fFTJTgKfIhII-D6pefx9hqnX3a022odFZS5AAmNK1Ao
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 193
ht-degree: 100%

---

# 关于类型和类型规则{#about-typology-rules}

通过 Campaign Standard 可将消息链接到&#x200B;**分类**，以检查消息是否有效且符合质量标准。

分类是在消息分析阶段执行的一系列&#x200B;**分类规则**。 利用分类，可确保电子邮件始终包含特定元素（如退订链接或主题行）或用于从预期目标中排除分组（如未订阅者、竞争对手或不忠诚客户）的筛选规则。

![](assets/typology_messagelink.png)

Campaign Standard 中提供了现成的分类和分类规则。 您也可以根据需要创建新规则，并将它们添加到现有分类或新分类以链接到消息。

创建分类并将其应用到消息的步骤如下：

1. 创建分类规则（请参阅[此章节](../../sending/using/managing-typology-rules.md#creating-a-typology-rule)）。
1. 创建分类并在其中引用之前创建的规则（请参阅[此章节](../../sending/using/managing-typologies.md#creating-a-typology)）。
1. 配置投放以使用创建的分类（请参阅[此章节](../../sending/using/managing-typologies.md#applying-typologies-to-messages)）。
1. 在消息准备期间，可排除满足相关条件的轮廓。 您可以检查日志以监视排除情况。
