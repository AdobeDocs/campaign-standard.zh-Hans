---
title: 创建用户档案
description: 了解如何创建用户档案并收集联系人的数据，使用API、导入功能、在线获取、自动或手动更新。
page-status-flag: never-activated
uuid: a5f5a58a-e798-400f-8648-05dc843d5557
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: 4ab8a984-f898-4fff-ad8c-ed8f95362f96
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 816d550d8bd0de085a47f97c1f6cc2fbb5e7acb9
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 1%

---


# 创建用户档案{#creating-profiles}

在Adobe Campaign中，默认情况下使用用户档案来定义消息的主目标。

要在活动中创建或更新用户档案，您可以：

* 通过工作流从文件导入用户档案 [列表](../../automating/using/importing-data.md#example--import-workflow-template)
* 通过登陆页在线收集数 [据](../../channels/using/getting-started-with-landing-pages.md)
* 通过REST API批量 [创建](../../api/using/get-started-apis.md)
* 同步Microsoft Dynamics [中的用户档案](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* 使用图形界面屏幕输入数据，如下所述

例如，要直接在用户界面中创建新用户档案，请执行以下步骤：

1. 在Adobe Campaign主页中，单 **击客户** 用户档案卡 **或** 用户档案选项卡，访问用户档案列表。

   ![](assets/profile_creation_1.png)

1. 然后单击 **[!UICONTROL Create]**。

   ![](assets/profile_creation.png)

1. 输入用户档案数据。

   ![](assets/profile_creation1.png)

   * 联系信息，如名字、姓氏、性别、出生日期、照片、首选语言(针对多语言电子邮件 [)等](../../channels/using/creating-a-multilingual-email.md)，有助于更好地个性化投放。
   * 用户档案 **[!UICONTROL Time zone]** 用于在用户档案时区发送投放。 For more on this, refer to this [section](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).
   * 该 **[!UICONTROL Channels]** 类别包含电子邮件地址、手机号码和退出信息，可让您知道用户档案可以访问的渠道。
   * 一 **[!UICONTROL No longer contact]** 旦类别取消订阅渠道，该用户档案即更新。
   * 该 **[!UICONTROL Address]** 类别包含需要填写的邮政地址以及向此用户档案发 **[!UICONTROL Address specified]** 送直邮 [的](../../channels/using/about-direct-mail.md) 选项。 如果未 **[!UICONTROL Address specified]** 选中此选项，则此用户档案将从每个直邮投放中排除。
   * 类别 **[!UICONTROL Access authorization]** 指示用户档案的组织单位(用于管 [理权限](../../administration/using/about-access-management.md))。 另请参阅 [分区用户档案](../../administration/using/organizational-units.md#partitioning-profiles)。
   * 类别 **[!UICONTROL Traceability]** 会自动更新与创建或修改用户档案的用户相关的信息。

1. 单击 **[!UICONTROL Create]** 以保存用户档案。

用户档案现在将显示在列表中。

>[!NOTE]
>
>用户档案创建也可以使用Adobe Campaign标准API。 有关此内容的详细信息，请参阅专 [用文档](../../api/using/creating-profiles.md)。

用户档案还可以根据其组织单位进行分区。 要向用户档案添加组织字段，请参阅“分区 [用户档案](../../administration/using/organizational-units.md#partitioning-profiles) ”部分。

>[!NOTE]
>
>首选语言字段用于在发送多语言消息时选择语言。 有关多语言消息的详 [细信息，请参阅本页](../../channels/using/creating-a-multilingual-email.md)。

**相关主题：**

* [关于登陆页](../../channels/using/getting-started-with-landing-pages.md) 、分步指南
* [导入用户档案](https://video.tv.adobe.com/v/24993?captions=chi_hans) 视频
