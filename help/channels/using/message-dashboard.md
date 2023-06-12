---
title: 消息仪表板
description: 了解消息仪表板由哪些部分组成，包括操作栏和各种功能块。
audience: channels
content-type: reference
topic-tags: about-communication-channels
context-tags: delivery,main
feature: Overview
role: User
level: Beginner
exl-id: 886aae39-2029-471c-b4d1-c6ca57d0e568
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 4%

---

# 消息仪表板{#message-dashboard}

消息仪表板是一个工作区，它由不同的图标（重组为操作栏）和各种功能块组成，允许您建立消息参数并将其发送。 这些要素将在下文介绍。

![](assets/delivery_dashboard_2.png)

## 灰色条 {#gray-bar}

灰色条可重组链接到消息的各种图标。

* **[!UICONTROL Summary]**：显示/隐藏有关消息的主要信息。
* **[!UICONTROL Edit properties]**：用于编辑消息的 [高级参数](../../administration/using/configuring-email-channel.md#list-of-email-properties).
* **[!UICONTROL Reports]**：用于访问与消息相关的报表。

**相关主题：**

* [配置渠道](../../administration/using/about-channel-configuration.md)
* [访问报告](../../reporting/using/about-dynamic-reports.md)

## 操作栏 {#action-bar}

利用操作栏中的不同图标，可与消息交互。

![](assets/delivery_dashboard_4.png)

根据已设置的参数和进度，某些图标可能不可用。

* **[!UICONTROL Show proofs]**：显示/隐藏已发送的验证列表（如果存在）。 此按钮仅在您发送验证后启用。

   有关验证的更多信息，请参阅 [发送校样](../../sending/using/sending-proofs.md).

* **[!UICONTROL Send a test]**：用于选择要使用的审批模式： **[!UICONTROL Email rendering]** （仅限电子邮件）， **[!UICONTROL Proof]** 或两者兼而有之。 有关测试用户档案的更多信息，请参阅 [发送校样](../../sending/using/sending-proofs.md). 只有在创建测试配置文件后，才会启用此按钮。

* **[!UICONTROL Prepare send]**：开始准备发送。 此 **[!UICONTROL Deployment]** 块并显示准备结果。 此按钮仅在输入目标后显示。 您可以使用相应的按钮随时停止准备。 有关消息准备的更多信息，请参阅 [准备发送](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**：确认发送消息。 发送统计信息显示在 **[!UICONTROL Deployment]** 块。 此按钮仅在准备发送后显示。 您可以使用来随时停止或暂停发送 **停止发送** 和 **[!UICONTROL Pause]** 按钮。 有关确认发送的更多信息，请参阅 [发送消息](../../sending/using/confirming-the-send.md).

## 个块 {#blocks}

主屏幕由不同的块组成。 单击块内部可访问相应的参数屏幕：

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**：用于跟踪消息准备或发送的进度。 单击此块右下方的按钮可访问发送和分析日志。 此块仅在准备发送后显示。 了解更多信息。 参见 [确认发送](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**：用于建立消息的主要目标和测试用户档案。 请参阅[创建受众](../../audiences/using/creating-audiences.md)。
* **[!UICONTROL Schedule]**：用于指定发送消息的日期。 参见 [计划](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**：用于定义消息的内容并预览。 参见 [发送消息的关键步骤](../../channels/using/key-steps-to-send-a-message.md).

## 警告 {#warnings}

在某些情况下，警告可能会显示在消息仪表板顶部的黄色横幅中。

![](assets/delivery_dashboard_warnings.png)

以下是可以显示的消息列表：

* *“此电子邮件已启用SMTP测试模式选项：不会发送任何邮件。”*

   有关更多信息，请参阅[此章节](../../administration/using/configuring-email-channel.md#smtp-test-mode)。

* *“已禁用路由外部帐户。”*

   有关此内容的更多信息，请参阅 [外部帐户](../../administration/using/external-accounts.md).

* *“无法发送消息，因为任何发送进程均未处理当前IP关联。”*

   如果您看到此消息，则表示IP关联定义级别或发送进程级别存在问题。 请联系您的Adobe管理员。

* *“这是一个现成的事务型消息模板。 如果您要修改它，则必须复制它并制作副本。”*

   这些现成的事务性消息模板中有一些是内置的登陆页面模板。 有关更多信息，请参阅[此章节](../../channels/using/landing-page-templates.md)。

* *“此消息是技术事务型消息模板。 您无法对其进行修改或发布。”*

   此警告显示在不可编辑的空事务型消息模板中。 有关事务型消息的更多信息，请参阅 [本节](../../channels/using/getting-started-with-transactional-msg.md).
