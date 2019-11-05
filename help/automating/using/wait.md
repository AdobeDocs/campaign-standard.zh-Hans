---
title: 等待
description: “等待”活动会暂时暂停执行工作流的一部分。
page-status-flag: 从未激活
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 执行活动
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: 等，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 等待{#wait}

## 说明 {#description}

![](assets/wait.png)

该活 **[!UICONTROL Wait]** 动暂时暂停执行工作流的一部分。 它在延迟（可能介于几秒到几个月之间）后激活其出站过渡，以执行随后进行的活动。

## 使用环境 {#context-of-use}

该 **[!UICONTROL Wait]** 活动用于允许在执行的两个活动之间经过一段时间。 例如，要在电子邮件发送活动后等待数天，请在执行任何后续操作（提醒电子邮件、创建受众等）之前分析此期间生成的打开次数和点击次数。

## 配置 {#configuration}

1. 将活动拖放 **[!UICONTROL Wait]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。
1. 指定 **[!UICONTROL Duration]** 活动的入站和出站转换激活后的等待时间。

   您可以手动输入持续时间或使用字段中可用的选择器。

   ![](assets/wait_duration.png)

1. 确认活动的配置并保存工作流。

## Example {#example}

以下示例说明了 **[!UICONTROL Wait]** 典型用例中的活动。 会发送活动的电子邮件邀请。 发送电子邮件24小时后，将分析电子邮件发送日志，并向收到第一封电子邮件但未注册的用户发送提醒电子邮件。

该工作流如下所示：

![](assets/wait_example_workflow.png)

* 第一个 **[!UICONTROL Query]** 目标是将通过电子邮件邀请发送的配置文件。
* 首次 **[!UICONTROL Email delivery]** 将邀请发送到选定的配置文件。
* 24 **[!UICONTROL Wait]** 小时的活动会在发送邀请的时间与工作流的其余部分之间暂停。
* 第二个 **[!UICONTROL Query]** 目标是收到第一封电子邮件但未点击内部订阅链接的配置文件。
* 第二个 **[!UICONTROL Email delivery]** 用户向所选用户发送邀请提醒。

