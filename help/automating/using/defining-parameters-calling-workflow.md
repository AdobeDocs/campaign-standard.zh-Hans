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
TQID: 'https://experienceleague.adobe.com/-YjlK1Op8P08sxb--BOHl8AWyciX4BqPnCPQ3lpD3Co'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
    internal-label: REST API
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
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
   * **[!UICONTROL Value]**：要分配给参数的值。 该值应遵循[此部分](../../automating/using/advanced-expression-editing.md#standard-syntax)中描述的&#x200B;**标准语法**。

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >确保已在&#x200B;**[!UICONTROL External signal]**&#x200B;活动中声明了所有的参数。 否则，运行活动时将出错。

1. 定义参数后，确认活动，然后保存工作流。
