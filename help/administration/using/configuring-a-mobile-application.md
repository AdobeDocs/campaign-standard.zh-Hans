---
title: 配置移动应用程序
description: 了解如何使用Experience PlatformSDK配置Adobe Campaign以发送推送通知或应用程序内消息
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 5f9a8e84-a362-42b6-8bd2-e5d56214c1db
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1260'
ht-degree: 3%

---

# 配置移动应用程序{#configuring-a-mobile-application}

## 使用Adobe Experience Platform SDK配置移动应用程序 {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
> Adobe Experience Platform Launch已更名为Adobe Experience Platform中的一套数据收集技术。 因此，在整个产品文档中推出了几项术语更改。 请参阅 [以下文档](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html) ，以了解术语更改的综合参考。

请注意，推送通知和应用程序内实施必须由专家用户执行。 如需帮助，请联系您的Adobe客户经理或专业服务合作伙伴。

要使用Experience PlatformSDK应用程序发送推送通知和应用程序内消息，必须在数据收集UI中设置移动应用程序，并在Adobe Campaign中进行配置。

设置移动应用程序后，您可以检索它收集的PII数据，以从数据库创建或更新用户档案。 有关更多信息，请参阅此章节： [基于移动应用程序数据创建和更新用户档案信息](../../channels/using/updating-profile-with-mobile-app-data.md).

要了解关于使用Adobe Experience Platform SDK在Adobe Campaign Standard中支持的各种移动使用案例的更多信息，请参阅此 [页面](../../administration/using/supported-mobile-use-cases.md).

要完成配置，请完成以下步骤：

1. 在Adobe Campaign中，确保您可以访问以下内容：
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   如果没有，请联系您的客户团队。

1. 检查您的用户是否拥有Adobe Campaign Standard中的必要权限和Adobe Experience Platform中的标记。
   * 在Adobe Campaign Standard中，确保IMS用户属于标准用户和管理员产品配置文件。 此步骤允许用户登录Adobe Campaign Standard，导航到Experience PlatformSDK移动应用程序页面，并查看您在数据收集UI中创建的移动应用程序属性。

   * 在数据收集UI中，确保您的IMS用户属于Experience Platform Launch产品配置文件。
