---
title: AND-连接
description: AND-join活动允许您同步工作流的多个执行分支。
page-status-flag: 从未激活
uuid: 9b54fd4c-9915-400f-a494-74e52c329b8a
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 执行活动
discoiquuid: 4b55efa2-652e-4493-bfa7-eae59b383ca
context-tags: andjoin, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# AND-连接{#and-join}

## 说明 {#description}

![](assets/and_join.png)

该活 **[!UICONTROL AND-join]** 动允许您同步工作流的多个执行分支。

## 使用环境 {#context-of-use}

活 **[!UICONTROL AND-join]** 动仅在激活所有入站过渡后触发其出站过渡，换言之，在所有前面的活动完成之后。

## 配置 {#configuration}

1. 将多个活动（如查询）放入您的工作流中，以至少形成两个不同的执行分支。
1. 将活动拖放 **[!UICONTROL AND-join]** 到工作流中。
1. 在要同步的两个不同的分支之后连接它。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。
1. 选择要在出站过渡中保留的主集。 如果不选择任何集，则会从活动中发送随机人群。
1. 确认活动的配置并保存工作流。

## Example {#example}

以下示例显示了两个工作流分支，然后再将其与活动结合 **[!UICONTROL AND-join]** 在一起。 只有在启用活动的三个入站过渡时，才能进行 **[!UICONTROL AND-join]** 文件提取。

![](assets/wkf_and-join_example.png)

