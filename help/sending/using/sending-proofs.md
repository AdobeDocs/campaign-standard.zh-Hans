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
source-git-commit: f7f90991ed4c7323e3a2f8ac7d38da9ff165ef76

---


# 发送校样 {#sending-proofs}

## 关于校样 {#about-proofs}

证明是一条特定消息，允许您在将消息发送到主目标之前测试该消息。 证明的收件人负责批准邮件（其内容和表单）。

有两种类型的证明收件人：

* **测试配置文件** ，允许您定位不符合定义的定位标准的其他收件人。

   可以将其添加到消息的受众中，以检测对收件人数据库的任何欺骗性使用，或确保电子邮件送达收件箱中。 有关此方面的详细信息，请参阅 [管理测试配置文件](../../audiences/using/managing-test-profiles.md)。

   >[!NOTE]
   >
   >为了发送证明，测试配置文件必须包含在邮件的受众中。

* **替换配置文件** ，允许您将自己置于某个目标配置文件的位置，并获得配置文件将收到的消息的精确表示形式。 有关此方面的详细信息，请参阅 [使用目标配置文件测试电子邮件](../../sending/using/testing-messages-using-target.md)。

   >[!NOTE]
   >
   >此功能仅适用于电子邮件渠道。

## 发送证明 {#sending-a-proof}

要发送校样，请按照以下步骤操作：

1. 确保已配置校样收件人：
   * **测试档案** ，必须包含在您消息的受众中。
   * **消息准备成功** 后，必须添加替代配置文件(请参 [阅本节](../../sending/using/testing-messages-using-target.md))。

1. Click the **[!UICONTROL Send a test]** button.

   ![](assets/bat_select.png)

1. 选择要使用的校样类型：

   * **[!UICONTROL Email rendering]**:选择此选项可根据目标收件箱测试接收消息的方式。 有关详细信息，请参阅电子 [邮件渲染](../../sending/using/email-rendering.md)。
   * **[!UICONTROL Proof]**:选择此选项可在将消息发送到主目标之前测试该消息。 证明接收方负责通过检查其内容和格式来批准交付。
   * **[!UICONTROL Proof + Email rendering]**:此选项组合了前两个选项。
   ![](assets/bat_select1.png)

   >[!NOTE]
   >
   >电子邮件渲染仅适用于测试配置文件。 如果消息中未添加测试配置文件，则只 **[!UICONTROL Proof]** 有选项可供选择。

1. 确认您的选择。

   校样将发送给已配置的收件人。

   ![](assets/bat_select2.png)

1. 您可以使用下拉列表查 **[!UICONTROL Proofs]** 看校样。

   ![](assets/bat_view.png)

1. 选择一个证明以访问其摘要。 对于电子邮件，如果您选择了“电 **子邮件渲染****[!UICONTROL Access email rendering]** ”选项作为校样类型，则校样标签的右侧将显示该图标。 请参阅 [电子邮件渲染](../../sending/using/email-rendering.md)。

   ![](assets/bat_view2.png)

根据收到证明的人员的评论，可能会要求您修改交付内容。 进行修改后，您必须重新开始准备电子邮件，然后重新发送证明。 每个新的证明都可以使用按钮 **[!UICONTROL Show proofs]** 访问。

在完成交付内容之前，您必须发送所需数量的校样。 完成此操作后，您可以将交付发送到主目标并关闭审批周期。

## 配置校样的主题行 {#configuring-proofs-subject-line}

当发送证明时，其主题行默认配置有“ **Proof”** 前缀，以及表示证明编号的计数器。

![](assets/proof-prefix.png)

要更改要使用的默认主题行，请执行以下步骤：

1. 在消息功能板中，单击按 **[!UICONTROL Open properties]** 钮。
1. 在部 **[!UICONTROL Advanced parameters]** 分中，定义要在主题行中默认使用的前缀。

要在主题行中隐藏证明编号，请激活选 **[!UICONTROL Hide proof prefix counter]** 项。

>[!NOTE]
>
>如果要隐藏整个证明前缀，请将该字段留 **[!UICONTROL Subject line prefix]** 空。

![](assets/proof-prefix-configuration.png)

1. 单击 **[!UICONTROL Confirm]**. 默认情况下，设置将应用于为选定消息发送的所有校样。

**相关主题：**

* [发送测试、准备和发送电子邮件视频](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/sending-test-preparing-sending-email.html)
* [使用目标配置文件测试电子邮件](../../sending/using/testing-messages-using-target.md)。
* [管理测试配置文件](../../audiences/using/managing-test-profiles.md)。
* [预览消息](../../sending/using/previewing-messages.md)
* [配置电子邮件渠道](../../administration/using/configuring-email-channel.md)
