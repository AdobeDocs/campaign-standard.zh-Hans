---
solution: Campaign Standard
product: campaign
title: 等待
description: “等待”活动可暂停执行部分工作流。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: wait,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 100%

---


# 等待{#wait}

## 说明{#description}

![](assets/wait.png)

**[!UICONTROL Wait]** 活动可暂停执行部分工作流。利用此活动，可以在延迟一段时间后（范围从几秒钟到几个月）再激活叫客过渡，即执行后续活动。

## 使用环境{#context-of-use}

**[!UICONTROL Wait]** 活动可为两个执行的活动之间添加一段等待的时间。例如，在执行电子邮件投放活动后，等待几天，再分析这期间产生的打开次数和点击次数，然后再执行所有后续操作（提醒电子邮件、创建受众等）。

## 配置{#configuration}

1. 将 **[!UICONTROL Wait]** 活动拖放到工作流中。
1. 选择活动，然后使用所显示快捷操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。
1. 指定激活活动的集客过渡和叫客过渡之间需要等待的时间，即 **[!UICONTROL Duration]**。

   您可以手动输入持续时间，也可使用字段中提供的选择器。

   ![](assets/wait_duration.png)

1. 确认活动的配置并保存工作流。

## 示例{#example}

下方的示例展示了典型使用案例中的 **[!UICONTROL Wait]** 活动。发送某个活动的电子邮件邀请。邮件发送 24 小时后，分析电子邮件投放日志，并向收到第一封邮件但未注册的人发送提醒电子邮件。

其工作流如下所示：

![](assets/wait_example_workflow.png)

* 第一个 **[!UICONTROL Query]** 确定要接收电子邮件邀请的用户档案。
* **[!UICONTROL Email delivery]** 首次向选定的用户档案发送邀请。
* 发送邀请后，进行 24 小时的 **[!UICONTROL Wait]** 活动，然后再继续进行工作流。
* 第二个 **[!UICONTROL Query]** 确定收到第一封电子邮件但未单击其内部订阅链接的用户档案。
* **[!UICONTROL Email delivery]** 第二次向选定的用户档案发送邀请提醒。

