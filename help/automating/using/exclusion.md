---
title: 排除
description: 排除活动允许您根据特定标准从一个人群中排除元素。
page-status-flag: 从未激活
uuid: b79e7f73-37a0-4ec3-ac5a-5449dc1b1f22
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 定位活动
discoiquuid: d5312fcd-43ad-428e-bde9-90f062e9358c
context-tags: 排除，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 排除{#exclusion}

## 说明 {#description}

![](assets/exclusion.png)

该活 **[!UICONTROL Exclusion]** 动允许您根据特定标准从一个人群中排除元素。

## 使用环境 {#context-of-use}

该活 **[!UICONTROL Exclusion]** 动主要用于对入站转移人群进行额外的过滤。

在入站过渡中定义主集。 其他入站过渡的成员将从主集合中排除。 排除活动的出站过渡只包含其他入站过渡中未遇到的主集的成员。

## 配置 {#configuration}

1. 将活动拖放 **[!UICONTROL Exclusion]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。
1. 从入站 **[!UICONTROL Primary set]** 过渡中选择。 这是从中排除元素的集合。 其他集合在从主集合中排除之前匹配元素。

   >[!NOTE]
   >
   >入站过渡必须包含相同类型的人口。 例如，如果主集包含测试配置文件，则其他过渡还必须包含测试配置文件。

1. 如果需要，可以管理活动的“过 [渡](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) ”以访问出站人群的高级选项。
1. 确认活动的配置并保存工作流。

## Example {#example}

以下示例显示了两个查询活动，这些查询活动被配置为从Adobe Campaign数据库中筛选18到27岁之间且电子邮件地址无效的配置文件。 随后，具有无效电子邮件地址的配置文件将从第一个集中排除。 这允许您随后发送电子邮件，例如。

![](assets/wkf_exclusion_example.png)

