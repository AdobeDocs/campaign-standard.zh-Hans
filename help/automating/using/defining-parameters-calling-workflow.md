---
title: 在调用工作流时定义参数
description: 本节详细介绍如何使用外部参数调用工作流。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: f7de0186-4136-4603-8f80-9f58c641cd9d
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 13%

---

# 在调用工作流时定义参数 {#defining-the-parameters-when-calling-the-workflow}

本节详细介绍在调用工作流时如何定义参数。 有关如何通过API调用执行此操作的更多信息，请参阅[REST API文档](../../api/using/triggering-a-signal-activity.md)。

在定义参数之前，请确保：

* 已在&#x200B;**[!UICONTROL External Signal]**&#x200B;活动中声明了参数。 请参阅[此页](../../automating/using/declaring-parameters-external-signal.md)。
* 包含信号活动的工作流正在运行。

要配置&#x200B;**[!UICONTROL End]**&#x200B;活动，请执行以下步骤：

1. 打开&#x200B;**[!UICONTROL End]**&#x200B;活动，然后选择&#x200B;**[!UICONTROL External signal]**&#x200B;选项卡。
1. 选择要调用的工作流和外部信号活动。
1. 单击&#x200B;**[!UICONTROL Create element]**&#x200B;按钮以添加参数，然后填写其名称和值。

   * **[!UICONTROL Name]**：已在&#x200B;**[!UICONTROL External signal]**&#x200B;活动中声明的名称（请参阅[此页面](../../automating/using/declaring-parameters-external-signal.md)）。
   * **[!UICONTROL Value]**：要分配给参数的值。 该值应遵循&#x200B;**此部分**&#x200B;中描述的[标准语法](../../automating/using/advanced-expression-editing.md#standard-syntax)。

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >确保已在&#x200B;**[!UICONTROL External signal]**&#x200B;活动中声明了所有的参数。 否则，运行活动时将出错。

1. 定义参数后，确认活动，然后保存工作流。
