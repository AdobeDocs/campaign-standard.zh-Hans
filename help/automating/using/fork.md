---
title: 分叉
description: 利用分叉活动，可创建叫客过渡以同时开始多个活动。
page-status-flag: never-activated
uuid: e4eaf69b-84ee-4f79-8b80-99284697cd2c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: f8ffe7af-e18c-4599-8fd0-fcd192565323
context-tags: fork,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 分叉{#fork}

## 说明{#description}

![](assets/fork.png)

利用 **[!UICONTROL Fork]** 活动，可创建叫客过渡以同时开始多个活动。

## 使用环境{#context-of-use}

利用 **[!UICONTROL Fork]** 活动，可在同一工作流中独立地执行多个不同的活动。

## 配置{#configuration}

1. 将 **[!UICONTROL Fork]** 活动拖放到工作流中。
1. 将其连接至其前方的其他活动，例如查询。
1. 选择活动，然后使用所显示快捷操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。
1. 通过创建、删除或复制叫客过渡来指定其数量。您还可以为其添加名称和标签属性。
1. 确认活动的配置并保存工作流。

## 示例{#example}

下方的示例展示了用于 Adobe Campaign 数据库中目标用户档案的两个查询的交集，在本例中，目标是居住在巴黎的女士。因此，利用交叉活动可同时使用多个活动：一个用于保存受众以记住计算出的群体，另一个用于细分群体以发送两封不同的电子邮件，从而为各个区段提供不同的内容。第一封邮件发给 18 至 40 岁的巴黎女士，另一封邮件发给 40 岁以上的巴黎女士。

![](assets/wkf_fork_example.png)

