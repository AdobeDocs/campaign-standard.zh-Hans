---
title: 管理测试配置文件和发送校样
seo-title: 管理测试配置文件和发送校样
description: 管理测试配置文件和发送校样
seo-description: 了解如何管理测试配置文件和校样。
page-status-flag: 从未激活
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 发送
content-type: 参考
topic-tags: 准备和测试消息
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember，概述
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# 管理测试配置文件和发送校样{#managing-test-profiles-and-sending-proofs}

## 关于测试配置文件 {#about-test-profiles}

测试配置文件允许您定位不符合定义的定位标准的其他收件人。 它们会添加到消息的受众中，以检测对收件人数据库的任何欺骗性使用，或确保电子邮件会到达收件箱中。

您可以从高级菜单管理测试配置文件 **[!UICONTROL Profiles & audiences > Test profiles]**。

测试配置文件包含由发送者控制的虚假联系信息或联系信息，这些信息随后可用于以下上下文中的消息：

* 用于发送 **校样**:证明是用于在向收件人发送最终交付之前检查消息的特定消息。 Proof测试配置文件负责检查分发的内容和格式。 请参阅 [发送校样](#sending-proofs)。
* 对于电 **子邮件渲染**:电子邮件呈现测试配置文件用于检查根据接收消息的收件箱显示消息的方式。 例如，Web邮件、消息服务、移动等。 请参阅 [电子邮件渲染](../../sending/using/email-rendering.md)。

   电子 **邮件渲染** ，使用是只读的。 使用此功能的测试配置文件仅在Adobe Campaign中现成可用。

* 作为陷 **阱**:消息将发送到测试配置文件，就像发送到主目标一样。 请参阅 [使用陷印](#using-traps)。
* 要预览 **消息** ，请执行以下操作：在预览消息以测试个性化元素时，可以选择测试配置文件。 请参阅 [预览消息](/help/sending/using/previewing-messages.md)。

![](assets/test_profile.png)

## 管理测试配置文件 {#managing-test-profiles}

### 创建测试配置文件 {#creating-test-profiles}

1. 从高级菜单中，通过Adobe Campaign徽标，选择“配置文件和受众”&gt;“ **测试配置文件** ”以访问测试配置文件列表。

   ![](assets/test_profile_creation_1.png)

1. 在功能板 **[!UICONTROL Test profiles]** 中，单击“ **创建**”。

   ![](assets/test_profile_creation_2.png)

1. 输入此配置文件的数据。

   ![](assets/test_profile_creation_3.png)

1. 选择要用于测试配置文件的用途。

   ![](assets/test_profile_creation_4.png)

1. 根据需要输 **[!UICONTROL Email, Telephone, Mobile, Mobile app]**&#x200B;入联系渠道和测试配置文件地址。

   >[!NOTE]
   >
   >您可以定义首选电子邮件格式：或 **[!UICONTROL Text]** 者 **[!UICONTROL HTML]**。

1. 如果要使用此测试配置文件测试交易消息的个性化，请指定事件类型和此事件的数据。
1. 单击 **[!UICONTROL Create]** 以保存测试配置文件。

测试配置文件随后将添加到配置文件列表中。

**相关主题：**

[创建测试配置文件](https://helpx.adobe.com/campaign/kt/acs/using/acs-test-profiles-feature-video-use.html) 视频

### 编辑测试配置文件 {#editing-test-profiles}

要编辑测试配置文件并查阅与其关联的数据，或要修改它，请执行以下操作：

1. 单击要编辑的测试配置文件的图像，以选择该配置文件。
1. 请查阅或修改字段。

   ![](assets/test_profile_edit.png)

1. 单 **[!UICONTROL Save]****[!UICONTROL Test profiles]** 击（如果已输入更改），或选择测试配置文件的名称，然后在屏幕顶部的部分中返回至测试配置文件功能板。

## 发送校样 {#sending-proofs}

证明是一条特定消息，允许您在将消息发送到主目标之前测试该消息。

证明的收件人负责批准邮件（其内容和表单）。 测试配置文件中定 **义了这些**。 有关此方面的详细信息，请参阅 [管理测试配置文件](#managing-test-profiles)。

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

[发送测试、准备和发送电子邮件视频](https://helpx.adobe.com/campaign/kt/acs/using/acs-sending-test-preparing-sending-email-feature-video-use.html)

## 使用陷印 {#using-traps}

使用陷阱时，消息将像发送到主目标一样发送到测试配置文件，作为确定客户端文件是否被欺骗使用的手段。

陷阱最初设计用于直接邮寄。 它们允许您：
* 验证您的直邮提供商是否确实在发送通信。
* 在与客户相同的条件下同时接收邮件。
* 保留已发送的邮件的精确副本。
* 检查您的直邮提供商是否未滥用您的客户列表。 事实上，如果将任何其他通信发送到您的测试配置文件的地址，您的客户端文件可能在您不知情的情况下被使用。 因此，测试配置文件的地址只能用于此目的。

有关向直邮受众添加陷印的详细信息，请参阅添 [加测试和陷印配置文件](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)。

对于其他通信渠道，您可以向主目标添加陷印测试配置文件，以便：
* 检查您的消息是否已成功发送。
* 获取并保留消息的精确副本。
* 跟踪发送和接收时间。

要将测试配置文件用作陷阱，它必须包含在消息的受众中。

>[!NOTE]
>
>与用于校样或电子邮 [件渲染](#sending-proofs)[的测试配置文件不同](../../sending/using/email-rendering.md)，消息将同时发送到主目标和用作陷阱的测试配置文件。

定义消息的受众时：

1. 从选项卡 **[!UICONTROL Test profiles]** 中，选择测试配置文件。 确保其已作 **[!UICONTROL Trap]** 为预期用途。

   ![](assets/trap_select.png)

1. 消息内容准备就绪后，单击该 **[!UICONTROL Prepare]** 按钮。 请参 [阅准备发送](../../sending/using/preparing-the-send.md)。
   >[!NOTE]
   >
   >确保选择了主目标。 否则，将无法发送您的消息。

1. Click the **[!UICONTROL Confirm]** button. 请参 [阅确认发送](../../sending/using/confirming-the-send.md)。

   ![](assets/trap_confirm.png)

消息将发送到主目标和测试配置文件。

>[!NOTE]
>
>当使用测试配置文件作为陷印时，对于消息中的任何富集字段，从实际目标配置文件随机选取相应的附加数据并分配给陷印测试配置文件。 有关丰富化的更多信息，请参 [阅此示例](../../automating/using/enrichment.md#example--enriching-profile-data-with-data-contained-in-a-file)。
