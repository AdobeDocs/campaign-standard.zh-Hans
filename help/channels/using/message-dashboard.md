---
title: 消息功能板
seo-title: 消息功能板
description: 消息功能板
seo-description: 了解消息功能板由哪些部分组成，包括操作栏和各种功能块。
page-status-flag: 从未激活
uuid: 9bb44ee8-2cf6-43ce-94a4-367f4e469713
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 频道
content-type: 参考
topic-tags: 关于通信通道
discoiquuid: 90a78742-697f-46da-8c54-108048e57b67
context-tags: 交付，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aa52fcca887c9423476a1bc0160d340f255b9ac8

---


# 消息功能板{#message-dashboard}

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

   有关校样的详细信息，请参 [阅管理测试配置文件和发送校样](../../sending/using/managing-test-profiles-and-sending-proofs.md)。

* **[!UICONTROL Send a test]**:允许您选择要使用的批准模式：或 **[!UICONTROL Email rendering]**&#x200B;两者 **[!UICONTROL Proof]** 兼有。 有关测试配置文件的详细信息，请参 [阅发送校样](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs)。

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
* **[!UICONTROL Content]**:允许您定义消息的内容并预览该消息。 请参 [阅发送消息的关键步骤](../../channels/using/key-steps-to-send-a-message.md)。