此步骤允许用户登录到数据收集UI以创建和查看属性。 有关数据收集UI中产品配置文件的更多信息，请参阅 [创建您的产品配置文件](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/manage-permissions.html#gain-admin-rights-for-a-tags-product-profile). 在产品配置文件中，不应在公司或资产上设置权限，但用户应能够登录。

   要完成其他任务（如安装扩展、发布应用程序、配置环境等），您需要在产品配置文件中设置权限。

1. 在数据收集UI中，创建 **[!UICONTROL Mobile property]**. 有关更多信息，请参阅[设置移动属性](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property)。

1. 在数据收集UI中，单击 **[!UICONTROL Extensions]** 选项卡，转到 **[!UICONTROL Catalog]**，并搜索 **[!UICONTROL Adobe Campaign Standard]** 扩展。 有关更多信息，请参阅 [Adobe Campaign Standard](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard).

1. 要支持Campaign Standard中的位置用例，请安装 **[!UICONTROL Places]** 数据收集UI中的扩展。 请参阅此 [页面](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-extension/places-extension.html).

1. 在Adobe Campaign Standard中，配置您在数据收集UI中创建的移动资产。 请参阅 [在Adobe Campaign中设置Adobe Experience Platform Launch应用程序](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. 将特定于渠道的配置添加到您的移动应用设置中。有关更多信息，请参阅 [Adobe Campaign 中特定于渠道的应用程序配置](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)。

1. 如果需要，您可以删除标记属性。
有关更多信息，请参阅 [正在删除您的应用程序](../../administration/using/configuring-a-mobile-application.md#delete-app).

## 从Launch技术工作流同步移动应用程序AEPSDK {#aepsdk-workflow}

在数据收集UI中创建和配置移动资产后， **[!UICONTROL Sync Mobile app AEPSDK from Launch]** 技术工作流现在将同步在Adobe Campaign Standard中导入的标记移动资产。

默认情况下，技术工作流每15分钟启动一次。 如果需要，可以手动重新启动：

1. 在Adobe Campaign Standard中，从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.
1. 打开 **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]** 工作流。

   ![](assets/launch_10.png)

1. 单击 **[!UICONTROL Scheduler]** 活动。

1. 选择 **[!UICONTROL Immediate execution]**。

   ![](assets/launch_11.png)

现在，您的工作流将重新启动并同步在Adobe Campaign Standard中导入的标记移动资产。

## 在Adobe Campaign中设置应用程序 {#set-up-campaign}

要在Campaign中使用标记移动资产，您还必须在Adobe Campaign中配置此资产。 在Adobe Campaign中，确保IMS用户属于标准用户和管理员产品配置文件。

您必须等待技术工作流运行并将标记移动资产同步到Adobe Campaign。 然后，您可以在Adobe Campaign中对其进行配置。

有关通过Launch技术工作流同步移动应用程序AEPSDK的更多信息，请参阅此 [部分](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow).

>[!NOTE]
>
>默认情况下，组织单位设置为“全部”的管理员可以编辑移动应用程序。

1. 从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/launch.png)

1. 选择您在数据收集UI中创建的移动应用程序。
Its **[!UICONTROL Property Status]** 应为 **[!UICONTROL Ready to configure]**.

   >[!NOTE]
   >
   >默认情况下，要检索在数据收集UI中创建的移动应用程序列表，Campaign Standard使用NmsServer_URL选项中定义的值来查找匹配的属性。
   >
   >在某些情况下，移动应用程序的Campaign端点可能与NmsServer_URL中定义的端点不同。 在这种情况下，请在 `Launch_URL_Campaign` 选项。 Campaign将使用此选项中的值在数据收集UI中查找匹配的属性。

   ![](assets/launch_4.png)

1. 您可以在下更改移动应用程序的组织单位 **[!UICONTROL Access Authorization]** 部分来限制特定组织单位对此移动应用程序的访问。 有关详细信息，请参见此页面。

   在此，管理员可以通过从下拉菜单中选择子组织单位来分配子组织单位。

   ![](assets/launch_12.png)

1. 要在Campaign与Adobe Experience Platform中的标记之间建立连接，请单击 **[!UICONTROL Save]**.

1. 验证移动应用程序的状态是否已从更改 **[!UICONTROL Ready to Configure]** 到 **[!UICONTROL Configured]**.

   当Campaign扩展显示已成功设置密钥时，您还可以验证是否已在Campaign中成功设置属性。

   ![](assets/launch_5.png)

1. 要使此配置生效，更改需要在数据收集UI中发布。

   有关更多信息，请参阅 [发布配置](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration)

## Adobe Campaign中特定于渠道的应用程序配置 {#channel-specific-config}

您的移动应用程序现在可以在Campaign中用于推送通知或应用程序内投放。 现在，您可以根据需要进一步配置推送消息，以创建将触发应用程序内消息和/或上传推送证书的事件。

1. 从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

1. 选择您在数据收集UI中创建和配置的移动应用程序。

1. 在 **[!UICONTROL Mobile application properties]** 选项卡中，您可以开始添加可在移动设备应用程序中用于应用程序内消息的事件。

1. 要配置事件，请单击 **[!UICONTROL Create Element]**.

   ![](assets/launch_6.png)

1. 键入名称和描述。

   ![](assets/launch_7.png)

1. 单击 **[!UICONTROL Add]**。

   现在，当您创建应用程序内消息时，事件会显示在“触发器”选项卡上。 有关更多信息，请参阅 [准备和发送应用程序内消息](../../channels/using/preparing-and-sending-an-in-app-message.md).

1. 在 **[!UICONTROL Device-specific settings]** 移动应用程序仪表板的部分为每个设备提供应用程序详细信息，包括iOS的证书和Android的服务器密钥。

   上传证书后，将显示一条消息，通知您上传成功并显示证书的到期日期。

   >[!NOTE]
   >
   >在Adobe Campaign Standard中成功添加证书后，您将无法再重新更改设置，因为只能将一个APNS平台（生产或沙盒）添加到MCPNS应用程序中。

   ![](assets/launch_8.png)

1. 单击 **[!UICONTROL Mobile application subscribers]** 选项卡中查看订阅者的列表和有关这些订阅者的其他信息，例如，他们是否选择退出您的通知。

## 正在删除您的应用程序 {#delete-app}

>[!CAUTION]
>
>删除应用程序操作无法撤销。

要删除您的应用程序，请完成中的步骤 [删除移动资产](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#deleting-mobile-properties-in-the-data-collection-ui).

删除应用程序后，在Adobe Campaign中，验证应用程序的属性状态是否已在Launch中正确更新为“已删除”。

通过单击Adobe Campaign中的应用程序，您可以选择通过单击“从Campaign中删除”从Adobe Campaign中完全删除此应用程序。

![](assets/launch_9.png)
