---
title: 分叉
description: “分叉”活动允许您创建出站过渡以同时启动多个活动。
page-status-flag: 从未激活
uuid: e4eaf69b-84ee-4f79-8b80-99284697cd2c
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 执行活动
discoiquuid: f8ffe7af-e18c-4599-8fd0-fcd192565323
context-tags: 叉，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 分叉{#fork}

## 说明 {#description}

![](assets/fork.png)

该 **[!UICONTROL Fork]** 活动允许您创建出站过渡以同时启动多个活动。

## 使用环境 {#context-of-use}

该活 **[!UICONTROL Fork]** 动允许您在同一工作流中独立地执行多个不同的活动。

## 配置 {#configuration}

1. 将活动拖放 **[!UICONTROL Fork]** 到工作流中。
1. 将其连接到它前面的其他活动，如查询。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。
1. 通过创建、删除或复制出站过渡来指定其数量。 您还可以为其添加名称和标签。
1. 确认活动的配置并保存工作流。

## Example {#example}

以下示例展示了两个查询活动的交集，这两个查询活动的目标是Adobe Campaign数据库中的档案（本例中为巴黎妇女）。 因此，分叉活动允许您同时使用多个活动：一个是使受众能够记住计算出的人群，另一个是细分人群以发送两个不同的电子邮件，其中每个区段都有目标内容。 第一封邮件发给18至40岁的巴黎女性，另一封则针对40岁以上的巴黎女性。

![](assets/wkf_fork_example.png)

