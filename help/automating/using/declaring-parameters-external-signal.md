---
title: 使用外部参数调用工作流
description: 本节详细介绍如何使用外部参数调用工作流。
page-status-flag: never-activated
uuid: beccd1b6-8e6d-4504-9152-9ff537459c4a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 1676da91-55e3-414f-bcd3-bb0804b682bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51e98bb6212ad96d9c11b848df9dcad25b3f1b61
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 5%

---


# 在外部信号活动中声明参数 {#declaring-the-parameters-in-the-external-signal-activity}

使用参数调用工作流的第一步是在活动中声明这 **[!UICONTROL External signal]** 些参数。

1. Open the **[!UICONTROL External signal]** activity, then select the **[!UICONTROL Parameters]** tab.
1. 单击按 **[!UICONTROL Create element]** 钮，然后指定每个参数的名称和类型。

   >[!CAUTION]
   >
   >确保参数的名称和数量与调用工作流时定义的参数相同(请参 [](../../automating/using/defining-parameters-calling-workflow.md)阅)。 此外，参数类型必须与期望值一致。

   ![](assets/extsignal_declaringparameters_1.png)

1. 声明参数后，完成工作流配置，然后运行它。
