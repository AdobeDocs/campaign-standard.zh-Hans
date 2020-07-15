---
title: 关于访问管理
description: 使用角色、组和组织单位管理Adobe Campaign操作员。
page-status-flag: never-activated
uuid: 4f538452-cc67-4e03-9e2f-2d9eecc081c7
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 54028f63-c9ca-4397-a079-e27e0cfdebf6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d0a0c59763af8babc9701206cc39fe41b98e0cd4
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 0%

---


# SyncWithLaunch技术工作流程常见问题解答 {#syncwithlaunch-faq}

该工 **[!UICONTROL Sync with Launch]** 作流程支持将所有Adobe Launch移动属性自动导入Adobe Campaign Standard。

For more information on this, refer to this [page](../../administration/using/technical-workflows.md).

>[!NOTE]
>
>您需要向Adobe客户服务中心（直接或通过您的Adobe联系人）提交票证，以便在活动实例 **[!UICONTROL syncWithLaunch]** 中启用技术工作流程。

## 我在(组织单 [!DNL Launch] 元全部非管理员)中创建了属性。 我的应用程序处于Adobe Campaign中“准备配置”状态，但无法打开／配置它。 {#configuring-property}

只有组织单元的管理员才能在Adobe Campaign Standard中配置移动应用程序。 配置完毕后，只有分配的组织单位的用户才能编辑应用程序。 有关组织单位的详细信息，请参 [阅本页](../../administration/using/organizational-units.md)。

## 我无法编辑Adobe Campaign Standard中已配置的移动应用程序，而移动应用程序只处于读模式。 {#read-mode-mobile-app}

在部分中检查移动应用程序的组织 **[!UICONTROL Access Authorization ]** 单位。 只有已分配组织单元的用户才能编辑移动应用程序。

有关组织单位的详细信息，请参 [阅本页](../../administration/using/organizational-units.md)。

## 我是Adobe Campaign Standard组织单元ALL的管理员，但无法配置移动应用程序。 {#org-unit-mobile}

组织单元设置为“全部”的管理员应对中的所有移动属性具有 [!DNL Launch] 配置移动应用程序的权限。

有关组织单位的详细信息，请参 [阅本页](../../administration/using/organizational-units.md)。

## 我在中创建了移动属 [!DNL Launch] 性，但我的属性在Adobe Campaign Standard中不可见。 {#visibility-mobile-property}

1. 检查Adobe Campaign Standard扩展是否安装在中的移动属性中 [!DNL Launch]。

1. 验证实例的端点是否在扩展中正确配置。

1. 检查“Launch_URL_活动”或“NmsServer_URL”是否正确。

1. 然后，检查是否已使用技 [!DNL Launch] 术工作流完成与Adobe Campaign **[!UICONTROL syncWithLaunch]** 之间的同步。

## 如何检查Adobe Campaign和启动项之间的同步是否已完成？ {#sync-campaign-launch}

1. 在Adobe Campaign Standard中，从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。

1. 打开工 **[!UICONTROL syncWithLaunch]** 作流。

1. 检查工作流是否已结束且无错误。

1. 检查已启用并成功完成工作流同步的日志。

## 我在Launch中重置了已配置移动应用程序的键。 如何在Launch中重新配置密钥？ {#configuring-pkey}

1. 在Adobe Launch中打开移动属性。

1. 在Adobe Campaign Standard扩展中设置PKey已重置的新URL。

1. 保存它，让工作流在Adobe Campaign和之间同步 [!DNL Launch]。

1. 完成同步后，在中打开移动属性 [!DNL Launch]。

1. 在重置了PKey的Adobe Campaign Standard扩展中设置正确的URL。

1. 保存它，然后让工作流同步再次运行。

1. 只有这样，该属性才会以 **[!UICONTROL Ready to Configure]** Adobe Campaign显示，并且现在可以进行配置。

## 我想在Adobe Campaign中配置移动属性。 我是否必须等待技术工作流程在Adobe Launch和Adobe Campaign之间同步？

您可以立即执行工作流：

1. 在Adobe Campaign Standard中，从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。

1. 打开工 **[!UICONTROL syncWithLaunch]** 作流。

1. 单击活动 **[!UICONTROL Scheduler]** 并选择 **[!UICONTROL Immediate execution]**。
