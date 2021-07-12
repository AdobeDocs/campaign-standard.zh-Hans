---
solution: Campaign Standard
product: campaign
title: 与Launch同步技术工作流常见问题解答
description: 有关Launch技术工作流的常见问题。
audience: administration
content-type: reference
topic-tags: users-and-security
feature: 实例设置
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 0%

---

# Adobe Launch Synchronization 常见问题解答 {#syncwithlaunch-faq}

您可以通过&#x200B;**[!UICONTROL Sync with Launch]**&#x200B;专用技术工作流将AdobeLaunch移动资产导入Adobe Campaign Standard。 有关更多信息，请参见此[页面](../../administration/using/technical-workflows.md)

以下部分列出了有关此同步的常见问题。

## 我在[!DNL Launch]中创建了属性（组织单元ALL的非管理员）。 我的应用程序在Adobe Campaign中处于“准备配置”状态，但无法打开/配置它。 {#configuring-property}

只有组织单位ALL的管理员才能在Adobe Campaign Standard中配置移动应用程序。 配置完毕后，只有分配的组织单位的用户才能编辑
应用程序。 有关组织单位的详细信息，请参阅此[页面](../../administration/using/organizational-units.md)。

## 我无法编辑在Adobe Campaign Standard中配置的移动应用程序，并且移动应用程序仅处于读模式。 {#read-mode-mobile-app}

在&#x200B;**[!UICONTROL Access Authorization]**&#x200B;部分中查看移动应用程序的组织单位。 只有分配的组织单位的用户才能编辑移动应用程序。

有关组织单位的详细信息，请参阅此[页面](../../administration/using/organizational-units.md)。

## 我是Adobe Campaign Standard中组织单位为ALL的管理员，但无法配置移动应用程序。 {#org-unit-mobile}

将组织单位设置为ALL的管理员应具有[!DNL Launch]中所有移动属性的权限，以配置移动应用程序。

有关组织单位的详细信息，请参阅此[页面](../../administration/using/organizational-units.md)。

## 我在[!DNL Launch]中创建了移动资产，但我的资产在Adobe Campaign Standard中不可见。 {#visibility-mobile-property}

1. 检查是否已在[!DNL Launch]的移动资产中安装Adobe Campaign Standard扩展。

1. 验证实例的端点是否在扩展中正确配置。

1. 检查“Launch_URL_Campaign”或“NmsServer_URL”是否正确。

1. 然后，使用&#x200B;**[!UICONTROL syncWithLaunch]**&#x200B;技术工作流检查[!DNL Launch]与Adobe Campaign之间的同步是否已完成。

## 如何检查Adobe Campaign与Launch之间的同步是否已完成？ {#sync-campaign-launch}

1. 在Adobe Campaign Standard的高级菜单中，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。

1. 打开&#x200B;**[!UICONTROL syncWithLaunch]**&#x200B;工作流。

1. 检查工作流是否已结束且没有错误。

1. 在日志中检查工作流同步是否已启用并成功完成。

## 我在Launch中为已配置的移动应用程序重置了密钥。 如何在Launch中再次重新配置密钥？ {#configuring-pkey}

1. 在Launch中打开移动资产Adobe。

1. 在重置了PKey的Adobe Campaign Standard扩展中设置一个新URL。

1. 保存它，然后让工作流在Adobe Campaign和[!DNL Launch]之间同步。

1. 同步完成后，在[!DNL Launch]中打开移动属性。

1. 在重置了PKey的Adobe Campaign Standard扩展中设置正确的URL。

1. 保存它并让工作流同步再次运行。

1. 只有这样，该属性才会在Adobe Campaign中显示为&#x200B;**[!UICONTROL Ready to Configure]**&#x200B;状态，并且现在可以进行配置。

## 我想在Adobe Campaign中配置移动资产。 我是否必须等待技术工作流在Launch和AdobeAdobe Campaign之间同步？

您可以立即执行工作流：

1. 在Adobe Campaign Standard的高级菜单中，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。

1. 打开&#x200B;**[!UICONTROL syncWithLaunch]**&#x200B;工作流。

1. 单击&#x200B;**[!UICONTROL Scheduler]**&#x200B;活动，然后选择&#x200B;**[!UICONTROL Immediate execution]**。
