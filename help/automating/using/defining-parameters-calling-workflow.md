---
solution: Campaign Standard
product: campaign
title: 使用外部参数调用工作流
description: 本节详细介绍如何使用外部参数调用工作流。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 13%

---


# 在调用工作流时定义参数 {#defining-the-parameters-when-calling-the-workflow}

本节详细介绍如何在调用工作流时定义参数。 有关如何从API调用执行此操作的详细信息，请参阅 [REST API文档](../../api/using/triggering-a-signal-activity.md)。

在定义参数之前，请确保：

* 参数已在活动中声 **[!UICONTROL External Signal]** 明。 请参阅[此页](../../automating/using/declaring-parameters-external-signal.md)。
* 正在运行包含信号活动的工作流。

要配置 **[!UICONTROL End]** 活动，请执行以下步骤：

1. Open the **[!UICONTROL End]** activity, then select the **[!UICONTROL External signal]** tab.
1. 选择要调用的工作流和外部信号活动。
1. 单击按 **[!UICONTROL Create element]** 钮以添加参数，然后填写其名称和值。

   * **[!UICONTROL Name]**:已在活动中声明的 **[!UICONTROL External signal]** 名称(请 [参阅此页](../../automating/using/declaring-parameters-external-signal.md))。
   * **[!UICONTROL Value]**:要分配给参数的值。 该值应遵循本 **节所述**&#x200B;的标 [准语法](../../automating/using/advanced-expression-editing.md#standard-syntax)。

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Make sure that all the parameters have been declared in the **[!UICONTROL External signal]** activity. 否则，运行活动时将出错。

1. 定义参数后，确认活动，然后保存工作流。
