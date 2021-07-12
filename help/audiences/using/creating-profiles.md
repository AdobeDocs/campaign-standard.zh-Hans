---
solution: Campaign Standard
product: campaign
title: 创建用户档案
description: 了解如何使用 API、导入功能、在线获取、自动或手动更新，创建用户档案并收集联系人的数据。
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: 用户档案
role: User
level: Beginner
exl-id: 827df9f6-070c-466a-890c-e363de6b129b
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 89%

---

# 创建用户档案{#creating-profiles}

Adobe Campaign 默认使用用户档案来定义消息的主目标。

>[!NOTE]
>
>也可以使用 Adobe Campaign Standard API 创建用户档案。有关更多信息，请参阅[专用文档](../../api/using/creating-profiles.md)。

![](assets/do-not-localize/how-to-video.png) [了解如何使用视频中的工作流导入用户档案](#video)

要在 Campaign 中创建或更新用户档案，您可以：

* 通过[工作流](../../automating/using/creating-import-workflow-templates.md)从文件导入用户档案列表
* 通过[登陆页面](../../channels/using/getting-started-with-landing-pages.md)在线收集数据
* 通过 [REST API](../../api/using/get-started-apis.md) 批量创建
* 同步来自 [Microsoft Dynamics](../../integrating/using/d365-acs-get-started.md) 的用户档案
* 使用图形界面屏幕输入数据，如下所述

例如，要直接在用户界面中创建新用户档案，请执行以下步骤：

1. 在 Adobe Campaign 主页中，单击 **Customer Profiles** 卡或 **Profiles** 选项卡，以访问用户档案列表。

   ![](assets/profile_creation_1.png)

1. 单击 **[!UICONTROL Create]**。

   ![](assets/profile_creation.png)

1. 输入用户档案数据。

   ![](assets/profile_creation1.png)

   * 联系信息，如名字、姓氏、性别、出生日期、照片、首选语言（用于[多语言电子邮件](../../channels/using/creating-a-multilingual-email.md)）等，有助于更好地个性化投放。
   * 用户档案的 **[!UICONTROL Time zone]** 用于以用户档案的时区确定投放发送时间。有关更多信息，请参阅此](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)章节[。
   * **[!UICONTROL Channels]** 类别包含电子邮件地址、手机号码和选择退出信息，可让您了解联系用户档案的渠道。
   * 一旦用户档案取消订阅了某个渠道，则会立即更新 **[!UICONTROL No longer contact]** 类别。
   * **[!UICONTROL Address]** 类别包含需要填写的邮政地址以及向此用户档案发送[直邮](../../channels/using/about-direct-mail.md)的 **[!UICONTROL Address specified]** 选项。如果未勾选 **[!UICONTROL Address specified]** 选项，则此用户档案将从所有直邮投放中排除。
   * **[!UICONTROL Access authorization]**&#x200B;类别指示用户档案的组织单位为[管理权限](../../administration/using/about-access-management.md)。 要向用户档案添加组织字段，请参阅[划分用户档案](../../administration/using/organizational-units.md#partitioning-profiles)一节。
   * **[!UICONTROL Traceability]** 类别会自动更新与创建或修改用户档案之用户相关的信息。

1. 单击 **[!UICONTROL Create]** 以保存用户档案。

现在，该用户档案会显示在列表中。

>[!NOTE]
>首选语言字段用于在发送多语言消息时选择语言。有关多语言消息的更多信息，[请参阅此页面](../../channels/using/creating-a-multilingual-email.md)。

## 教程视频 {#video}

此视频演示如何使用工作流导入用户档案。

>[!VIDEO](https://video.tv.adobe.com/v/24993?quality=12)

其他Campaign Standard操作方法视频可在[此处](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hans)获取。
