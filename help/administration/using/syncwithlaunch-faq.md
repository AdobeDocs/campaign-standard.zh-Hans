---
title: 与Launch同步技术工作流常见问题解答
description: 有关Adobe启动技术工作流的常见问题
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 1%

---

# Adobe Experience Platform 同步中的标记常见问题解答 {#syncwithlaunch-faq}

您可以通过以下方式将标记移动资产导入Adobe Campaign Standard **[!UICONTROL Sync with Launch]** 专门的技术工作流。 有关更多信息，请参阅此 [页面](../../administration/using/technical-workflows.md)

以下部分列出了有关此同步的常见问题。

## 我创建了一个标记属性（组织单元ALL的非管理员）。 在Adobe Campaign中，我的应用程序处于“准备配置”状态，但无法打开/配置该应用程序。 {#configuring-property}

只有组织单位ALL的管理员才能在Adobe Campaign Standard中配置移动应用程序。 配置完毕后，只有已分配组织单位的用户可以编辑应用程序。 有关组织单位的更多信息，请参阅此 [页面](../../administration/using/organizational-units.md).

## 我无法在Adobe Campaign Standard中编辑配置的移动应用程序，并且移动应用程序处于只读模式。 {#read-mode-mobile-app}

在中检查移动应用程序的组织单位 **[!UICONTROL Access Authorization]** 部分。 只有已分配组织单位的用户才能编辑移动应用程序。

有关组织单位的更多信息，请参阅此 [页面](../../administration/using/organizational-units.md).

## 我是Adobe Campaign Standard中组织单位ALL的管理员，但无法配置移动应用程序。 {#org-unit-mobile}

组织单位设置为“全部”的管理员应有权使用所有标记移动属性来配置移动应用程序。

有关组织单位的更多信息，请参阅此 [页面](../../administration/using/organizational-units.md).

## 我创建了一个标记移动资产，但我的资产在Adobe Campaign Standard中不可见。 {#visibility-mobile-property}

1. 检查数据收集UI中的移动资产中是否安装了Adobe Campaign Standard扩展。

1. 验证在扩展中是否正确配置了实例的端点。

1. 请检查“Launch_URL_Campaign”或“NmsServer_URL”是否正确。

1. 然后，检查同步是否已完成 **[!UICONTROL syncWithLaunch]** 技术工作流。

## 如何检查是否已完成Adobe Campaign与Adobe Experience Platform中的标记之间的同步？ {#sync-campaign-launch}

1. 在Adobe Campaign Standard中，从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. 打开 **[!UICONTROL syncWithLaunch]** 工作流。

1. 检查工作流是否已结束且未出现错误。

1. 在日志中检查是否已启用并成功完成工作流同步。

## 我重置了已配置标记移动应用程序的密钥。 如何在数据收集UI中再次重新配置密钥？ {#configuring-pkey}

1. 在数据收集UI中打开移动设备属性。

1. 在Adobe Campaign Standard扩展中设置一个新URL，并为其重置PKey。

1. 保存它并让工作流同步。

1. 同步完成后，在数据收集UI中打开移动设备属性。

1. 在已重置密钥的Adobe Campaign Standard扩展中设置正确的URL。

1. 保存它并再次运行工作流同步。

1. 只有这样，该资产才会显示在 **[!UICONTROL Ready to Configure]** Adobe Campaign中的状态，现在可以进行配置。

## 我想在Adobe Campaign中配置移动资产。 我是否需要等待技术工作流在Adobe Experience Platform和Adobe Campaign中的标记之间同步？

您可以立即执行工作流：

1. 在Adobe Campaign Standard中，从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. 打开 **[!UICONTROL syncWithLaunch]** 工作流。

1. 单击 **[!UICONTROL Scheduler]** 活动和选择 **[!UICONTROL Immediate execution]**.
