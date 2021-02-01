---
solution: Campaign Standard
product: campaign
title: 与Launch技术工作流程同步常见问题解答
description: 有关Launch技术工作流程的常见问题。
audience: administration
content-type: reference
topic-tags: users-and-security
translation-type: tm+mt
source-git-commit: a8730046710445022f6df1e7af407bb078a3edf9
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 0%

---


# Adobe Launch Synchronization 常见问题解答 {#syncwithlaunch-faq}

您可以通过&#x200B;**[!UICONTROL Sync with Launch]**&#x200B;专用技术工作流将Adobe启动移动属性导入Adobe Campaign Standard。 有关详细信息，请参阅此[页面](../../administration/using/technical-workflows.md)

以下部分列表了有关此同步的常见问题。

## 我在[!DNL Launch]（非Org-unit ALL管理员）中创建了一个属性。 我的应用程序处于Adobe Campaign中“准备配置”状态，但无法打开／配置它。{#configuring-property}

只有组织单位ALL的管理员才能在Adobe Campaign Standard配置移动应用程序。 配置完毕后，只有已分配组织单位的用户才能编辑
的双曲余切值。 有关组织单位的详细信息，请参阅此[页面](../../administration/using/organizational-units.md)。

## 我无法编辑在Adobe Campaign Standard配置的移动应用程序，并且移动应用程序只处于读模式。{#read-mode-mobile-app}

在&#x200B;**[!UICONTROL Access Authorization]**&#x200B;部分检查移动应用程序的组织单位。 只有已分配组织单元的用户才能编辑移动应用程序。

有关组织单位的详细信息，请参阅此[页面](../../administration/using/organizational-units.md)。

## 我是Adobe Campaign StandardALL组织单位的管理员，但无法配置移动应用程序。{#org-unit-mobile}

组织单元设置为“全部”的管理员应对[!DNL Launch]中的所有移动属性具有配置移动应用程序的权限。

有关组织单位的详细信息，请参阅此[页面](../../administration/using/organizational-units.md)。

## 我在[!DNL Launch]中创建了移动属性，但我的属性在Adobe Campaign Standard不可见。{#visibility-mobile-property}

1. 检查是否已在[!DNL Launch]的移动属性中安装Adobe Campaign Standard扩展。

1. 验证实例的端点是否在扩展中正确配置。

1. 检查“Launch_URL_活动”或“NmsServer_URL”是否正确。

1. 然后，检查[!DNL Launch]与Adobe Campaign之间的同步是否已通过&#x200B;**[!UICONTROL syncWithLaunch]**&#x200B;技术工作流程完成。

## 如何检查Adobe Campaign和启动项之间的同步是否已完成？{#sync-campaign-launch}

1. 在Adobe Campaign Standard，从高级菜单中，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。

1. 打开&#x200B;**[!UICONTROL syncWithLaunch]**&#x200B;工作流。

1. 检查工作流是否已结束且无错误。

1. 检查已启用并成功完成工作流同步的日志。

## 我在Launch中重置了已配置移动应用程序的键。 如何在Launch中重新配置密钥？{#configuring-pkey}

1. 在Adobe启动中打开移动属性。

1. 在重置PKey的Adobe Campaign Standard扩展中设置新URL。

1. 保存它，让工作流在Adobe Campaign和[!DNL Launch]之间同步。

1. 完成同步后，打开[!DNL Launch]中的mobile属性。

1. 在重置了PKey的Adobe Campaign Standard扩展中设置正确的URL。

1. 保存它，然后让工作流同步再次运行。

1. 只有这样，该属性才会以Adobe Campaign **[!UICONTROL Ready to Configure]**&#x200B;状态显示，并且现在可以配置。

## 我想在Adobe Campaign中配置移动属性。 我是否必须等待技术工作流在Adobe启动和Adobe Campaign之间同步？

您可以立即执行工作流：

1. 在Adobe Campaign Standard，从高级菜单中，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。

1. 打开&#x200B;**[!UICONTROL syncWithLaunch]**&#x200B;工作流。

1. 单击&#x200B;**[!UICONTROL Scheduler]**&#x200B;活动，然后选择&#x200B;**[!UICONTROL Immediate execution]**。
