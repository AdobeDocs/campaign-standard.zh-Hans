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
source-git-commit: 663ce734a79d7895e1e5cbd6d5756447d42299fd

---


# Managing test profiles and sending proofs{#managing-test-profiles-and-sending-proofs}

## About test profiles {#about-test-profiles}

测试配置文件允许您定位与定义的定位条件不匹配的其他收件人。将它们添加到消息的受众以检测收件人数据库的任何欺骗性使用或确保电子邮件送达收件箱。

You can manage your test profiles from the advanced menu **[!UICONTROL Profiles & audiences > Test profiles]**.

测试配置文件包含虚构的联系信息或由发送者控制的联系信息，随后可以在以下上下文中将其用于消息：

* For sending **Proofs**: the Proof is a specific message used to check the message before sending the finalized delivery to recipients. 校样测试配置文件负责检查交付内容及其内容和格式。See [Sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).
* **对于电子邮件渲染**：电子邮件渲染测试配置文件用于检查接收消息收件箱中显示消息的方式。例如，webmail、message service、mobile等。See [Email rendering](../../sending/using/email-rendering.md).

   **电子邮件渲染** 使用是只读的。只有Adobe Campaign中提供的测试配置文件才可用。

* As a **Trap**: the message is sent to the test profile just as it is sent to the main target, as a means to identify whether your client file is being used fraudulently.
* **要预览** 消息，请执行以下操作：预览消息以测试个性化元素时，可以选择测试配置文件。

![](assets/test_profile.png)

## Managing test profiles {#managing-test-profiles}

### Creating test profiles {#creating-test-profiles}

1. From the advanced menu, via the Adobe Campaign logo, select **Profiles &amp; audiences &gt; Test profiles** to access the list of test profiles.

   ![](assets/test_profile_creation_1.png)

1. From the **[!UICONTROL Test profiles]** dashboard, click **Create**.

   ![](assets/test_profile_creation_2.png)

1. 输入此配置文件的数据。

   ![](assets/test_profile_creation_3.png)

1. 选择用于测试配置文件的用途。

   ![](assets/test_profile_creation_4.png)

1. Enter the contact channels **[!UICONTROL Email, Telephone, Mobile, Mobile app]**, as well as the test profile address if necessary.

   >[!NOTE]
   >
   >You can define a preferred email format: **[!UICONTROL Text]** or **[!UICONTROL HTML]**.

1. 如果要使用此测试配置文件测试交易消息的个性化，请指定事件类型和此事件的数据。
1. Click **[!UICONTROL Create]** to save the test profile.

测试配置文件随后将添加到配置文件列表中。

**相关主题：**

[创建测试配置文件](https://helpx.adobe.com/campaign/kt/acs/using/acs-test-profiles-feature-video-use.html) 视频

### Editing test profiles {#editing-test-profiles}

要编辑测试配置文件，请参考链接到的数据，或对其进行修改：

1. 单击其图像，选择要编辑的测试配置文件。
1. 查阅或修改字段。

   ![](assets/test_profile_edit.png)

1. Click **[!UICONTROL Save]** if you have entered your changes, or select the name of the test profile then **[!UICONTROL Test profiles]** in the section at the top of the screen to go back to the test profiles dashboard.

## Sending proofs {#sending-proofs}

证据是一条特定消息，允许您先测试消息，然后再将其发送到主目标。

证据收件人负责批准消息(其内容和表单)。They are defined in the **Test profiles**. For more on this, see [Managing test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles).

要发送证据，必须将测试配置文件包含在邮件的受众中。

在消息中：

1. Click the **[!UICONTROL Send a test]** button.

   ![](assets/bat_select.png)

1. 选择要使用的校样类型：

   * **[!UICONTROL Email rendering]**：选择此选项可测试根据目标收件箱接收消息的方式。For more information, refer to [Email rendering](../../sending/using/email-rendering.md).
   * **[!UICONTROL Proof]**：选择此选项可在发送到主目标之前测试消息。校样收件人负责批准交付内容及其格式和格式。
   * **[!UICONTROL Proof + Email rendering]**：此选项组合了前两个选项。
   ![](assets/bat_select1.png)

1. 确认您的选择。

   校样会发送到测试配置文件。

   ![](assets/bat_select2.png)

1. You can view your proofs using the **[!UICONTROL Proofs]** drop-down list.

   ![](assets/bat_view.png)

1. 选择一个证明以访问其摘要。For an email, if you have selected the **Email rendering** option as the proof type, the **[!UICONTROL Access email rendering]** icon is displayed on the right of the proof label. See [Email rendering](../../sending/using/email-rendering.md).

   ![](assets/bat_view2.png)

根据收到证据的人员的注释，可能会要求您修改分发内容。完成修改后，您必须重新开始电子邮件准备，然后再发送证据。Each new proof can be accessed using the **[!UICONTROL Show proofs]** button.

在完成交付内容之前，您必须根据需要发送尽可能多的校样。完成此操作后，您可以将分发发送到主目标并关闭审批周期。

**相关主题：**

[发送测试、准备和发送电子邮件](https://helpx.adobe.com/campaign/kt/acs/using/acs-sending-test-preparing-sending-email-feature-video-use.html) 视频

## Sending proofs using additional data {#sending-proofs-using-additional-data}

本节介绍如何使用通过工作流访问的真实客户数据发送校样，而不是使用假冒测试配置文件数据。这样，您就可以检查工作流中使用的变量是否准确无误，并获取收件人收到的消息的视图。

1. Create a test profile and enable **[!UICONTROL Proof]** and **[!UICONTROL Trap]** as the intended usage. For more on this, see [Managing test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles).

   此测试配置文件将成为目标受众的一部分。

   >[!NOTE]
   >
   >在使用测试配置文件作为陷印时，对于消息中的任何丰富字段，相应的额外数据会随机从真实目标配置文件中选取并分配给陷印测试配置文件。

1. 访问营销活动列表并创建测试工作流程。

   See [Creating a workflow](../../automating/using/building-a-workflow.md#creating-a-workflow).

1. Drag and drop a **[!UICONTROL Query]** activity into your workflow and open it.

   The Query activity is presented in the [Query](../../automating/using/query.md) section.

1. 从链接的表中添加其他数据。For more on this, see [Enriching data](../../automating/using/query.md#enriching-data).

1. Drag and drop an **Email delivery** activity into your workflow and open it.

   The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.

1. 从电子邮件消息控制板中，选择您创建的具有陷印使用情况的测试配置文件。

1. 使用您在查询活动中定义的附加数据，添加到电子邮件内容个性化字段。

1. 保存电子邮件并启动工作流。

在消息准备过程中，目标计数包括您选择的测试配置文件。
发送消息后，其他数据将由实际配置文件中的数据替换。

>[!NOTE]
>
>只替换其他数据。测试配置文件不会使用任何真实的配置文件数据，如名字或姓氏。
