---
title: 在调用工作流时定义参数
description: 本节详细介绍如何使用外部参数调用工作流。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: f7de0186-4136-4603-8f80-9f58c641cd9d
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 13%

---

# 在调用工作流时定义参数 {#defining-the-parameters-when-calling-the-workflow}

本节详细介绍在调用工作流时如何定义参数。 有关如何通过API调用执行此操作的更多信息，请参阅 [REST API文档](../../api/using/triggering-a-signal-activity.md).

在定义参数之前，请确保：

* 参数已在 **[!UICONTROL External Signal]** 活动。 请参阅[此页](../../automating/using/declaring-parameters-external-signal.md)。
* 包含信号活动的工作流正在运行。

配置 **[!UICONTROL End]** 活动，请按照以下步骤操作：

1. 打开 **[!UICONTROL End]** 活动，然后选择 **[!UICONTROL External signal]** 选项卡。
1. 选择要调用的工作流和外部信号活动。
1. 单击 **[!UICONTROL Create element]** 按钮以添加参数，然后填写其名称和值。

   * **[!UICONTROL Name]**:在 **[!UICONTROL External signal]** 活动(请参阅 [本页](../../automating/using/declaring-parameters-external-signal.md))。
   * **[!UICONTROL Value]**:要分配给参数的值。 值应在 **标准语法**，在 [此部分](../../automating/using/advanced-expression-editing.md#standard-syntax).

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >确保已在 **[!UICONTROL External signal]** 活动。 否则，运行活动时将出错。

1. 定义参数后，确认活动，然后保存工作流。
