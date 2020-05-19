---
title: 排除
description: “排除”活动允许您根据特定标准从一个人群中排除元素。
page-status-flag: never-activated
uuid: b79e7f73-37a0-4ec3-ac5a-5449dc1b1f22
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: d5312fcd-43ad-428e-bde9-90f062e9358c
context-tags: exclusion,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---


# 排除{#exclusion}

## 说明 {#description}

![](assets/exclusion.png)

该 **[!UICONTROL Exclusion]** 活动允许您根据特定标准从一个种群中排除元素。

## 使用环境 {#context-of-use}

该 **[!UICONTROL Exclusion]** 活动主要用于对入站过渡群进行额外过滤。

主集在入站过渡中定义。 其他入站过渡的成员将从主集中排除。 排除过渡的出站活动只包含其他入站过渡中未遇到的主集成员。

## 配置 {#configuration}

1. 将活动拖放 **[!UICONTROL Exclusion]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。
1. 从入站 **[!UICONTROL Primary set]** 过渡中选择。 这是从中排除元素的集合。 其他集合在从主集合中排除之前匹配元素。

   >[!NOTE]
   >
   >入站过渡必须包含相同类型的人口。 例如，如果主集包含测试用户档案，则其他过渡还必须包含测试用户档案。

1. 如果需要，可以管理活动 [的过渡](../../automating/using/activity-properties.md) ，以访问出站人口的高级选项。
1. 确认活动的配置并保存工作流。

## Example {#example}

以下示例显示了两个查询活动，配置为从Adobe Campaign库筛选年龄在18到27岁之间且电子邮件地址无效的用户档案。 具有无效电子邮件地址的用户档案随后将从第一组中排除。 这允许您随后发送电子邮件。

![](assets/wkf_exclusion_example.png)

