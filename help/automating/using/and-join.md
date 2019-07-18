---
title: 并加入
seo-title: 并加入
description: 并加入
seo-description: 通过与加入活动，您可以同步工作流的多个执行分支。
page-status-flag: 从未激活
uuid: 9b54fd4c-9915-400f-a494-74e52 c329 b8 a
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 执行活动
discoiquuid: 4b55efa2-652e-4493-bfa7-eaee59 b383 ca
context-tags: and join，main
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# AND-join{#and-join}

## Description {#description}

![](assets/and_join.png)

**[!UICONTROL AND-join]** 活动允许您同步工作流的多个执行分支。

## Context of use {#context-of-use}

**[!UICONTROL AND-join]** 在所有的入站过渡都已完成后，活动只会触发其出站过渡，也就是说，所有以前的活动都已完成。

## Configuration {#configuration}

1. 将多个活动等多个活动拖放到工作流程中，以形成至少两个不同的执行分支。
1. Drag and drop an **[!UICONTROL AND-join]** activity into your workflow.
1. 将其连接到您要同步的两个不同分支之后。
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. 选择要保留在出站过渡中的主集合。如果您未选择任何设置，将从活动中随机发送人群。
1. 确认活动的配置并保存工作流。

## Example {#example}

The following example shows two workflow branches before they are joined with the **[!UICONTROL AND-join]** activity. File extraction can only take place when the three inbound transitions of the **[!UICONTROL AND-join]** activity are enabled.

![](assets/wkf_and-join_example.png)

