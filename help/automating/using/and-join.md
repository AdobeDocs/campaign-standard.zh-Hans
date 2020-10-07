---
title: AND-连接
description: 利用 AND-连接活动，可同步工作流的多个执行分支。
page-status-flag: never-activated
uuid: 9b54fd4c-9915-400f-a494-74e52c329b8a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 4b55efa2-652e-4493-bfa7-eaee59b383ca
context-tags: andjoin,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# AND-连接{#and-join}

## 说明{#description}

![](assets/and_join.png)

利用 **[!UICONTROL AND-join]** 活动，可同步工作流的多个执行分支。

## 使用环境{#context-of-use}

一旦激活所有集客过渡，换言之，一旦完成所有先行工作，**[!UICONTROL AND-join]** 活动就会触发其所有叫客过渡。

## 配置{#configuration}

1. 将多个活动（例如查询）拖放到您的工作流中，以至少形成两个不同的执行分支。
1. 将 **[!UICONTROL AND-join]** 活动拖放到工作流中。
1. 将其连接到要同步的两个不同分支之后。
1. 选择活动，然后使用所显示快捷操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。
1. 选择要保留在叫客过渡中的主集。如果不选择任何集，则会从活动发送随机群体。
1. 确认活动的配置并保存工作流。

## 示例{#example}

下方的示例显示了在使用 **[!UICONTROL AND-join]** 活动连接之前的两个工作流分支。只有在启用了 **[!UICONTROL AND-join]** 活动的三个集客过渡后，才能进行文件提取活动。

![](assets/wkf_and-join_example.png)

