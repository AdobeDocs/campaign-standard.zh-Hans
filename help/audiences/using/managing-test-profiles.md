---
title: 管理测试配置文件
description: 了解如何管理测试配置文件。
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
source-git-commit: 767d4233236019213003961aae1abb317198e581

---


# 管理测试配置文件 {#managing-test-profiles}

## 关于测试配置文件 {#about-test-profiles}

测试配置文件允许您定位不符合定义的定位标准的其他收件人。 它们会添加到消息的受众中，以检测对收件人数据库的任何欺骗性使用，或确保电子邮件会到达收件箱中。

您可以从高级菜单管理测试配置文件 **[!UICONTROL Profiles & audiences > Test profiles]**。

测试配置文件包含由发送者控制的虚假联系信息或联系信息，这些信息随后可用于以下上下文中的消息：

* 用于发送 **校样**:证明是用于在将最终交付发送给收件人之前检查消息的特定消息。 Proof测试配置文件负责检查交付内容和格式。 请参阅 [发送校样](../../sending/using/sending-proofs.md)。
* 对于电 **子邮件渲染**:电子邮件呈现测试配置文件用于检查根据接收消息的收件箱显示消息的方式。 例如，Web邮件、消息服务、移动等。 请参阅 [电子邮件渲染](../../sending/using/email-rendering.md)。

   电 **子邮件呈现** 使用为只读。 使用此功能的测试配置文件仅在Adobe Campaign中现成可用。

* 作为陷 **阱**:消息将发送到测试配置文件，就像发送到主目标一样。 请参阅 [使用陷印](../../sending/using/using-traps.md)。
* 要预览 **消息** ，请执行以下操作：在预览消息以测试个性化元素时，可以选择测试配置文件。 请参阅 [预览消息](/help/sending/using/previewing-messages.md)。

![](assets/test_profile.png)

## 创建测试配置文件 {#creating-test-profiles}

1. 从高级菜单中，通过Adobe Campaign徽标，选择“配置文件和受众”>“ **测试配置文件** ”以访问测试配置文件列表。

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

[创建测试配置文件](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/test-profiles.html) 视频

## 编辑测试配置文件 {#editing-test-profiles}

要编辑测试配置文件并查阅与其关联的数据，或要修改它，请执行以下操作：

1. 单击要编辑的测试配置文件的图像，以选择该配置文件。
1. 请查阅或修改字段。

   ![](assets/test_profile_edit.png)

1. 单 **[!UICONTROL Save]** 击（如果已输入更改），或选择测试配置文件的名称，然后在屏幕顶部的部分中 **[!UICONTROL Test profiles]** ，返回至测试配置文件功能板。
