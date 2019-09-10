---
title: 管理测试配置文件和发送校样
seo-title: 管理测试配置文件和发送校样
description: 管理测试配置文件和发送校样
seo-description: 了解如何管理测试配置文件和校样。
page-status-flag: 从未激活
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 发送
content-type: reference
topic-tags: 准备和测试消息
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember，概述
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 27447db9ee0dd387c39976c7bd4e157a4b7899b8

---


# 管理测试配置文件和发送校样{#managing-test-profiles-and-sending-proofs}

## 关于测试配置文件 {#about-test-profiles}

测试配置文件允许您定位与定义的定位条件不匹配的其他收件人。将它们添加到消息的受众以检测收件人数据库的任何欺骗性使用或确保电子邮件送达收件箱。

您可以从高级菜单管理测试配置文件 **[!UICONTROL Profiles & audiences > Test profiles]**。

测试配置文件包含虚构的联系信息或由发送者控制的联系信息，随后可以在以下上下文中将其用于消息：

* 用于发送 **校样**：“校样”是一条特定消息，用于在向收件人发送已完成的交付之前检查消息。校样测试配置文件负责检查交付内容及其内容和格式。请参阅 [发送校样](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs)。
* **对于电子邮件渲染**：电子邮件渲染测试配置文件用于检查接收消息收件箱中显示消息的方式。例如，webmail、message service、mobile等。请参阅 [电子邮件渲染](../../sending/using/email-rendering.md)。

   **电子邮件渲染** 使用是只读的。只有Adobe Campaign中提供的测试配置文件才可用。

