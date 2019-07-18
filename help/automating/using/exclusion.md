---
title: 排除
seo-title: 排除
description: 排除
seo-description: 排除活动允许您根据某些条件排除一个人口中的元素。
page-status-flag: 从未激活
uuid: b79e7f73-37a0-4ec3-ac5 a-5449dc1 f f22
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 定位活动
discoiquuid: d5312fcd-43ad-428e-bde9-90f062 e9358 c
context-tags: 排除，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Exclusion{#exclusion}

## Description {#description}

![](assets/exclusion.png)

**[!UICONTROL Exclusion]** 活动允许您根据特定条件从一个人群排除元素。

## Context of use {#context-of-use}

**[!UICONTROL Exclusion]** 该活动主要用于对入站过渡人群进行额外过滤。

主要集合在入站过渡中定义。其他入站过渡的成员将从主要设置中排除。排除活动的出站过渡仅包含其他入站过渡中未遇到的主要设置的成员。

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Exclusion]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Primary set]** from the inbound transitions. 这是从中排除元素的设置。其他设置在将元素排除在主集合之前设置匹配元素。

   >[!NOTE]
   >
   >入站过渡必须包含相同类型的人群。例如，如果主集合包含测试配置文件，则其他过渡也必须包含测试配置文件。

1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.
1. 确认活动的配置并保存工作流。

## Example {#example}

以下示例显示了两个查询活动，它们配置为从Adobe Campaign数据库的18到27岁之间过滤配置文件，并且电子邮件地址无效。之后，将排除具有无效电子邮件地址的配置文件。这样，您就可以发送电子邮件等。

![](assets/wkf_exclusion_example.png)

