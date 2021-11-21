---
title: 与Launch同步技术工作流常见问题解答
description: 有关Launch技术工作流的常见问题。
audience: administration
content-type: reference
topic-tags: users-and-security
feature: Instance Settings
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 0%

---

# Adobe Launch Synchronization 常见问题解答 {#syncwithlaunch-faq}

您可以通过 **[!UICONTROL Sync with Launch]** 专门的技术工作流。 有关更多信息，请参阅 [页面](../../administration/using/technical-workflows.md)

以下部分列出了有关此同步的常见问题。

## 我在 [!DNL Launch] （组织单元ALL的非管理员）。 我的应用程序在Adobe Campaign中处于“准备配置”状态，但无法打开/配置它。 {#configuring-property}

只有组织单位ALL的管理员才能在Adobe Campaign Standard中配置移动应用程序。 配置完毕后，只有分配的组织单位的用户才能编辑应用程序。 有关组织单位的详细信息，请参阅 [页面](../../administration/using/organizational-units.md).

## 我无法编辑在Adobe Campaign Standard中配置的移动应用程序，并且移动应用程序仅处于读模式。 {#read-mode-mobile-app}

在 **[!UICONTROL Access Authorization]** 中。 只有分配的组织单位的用户才能编辑移动应用程序。

有关组织单位的详细信息，请参阅 [页面](../../administration/using/organizational-units.md).

## 我是Adobe Campaign Standard中组织单位为ALL的管理员，但无法配置移动应用程序。 {#org-unit-mobile}

将组织单位设置为“全部”的管理员应具有 [!DNL Launch] 来配置移动应用程序。

有关组织单位的详细信息，请参阅 [页面](../../administration/using/organizational-units.md).

## 我在 [!DNL Launch] 但我的财产在Adobe Campaign Standard不可见。 {#visibility-mobile-property}

1. 检查Adobe Campaign Standard扩展是否安装在 [!DNL Launch].

1. 验证实例的端点是否在扩展中正确配置。

1. 检查“Launch_URL_Campaign”或“NmsServer_URL”是否正确。

1. 然后，检查 [!DNL Launch] 而Adobe Campaign完成了 **[!UICONTROL syncWithLaunch]** 技术工作流。

## 如何检查Adobe Campaign与Launch之间的同步是否已完成？ {#sync-campaign-launch}

1. 在Adobe Campaign Standard中，从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. 打开 **[!UICONTROL syncWithLaunch]** 工作流。

1. 检查工作流是否已结束且没有错误。

1. 在日志中检查工作流同步是否已启用并成功完成。

## 我在Launch中为已配置的移动应用程序重置了密钥。 如何在Launch中再次重新配置密钥？ {#configuring-pkey}

1. 在Launch中打开移动资产Adobe。

1. 在重置了PKey的Adobe Campaign Standard扩展中设置一个新URL。

1. 保存该工作流，并在Adobe Campaign和 [!DNL Launch].

1. 同步完成后，在中打开移动资产 [!DNL Launch].

1. 在重置了PKey的Adobe Campaign Standard扩展中设置正确的URL。

1. 保存它并让工作流同步再次运行。

1. 只有在此时，该属性才会显示在 **[!UICONTROL Ready to Configure]** 状态，现在可以对其进行配置。

## 我想在Adobe Campaign中配置移动资产。 我是否必须等待技术工作流在Launch和AdobeAdobe Campaign之间同步？

您可以立即执行工作流：

1. 在Adobe Campaign Standard中，从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. 打开 **[!UICONTROL syncWithLaunch]** 工作流。

1. 单击 **[!UICONTROL Scheduler]** 活动，选择 **[!UICONTROL Immediate execution]**.