* 作为 **陷印**：消息会发送到测试配置文件，就像发送到主目标一样。请参阅 [使用陷印](../../sending/using/managing-test-profiles-and-sending-proofs.md#using-traps)。
* **要预览** 消息，请执行以下操作：预览消息以测试个性化元素时，可以选择测试配置文件。请参阅 [预览消息](/help/sending/using/previewing-messages.md)。

![](assets/test_profile.png)

## 管理测试配置文件 {#managing-test-profiles}

### 创建测试配置文件 {#creating-test-profiles}

1. 在高级菜单中，通过Adobe Campaign徽标选择 **配置文件和受众&gt;测试配置文件** 以访问测试配置文件列表。

   ![](assets/test_profile_creation_1.png)

1. 在 **[!UICONTROL Test profiles]** 仪表板中，单击 **创建**。

   ![](assets/test_profile_creation_2.png)

1. 输入此配置文件的数据。

   ![](assets/test_profile_creation_3.png)

1. 选择用于测试配置文件的用途。

   ![](assets/test_profile_creation_4.png)

1. 输入联系渠道 **[!UICONTROL Email, Telephone, Mobile, Mobile app]**，并根据需要输入测试配置文件地址。

   >[!NOTE]
   >
   >您可以定义首选电子邮件格式： **[!UICONTROL Text]****[!UICONTROL HTML]**&#x200B;或.

1. 如果要使用此测试配置文件测试交易消息的个性化，请指定事件类型和此事件的数据。
1. 单击 **[!UICONTROL Create]** 以保存测试配置文件。

测试配置文件随后将添加到配置文件列表中。

**相关主题：**

[创建测试配置文件](https://helpx.adobe.com/campaign/kt/acs/using/acs-test-profiles-feature-video-use.html) 视频

### 编辑测试配置文件 {#editing-test-profiles}

要编辑测试配置文件，请参考链接到的数据，或对其进行修改：

1. 单击其图像，选择要编辑的测试配置文件。
1. 查阅或修改字段。

   ![](assets/test_profile_edit.png)

1. 如果 **[!UICONTROL Save]** 您已输入更改，请单击，或者在屏幕顶部的部分中选择 **[!UICONTROL Test profiles]** 测试配置文件的名称，返回测试配置文件仪表板。

## 发送校样 {#sending-proofs}

证据是一条特定消息，允许您先测试消息，然后再将其发送到主目标。

证据收件人负责批准消息(其内容和表单)。它们在 **测试配置文件**&#x200B;中定义。有关此操作的详细信息，请参阅 [管理测试配置文件](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles)。

要发送证据，必须将测试配置文件包含在邮件的受众中。

在消息中：

1. 单击 **[!UICONTROL Send a test]** 按钮。

   ![](assets/bat_select.png)

1. 选择要使用的校样类型：

   * **[!UICONTROL Email rendering]**：选择此选项可测试根据目标收件箱接收消息的方式。有关详细信息，请参阅 [电子邮件渲染](../../sending/using/email-rendering.md)。
   * **[!UICONTROL Proof]**：选择此选项可在发送到主目标之前测试消息。校样收件人负责批准交付内容及其格式和格式。
   * **[!UICONTROL Proof + Email rendering]**：此选项组合了前两个选项。
   ![](assets/bat_select1.png)

1. 确认您的选择。

   校样会发送到测试配置文件。

   ![](assets/bat_select2.png)

1. 您可以使用 **[!UICONTROL Proofs]** 下拉列表查看校样。

   ![](assets/bat_view.png)

1. 选择一个证明以访问其摘要。对于电子邮件，如果您选择 **了电子邮件渲染** 选项作为校样类型， **[!UICONTROL Access email rendering]** 则图标会显示在校样标签的右侧。请参阅 [电子邮件渲染](../../sending/using/email-rendering.md)。

   ![](assets/bat_view2.png)

根据收到证据的人员的注释，可能会要求您修改分发内容。完成修改后，您必须重新开始电子邮件准备，然后再发送证据。可以 **[!UICONTROL Show proofs]** 使用按钮访问每个新的校样。

在完成交付内容之前，您必须根据需要发送尽可能多的校样。完成此操作后，您可以将分发发送到主目标并关闭审批周期。

**相关主题：**

[发送测试、准备和发送电子邮件](https://helpx.adobe.com/campaign/kt/acs/using/acs-sending-test-preparing-sending-email-feature-video-use.html) 视频

## 使用陷印 {#using-traps}

使用陷印时，消息会发送到测试配置文件，就像发送到主目标一样，这是一种识别客户端文件是否被欺骗性使用的方法。

陷印最初设计为直接发送邮件。它们允许您：
* 确认您的直邮提供商真的发送了通信。
* 以与客户相同的条件同时接收邮件。
* 保留发送的邮件的精确副本。
* 检查您的客户列表是否不被您的直接邮件提供商滥用。事实上，如果任何其他通信都发送到您的测试配置文件地址，您的客户端文件可能在不知情的情况下使用。因此，测试配置文件的地址应仅用于此目的。

有关向直接邮件受众添加陷印的更多信息，请参阅 [添加测试和陷印配置文件](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)。

对于其他通信渠道，您可以将陷印测试配置文件添加到主目标，以便：
* 检查消息是否成功发送。
* 获取并保留消息的精确副本。
* 跟踪发送和接收的时间。

要将测试配置文件用作陷印，必须将该配置文件包含在邮件的受众中。

>[!NOTE]
>
>与用于 [校样](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) 或 [电子邮件渲染](../../sending/using/email-rendering.md)的测试配置文件不同，该消息会同时发送到主目标和用作陷印的测试配置文件。

定义消息的受众时：

1. 从 **[!UICONTROL Test profiles]** 选项卡中，选择测试配置文件。确保它具有 **[!UICONTROL Trap]** 预期用途。

   ![](assets/trap_select.png)

1. 消息内容准备就绪后，单击 **[!UICONTROL Prepare]** 按钮。请参阅 [准备发送](../../sending/using/preparing-the-send.md)。
   >[!NOTE]
   >
   >确保选择了主目标。否则，不能发送您的消息。

1. 单击 **[!UICONTROL Confirm]** 按钮。请参阅 [确认发送](../../sending/using/confirming-the-send.md)。

   ![](assets/trap_confirm.png)

消息将发送到主目标和测试配置文件。

>[!NOTE]
>
>在使用测试配置文件作为陷印时，对于消息中的任何丰富字段，相应的额外数据会随机从真实目标配置文件中选取并分配给陷印测试配置文件。有关丰富的更多信息，请参阅 [此示例](../../automating/using/enrichment.md#example--enriching-profile-data-with-data-contained-in-a-file)。
