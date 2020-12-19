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


# 在外部信号活动{#declaring-the-parameters-in-the-external-signal-activity}中声明参数

使用参数调用工作流的第一步是在&#x200B;**[!UICONTROL External signal]**&#x200B;活动中声明它们。

1. 打开&#x200B;**[!UICONTROL External signal]**&#x200B;活动，然后选择&#x200B;**[!UICONTROL Parameters]**&#x200B;选项卡。
1. 单击&#x200B;**[!UICONTROL Create element]**&#x200B;按钮，然后指定每个参数的名称和类型。

   >[!CAUTION]
   >
   >确保参数的名称和数量与调用工作流时定义的参数相同（请参阅[此页](../../automating/using/defining-parameters-calling-workflow.md)）。 此外，参数类型必须与期望值一致。

   ![](assets/extsignal_declaringparameters_1.png)

1. 声明参数后，完成工作流配置，然后运行它。
