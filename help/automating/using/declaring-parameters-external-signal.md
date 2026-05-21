---
title: 声明外部信号活动中的参数
description: 本节详细介绍如何使用外部参数调用工作流。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: e6148b40-f608-4aab-81f6-756608c6828e
TQID: https://experienceleague.adobe.com/au0xUZ7C8m3hiK9wbm3QBiHd9RtpZQW-AEoc-SvnhfE
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 110
ht-degree: 0%

---

# 声明外部信号活动中的参数 {#declaring-the-parameters-in-the-external-signal-activity}

使用参数调用工作流的第一个步骤是在&#x200B;**[!UICONTROL External signal]**&#x200B;活动中声明它们。

1. 打开&#x200B;**[!UICONTROL External signal]**&#x200B;活动，然后选择&#x200B;**[!UICONTROL Parameters]**&#x200B;选项卡。
1. 单击&#x200B;**[!UICONTROL Create element]**&#x200B;按钮，然后指定每个参数的名称和类型。

   >[!CAUTION]
   >
   >确保参数的名称和数量与调用工作流时定义的参数相同（请参阅[此页面](../../automating/using/defining-parameters-calling-workflow.md)）。 此外，参数的类型必须与预期值一致。

   ![](assets/extsignal_declaringparameters_1.png)

1. 声明参数后，请完成工作流配置，然后运行它。
