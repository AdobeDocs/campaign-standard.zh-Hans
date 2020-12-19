---
solution: Campaign Standard
product: campaign
title: 消息仪表板
description: 发现消息仪表板由什么组成，包括操作栏和各种功能块。
audience: channels
content-type: reference
topic-tags: about-communication-channels
context-tags: delivery,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 4%

---


# 消息仪表板{#message-dashboard}

消息仪表板是由不同图标（重新分组为操作栏）和各种功能块组成的工作区，这些功能块允许您建立消息的参数并发送消息。 这些元素在下面介绍。

![](assets/delivery_dashboard_2.png)

## 灰色条{#gray-bar}

灰色栏会重新分组链接到消息的各种图标。

* **[!UICONTROL Summary]**:显示／隐藏有关消息的主要信息。
* **[!UICONTROL Edit properties]**:允许您编辑消息的高 [级参数](../../administration/using/configuring-email-channel.md#list-of-email-properties)。
* **[!UICONTROL Reports]**:允许您访问与消息相关的报告。

**相关主题：**

* [配置渠道](../../administration/using/about-channel-configuration.md)
* [访问报告](../../reporting/using/about-dynamic-reports.md)

## 操作栏{#action-bar}

操作栏具有不同的图标，允许您与消息进行交互。

![](assets/delivery_dashboard_4.png)

根据已设置的参数和完成的进度，某些图标可能不可用。

* **[!UICONTROL Show proofs]**:显示／隐藏已发送的验证的列表（如果存在）。此按钮仅在您发送验证后才启用。

   有关验证的详细信息，请参阅[发送验证](../../sending/using/sending-proofs.md)。

* **[!UICONTROL Send a test]**:允许您选择要使用的审批模式： **[!UICONTROL Email rendering]** （仅限电子邮件），或 **[!UICONTROL Proof]** 同时两者。有关测试用户档案的详细信息，请参阅[发送验证](../../sending/using/sending-proofs.md)。 仅在创建测试用户档案后，才启用此按钮。

* **[!UICONTROL Prepare send]**:开始准备发送。出现&#x200B;**[!UICONTROL Deployment]**&#x200B;块并显示准备结果。 此按钮仅在输入目标后才显示。 您可以随时使用相应的按钮停止准备。 有关消息准备的详细信息，请参阅[准备发送](../../sending/using/preparing-the-send.md)。

* **[!UICONTROL Confirm send]**:确认发送消息。发送统计信息显示在&#x200B;**[!UICONTROL Deployment]**&#x200B;块中。 此按钮仅在准备发送后显示。 您可以使用&#x200B;**停止发送**&#x200B;和&#x200B;**[!UICONTROL Pause]**&#x200B;按钮随时停止或暂停发送。 有关确认发送的详细信息，请参阅[发送消息](../../sending/using/confirming-the-send.md)。

## 块{#blocks}

主屏幕由不同的块组成。 在块内单击以访问相应的参数屏幕：

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**:允许您跟踪消息准备或发送的进度。单击此块右下部的按钮以访问发送和分析日志。 仅当准备发送后，才会显示此块。 更多关于此的信息。 请参阅[确认发送](../../sending/using/confirming-the-send.md)。
* **[!UICONTROL Audience]**:允许您建立消息的主目标和测试用户档案。请参阅[创建受众](../../audiences/using/creating-audiences.md)。
* **[!UICONTROL Schedule]**:允许您指定消息的发送日期。请参阅[计划](../../sending/using/about-scheduling-messages.md)。
* **[!UICONTROL Content]**:允许您定义消息的内容并对其进行预览。请参阅[发送消息](../../channels/using/key-steps-to-send-a-message.md)的关键步骤。

## 警告{#warnings}

在某些情况下，消息仪表板顶部的黄色横幅中可能会显示警告。

![](assets/delivery_dashboard_warnings.png)

以下是可显示的消息列表:

* *&quot;此电子邮件启用了SMTP测试模式选项：不会发送任何消息。”*

   有关更多信息，请参阅[此章节](../../administration/using/configuring-email-channel.md#smtp-test-mode)。

* *&quot;路由外部帐户已禁用。&quot;*

   有关详细信息，请参阅[外部帐户](../../administration/using/external-accounts.md)。

* *&quot;无法发送消息，因为当前IP关联不由任何发送进程处理。&quot;*

   如果您看到此消息，则在IP关联定义级别或发送进程级别存在问题。 与Adobe管理员联系。

* *“这是一个开箱即用的事务性消息模板。如果要修改它，必须重复它并处理副本。&quot;*

   其中一些现成事务性消息模板是内置登陆页模板。 有关更多信息，请参阅[此章节](../../channels/using/landing-page-templates.md)。

* *“这条消息是技术事务性消息模板。不能修改或发布它。&quot;*

   此警告以空事务性消息模板显示，但无法编辑。 有关事务性消息的详细信息，请参阅[此部分](../../channels/using/getting-started-with-transactional-msg.md)。
