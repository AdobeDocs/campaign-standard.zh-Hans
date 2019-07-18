---
title: 分叉
seo-title: 分叉
description: 分叉
seo-description: 分叉活动允许您创建出站过渡，以同时开始多个活动。
page-status-flag: 从未激活
uuid: e4eAF69b-84ee-4f79-8b80-9928497cd2c
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 执行活动
discoiquuid: f8ffe7af-e18 c-4599-8fd0-fcd192563523
context-tags: 分叉，主
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Fork{#fork}

## Description {#description}

![](assets/fork.png)

**[!UICONTROL Fork]** 活动允许您创建出站过渡，以同时开始多个活动。

## Context of use {#context-of-use}

**[!UICONTROL Fork]** 活动允许您在同一工作流程内独立执行多个不同的活动。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Fork]** activity into your workflow.
1. 将其连接到之前的其他活动，如查询。
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. 通过创建、删除或复制出站过渡来指定出站过渡的数量。您还可以对其属性和标签进行属性设置。
1. 确认活动的配置并保存工作流。

## Example {#example}

以下示例展示了两个针对Adobe Campaign数据库中的配置文件的查询活动的十字路口，该活动在巴黎的女性居住在巴黎。因此，分叉活动允许您同时使用多个活动：一种是保存受众以记住计算的人群，另一个则是将受众细分，以向每个细分发送具有针对性内容的两封不同电子邮件。第一封电子邮件发送给18到40岁之间的Pariasis女性，另一封发送给40岁以上的Parias女士。

![](assets/wkf_fork_example.png)

