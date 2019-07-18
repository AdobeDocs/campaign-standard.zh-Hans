---
title: 等待等
seo-title: 等待等
description: 等待等
seo-description: 等待活动暂时挂起执行工作流的一部分。
page-status-flag: 从未激活
uuid: 396a3de1-6ffa-4385-ac9 f-15fdeae5 a366
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 执行活动
discoiquuid: 377821e6-69f8-41cc-a1 ad-8a2 f5 ed4 d409
context-tags: 等待，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Wait{#wait}

## Description {#description}

![](assets/wait.png)

**[!UICONTROL Wait]** 活动偶尔会暂停工作流的一部分。它将在延迟的延迟时间(可能从几秒到几个月)激活其出站过渡，该延迟可能会执行随后放置的活动。

## Context of use {#context-of-use}

**[!UICONTROL Wait]** 活动用于允许在执行两个活动之间传递特定的时间。例如，要在电子邮件交付活动之后等待几天，然后在执行任何后续操作(提醒电子邮件、创建受众等)之前分析在此期间生成的打开和点击。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Wait]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Specify the **[!UICONTROL Duration]** of the wait between when the inbound and outbound transitions of the activity are activated.

   您可以手动输入持续时间或使用字段中可用的选择器。

   ![](assets/wait_duration.png)

1. 确认活动的配置并保存工作流。

## Example {#example}

The following example illustrates the **[!UICONTROL Wait]** activity in a typical use case. 发送活动电子邮件邀请。发送后24小时，会分析电子邮件分发日志，并会向收到第一封电子邮件但未注册的人员发送提醒电子邮件。

此时将显示工作流：

![](assets/wait_example_workflow.png)

* A first **[!UICONTROL Query]** targets the profiles that will be sent the email invitation.
* An **[!UICONTROL Email delivery]** sends the invitation for the first time to the profiles selected.
* **[!UICONTROL Wait]** 24h的活动在发送邀请和工作流的其余部分之间暂停。
* A second **[!UICONTROL Query]** targets the profiles that received the first email but did not click on the subscription link inside.
* A second **[!UICONTROL Email delivery]** sends a reminder of the invitation to the people selected.

