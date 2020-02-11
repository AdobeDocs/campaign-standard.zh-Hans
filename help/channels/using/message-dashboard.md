---
title: 消息仪表板
description: 了解消息功能板由哪些部分组成，包括操作栏和各种功能块。
page-status-flag: never-activated
uuid: 9bb44ee8-2cf6-43ce-94a4-367f4e469713
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: about-communication-channels
discoiquuid: 90a78742-697f-46da-8c54-108048e57b67
context-tags: delivery,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705

---


# 消息仪表板{#message-dashboard}

消息功能板是由不同图标（重新分组为操作栏）和各种功能块组成的工作区，这些功能块允许您建立消息的参数并发送消息。 这些元素如下所示。

![](assets/delivery_dashboard_2.png)

## 灰条 {#gray-bar}

灰色栏会重新分组与消息链接的各种图标。

* **[!UICONTROL Summary]**:显示／隐藏有关消息的主要信息。
* **[!UICONTROL Edit properties]**:允许您编辑消息的高 [级参数](../../administration/using/configuring-email-channel.md#list-of-email-properties)。
* **[!UICONTROL Reports]**:允许您访问与消息相关的报告。

**相关主题：**

* [配置渠道](../../administration/using/about-channel-configuration.md)
* [访问报告](../../reporting/using/about-dynamic-reports.md)

## 操作栏 {#action-bar}

操作栏具有不同的图标，允许您与消息交互。

![](assets/delivery_dashboard_4.png)

根据已设置的参数和完成的进度，某些图标可能不可用。

* **[!UICONTROL Show proofs]**:显示／隐藏已发送的校样列表（如果存在）。 仅在您发送校样后，才启用此按钮。

   有关校样的详细信息，请参阅 [发送校样](../../sending/using/sending-proofs.md)。

* **[!UICONTROL Send a test]**:允许您选择要使用的批准模式：或 **[!UICONTROL Email rendering]**&#x200B;两者 **[!UICONTROL Proof]** 兼有。 有关测试配置文件的详细信息，请参 [阅发送校样](../../sending/using/sending-proofs.md)。

   仅在您建立测试配置文件后，才启用此按钮。

   >[!NOTE]
   >
   >对于SMS消息，别无选择：它自动成为 **[!UICONTROL Proof]**。

* **[!UICONTROL Prepare send]**:开始准备发送。 出现 **[!UICONTROL Deployment]** 该块并显示准备结果。 此按钮仅在输入目标后才显示。 您可以随时使用相应的按钮停止准备。

   有关消息准备的详细信 [息，请准备发送](../../sending/using/preparing-the-send.md)。

* **[!UICONTROL Confirm send]**:确认发送消息。 发送统计信息显示在块 **[!UICONTROL Deployment]** 中。 此按钮仅在准备发送后显示。 您可以使用“停止发送”和“停止发送”按钮随 **时停止** 或暂停 **[!UICONTROL Pause]** 发送。

   有关确认发送的详细信息，请参阅 [发送消息](../../sending/using/confirming-the-send.md)。

## 块 {#blocks}

主屏幕由不同的块组成。 在块内单击以访问相应的参数屏幕：

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**:允许您跟踪消息准备或发送的进度。 单击此块右下角的按钮可访问发送和分析日志。 此块仅在准备发送后显示。 有关详情。 请参阅 [确认发送](../../sending/using/confirming-the-send.md)。
* **[!UICONTROL Audience]**:允许您建立消息的主目标以及测试配置文件。 请参阅 [创建受众](../../audiences/using/creating-audiences.md)。
* **[!UICONTROL Schedule]**:允许您指定消息的发送日期。 请参 [阅计划](../../sending/using/about-scheduling-messages.md)。
* **[!UICONTROL Content]**:允许您定义消息的内容并预览该消息。 See [Key steps to send a message](../../channels/using/key-steps-to-send-a-message.md).

## 警告 {#warnings}

在某些情况下，消息功能板顶部的黄色横幅中可能会显示警告。

![](assets/delivery_dashboard_warnings.png)

以下是可显示的消息列表：

* *“此电子邮件启用了SMTP测试模式选项：不会发送任何消息。”*

   For more on this, see [this section](../../administration/using/configuring-email-channel.md#smtp-test-mode).

* *“已禁用路由外部帐户。”*

   有关此问题的详细信息，请参 [阅外部帐户](../../administration/using/external-accounts.md)。

* *“无法发送消息，因为当前IP关联不由任何发送进程处理。”*

   如果您看到此消息，则在IP关联定义级别或发送进程级别会出现问题。 联系您的Adobe管理员。

* *“此交易消息是现成的交易消息模板。 如果要修改它，您必须复制它并处理副本。”*

   其中一些现成的事务性消息模板是内置的登录页面模板。 For more on this, see [this section](../../channels/using/landing-page-templates.md).

* *“此消息是一个技术性的交易消息模板。 您不能修改或发布它。”*

   此警告显示在不可编辑的空事务性消息模板中。 有关事务性消息的详细信息，请参 [阅此部分](../../channels/using/about-transactional-messaging.md)。
