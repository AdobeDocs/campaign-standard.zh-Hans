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
source-wordcount: '108'
ht-degree: 5%

---


# Declaring the parameters in the External signal activity {#declaring-the-parameters-in-the-external-signal-activity}

使用参数调用工作流的第一步是在活动中声明这 **[!UICONTROL External signal]** 些参数。

1. Open the **[!UICONTROL External signal]** activity, then select the **[!UICONTROL Parameters]** tab.
1. 单击按 **[!UICONTROL Create element]** 钮，然后指定每个参数的名称和类型。

   >[!CAUTION]
   >
   >确保参数的名称和数量与调用工作流时定义的参数相同(请参 [阅此页](../../automating/using/defining-parameters-calling-workflow.md))。 此外，参数类型必须与期望值一致。

   ![](assets/extsignal_declaringparameters_1.png)

1. 声明参数后，完成工作流配置，然后运行它。
