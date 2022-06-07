---
title: 与Launch同步技术工作流常见问题解答
description: 有关AdobeLaunch技术工作流的常见问题
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 0%

---

# Adobe Experience Platform同步中的标记常见问题解答 {#syncwithlaunch-faq}

您可以通过 **[!UICONTROL Sync with Launch]** 专门的技术工作流。 有关更多信息，请参阅 [页面](../../administration/using/technical-workflows.md)

以下部分列出了有关此同步的常见问题。

## 我创建了一个标记属性（组织单元ALL的非管理员）。 我的应用程序在Adobe Campaign中处于“准备配置”状态，但无法打开/配置它。 {#configuring-property}

只有组织单位ALL的管理员才能在Adobe Campaign Standard中配置移动应用程序。 配置完毕后，只有分配的组织单位的用户才能编辑应用程序。 有关组织单位的详细信息，请参阅 [页面](../../administration/using/organizational-units.md).

## 我无法编辑在Adobe Campaign Standard中配置的移动应用程序，并且移动应用程序仅处于读模式。 {#read-mode-mobile-app}

在 **[!UICONTROL Access Authorization]** 中。 只有分配的组织单位的用户才能编辑移动应用程序。

有关组织单位的详细信息，请参阅 [页面](../../administration/using/organizational-units.md).

## 我是Adobe Campaign Standard中组织单位为ALL的管理员，但无法配置移动应用程序。 {#org-unit-mobile}

将组织单位设置为“全部”的管理员应具有配置移动应用程序的所有标记移动属性的权限。

有关组织单位的详细信息，请参阅 [页面](../../administration/using/organizational-units.md).

## 我创建了标记移动资产，但我的资产在Adobe Campaign Standard中不可见。 {#visibility-mobile-property}

1. 检查数据收集UI中的移动资产中是否安装了Adobe Campaign Standard扩展。

1. 验证实例的端点是否在扩展中正确配置。

1. 检查“Launch_URL_Campaign”或“NmsServer_URL”是否正确。

1. 然后，检查同步是否已完成 **[!UICONTROL syncWithLaunch]** 技术工作流。

## 如何检查Adobe Experience Platform中的Adobe Campaign和标记之间的同步是否已完成？ {#sync-campaign-launch}

1. 在Adobe Campaign Standard中，从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. 打开 **[!UICONTROL syncWithLaunch]** 工作流。

1. 检查工作流是否已结束且没有错误。

1. 在日志中检查工作流同步是否已启用并成功完成。

## 我为已配置的标记移动应用程序重置密钥。 如何在数据收集UI中重新配置密钥？ {#configuring-pkey}

1. 在数据收集UI中打开移动资产。

1. 在重置了PKey的Adobe Campaign Standard扩展中设置一个新URL。

1. 保存并同步工作流。

1. 完成同步后，在数据收集UI中打开移动设备属性。

1. 在重置了PKey的Adobe Campaign Standard扩展中设置正确的URL。

1. 保存它并让工作流同步再次运行。

1. 只有在此时，该属性才会显示在 **[!UICONTROL Ready to Configure]** 状态，现在可以对其进行配置。

## 我想在Adobe Campaign中配置移动资产。 我是否必须等待技术工作流在Adobe Experience Platform中的标记和Adobe Campaign之间同步？

您可以立即执行工作流：

1. 在Adobe Campaign Standard中，从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. 打开 **[!UICONTROL syncWithLaunch]** 工作流。

1. 单击 **[!UICONTROL Scheduler]** 活动，选择 **[!UICONTROL Immediate execution]**.
