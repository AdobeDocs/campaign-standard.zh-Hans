---
title: 管理测试用户档案
description: 了解如何管理测试用户档案。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: Profiles
role: User
level: Intermediate
exl-id: 56ece9da-18ec-4d27-a637-c22709a5e6aa
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 94%

---

# 管理测试用户档案 {#managing-test-profiles}

## 关于测试用户档案 {#about-test-profiles}

利用测试用户档案可定向不符合所规定定向标准的其他收件人。可以将测试用户档案添加到消息的受众，以检测收件人数据库是否用于任何欺诈行为，或确保电子邮件送达收件箱中。

![](assets/do-not-localize/how-to-video.png) [通过观看视频了解此功能](#video)

您可以通过高级菜单 **[!UICONTROL Profiles & audiences > Test profiles]** 管理测试用户档案。

测试用户档案包含虚构的联系信息或由发送者控制的联系信息，这些信息随后将被用在以下上下文的消息中：

* 用于发送&#x200B;**校样**：校样是一种特定的消息，用于在将最终消息投放到收件人之前对消息进行测试。校样测试用户档案负责检查投放的内容和格式。请参阅[发送校样](../../sending/using/sending-proofs.md)。
* 用于&#x200B;**电子邮件渲染**：电子邮件渲染测试用户档案用于检查在收件人的收件箱中显示消息的方式。例如，Web 邮件、消息服务、手机等。请参阅[电子邮件渲染](../../sending/using/email-rendering.md)。

  **电子邮件渲染**&#x200B;仅以只读状态提供使用。用于此用途的测试用户档案，仅可用在 Adobe Campaign 中。

* 作为&#x200B;**陷阱**：消息看起来像是发送给主目标，其实是发送到测试用户档案。请参阅[使用陷阱](../../sending/using/using-traps.md)。
* 用于&#x200B;**预览**&#x200B;消息：在预览消息以测试个性化元素时，可以选择测试用户档案。请参阅[预览消息](/help/sending/using/previewing-messages.md)。

![](assets/test_profile.png)

## 创建测试用户档案 {#creating-test-profiles}

1. 从高级菜单中，通过 Adobe Campaign 徽标，选择 **Profiles &amp; audiences > Test profiles**，以访问测试用户档案的列表。

   ![](assets/test_profile_creation_1.png)

1. 在 **[!UICONTROL Test profiles]** 仪表板中，单击 **Create**。

   ![](assets/test_profile_creation_2.png)

1. 输入此用户档案的数据。

   ![](assets/test_profile_creation_3.png)

1. 选择测试用户档案的预期用途。

   ![](assets/test_profile_creation_4.png)

1. 根据需要输入联系渠道 **[!UICONTROL Email, Telephone, Mobile, Mobile app]** 以及测试用户档案地址。

   >[!NOTE]
   >
   >您可以定义偏好的电子邮件格式：**[!UICONTROL Text]** 或 **[!UICONTROL HTML]**。

1. 如果要使用此测试用户档案测试事务型消息的个性化情况，请指定此事件的事件类型和数据。
1. 单击 **[!UICONTROL Create]** 以保存测试用户档案。

该测试用户档案随后将添加到用户档案的列表。

## 编辑测试用户档案 {#editing-test-profiles}

要编辑测试用户档案并查阅与其链接的数据，或对其进行修改，请执行以下步骤：

1. 单击想要编辑之测试用户档案的图像，以选择该测试用户档案。
1. 查阅或修改其字段。

   ![](assets/test_profile_edit.png)

1. 单击 **[!UICONTROL Save]**（如果已输入更改），或选择测试用户档案的名称，然后在屏幕顶部选择 **[!UICONTROL Test profiles]** 以返回测试用户档案仪表板。

## 教程视频 {#video}

本视频说明如何创建测试用户档案。

>[!VIDEO](https://video.tv.adobe.com/v/328367?quality=12&captions=chi_hans)

[此处](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hans)提供了其他Campaign Standard操作方法视频。
