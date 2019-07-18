---
title: 消息仪表板
seo-title: 消息仪表板
description: 消息仪表板
seo-description: 发现信息仪表板由操作栏和各种功能块组成的功能。
page-status-flag: 从未激活
uuid: 9bb44ee8-2cf6-43ce-94a4-367f4e469713
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: 关于通信通道
discoiquuid: 90a78742-697f-46da-8c54-108048e57b67
context-tags: 交付，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Message dashboard{#message-dashboard}

消息仪表板是由不同图标组成的工作区，该工作区重新嵌入到操作栏中以及各种功能块中，它们允许您建立消息的参数并发送。下文介绍这些元素。

![](assets/delivery_dashboard_2.png)

## Gray bar {#gray-bar}

灰条将重新排列链接到您的消息的各种图标。

* **[!UICONTROL Summary]**：显示/隐藏有关消息的主要信息。
* **[!UICONTROL Edit properties]**：允许您编辑消息的高级参数。
* **[!UICONTROL Reports]**：使您能够访问与消息相关的报告。

**相关主题：**

* [配置渠道](../../administration/using/about-channel-configuration.md)
* [访问报告](../../reporting/using/about-dynamic-reports.md)

## Action bar {#action-bar}

操作栏具有允许您与消息交互的不同图标。

![](assets/delivery_dashboard_4.png)

根据设置的参数和进度，某些图标可能不可用。

* **[!UICONTROL Show proofs]**：显示/隐藏已发送的校样列表(如果存在)。仅在您发送校样后才启用此按钮。

   For more on proofs, see [Managing test profiles and sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md).

* **[!UICONTROL Send a test]**：允许您选择要使用的批准模式： **[!UICONTROL Email rendering]**&#x200B;或 **[!UICONTROL Proof]** 同时用于电子邮件。For more on test profiles, see [Sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).

   只有在您已建立测试配置文件后，才启用此按钮。

   >[!NOTE]
   >
   >For an SMS message, there is no other choice: it is automatically a **[!UICONTROL Proof]**.

* **[!UICONTROL Prepare send]**：开始准备发送。**[!UICONTROL Deployment]** 将显示该块并显示准备结果。此按钮仅在输入目标后才显示。您可以随时使用相应的按钮停止准备。

   For more on message preparation, [Preparing the send](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**：确认发送消息。The sending statistics appear in the **[!UICONTROL Deployment]** block. 此按钮仅在准备好发送之后才显示。You can stop or pause the send at any time using the **Stop send** and **[!UICONTROL Pause]** buttons.

   For more on confirming sending, see [Sending messages](../../sending/using/confirming-the-send.md).

## Blocks {#blocks}

主屏幕由不同的块构成。在块内单击以访问相应的参数屏幕：

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**：允许您跟踪消息准备或发送进度。单击此块右下方的按钮可访问发送和分析日志。此块仅在准备好发送后才会显示。有关更多信息，请访问。See [Confirming send](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**：允许您建立消息的主目标以及测试配置文件。See [Creating audiences](../../audiences/using/creating-audiences.md).
* **[!UICONTROL Schedule]**：允许您指定消息发送的日期。See [Scheduling](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**：允许您定义消息的内容并进行预览。See [Defining content](../../designing/using/designing-content-in-adobe-campaign.md).

