---
title: 创建配置文件
seo-title: 创建配置文件
description: 创建配置文件
seo-description: 了解如何使用API、导入功能、在线获取、自动或手动更新创建档案并收集联系人数据。
page-status-flag: 从未激活
uuid: a5f5a58a-e798-400f-8648-05dc843 d5557
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 受众
content-type: reference
topic-tags: 管理配置文件
discoiquuid: ab8a984-f898-4fff-ad8 c-ed8 f95362 f96
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: f883986392f6b739832093e0473591aa39dfcbfe

---


# Creating profiles{#creating-profiles}

在Adobe Campaign中，默认情况下使用配置文件来定义消息的主要目标。

要在Campaign中创建或更新配置文件，您可以：

* [通过工作流从文件导入配置文件列表](https://helpx.adobe.com/campaign/kt/acs/using/acs-importing-profiles-feature-video-using.html)
* Collect data online, via [landing pages](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_CreateLandingPage.html)
* Create bulk via [REST API](http://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)
* Synchronize profiles from [Microsoft Dynamics](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html)
* 使用图形界面屏幕输入数据，如下所述

例如，要在用户界面中直接创建新配置文件，请按照以下步骤操作：

1. From the Adobe Campaign home page, click the **Customer Profiles** card or the **Profiles** tab to access the list of profiles.

   ![](assets/profile_creation_1.png)

1. **[!UICONTROL Create]**&#x200B;然后单击。

   ![](assets/profile_creation.png)

1. 输入配置文件数据。

   ![](assets/profile_creation1.png)

   * The contact information, such as first name, last name, gender, date of birth, photo, preferred language (for [multilingual emails](../../channels/using/creating-a-multilingual-email.md)) helps better personalize deliveries.
   * The profile's **[!UICONTROL Time zone]** is used to send deliveries at the profile's time zone. For more on this, refer to this [section](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).
   * **[!UICONTROL Channels]** 该类别包含电子邮件地址、移动电话号码、选择退出信息，可让您了解配置文件可重用的频道。
   * **[!UICONTROL No longer contact]** 配置文件将在配置文件取消订阅渠道后更新。
   * **[!UICONTROL Address]** 该类别包含需要填写的邮政地址以及将 **[!UICONTROL Address specified]**[直邮](../../channels/using/about-direct-mail.md) 发送到此配置文件的选项。If the **[!UICONTROL Address specified]** option is not checked, this profile will be excluded from every direct mail delivery.
   * **[!UICONTROL Access authorization]** 该类别指示配置文件的组织单位(用于 [管理权限](../../administration/using/about-access-management.md))。See also [Partitioning profiles](../../administration/using/organizational-units.md#partitioning-profiles).
   * **[!UICONTROL Traceability]** 该类别会自动更新与创建或修改配置文件的用户相关的信息。

1. Click **[!UICONTROL Create]** to save the profile.

配置文件现在将显示在列表中。

>[!NOTE]
>
>也可以使用Adobe Campaign Standard API创建配置文件。For more on this, refer to the [dedicated documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#creating-profiles) .

配置文件也可以根据其组织单位划分。To add the organizational fields to your profiles, refer to the [Partitioning profiles](../../administration/using/organizational-units.md#partitioning-profiles) section.

>[!NOTE]
>
>首选语言字段用于在发送多语言消息时选择语言。For more information about the multilingual messages [refer to this page](../../channels/using/creating-a-multilingual-email.md).

**相关主题：**

* [创建登陆页面](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_CreateLandingPage.html) 分步指南
* [导入配置文件](https://helpx.adobe.com/campaign/kt/acs/using/acs-importing-profiles-feature-video-using.html)

