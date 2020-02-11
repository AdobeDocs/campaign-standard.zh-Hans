---
title: 发送校样
description: 了解如何发送校样。
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ff9d0c3ca42606f097a34b1835d285541061e57b

---


# 发送校样 {#sending-proofs}

证明是一条特定消息，允许您在将消息发送到主目标之前测试该消息。

证明的收件人负责批准邮件（其内容和表单）。 测试配置文件中定 **义了这些**。 有关此方面的详细信息，请参阅 [管理测试配置文件](../../audiences/using/managing-test-profiles.md)。

为了发送证明，测试配置文件必须包含在邮件的受众中。

在消息中：

1. Click the **[!UICONTROL Send a test]** button.

   ![](assets/bat_select.png)

1. 选择要使用的校样类型：

   * **[!UICONTROL Email rendering]**:选择此选项可根据目标收件箱测试接收消息的方式。 有关详细信息，请参阅电子 [邮件渲染](../../sending/using/email-rendering.md)。
   * **[!UICONTROL Proof]**:选择此选项可在将消息发送到主目标之前测试该消息。 证明接收方负责通过检查其内容和格式来批准交付。
   * **[!UICONTROL Proof + Email rendering]**:此选项组合了前两个选项。
   ![](assets/bat_select1.png)

1. 确认您的选择。

   校样被发送到测试配置文件。

   ![](assets/bat_select2.png)

1. 您可以使用下拉列表查 **[!UICONTROL Proofs]** 看校样。

   ![](assets/bat_view.png)

1. 选择一个证明以访问其摘要。 对于电子邮件，如果您选择了“电 **子邮件渲染****[!UICONTROL Access email rendering]** ”选项作为校样类型，则校样标签的右侧将显示该图标。 请参阅 [电子邮件渲染](../../sending/using/email-rendering.md)。

   ![](assets/bat_view2.png)

根据收到证明的人员的评论，可能会要求您修改交付内容。 进行修改后，您必须重新开始准备电子邮件，然后重新发送证明。 每个新的证明都可以使用按钮 **[!UICONTROL Show proofs]** 访问。

在完成交付内容之前，您必须发送所需数量的校样。 完成此操作后，您可以将交付发送到主目标并关闭审批周期。

**相关主题：**

[发送测试、准备和发送电子邮件视频](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/sending-test-preparing-sending-email.html)
